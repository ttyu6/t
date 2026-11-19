> [English](./README.md) | 简体中文

<div align="center">

<a href="https://github.com/ttyu6/t">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://ttyu.net/ui/logo.png">
  <img alt="Pristine Design Logo" src="https://ttyu.net/ui/logo.png" width="180"/>
</picture>
</a>

<br/>

# Pristine Design
### 众易搭 ZYDA PSL（T语言）原生Web UI组件库

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
  <strong>简洁DSL文本，渲染现代化Web交互界面</strong><br>
  零依赖 · 原生JS · 无虚拟DOM · PSL声明式渲染
</p>

<p align="center">
  <a href="https://ttyu.net/ui/index.html"><strong>🚀 在线演示</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://ttyu6.github.io/t/"><strong>📖 文档</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-快速开始"><strong>⚡ 快速开始</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/ttyu6/t/issues"><strong>🐛 问题反馈</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-集成方案"><strong>📦 生态</strong></a>
</p>

</div>

---

## 📋 目录
- [概述](#-概述)
- [为什么选择 Pristine?](#-为什么选择-pristine)
- [特性](#-特性)
- [快速开始](#-快速开始)
- [PSL语法](#-psl语法)
- [组件列表](#-组件列表)
- [集成方案](#-集成方案)
- [本地文档部署](#-本地文档部署)
- [仓库目录结构](#-仓库目录结构)
- [浏览器兼容](#-浏览器兼容)
- [路线图](#-路线图)
- [贡献指南](#-贡献指南)
- [社区](#-社区)
- [协议](#-协议)

---

## 📌 概述
**Pristine Design** 是为众易搭ZYDA低代码平台打造的原生JavaScript UI组件库，配套 **PSL（Pristine Script Language / T语言）** 声明式DSL。

和Vue/React组件库不同，它以纯文本DSL作为界面唯一描述源，内置PSL解析器，直接渲染原生DOM，框架无关。

> **设计理念：Pristine = 纯净精简**
> 摒弃重型运行时、虚拟DOM与预编译器，充分利用浏览器原生能力，将界面描述与渲染逻辑解耦。

### 🎯 适用场景
- ✅ 低代码平台：表单、表格、配置面板
- ✅ AI生成界面：大模型输出PSL文本，即时渲染
- ✅ 企业后台、审批工作流系统
- ✅ 嵌入 .NET / Java / Python 后端模板
- ✅ 作为微件嵌入 Vue / React / Svelte 项目

---

## 💡 为什么选择 Pristine?
Pristine 不是用来替代Vue或React，而是专门解决特定场景下“运行时过重”的痛点。

| 对比项 | Vue/React组件库 | Pristine Design |
|---|---|---|
| 环境依赖 | 需要Node、打包工具 | 仅一行CDN script标签 |
| 渲染机制 | 虚拟DOM Diff | 解析DSL直接生成原生DOM |
| 老旧系统接入 | 迁移成本高 | 以微件嵌入现有HTML/PHP |
| AI友好度 | 需要生成复杂JSX/模板 | 简单纯文本DSL |
| 包体积 | 运行时体积大 | 内核轻量，零外部依赖 |

---

## ⭐ 特性
<div align="center">
<table>
<tr>
<td align="center"><b>📝 声明式DSL</b></td>
<td align="center"><b>⚡ 原生高性能</b></td>
<td align="center"><b>🧩 丰富组件</b></td>
</tr>
<tr>
<td>使用PSL描述界面，无需手动操作DOM</td>
<td>无虚拟DOM，挂载速度快、内存占用低</td>
<td>50+业务组件：表单、表格、图表、弹窗、上传</td>
</tr>
<tr>
<td align="center"><b>🔌 框架无关</b></td>
<td align="center"><b>🎯 双向绑定</b></td>
<td align="center"><b>📦 按需注册</b></td>
</tr>
<tr>
<td>纯原生JS，任意地方嵌入</td>
<td>内置数据管理器，自动响应、表单联动校验</td>
<td>全量引入或者按需注册组件</td>
</tr>
<tr>
<td align="center"><b>✅ 表单校验</b></td>
<td align="center"><b>🎨 主题系统</b></td>
<td align="center"><b>📜 MIT协议</b></td>
</tr>
<tr>
<td>规则校验、自定义校验、异步校验</td>
<td>CSS变量主题，明暗模式、自定义品牌色</td>
<td>允许商用、二次修改</td>
</tr>
</table>
</div>

---

## ⚡ 快速开始
无需Node.js、无需打包，直接引入脚本。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Pristine Demo</title>
<script src="https://ttyu.net/ui/pristine.min.js"></script>
</head>
<body>
<div id="app"></div>
<script>
// 1. 使用PSL定义界面
const dsl = `
form@myForm layout="vertical" {
  input@userName label="用户名" placeholder="请输入用户名" required
  input@password label="密码" type="password" required
  button text="登录" type="primary" onclick="onLogin()"
}
`;

// 2. 将DSL渲染到目标容器
const app = Pristine.render('#app', dsl);

// 3. 处理交互
window.onLogin = function () {
  const data = app.getValues();
  console.log(data);
};
</script>
</body>
</html>
