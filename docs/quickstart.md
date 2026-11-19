# 快速开始

> 从零到渲染第一个 PSL 页面，约 5 分钟。

## 1. 引入

Pristine Design 无构建依赖，直接引入两个文件即可。

```html
<link rel="stylesheet" href="pristine/pristine.min.css">
<script src="pristine/pristine.min.js"></script>
```

或通过 CDN：

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/liysoft/t/pristine/pristine.min.css">
<script src="https://cdn.jsdelivr.net/gh/liysoft/t/pristine/pristine.min.js"></script>
```

## 2. 准备容器

```html
<div id="app"></div>
```

## 3. 编写 T 语言文本

```psl
header("员工登记")
form(prop="staff", submit="/api/staff/save")
  input("name", "姓名", required=true)
  input("phone", "手机号", rule="phone")
  radio("level", "职级", ["P4", "P5", "P6"])
  cascader("dept", "部门", url="/api/dept/tree")
  upload("photo", "证件照", accept="image/*", limit=1)
```

## 4. 渲染

```js
const app = new UIManager('#app');
app.mount(pslText);      // 解析 + 实例化 + 渲染
```

`mount` 内部流程：`DSLParser.parse()` → 生成组件树 → `UIManager.register()` → `BaseUI.init()`。

## 5. 取数据

```js
const form = app.get('staff');   // 按 prop 取组件实例
const data = form.getValue();    // { name, phone, level, dept, photo }
```

## 完整可运行示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <link rel="stylesheet" href="pristine/pristine.min.css">
</head>
<body>
  <div id="app"></div>
  <script src="pristine/pristine.min.js"></script>
  <script>
    const psl = `
header("员工登记")
form(prop="staff")
  input("name", "姓名", required=true)
  radio("level", "职级", ["P4", "P5"])
    `;
    new UIManager('#app').mount(psl);
  </script>
</body>
</html>
```

## 常见坑

| 现象 | 原因 | 处理 |
| --- | --- | --- |
| 页面空白 | 容器未找到 | 确认 `#app` 在脚本之前 |
| 组件不渲染 | 缩进层级错误 | 子节点必须比父节点多缩进 2 空格 |
| 中文乱码 | 缺 charset | 补 `<meta charset="UTF-8">` |
| 事件不触发 | 重复 mount 同一容器 | 先 `destroy()` 再 mount |

## 下一步

- 学语法：[T 语言语法](/psl-syntax.md)
- 看组件：[表单 FormUI](/ui/form.md)
- 抄模板：[实战案例](/cases/simple-form.md)
