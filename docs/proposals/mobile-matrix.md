# Mobile Matrix 官网提案

最后更新：2026-11-12

## 提案目标

为 Mobile Matrix 建立独立的 macOS Android 设备控制官网页，承接“Android device control for macOS”“ADB GUI for Mac”“Android screen mirroring Mac”和多设备测试等搜索意图，并将搜索访问转化为 GitHub 仓库访问和 Release 下载。

## 页面身份

| 项目 | 值 |
| --- | --- |
| 页面中文名 | Mobile Matrix官网页 |
| 公开地址 | `https://www.salton123.com/mobile-matrix/` |
| 文件路径 | `mobile-matrix/index.html` |
| 产品名 | `Mobile Matrix` |
| 产品仓库 | `https://github.com/LiveSalton/mobile_matrix_flutter` |
| 当前发布 | `v1.0.1`，macOS Apple Silicon（arm64） |
| 素材目录 | `images/apps/mobile-matrix/` |
| 当前状态 | 已实现首版静态官网 |

## 权威资料来源

- 产品能力、安装要求、平台边界和 Release：Mobile Matrix 项目的 `README.md`、`README-ZH.md` 与 GitHub Release。
- 品牌图标：`/Users/salton/codeGit/mobile-matrix/vendor/devicefarmer-stf/res/common/logo/exports/mobile-matrix-1024.png`。
- 页面路由与共享站点规则：本站 `docs/site-route-book.md`。

## 页面范围

范围内：

- macOS Android 设备控制、ADB、实时投屏、键盘触摸、剪贴板、截图、设备工具和多设备预览。
- GitHub 仓库和 Release 下载入口。
- 本地优先、内置 STF Lite、无需 Docker/RethinkDB 的边界说明。
- 系统要求、安装流程、FAQ 和当前 Windows/Linux 未提供正式包的限制说明。
- `title`、description、canonical、Open Graph、Twitter Card、`SoftwareApplication` JSON-LD。

范围外：

- 不声称 Mobile Matrix 是完整 STF Server、云控服务或 Android 客户端。
- 不声称 Windows/Linux 已经可以分发。
- 不上传 App Store 或 Google Play。
- 不修改共享隐私政策、服务条款或域名配置。

## 首版实现记录

- 2026-11-12 共享首页新增 USB Camera 导航与产品卡片；Mobile Matrix 原有卡片、详情与 GitHub Release 地址不变。导航在窄屏按行换行；卡片键盘事件不再拦截内部链接的 Enter。

- 新增页面：`mobile-matrix/index.html`
- 新增页面样式：`css/mobile-matrix-site.css`
- 新增品牌素材：`images/apps/mobile-matrix/icon-1024.png`
- 新增产品配图：`images/apps/mobile-matrix/feature-graphic.png`（`1024 × 500`），用于聚合首页卡片和社交分享预览，与现有 Uninstaller feature graphic 尺寸统一。
- 根首页新增产品卡片和导航入口，但保留现有 Uninstaller Google Play Banner 轮播。
- 根首页 Mobile Matrix 卡片使用设备总览配图，避免仅展示方形 Logo 造成信息密度不足。
- 新增 `sitemap.xml` 与 `robots.txt`。
- Mobile Matrix 项目的两个 README 增加官网反向链接。
- 首版使用无个人数据的 CSS 产品预览，后续可替换为脱敏后的真实 v1.0.1 截图。

## SEO 关键词策略

主关键词：`Android device control for macOS`、`ADB GUI for Mac`、`Android screen mirroring Mac`。

辅助关键词：`control Android phone from Mac`、`Android device manager desktop`、`multi-device Android testing`、`keyboard and touch input`、`clipboard sync`、`STF Lite`。

关键词必须出现在自然标题、功能说明、安装流程和 FAQ 的上下文中，不创建关键词堆砌区，也不引入与实际能力无关的竞品或平台词。

## 站点同步门禁

修改以下内容时必须同步本提案和路书：

- `/mobile-matrix/` 页面结构、导航、CTA、SEO 元信息或能力描述。
- `images/apps/mobile-matrix/` 素材和截图。
- 根首页 Mobile Matrix 卡片、导航和 SEO 元信息。
- GitHub 仓库、Release、版本号或下载链接。
- 未来增加 Mobile Matrix 指南页或中文独立路由。

## 发布同步规则

Mobile Matrix 新版本发布时，若官网仍使用固定的 `softwareVersion` 或版本文案，应同步更新本页面、README 反向链接和 sitemap 的更新时间。下载 CTA 默认指向 GitHub Releases latest 页面，避免固定版本链接失效。

## 验证清单

- 页面在 GitHub Pages 静态环境无需构建步骤即可打开。
- canonical、Open Graph、JSON-LD 和 GitHub 链接指向正确地址。
- Release CTA 指向 Mobile Matrix 仓库，不指向 Google Play。
- 页面包含隐私政策和服务条款链接。
- 桌面端、平板宽度和移动端无横向溢出。
- `sitemap.xml` 包含根页、两个现有 Uninstaller 页面和 Mobile Matrix 页面。
