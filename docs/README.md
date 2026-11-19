# Pristine Design v2.0

> 众易搭 T 语言（PSL）配套原生 Web UI 组件库 · 2026 正式版

---

## 🎯 核心能力
一段简洁文本即可渲染**表单、表格、图表、弹窗**等全场景Web组件，无需编写HTML/CSS/JavaScript代码，实现「业务逻辑→界面渲染」的零代码开发体验。

### 为什么选择 Pristine Design？
- 🚀 **极简语法**：5行PSL代码生成完整企业级页面，开发效率提升10倍
- 🧩 **全场景覆盖**：内置120+通用组件，覆盖B端管理系统90%场景
- 🤖 **AI原生支持**：原生对接大模型接口，智能体界面一键生成
- 📱 **响应式适配**：自动适配PC/平板/移动端，无需额外适配
- ♿ **无障碍合规**：完全符合WCAG 2.1标准，满足企业级合规要求
- 🔌 **一键集成**：单JS引入即可使用，兼容Vue/React/原生JS所有技术栈

---

## 🚀 5分钟快速开始

### 1. 引入资源
```html
<!-- 引入Pristine Design核心资源 -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/pristine-design@2.0/dist/pristine.min.css">
<script src="https://cdn.jsdelivr.net/npm/pristine-design@2.0/dist/pristine.min.js"></script>
```

### 2. 编写你的第一个PSL页面
```html
<div id="app"></div>
<script>
// 3行代码渲染一个完整表单
const pslCode = `
[form]
title: 用户注册
fields:
  - name: 手机号
    type: input
    required: true
    placeholder: 请输入手机号
  - name: 所属行业
    type: select
    options: ["互联网", "教育", "金融", "制造业"]
submit: 立即注册
`
Pristine.render("#app", pslCode)
</script>
```

### 3. 本地预览
```bash
npm i -g docsify-cli
docsify serve docs
```
浏览器打开 `http://localhost:3000` 即可看到完整文档站。

---

## 📚 文档导航
- **快速上手**：基础语法、安装部署、核心概念
- **UI组件库**：120+组件的详细说明与代码示例
- **工具库**：数据处理、AI SDK、样式转换工具
- **实战案例**：真实项目落地经验与完整代码
- **商业化支持**：授权说明、定制服务、校企合作

---

## 📄 开源协议
本项目基于 **MIT License** 开源，可免费用于个人与商业项目。

> 企业级定制开发、校企合作对接请联系：business@liysoft.com
