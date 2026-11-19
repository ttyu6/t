# 工具库

> Pristine Design 除组件外提供的通用函数，全部挂载在 `Pristine` 命名空间下，无外部依赖。

## 调用方式

```js
const { $, $all, on, dom, fmt, req, store, esc } = Pristine.util;
```

## 1. DOM 选择

| 函数 | 签名 | 说明 |
| --- | --- | --- |
| `$` | `(sel, root?)` | `querySelector` 简写 |
| `$all` | `(sel, root?)` | `querySelectorAll` 转数组 |
| `on` | `(el, type, fn, opt?)` | 统一绑定，返回解绑函数 |
| `off` | `(el, type, fn)` | 解绑 |
| `create` | `(tag, attrs?, children?)` | 创建元素 |
| `show` / `hide` | `(el)` | display 切换 |
| `css` | `(el, obj)` | 批量设置样式 |

```js
const unbind = on(btn, 'click', handle);
unbind();   // 页面销毁时调用，避免内存泄漏
```

## 2. 数据处理

| 函数 | 说明 |
| --- | --- |
| `deepClone(obj)` | 深拷贝，支持 Date / Array / 嵌套对象 |
| `extend(target, ...src)` | 浅合并，`deepExtend` 为深合并 |
| `mergeRows(list, fields)` | 按字段生成合并信息 `{ rowspan, hidden }`，供 TableUI 使用 |
| `treeEach(tree, fn, childrenKey?)` | 递归遍历树，可中断（返回 false） |
| `toTree(list, idKey, pidKey)` | 扁平列表转树 |
| `flatten(tree)` | 树转扁平 |

```js
const tree = toTree(deptList, 'id', 'pid');
const merged = mergeRows(rows, ['dept', 'group']);
```

## 3. 格式化

| 函数 | 示例 | 输出 |
| --- | --- | --- |
| `fmt.money` | `fmt.money(12345.6)` | `¥12,345.60` |
| `fmt.date` | `fmt.date(d, 'YYYY-MM-DD')` | `2026-11-16` |
| `fmt.percent` | `fmt.percent(0.235, 1)` | `23.5%` |
| `fmt.bytes` | `fmt.bytes(1572864)` | `1.50 MB` |
| `fmt.num` | `fmt.num(1234567)` | `1,234,567` |
| `fmt.thousands` | `fmt.thousands(1234.5, 2)` | `1,234.50` |

日期格式化手写实现，不引入 dayjs。

## 4. 请求封装

```js
req.get(url, params)
req.post(url, data, { headers })
req.file(url, file, { onProgress })
```

- 自动序列化 query、自动带 `Content-Type`
- 非 2xx 抛错，错误对象含 `status`、`message`
- 超时默认 15000ms，可用 `req.setup({ timeout: 20000 })`
- 可注入全局拦截器：

```js
req.interceptors.push((conf) => {
  conf.headers.Authorization = 'Bearer ' + token;
  return conf;
});
```

## 5. 本地存储

```js
store.set('token', 'xxx', 7 * 24 * 3600);  // 带过期秒数
store.get('token');
store.remove('token');
```

内部以 `pristine_` 前缀写入 localStorage，读取时校验过期时间，过期自动清除。

## 6. 安全

| 函数 | 说明 |
| --- | --- |
| `esc(str)` | HTML 转义，`< > & " '` |
| `escAttr(str)` | 属性值转义 |
| `safeHtml(str)` | 白名单过滤标签，允许 `b/i/span/p/br` |

**所有把用户输入拼进 HTML 的地方都必须走 `esc`**，这是组件内部的默认行为，自定义 `render` 时请显式调用。

## 7. ID 与防抖

```js
uid('chart');            // "chart_3f9a1"
debounce(fn, 300);
throttle(fn, 100);
nextTick(fn);
```

## 8. 常量

```js
Pristine.CONST = {
  Z_INDEX: 9000,
  ANIM: 200,
  BREAKPOINT: { sm: 576, md: 768, lg: 992 },
  COLOR: { primary: '#4285f4', success: '#12b76a', warn: '#f79009', danger: '#e5484d' }
};
```

## 下一步

- [BaseUI 管理器基类](/tools/base-ui.md)
- [DSL 解析器](/tools/dsl-parser.md)
