# PSL基础语法

T语言（PSL）是专门用于UI界面描述的极简标记语言，采用类YAML的语法结构，学习成本极低。

---

## 基本结构
一个完整的PSL组件由三部分组成：
```psl
# 1. 组件声明：[]内为组件类型，声明这是一个什么组件
[form]

# 2. 配置属性：组件的全局配置项
title: 用户信息录入
width: 600px
labelPosition: left

# 3. 内容字段：组件的具体内容/字段配置
fields:
  - name: 用户名
    type: input
    required: true
```

---

## 数据类型
PSL支持4种基础数据类型：
| 类型 | 示例 | 说明 |
|------|------|------|
| 字符串 | `title: 用户注册` | 直接书写即可，无需引号，包含特殊字符时用双引号包裹 |
| 数字 | `pageSize: 20` | 整数/浮点数直接书写 |
| 布尔值 | `required: true` | 仅支持true/false两个值 |
| 数组 | `options: ["选项1", "选项2"]` | 用[]包裹，逗号分隔，支持字符串/数字/对象 |
| 对象 | `style: {color: "#333", fontSize: "14px"}` | 用{}包裹，键值对形式 |

---

## 常用组件语法示例

### 1. 表单组件
```psl
[form]
title: 表单标题
inline: false
labelWidth: 100px
fields:
  - name: 字段名称
    type: input/select/radio/checkbox/date
    required: true
    placeholder: 提示文字
    options: ["选项1", "选项2"]
    default: 默认值
submit: 提交按钮文字
```

### 2. 表格组件
```psl
[table]
title: 表格标题
border: true
striped: true
pageSize: 10
columns: ["列名1", "列名2", "列名3"]
dataSource: 接口地址或数据数组
```

### 3. 图表组件
```psl
[chart]
type: line/bar/pie/radar
title: 图表标题
height: 400px
xAxis: ["分类1", "分类2", "分类3"]
series:
  - name: 系列1
    data: [10, 20, 30]
  - name: 系列2
    data: [15, 25, 35]
```

---

## 语法注意事项
1. **缩进规范**：采用2空格或4空格缩进，禁止使用Tab，同一层级缩进必须一致
2. **注释写法**：`#` 开头为注释，不会被渲染
3. **特殊字符**：属性值包含冒号、引号时，需要用双引号包裹整个值
4. **组件嵌套**：支持容器组件嵌套基础组件，实现复杂布局

---

## 高级用法
- **事件绑定**：支持`onClick`、`onSubmit`等事件绑定，直接调用JavaScript函数
- **数据联动**：支持字段之间的联动显示/隐藏、选项动态加载
- **自定义样式**：通过`style`属性自定义组件样式，支持标准CSS属性
- **AI集成**：通过`aiPrompt`属性直接对接大模型，实现智能表单、数据自动填充
