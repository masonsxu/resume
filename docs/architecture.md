# Radius 系统架构图

> 基于 radius-backend 项目实际架构分析绘制

## 整体架构视图

```mermaid
flowchart TB
    subgraph Clients["① 请求从哪进？"]
        direction LR
        Web["🌐 Web 应用"]
        Mobile["📱 移动应用"]
        Third["🔗 第三方系统"]
    end

    subgraph Gateway["🚪 API Gateway"]
        direction LR
        Hertz["Hertz HTTP :8080"]
        MW["JWT认证 | CORS | 路由 | 限流"]
    end

    subgraph Services["② 核心系统怎么组织？"]
        direction TB
        
        subgraph Core["核心服务 ━━━━━━━━━"]
            identity["🔐 identity_srv<br/>身份认证 :9000"]
            permission["🛡️ permission_srv<br/>权限控制 :9001"]
            datalake["📊 datalake_srv<br/>数据湖 :9002"]
        end
        
        subgraph Business["业务服务 ───────"]
            dicom["🏥 dicom_srv<br/>医学影像 :9003"]
            patient["👤 patient_srv<br/>患者管理 :9004"]
            medrec["📋 medrec_srv<br/>电子病历 :9005"]
        end
        
        subgraph Extend["扩展服务 ───────"]
            cancer["🔬 cancer_srv<br/>癌症数据 :9006"]
            athoslide["🔍 athoslide_srv<br/>病理切片 :9007"]
            ocr["📝 ocr_srv<br/>文字识别 :9008"]
        end
    end

    subgraph Discovery["服务发现层"]
        Etcd["⚙️ Etcd :2379<br/>服务注册与发现"]
    end

    subgraph Storage["③ 数据往哪走？"]
        direction LR
        PG["🐘 PostgreSQL :5432<br/>用户 | 组织 | 权限 | 病历"]
        S3["📦 RustFS/S3 :9000<br/>影像 | 切片 | 文档"]
        Redis["⚡ Redis (可选)<br/>会话 | 缓存"]
    end

    Web & Mobile & Third -->|HTTP/HTTPS| Gateway
    Gateway -->|Thrift RPC| Services
    
    Core & Business & Extend <-.->|注册/发现| Discovery
    Gateway <-.->|服务发现| Discovery
    
    Core & Business & Extend -->|读写| Storage
```

## 数据流向图

```mermaid
flowchart LR
    subgraph Request["请求流"]
        A["客户端请求"] --> B["API Gateway"]
        B -->|"1. JWT验证"| C{"认证通过?"}
        C -->|Yes| D["路由转发"]
        C -->|No| E["401 拒绝"]
        D -->|"2. RPC调用"| F["微服务处理"]
        F -->|"3. 数据操作"| G["存储层"]
        G -->|"4. 返回结果"| H["响应客户端"]
    end
```

## 服务分层架构

```mermaid
flowchart TB
    subgraph L1["接入层 Presentation"]
        HTTP["HTTP API<br/>Hertz Framework"]
    end

    subgraph L2["应用层 Application"]
        Handler["Handler 处理器"]
        Middleware["Middleware 中间件"]
        Assembler["Assembler 组装器"]
    end

    subgraph L3["领域层 Domain"]
        Logic["Logic 业务逻辑"]
        Model["Model 领域模型"]
        Service["Service 领域服务"]
    end

    subgraph L4["基础设施层 Infrastructure"]
        DAL["DAL 数据访问"]
        RPC["RPC 客户端"]
        Config["Config 配置"]
    end

    subgraph L5["外部资源"]
        DB[("PostgreSQL")]
        FS[("文件存储")]
        ETCD[("Etcd")]
    end

    L1 --> L2 --> L3 --> L4 --> L5
```

## 核心架构特点

| 层次 | 技术选型 | 职责 |
|:-----|:---------|:-----|
| **接入层** | Hertz HTTP | 统一入口、认证鉴权、协议转换、流量控制 |
| **服务层** | Kitex RPC + Thrift | 业务逻辑处理、服务间通信、领域隔离 |
| **发现层** | Etcd | 服务注册、动态发现、配置管理 |
| **存储层** | PostgreSQL + S3 | 结构化数据持久化、文件对象存储 |
