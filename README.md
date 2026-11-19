> English | [简体中文](./README.zh-CN.md)

<div align="center">

<a href="https://github.com/ttyu6/t">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://ttyu.net/ui/logo.png">
  <img alt="Pristine Design Logo" src="https://ttyu.net/ui/logo.png" width="180"/>
</picture>
</a>

<br/>

# Pristine Design
### Native Web UI Library for ZYDA PSL (T Language)

<p align="center">
  <a href="https://github.com/ttyu6/t">
    <img src="https://ttyu.net/ui/logo.png" alt="Version">
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
  <strong>Render interactive web UI from simple DSL text</strong><br>
  Zero Dependency · Vanilla JS · No Virtual DOM · PSL Declarative Rendering
</p>

<p align="center">
  <a href="https://ttyu.net/ui/index.html"><strong>🚀 Online Demo</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://ttyu6.github.io/t/"><strong>📖 Docs</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-quick-start"><strong>⚡ Quick Start</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/ttyu6/t/issues"><strong>🐛 Issues</strong></a> &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#-integration"><strong>📦 Ecosystem</strong></a>
</p>

</div>

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Why Pristine?](#-why-pristine)
- [Features](#-features)
- [Quick Start](#-quick-start)
- [PSL Syntax](#-psl-syntax)
- [Component List](#-components)
- [Integration](#-integration)
- [Local Documentation](#-local-documentation)
- [Repository Structure](#-repository-structure)
- [Browser Support](#-browser-support)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Community](#-community)
- [License](#-license)

---

## 📌 Overview
**Pristine Design** is a vanilla JavaScript UI library built for the ZYDA low-code platform, paired with **PSL (Pristine Script Language / T Language)** declarative DSL.

Unlike Vue / React UI libraries, it takes plain DSL text as the single source of UI definition. It ships with a built-in PSL parser and renders native DOM directly, framework agnostic.

> **Philosophy: Pristine = Clean & Minimal**
> Drop heavyweight runtimes, virtual DOMs, and pre-compilers. Leverage native browser capabilities and decouple UI description from rendering logic.

### 🎯 Use Cases
- ✅ Low-code platforms: forms, tables, config panels
- ✅ AI-generated UI: LLMs output PSL text, rendered instantly
- ✅ Internal admin dashboards & workflow systems
- ✅ Embed into .NET / Java / Python backend templates
- ✅ Widgets inside Vue / React / Svelte apps

---

## 💡 Why Pristine?
Pristine is not intended to replace Vue or React. It solves the "overweight runtime" pain for specific scenarios.

| Item | Vue/React Component Library | Pristine Design |
|---|---|---|
| Setup | Node.js, bundler required | Single script tag via CDN |
| Render | Virtual DOM diffing | Parse DSL → native DOM |
| Legacy System | High migration cost | Embed as a widget into existing HTML/PHP |
| AI Friendly | Complex JSX / templates | Simple plain-text DSL |
| Bundle Size | Large runtime | Lightweight core, zero deps |

---

## ⭐ Features
<div align="center">
<table>
<tr>
<td align="center"><b>📝 Declarative DSL</b></td>
<td align="center"><b>⚡ Native Performance</b></td>
<td align="center"><b>🧩 Rich Components</b></td>
</tr>
<tr>
<td>Describe UI in PSL, no manual DOM manipulation</td>
<td>No virtual DOM, fast mount, low memory footprint</td>
<td>50+ business components: forms, tables, charts, modals, uploads</td>
</tr>
<tr>
<td align="center"><b>🔌 Framework Agnostic</b></td>
<td align="center"><b>🎯 Two-way Binding</b></td>
<td align="center"><b>📦 On-demand Registration</b></td>
</tr>
<tr>
<td>Pure vanilla JS, embed anywhere</td>
<td>Built-in data store, auto reactive, form linkage & validation</td>
<td>Full import or register components on demand</td>
</tr>
<tr>
<td align="center"><b>✅ Form Validation</b></td>
<td align="center"><b>🎨 Theme System</b></td>
<td align="center"><b>📜 MIT</b></td>
</tr>
<tr>
<td>Rule validators, custom & async validators</td>
<td>CSS variable themes, light / dark mode, brand colors</td>
<td>Free for commercial use and modification</td>
</tr>
</table>
</div>

---

## ⚡ Quick Start
No Node.js, no bundler — just load the script.

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
// 1. Define UI with PSL
const dsl = `
form@myForm layout="vertical" {
  input@userName label="Username" placeholder="Input username" required
  input@password label="Password" type="password" required
  button text="Login" type="primary" onclick="onLogin()"
}
`;

// 2. Render the DSL into the target container
const app = Pristine.render('#app', dsl);

// 3. Handle interactions
window.onLogin = function () {
  const data = app.getValues();
  console.log(data);
};
</script>
</body>
</html>
