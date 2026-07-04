# 官网项目交接清单

最后更新：2026-07-04

## 当前状态

- 站点根首页已改为 App 聚合页，首屏直接引导到 `Uninstaller - App Cleaner`。
- Origin 官网页已创建：`uninstaller/index.html`。
- Origin 官网样式已创建：`css/uninstaller-site.css`。
- Origin 官网素材已放入：`images/apps/appuninstaller-origin/`。
- 站点规范和路书已中文化：`AGENTS.md`、`docs/site-route-book.md`。
- Origin 和 Lite 已有独立提案：`docs/proposals/appuninstaller-origin.md`、`docs/proposals/appuninstaller-lite.md`。

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
- Origin 官网暂不放出 Lite 互链，避免 Lite 页面未实现前产生 404。

## 剩余问题

### 1. 首页移动端存在横向溢出

现象：

- 390px 宽度下，首页首屏标题 `Uninstaller - App Cleaner` 右侧仍会被裁切。
- 首屏 CTA 已调整为纵向排列，但页面整体仍疑似被某个宽元素撑开。

建议处理：

- 优先检查 `index.html` 首页首屏和 `css/uninstaller-site.css` 中的移动端规则。
- 重点排查 header 导航、hero 背景区域、按钮组、App 卡片是否造成 `body` 横向滚动。
- 修复后重新截 390px 宽度移动端截图确认无横向滚动。

### 2. 需要补一次移动端和桌面端视觉回归

建议至少检查：

- `/` 桌面端 1440px。
- `/` 移动端 390px。
- `/uninstaller/` 桌面端 1440px。
- `/uninstaller/` 移动端 390px。

检查重点：

- 首屏标题、按钮、导航不裁切。
- 图片不遮挡文案。
- 截图区不横向溢出。
- 法务链接和 Google Play 链接可点击。

### 3. Lite 官网尚未实现

当前只完成 origin 官网。

Lite 后续落地前需要：

- 按 `docs/proposals/appuninstaller-lite.md` 实现 `uninstaller-lite/index.html`。
- 新增 `images/apps/appuninstaller-lite/` 素材。
- 更新 `docs/site-route-book.md`。
- 更新 `docs/proposals/appuninstaller-lite.md`。
- 再决定首页是否同时展示 origin 与 lite。
- Lite 页面上线后，再考虑 origin 与 lite 的互链。

### 4. 历史模板页面尚未整理

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
- 文档是否同步更新了对应提案。
- 文档中不要出现本机绝对路径。
- 不要提交 `.idea/`。

## 接手注意事项

- 本站是 GitHub Pages 静态站，不需要引入后端、数据库或构建系统。
- 每个 App 都要有自己的提案，放在 `docs/proposals/`。
- 修改 App 官网、首页中 App 展示、SEO/ASO 文案、素材或跳转时，必须同步更新对应提案。
- 文档中不要写本机绝对路径；需要描述外部资料时，用“origin 项目资料”“lite 项目资料”“本站项目资料”等表达。
