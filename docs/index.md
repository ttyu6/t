# Pristine Design

> 众易搭 T 语言（PSL）配套原生 Web UI 组件库 · v2.0

Pristine Design 是一套**纯原生 JavaScript** 的 UI 组件库。它接收一段 T 语言（PSL）文本，直接渲染为表单、表格、图表、弹窗等界面，不依赖 jQuery、不依赖框架，浏览器里 `new` 一下就能跑。

## 它解决什么问题

| 传统做法 | Pristine Design |
| --- | --- |
| 手写大量 HTML + 事件绑定 | 一段 DSL 文本即界面 |
| 引入框架与构建链 | 单文件引入，无构建 |
| 表格合并、树形展开逐页实现 | 组件内置，配置即可用 |
| 业务页面各写一套交互 | 统一 `BaseUI` 基类与管理器 |

## 核心特性

### 1. DSL 即界面
```psl
header("用户信息")
form(prop="user")
  input("name", "姓名", required=true)
  radio("gender", "性别", ["男", "女"])
  cascader("area", "所在地区", url="/api/area")
  upload("avatar", "头像", accept="image/*")
```

### 2. 管理器 + 基类体系
所有组件继承 `BaseUI`，统一生命周期 `init → render → bind → destroy`，由 `UIManager` 负责注册、实例化与销毁，页面卸载不残留监听。

```js
const mgr = new UIManager();
mgr.register('table', TableUI);
mgr.mount(document.body, pslText);
```

### 3. 组件覆盖

| 分类 | 组件 | 说明 |
| --- | --- | --- |
| 基础 | BasicUI | 标题、文本、分割线、标签 |
| 表单 | FormUI / InputUI / RadioUI | 表单容器与各类输入 |
| 表格 | TableUI | 多级表头、单元格合并、冻结列 |
| 图表 | ChartUI | Canvas 折线/柱状/饼图 |
| 树形 | TreeSelect | 递归解析、勾选、搜索 |
| 选择 | Cascader | 多级联动、异步加载 |
| 反馈 | Modal / Toast | 弹窗、确认框、轻提示 |
| 媒体 | Upload / Carousel | 文件上传、图片轮播 |

## 一条命令开始

```bash
npm i -g docsify-cli
docsify serve docs
```

打开 <http://localhost:3000> 即可浏览本文档站。

## 目录

- [快速开始](/quickstart.md) — 5 分钟渲染第一个页面
- [T 语言语法](/psl-syntax.md) — DSL 词法与属性简写
- [UI 组件](/ui/form.md) — 组件 API 与示例
- [工具库](/tools.md) — 工具函数与管理器基类
- [实战案例](/cases/data-table.md) — 可直接复用的页面模板

## 许可

[MIT](license.md) © liysoft
