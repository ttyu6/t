# 提交核对清单

> 用于核对 Pristine Design 文档仓库文件是否齐全。提交前逐项勾选。

## 一、根目录文件

- [ ] `LICENSE`（MIT）
- [ ] `.gitignore`
- [ ] `CONTRIBUTING.md`
- [ ] `README.md`（徽章已替换为实际用户名/仓库名/Pages 地址）
- [ ] `CHECKLIST.md`（本文件）
- [ ] `requirements.txt`（MkDocs 方案需要；Docsify 方案可省略）
- [ ] `mkdocs.yml`（仅 MkDocs 方案需要）

## 二、`docs/` 根目录

- [ ] `.nojekyll`（空文件，跳过 Jekyll 处理，避免下划线文件被忽略）
- [ ] `index.html`（Docsify 入口，含 `coverpage: true`、`loadSidebar: true`、`search`、`copyCode`）
- [ ] `README.md`（文档首页）
- [ ] `_sidebar.md`（侧边栏，链接与 `ui/`、`cases/` 文件一一对应）
- [ ] `_coverpage.md`（封面，链接指向 `README.md` 与 GitHub 仓库）
- [ ] `tools.md`（工具库 12 项）

## 三、`docs/ui/`（10 个分类页面）

- [ ] `basic.md`：基础 7 项
- [ ] `container.md`：容器 6 项（Typography `New`）
- [ ] `layout.md`：布局 5 项（Flex / Row / Col `New`）
- [ ] `navigation.md`：导航 9 项
- [ ] `data-entry.md`：数据录入 22 项（Upload `HOT`）
- [ ] `data-display.md`：数据展示 15 项（Statistic / Calendar / ImagePreview / Avatar / Badge / Tag / QRCode `New`）
- [ ] `data-interaction.md`：数据交互 6 项（Code / CodeTool / FindForm / Search `New`）
- [ ] `feedback.md`：反馈 14 项
- [ ] `media.md`：多媒体 3 项（Video / Audio `New`）
- [ ] `other.md`：其他 5 项（FloatButton / html `New`）

## 四、`docs/cases/`（3 个案例页面）

- [ ] `app.md`：App（电商类）17 个页面
- [ ] `software.md`：软件（后台）22 个页面
- [ ] `website.md`：网站（门户/大屏）13 个页面

## 五、`.github/workflows/`（二选一）

- [ ] `pages-docsify.yml`（Docsify 方案）
- [ ] `pages-mkdocs.yml`（MkDocs 方案）

> 两个工作流不要同时启用，保留一个即可。

## 六、仓库设置（非文件）

- [ ] Settings → Pages → Source 选择 **GitHub Actions**（或 `main` 分支 `/docs` 目录）
- [ ] About 描述已填写
- [ ] Topics 已添加（建议：`pristine-design`、`psl`、`t-language`、`ui-components`、`component-library`、`native-web`、`docsify`、`documentation`、`github-pages`、`chinese`）
- [ ] 首次 Actions 运行成功，Pages 地址可访问
- [ ] 访问 Pages 首页能看到封面与侧边栏；若 404，检查 `docs/.nojekyll` 是否存在、`_sidebar.md` / `_coverpage.md` 是否在 `docs/` 根目录

## 七、数量汇总（与清单一致性自查）

| 板块 | 分类数 | 条目数 |
| --- | --- | --- |
| UI 组件 | 10 | 102（基础 7 + 容器 6 + 布局 5 + 导航 9 + 数据录入 22 + 数据展示 15 + 数据交互 6 + 反馈 14 + 多媒体 3 + 其他 5） |
| 工具库 | 1 | 12 |
| 实战案例 | 3 | 52（App 17 + 软件 22 + 网站 13） |

> 若原始清单条目数与此不同，以清单为准逐项核对；上表用于快速发现漏项。
