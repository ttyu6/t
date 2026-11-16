```
<div align="center">

<a href="[https://github.com/ttyu6/t](https://github.com/ttyu6/t)">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="[https://p.ttyu.net/ui/logo-dark.svg](https://p.ttyu.net/ui/logo-dark.svg)">
  <img alt="Pristine Design Logo" src="[https://p.ttyu.net/ui/logo.svg](https://p.ttyu.net/ui/logo.svg)" width="180"/>
</picture>
</a>

<br/>

# Pristine Design
### 众易搭 T 语言（PSL）配套原生 Web UI 组件库

<p align="center">
  <a href="[https://github.com/ttyu6/t](https://github.com/ttyu6/t)">
    <img src="[https://img.shields.io/badge/version-2.0.0-blue?style=for-the-badge&logo=semver](https://img.shields.io/badge/version-2.0.0-blue?style=for-the-badge&logo=semver)" alt="Version">
  </a>
  <a href="./LICENSE">
    <img src="[https://img.shields.io/badge/license-MIT-green?style=for-the-badge](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)" alt="MIT License">
  </a>
  <a href="[https://github.com/ttyu6/t/actions](https://github.com/ttyu6/t/actions)">
    <img src="[https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge&logo=github-actions](https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge&logo=github-actions)" alt="Build Status">
  </a>
  <a href="[https://github.com/ttyu6/t/pulls](https://github.com/ttyu6/t/pulls)">
    <img src="[https://img.shields.io/badge/PRs-welcome-orange?style=for-the-badge](https://img.shields.io/badge/PRs-welcome-orange?style=for-the-badge)" alt="PR Welcome">
  </a>
  <a href="[https://www.npmjs.com/package/pristine-design](https://www.npmjs.com/package/pristine-design)">
    <img src="[https://img.shields.io/npm/dm/pristine-design?style=for-the-badge&logo=npm](https://img.shields.io/npm/dm/pristine-design?style=for-the-badge&logo=npm)" alt="NPM Downloads">
  </a>
</p>

<p align="center">
  <strong>一段简洁 DSL 文本，驱动现代化 Web 交互界面</strong><br>
  零依赖 · 原生 JS · 无虚拟 DOM · PSL 声明式渲染
</p>

<p align="center">
  <a href="[http://p.ttyu.net/ui/index.html](http://p.ttyu.net/ui/index.html)"><strong>🚀 在线演示</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="[https://ttyu6.github.io/t/](https://ttyu6.github.io/t/)"><strong>📖 官方文档</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#快速开始"><strong>⚡ 快速开始</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="[https://github.com/ttyu6/t/issues](https://github.com/ttyu6/t/issues)"><strong>🐛 反馈与 Bug</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#生态与案例"><strong>📦 生态案例</strong></a>
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
```

┌─────────────────────────────────────────┐
│ PSL 业务层：DSL文本、业务配置、AI生成内容 │
├─────────────────────────────────────────┤
│ DSLParser 解析器：词法解析、AST构建、表达式求值 │
├─────────────────────────────────────────┤
│ BaseUI 基类管理器：生命周期、数据模型、事件总线 │
├─────────────────────────────────────────┤
│ UI组件实例：TableUI / ChartUI / Modal / Upload … │
├─────────────────────────────────────────┤
│ 原生 DOM + CSS 渲染层                   │
└─────────────────────────────────────────┘

```
- **BaseUI**：所有组件统一基类，标准化生命周期（`init` / `render` / `bind` / `destroy`）
- **UIManager**：全局实例管理器，负责组件注册、查找、销毁、事件派发
- **DSLParser**：独立解析模块，支持动态解析、增量更新、热重载
- **EventBus**：跨组件通信，轻松实现表单联动、表格筛选、级联联动

> 优势：解析器与渲染层解耦，后端、AI 服务只需要输出标准 PSL 文本，前端无需修改代码即可渲染界面。

---

## 🚀 快速开始
### 方式1：CDN 引入（推荐，开箱即用）
```html
<!-- 样式 -->
<link rel="stylesheet" href="[https://p.ttyu.net/ui/pd.min.css](https://p.ttyu.net/ui/pd.min.css)">
<!-- 核心运行时 -->
<script src="[https://p.ttyu.net/ui/pd.min.js](https://p.ttyu.net/ui/pd.min.js)"></script>

<!-- PSL 容器标签 -->
<pristine-form id="loginForm">
  title: 用户登录
  field: 用户名 (text, required, placeholder="请输入账号")
  field: 密码 (password, required, placeholder="请输入密码")
  action: 提交 (submit)
  action: 重置 (reset)
</pristine-form>

<script>
// 监听表单提交事件
Pristine.on('loginForm.submit', (data) => {
  console.log('表单数据：', data);
})
</script>
```

### 方式2：NPM 引入

```
npm install pristine-design
```

```
import 'pristine-design/dist/pd.min.css'
import Pristine from 'pristine-design'

Pristine.mount('#app', `
header("用户信息")
form
  input(name="nickname", label="昵称")
  input(name="phone", label="手机号")
`)
```

### 方式3：动态渲染（JS API 传入 PSL）

```
const code = `
header("数据看板")
table
  column: ID
  column: 名称
  column: 状态
`
Pristine.render('#container', code)
```

---

## 🧱 组件矩阵

| 分类 | 组件 |
| --- | --- |
| 基础组件 | Text、Label、Divider、Alert、Badge、Tag、Button、Card |
| 表单组件 | Input、Textarea、Number、Radio、Checkbox、Select、TreeSelect、Cascader、DatePicker、Switch |
| 高级表单 | Upload、ImageUpload、Signature、RichText |
| 数据组件 | TableUI（支持合并单元格、拖拽排序、行编辑）、ChartUI |
| 弹窗反馈 | Modal、Drawer、Toast、Confirm、Notification |
| 布局容器 | Header、Grid、Row、Col、Tabs、Collapse、Carousel |
| 工具组件 | Progress、Loading、Timeline、Step |

> 
> 全部组件统一生命周期、统一事件模型、统一属性规则，学习成本低。

---

## 📖 PSL语法概览

PSL 采用缩进式语法，支持简写、属性配置、表达式，示例：

```
header("商品编辑")
form
  input(name="title", label="商品名称", required)
  number(name="price", label="售价", min=0)
  upload(name="cover", label="封面图")
  cascader(name="area", label="地区")
  action: 保存 (submit)
```

支持：

- 缩进嵌套结构
- 括号属性、简写属性
- 内置校验规则
- 联动表达式
- 注释、变量、分支（进阶）

详细语法：👉 [PSL 语法文档](https://ttyu6.github.io/t/psl-syntax.html)

---

## 🔗 集成方案

### 在 Vue3 中嵌入

```
<template>
  <div ref="pdRef"></div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
import Pristine from 'pristine-design'
const pdRef = ref(null)
onMounted(()=>{
  Pristine.render(pdRef.value, `header("Vue内嵌面板")`)
})
</script>
```

### 在 React 中嵌入

```
useEffect(()=>{
  Pristine.render(ref.current, `header("React内嵌面板")`)
},[])
```

### 后端模板（ASP.NET / Thymeleaf / Jinja2）

直接在模板输出 `<pristine-xxx>` 标签或者输出 PSL 文本，无需编译。

---

## 📚 本地文档部署

文档基于 Docsify 构建，文档目录：`docs/`

```
# 安装工具
npm i -g docsify-cli
# 启动文档服务
docsify serve docs
# 访问 [http://localhost:3000](http://localhost:3000)
```

文档包含：组件API、示例、FAQ、迁移指南、语法手册。

---

## 📁 仓库目录结构

```
t/
├── src/                          # 源码目录
│   ├── core/                     # 内核：BaseUI / UIManager / EventBus
│   ├── parser/                   # DSLParser T语言解析器
│   ├── ui/                       # 各个组件源码
│   ├── theme/                    # CSS变量、主题样式
│   └── index.js                  # 入口
├── dist/                         # 编译产物 pd.min.js / pd.min.css
├── docs/                         # Docsify 官方文档站
│   ├── _coverpage.md
│   ├── _sidebar.md
│   ├── index.md
│   ├── quickstart.md
│   ├── psl-syntax.md
│   ├── ui/                       # 组件文档
│   ├── tools/                    # 内核、解析器文档
│   ├── cases/                    # 实战案例
│   ├── changelog.md
│   └── license.md
├── examples/                     # 独立HTML示例
├── .github/workflows/            # GitHub Pages 自动部署
├── package.json
├── README.md
└── LICENSE
```

---

## 🌐 浏览器兼容

| 浏览器 | 最低版本 |
| --- | --- |
| Chrome | ≥ 80 |
| Edge | ≥ 80 |
| Firefox | ≥ 78 |
| Safari | ≥ 14 |
| 移动端 | 现代移动端浏览器 |

> 
> 不依赖 Polyfill，使用 ES6+ 原生 API。如需兼容低版本浏览器，可自行引入 core-js。

---

## 🗺️ 路线图（Roadmap）

- v2.0 基础组件矩阵、DSL解析器、TableUI / ChartUI
- 暗色主题、CSS变量体系
- 完整 Docsify 文档站
- v2.1：打印组件、导出Excel、水印组件
- v2.2：PSL 可视化编辑器（拖拽生成 T语言）
- v2.3：服务端渲染支持、Schema 导出
- v3.0：独立设计令牌系统、无障碍访问优化

---

## 🤝 贡献指南

欢迎参与共建：

1. Fork 仓库
2. 新建分支：`feat/xxx` / `fix/xxx`
3. 开发、自测、补充对应文档示例
4. 提交 PR，描述改动内容
5. 等待评审合并

提交 Bug 建议：请在 Issue 附带复现 PSL 代码、浏览器版本、截图。

---

## 📄 协议说明

**MIT License**

> 
> 可自由使用、复制、修改、合并、发布、分发、销售本软件副本；
> 保留版权声明，作者不承担软件使用带来的风险。

---

  

**Pristine Design · 众易搭 T语言 PSL**
  

Make UI as simple as text.

```
