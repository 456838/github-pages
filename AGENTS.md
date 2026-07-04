# AI 接手指南

本仓库通过 GitHub Pages 托管 `www.salton123.com` 的静态 ASO 官网。

## 项目范围

- 本站是静态 HTML/CSS/JavaScript 网站。除非用户明确要求，不要引入服务端运行时、后端 API、数据库、构建步骤或前端框架。
- 仓库必须保持可被 GitHub Pages 直接托管：提交后的静态文件就是线上内容。
- 本仓库后续会承载多个 App 官网。不要默认根首页永久属于某一个 App。
- 当前规划的 App 官网：
  - `origin`：AppUninstaller 完整版，包名 `com.hello.uninstaller`。
  - `lite`：AppUninstaller Lite 版，包名 `com.hello.uninstaller.lite`。
  - 未来 App：只有在用户明确 App 名称并提供或确认资料来源后再新增。

## 权威信息源

- 站点路由与页面归属：`docs/site-route-book.md`。
- App 官网提案：`docs/proposals/<app-slug>.md`。
- 域名配置：`CNAME` 和 `docs/CNAME`。
- AdMob 广告声明：`app-ads.txt`。
- 法务页面：`privacy-policy.html` 和 `terms-of-service.html`。
- AppUninstaller 的商店文案、截图和 ASO 素材来自 `/Users/salton/codeGit/AppUninstaller`，不要凭空编写或混用。

## App 提案门禁

- 每一个 App 必须有自己的官网提案，统一放在 `docs/proposals/` 下。
- 新增 App 官网前，必须先创建该 App 的提案，再创建页面、复制素材或修改导航。
- 修改某个 App 的官网页面、路由、跳转、素材、SEO/ASO 文案、Play 链接、法务链接、统计脚本或结构时，必须同步更新对应 App 提案。
- 修改共享首页、共享导航或共享样式且会影响某个 App 展示时，必须更新所有受影响 App 的提案。
- 如果某个 App 没有提案，禁止直接落地该 App 官网；必须先补提案。
- 每次开始 App 相关修改前，必须读取 `docs/site-route-book.md` 和对应 `docs/proposals/<app-slug>.md`。

## 多 App 路由规则

- 根目录 `index.html` 作为站点聚合页，或作为用户明确批准的主推 App 官网首页。
- App 专属公开落地页放在稳定、用户可读的目录下：
  - `uninstaller/index.html`
  - `uninstaller-lite/index.html`
  - `<app-slug>/index.html`
- App 专属素材放在匹配目录下：
  - `images/apps/appuninstaller-origin/`
  - `images/apps/appuninstaller-lite/`
  - `images/apps/<app-slug>/`
- 共享素材放在 `css/`、`fonts/` 和 `images/shared/`。
- 不要混用 origin 与 lite 的截图、包名、Google Play 链接或 ASO 文案。

## 编辑规则

- 修改页面前，先读取 `docs/site-route-book.md` 和目标 HTML/CSS 文件。
- 改动保持最小范围，并符合静态站点托管方式。
- 除非用户明确要求，不要修改 `CNAME`、`docs/CNAME`、`app-ads.txt`、法务页面和现有备案信息。
- 不要提交密钥、服务账号 JSON、keystore、token 或 Play Console 私密数据。
- JavaScript 只用于前端交互，例如菜单、FAQ 展开、截图轮播、统计标签和语言切换。不要在 JavaScript 中放任何密钥。
- SEO 元信息优先使用普通 HTML：`title`、`description`、canonical、Open Graph、Twitter Card，以及必要时的 JSON-LD。
- ASO 文案要自然覆盖关键词。避免关键词墙；除非用户明确批准并理解平台政策风险，否则避免价格或促销类表达。

## 路书维护规则

新增、删除、重命名或重新定位页面时，必须：

1. 同步更新 `docs/site-route-book.md`。
2. 同步更新受影响的 `docs/proposals/<app-slug>.md`。
3. 在页面顶部附近添加可检索的中文注释：

```html
<!-- 【页面中文名】50字以内功能描述 -->
```

4. 更新路书中的导航关系和素材归属。
5. 用 `python3 -m http.server` 或浏览器直接打开页面做本地静态检查。

## 验证要求

只改文档时：

- 检查 Markdown 可读性。
- 运行 `git diff --check` 或等价空白检查。

修改 HTML/CSS 时：

- 本地打开页面，或在仓库根目录运行 `python3 -m http.server` 后访问页面。
- 检查桌面和移动端宽度。
- 确认图片路径、法务链接、App 链接、canonical URL 和包名都正确。
