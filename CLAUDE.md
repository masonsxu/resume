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
