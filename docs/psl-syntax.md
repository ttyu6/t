# T 语言语法

> T 语言（PSL，Pristine Script Language）是一套面向界面的极简 DSL：**一行一个节点，缩进表示层级，括号写属性，引号写文本**。

## 1. 基本结构

```psl
指令名(属性名=值, 属性名=值)
  子指令(属性名=值)
  子指令
```

- 每行一个节点，行首缩进决定父子关系（统一 2 空格）
- 指令名后必须紧跟 `(`，括号内为属性
- 属性之间用 `,` 分隔；无属性时可省略括号

## 2. 指令命名

| 形式 | 含义 | 示例 |
| --- | --- | --- |
| `input("name", "姓名")` | 位置参数：字段名 + 标签 | 通用简写 |
| `input(name="user_name", label="姓名")` | 具名参数 | 显式写法 |
| `header("标题")` | 单文本参数 | 标题栏 |

位置参数的约定顺序：**字段名 → 标签 → 数据源 → 其余具名属性**。

## 3. 属性值与类型

```psl
input("age", "年龄", value=18, min=0, max=120, readonly=false)
```

| 字面量 | 写法 | 解析结果 |
| --- | --- | --- |
| 字符串 | `"姓名"` | `"姓名"` |
| 数字 | `18` / `3.5` | `number` |
| 布尔 | `true` / `false` | `boolean` |
| 数组 | `["男", "女"]` | `Array` |
| 对象 | `{name: "张三", age: 18}` | `Object` |
| 空值 | `null` | `null` |

## 4. 数据源三写法

```psl
-- 内联数组
radio("level", "职级", ["P4", "P5", "P6"])

-- 变量引用
table("user")
  data users

-- 远程接口
table("user", url="/api/user/list", method="get")
```

## 5. CSS 属性简写

T 语言把高频布局属性映射为短名，解析时自动展开为 CSS。

| 简写 | 展开 | 示例 |
| --- | --- | --- |
| `w` | `width` | `w=320` → `320px` |
| `h` | `height` | `h="100%"` |
| `ml` | `margin-left` | `ml=12` → `12px` |
| `mt` / `mb` / `mr` | `margin-top/bottom/right` | `mt=8` |
| `pd` | `padding` | `pd=16` |
| `bg` | `background` | `bg="#fff"` |
| `c` | `color` | `c="#333"` |
| `fs` | `font-size` | `fs=14` |
| `bdr` | `border-radius` | `bdr=6` |

无单位数字默认补 `px`；`%`、`vw`、`auto` 等需写成字符串。

## 6. 事件绑定

```psl
input("keyword", "关键词", change="onKeywordChange")
button("查询", click="onSearch")
```

`change` / `click` 等属性值为**方法名**，由宿主页面传入回调对象：

```js
mgr.mount(psl, {
  onKeywordChange(val, ctx) { console.log(val); },
  onSearch() { mgr.get('form').submit(); }
});
```

## 7. 注释

```psl
-- 行注释（推荐）
// 行注释（兼容 JS 风格）
```

注释节点在解析阶段被清洗，不产生任何组件。

## 8. 完整示例

```psl
header("数据检索")
form(prop="search", w="100%")
  input("keyword", "关键词", placeholder="输入姓名或工号", change="onKeywordChange")
  radio("status", "状态", ["全部", "在职", "离职"], value="全部")
  button("查询", click="onSearch", bg="#4285f4", c="#fff", bdr=4)

table("result", mode="edit", h=480, ml=0)
  column("name", "姓名", w=120, merge="row")
  column("dept", "部门", w=180, merge="row")
  column("salary", "薪资", align="right", format="money")
  data resultList
```

## 对照表：T 语言 ↔ HTML

| T 语言 | 等价 HTML |
| --- | --- |
| `header("标题")` | `<h1>标题</h1>` |
| `form(prop="f")` | `<form id="f">` |
| `input("name","姓名")` | `<input name="name" placeholder="姓名">` |
| `table()` + `column()` | `<table><thead>…` |
| `modal("提示")` | 遮罩层 + 对话框 |

## 下一步

- [DSL 解析器](/tools/dsl-parser.md)：看解析全过程
- [组件文档](/ui/table.md)：看指令对应的完整属性
