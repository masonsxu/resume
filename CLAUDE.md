# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个个人简历项目，使用纯HTML+CSS构建，用于生成可打印的A4格式简历PDF文件。

## 文件结构

- `resume.html` - 简历主文件，包含完整的样式和内容
- `resume.pdf` - 从HTML生成的PDF版本

## 常用命令

### 预览简历
直接在浏览器中打开 `resume.html` 文件即可预览。

### 生成PDF
使用浏览器的打印功能（Ctrl+P），选择"保存为PDF"，确保：
- 纸张大小：A4
- 边距：使用CSS中定义的边距（10mm）
- 背景图形：启用

## 技术说明

- 简历使用中文（zh-CN）
- 样式针对A4纸张打印优化（210mm宽度）
- 使用 `@page` 和 `@media print` 规则确保打印效果
- 颜色方案：主色 #2c3e50（深蓝灰），强调色 #3498db（蓝色），高亮 #c0392b（红色）

## 简历 HTML 转 PDF 技术规范

为了确保 HTML 编写的简历在通过 Chrome 导出 PDF 时保持**矢量格式（文字可选中）**、**超链接有效**且**视觉还原度高**，请遵循以下规范：

### 1. 布局与尺寸控制 (Layout)
* **严禁设置物理宽度**：不要在 `html` 或 `body` 标签上设置 `width: 210mm`。这会诱发 Chrome 打印引擎为了"强行适配"而将页面扁平化（变图片）。
* **使用百分比宽度**：根容器应使用 `width: 100%`，最大宽度限制使用 `max-width: 196mm` (针对 A4 扣除边距)。
* **标准页边距**：利用 CSS 的 `@page` 规则定义 A4 纸张和边距：
    ```css
    @page {
        size: A4 portrait;
        margin: 10mm 8mm;
    }
    ```

### 2. PDF 交互性保障 (Interactivity)
* **超链接层级**：所有 `<a>` 标签必须具有显式的层级，防止被背景容器遮挡导致热区失效：
    ```css
    a {
        position: relative;
        z-index: 10;
        text-decoration: none;
    }
    ```
* **避免混合模式**：禁用 CSS 的 `opacity`（透明度 < 1）、`box-shadow`（复杂阴影）或 `filter` 属性。这些属性极易触发 Chrome 的位图渲染模式，导致超链接和文字矢量层丢失。

### 3. 打印专属 CSS 优化 (Print CSS)
* **颜色还原**：必须设置颜色调整属性以保留背景色和边框颜色：
    ```css
    * {
        -webkit-print-color-adjust: exact !important;
        print-color-adjust: exact !important;
    }
    ```
* **分页控制**：
    * 关键区块（如工作经历、教育背景）必须使用 `page-break-inside: avoid;` 防止被跨页切断。
    * 标题后严禁直接分页：`page-break-after: avoid;`。
* **简化排版结构**：在打印模式下，尽量将 `display: table` 转换为 `display: block` 或 `flex`，这在处理复杂技能列表时更为稳健。

### 4. 标准导出流程 (Workflow)
在 Chrome 中执行 `Ctrl + P` 时，必须核对以下设置：
1.  **目标打印机**：**必须选择"另存为 PDF" (Save as PDF)**。**严禁**选择 "Microsoft Print to PDF"。
2.  **背景图形 (Background graphics)**：**必须勾选**，否则所有的主题色背景、标签颜色都会消失。
3.  **页眉和页脚 (Headers and footers)**：建议取消勾选，以保持简历简洁。
4.  **边距 (Margins)**：选择"无" (None) 或"默认"，前提是 CSS 中已定义 `@page`。

### 5. 验证准则
导出的 PDF 文件必须满足：
1.  **Ctrl + F** 可搜索页面内任意文字。
2.  鼠标可正常划选文字。
3.  所有 URL 和邮箱地址点击可跳转。
