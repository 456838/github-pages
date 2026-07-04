# 官网项目交接清单

最后更新：2026-07-04

## 当前状态

- 站点根首页已改为 App 聚合页，首屏直接引导到 `Uninstaller - App Cleaner`。
- Origin 官网页已创建：`uninstaller/index.html`。
- Origin 官网样式已创建：`css/uninstaller-site.css`。
- Origin 官网素材已放入：`images/apps/appuninstaller-origin/`。
- 站点规范和路书已中文化：`AGENTS.md`、`docs/site-route-book.md`。
- Origin 和 Lite 均已有独立提案并均已实现：`docs/proposals/appuninstaller-origin.md`、`docs/proposals/appuninstaller-lite.md`。
- Origin官网页（`uninstaller/index.html`）与 Lite官网页（`uninstaller-lite/index.html`）已部署高级华丽质感UI。
- Origin 与 Lite 已共用同一套 AppUninstaller ASO 关键词池，页面内已写入推荐英文词、扩展英文词和本地化候选词，排除 `Avoid` 高风险词。
- 用户可见页脚不展示 `app-ads.txt` 链接；根目录文件本身仍保留给广告平台读取。
- 首页移动端横向溢出问题已修复，全站通过响应式回归检查。

## 本地运行方式

在项目根目录执行：

```bash
python3 -m http.server 4173 --bind 127.0.0.1
```

访问：

- 首页：`http://127.0.0.1:4173/`
- Origin 官网：`http://127.0.0.1:4173/uninstaller/`

## 已确认的结果

- 首页和 `/uninstaller/` 本地访问均返回 200。
- 首页桌面端首屏入口已经明确：顶部导航、首屏主按钮、App 卡片都能进入 Uninstaller 官网。
- 文档中已避免出现本机绝对路径。
- Google Play 链接指向 origin 包名：`com.hello.uninstaller`。
- Origin 与 Lite 官网页均已存在，可以互链；互链时必须清楚区分包名。

### 1. 历史模板页面尚未整理

以下页面仍是旧模板或共享历史页面：

- `about.html`
- `contact.html`
- `faq.html`
- `pricing.html`

建议：

- 不要在没有明确需求时删除。
- 后续如果要做品牌官网，可以逐步改成共享站点页面。
- 如果只保留 App 官网，也需要先确认路由策略再处理。

### 5. 提交前验证清单

建议提交前运行：

```bash
git diff --check
python3 -m http.server 4173 --bind 127.0.0.1
```

并人工检查：

- 首页入口是否一眼能进入 Uninstaller 官网。
- `/uninstaller/` 是否符合 origin 包名和 Google Play 链接。
- `/uninstaller-lite/` 是否符合 lite 包名、Lite 项目资料文案和 Lite 项目素材。
- 如果项目 ASO 关键词文档更新，必须同步更新 `/uninstaller/` 和 `/uninstaller-lite/` 两个页面的关键词索引。
- 文档是否同步更新了对应提案。
- 文档中不要出现本机绝对路径。
- 不要提交 `.idea/`。

## 接手注意事项

- 本站是 GitHub Pages 静态站，不需要引入后端、数据库或构建系统。
- 每个 App 都要有自己的提案，放在 `docs/proposals/`。
- 修改 App 官网、首页中 App 展示、SEO/ASO 文案、素材或跳转时，必须同步更新对应提案。
- 文档中不要写本机绝对路径；需要描述外部资料时，用“origin 项目资料”“lite 项目资料”“本站项目资料”等表达。
