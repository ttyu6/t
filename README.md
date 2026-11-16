<div align="center">

<a href="https://github.com/ttyu6/t">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://p.ttyu.net/ui/logo-dark.svg">
  <img alt="Pristine Design Logo" src="https://p.ttyu.net/ui/logo.svg" width="180"/>
</picture>
</a>

<br/>

# Pristine Design
### 众易搭 T 语言（PSL）配套原生 Web UI 组件库

<p align="center">
  <a href="https://github.com/ttyu6/t">
    <img src="https://img.shields.io/badge/version-2.0.0-blue?style=for-the-badge&logo=semver" alt="Version">
  </a>
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-green?style=for-the-badge" alt="MIT License">
  </a>
  <a href="https://github.com/ttyu6/t/actions">
    <img src="https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge&logo=github-actions" alt="Build Status">
  </a>
  <a href="https://github.com/ttyu6/t/pulls">
    <img src="https://img.shields.io/badge/PRs-welcome-orange?style=for-the-badge" alt="PR Welcome">
  </a>
</p>

<p align="center">
  <strong>一段简洁 DSL 文本，驱动现代化 Web 交互界面</strong><br>
  零依赖 · 原生 JS · 无虚拟 DOM · PSL 声明式渲染
</p>

<p align="center">
  <a href="http://p.ttyu.net/ui/index.html"><strong>🚀 在线演示</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://ttyu6.github.io/t/"><strong>📖 官方文档</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-快速开始"><strong>⚡ 快速开始</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/ttyu6/t/issues"><strong>🐛 反馈与 Bug</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-集成方案"><strong>📦 生态案例</strong></a>
</p>

</div>

---

## 📋 目录
- [概述](#-概述)
- [核心特性](#-核心特性)
- [架构设计](#-架构设计)
- [快速开始](#-快速开始)
- [组件矩阵](#-组件矩阵)
- [PSL 语法概览](#-psl语法概览)
- [集成方案](#-集成方案)
- [本地文档部署](#-本地文档部署)
- [仓库目录结构](#-仓库目录结构)
- [浏览器兼容](#-浏览器兼容)
- [路线图](#-路线图)
- [贡献指南](#-贡献指南)
- [协议说明](#-协议说明)

---

## 📌 概述
**Pristine Design** 是面向低代码平台「众易搭」自研的原生 Web UI 组件库，配套 **PSL（Pristine Script Language，T 语言）** 声明式 DSL。
区别于 Vue / React 组件库，它以**文本描述作为界面唯一配置源**，内置独立 DSL 解析引擎，直接输出原生 DOM，不绑定任何前端框架。

> 设计理念：**Pristine = 纯净、无冗余**
> 剥离重型运行时、虚拟DOM、编译预处理器，回归浏览器原生能力，让界面描述与渲染逻辑解耦，适配低代码、表单中台、管理后台、AI 生成界面等场景。

适用场景：
- ✅ 低代码平台表单、报表、配置面板
- ✅ AI 自动生成界面（大模型输出 PSL，直接渲染）
- ✅ 企业内部管理系统、数据看板、审批流
- ✅ 轻量化嵌入式面板（内嵌至 .NET、Java、Python 后端页面）
- ✅ 混合开发：嵌入 Vue / React / Svelte 项目

---

## ⭐ 核心特性
<div align="center">
<table>
<tr>
<td align="center"><b>📝 声明式DSL</b></td>
<td align="center"><b>⚡ 原生高性能</b></td>
<td align="center"><b>🧩 组件完备</b></td>
</tr>
<tr>
<td>PSL 文本驱动界面，专注描述结构，不关心 DOM 操作</td>
<td>零外部依赖，无虚拟DOM，毫秒级渲染，内存占用低</td>
<td>内置 50+ 业务组件，覆盖表单、表格、图表、弹窗、上传</td>
</tr>
<tr>
<td align="center"><b>🔌 框架无关</b></td>
<td align="center"><b>🎯 双向绑定</b></td>
<td align="center"><b>📦 按需加载</b></td>
</tr>
<tr>
<td>纯原生 JS，可嵌入任意前端框架、后端模板页面</td>
<td>内置数据管理器，自动响应变更，支持联动校验</td>
<td>支持全量引入 / 按需注册组件，减少资源体积</td>
</tr>
<tr>
<td align="center"><b>✅ 内置校验</b></td>
<td align="center"><b>🎨 主题系统</b></td>
<td align="center"><b>📜 MIT开源</b></td>
</tr>
<tr>
<td>规则校验、自定义校验器、异步校验、错误提示</td>
<td>CSS变量驱动，一键切换亮色/暗色主题，自定义品牌色</td>
<td>允许商用、二次分发、二次改造，无版权限制</td>
</tr>
</table>
</div>

---

## 🏛️ 架构设计
整体分层设计，职责清晰：
