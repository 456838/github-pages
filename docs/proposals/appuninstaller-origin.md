# AppUninstaller Origin 官网提案

最后更新：2026-07-05

## 提案目标

为 AppUninstaller 完整版建立独立官网页，承接 Google Play ASO 流量、搜索流量和品牌访问流量，并清楚区分 origin 与 lite 的包名、下载入口和素材来源。

## 页面身份

| 项目 | 值 |
| --- | --- |
| 页面中文名 | Origin官网页 |
| 公开地址 | `https://www.salton123.com/uninstaller/` |
| 文件路径 | `uninstaller/index.html` |
| 产品名 | `Uninstaller - App Cleaner` |
| 中文名 | `卸载大师 - 应用清理` |
| 包名 | `com.hello.uninstaller` |
| Google Play | `https://play.google.com/store/apps/details?id=com.hello.uninstaller` |
| 素材目录 | `images/apps/appuninstaller-origin/` |
| 当前状态 | 已实现首版静态官网 |

## 权威资料来源

- 商店文案：origin 项目资料
- Fastlane metadata：origin 项目资料
- 英文市场图：origin 项目资料
- 原始截图：origin 项目资料
- 网站路书：本站项目资料

## 页面范围

范围内：

- 首屏产品定位、Google Play CTA、主截图。
- 功能区：app uninstaller、batch remove apps、batch uninstall、app remover、APK backup、storage cleanup、app manager、no root。
- 安全区：Android 官方确认流程、本地优先处理、系统应用限制。
- 截图展示、使用流程、FAQ、最终 CTA、法务链接。
- SEO/ASO 元信息：title、description、canonical、Open Graph、Twitter Card、SoftwareApplication JSON-LD。

范围外：

- 不修改 Android App 代码。
- 不上传 Google Play。
- 不修改价格、订阅、隐私政策正文或服务条款正文，除非用户明确要求。
- 不承诺绕过 Android 限制、删除受保护系统应用或保证释放固定空间。

## 首版实现记录

- 新增页面：`uninstaller/index.html`
- 新增样式：`css/uninstaller-site.css`
- 新增素材目录：`images/apps/appuninstaller-origin/`
- 根首页入口：`index.html` 作为 App 聚合页展示 origin/lite，首屏优先引导 Google Play 下载，下方卡片进入详情页。
- 2026-07-05 转化优化：根首页首屏改为 App banner 轮播，每 5 秒在 origin/lite 之间切换；当前 banner 的主 CTA 和导航 CTA 直接指向对应 Google Play，App 卡片点击进入详情页。
- 公开路径：`https://www.salton123.com/uninstaller/`
- 页面风格：浅色可信工具风，真实 feature graphic 首屏背景，真实手机截图展示。
- 页面模块：首屏、信任点、核心功能、安全说明、截图展示、使用流程、FAQ、最终 CTA、页脚法务链接。
- Lite 互链：Lite 官网已落地，origin 页面可链接到 `/uninstaller-lite/`，但必须清楚说明 Lite 是另一个包名。
- ASO 关键词索引：已复用 Lite 项目资料中的 AppUninstaller 关键词池，在页面中写入 74 个推荐英文词、258 个扩展英文词和 298 个本地化候选词；`Avoid` 高风险词不进入官网页面。
- 2026-07-05 ASO 同步：根据 Google Play 表现报告，把 `uninstaller` 定为最高优先级，把 `app uninstaller` 定为高潜力精准词，并在 title、description、首屏、结构化数据中同步 `batch remove apps`、`APK backup`、`storage cleanup`。
- 页脚链接：保留 Home、隐私政策、服务条款等用户入口，不在页面底部暴露 `app-ads.txt`。

## 跳转规则

```text
/
  └── /uninstaller/
      ├── Google Play: com.hello.uninstaller
      ├── Lite 版本: /uninstaller-lite/
      ├── 隐私政策: /privacy-policy.html
      └── 服务条款: /terms-of-service.html
```

- `/uninstaller/` 的 canonical 必须指向 `https://www.salton123.com/uninstaller/`。
- 该页面只能把主下载 CTA 指向 `com.hello.uninstaller`。
- 可以在对比或页脚位置链接到 `/uninstaller-lite/`，但必须清楚说明 Lite 是另一个包名。
- 根首页展示 origin 时，banner 主 CTA 必须指向 `com.hello.uninstaller` 的 Google Play；origin 卡片点击进入 `/uninstaller/` 详情页。

## 文案与 ASO 规则

- 使用自然文案覆盖 `uninstaller`、`app uninstaller`、`batch remove apps`、`app remover`、`batch uninstall`、`bulk uninstall`、`APK backup`、`storage cleanup`、`reclaim storage`、`app manager`、`no root`。
- 关键词优先级：`uninstaller` 最高，`app uninstaller` 次高；`batch remove apps`、`APK backup`、`storage cleanup` 作为 title、description、首屏和结构化数据的常驻主轴。
- Origin 与 Lite 共用同一套项目 ASO 关键词池，页面差异只体现在产品名、包名、Play 链接和素材来源。
- 不做关键词墙。
- 不使用价格、折扣、限时、免费等促销表达，除非用户明确批准并更新本提案。
- 安全表达必须包含 Android confirmation、no root、local-first processing。

## 变更同步门禁

修改以下内容时，必须同步更新本提案：

- `/uninstaller/` 页面结构、导航、CTA、SEO 元信息。
- origin 图片、截图、feature graphic 或资源命名。
- origin Play 链接、包名、产品名、标题或 ASO 文案。
- 根首页中 origin 的展示卡片或跳转。
- 与 lite 的互链、对比或差异描述。
- 页脚链接展示策略。

## 验证清单

- 页面能在 GitHub Pages 静态环境运行，无构建步骤。
- Google Play 链接包名为 `com.hello.uninstaller`。
- canonical 为 `https://www.salton123.com/uninstaller/`。
- 图片路径从 `images/apps/appuninstaller-origin/` 读取。
- 页脚包含隐私政策和服务条款。
- 桌面端和移动端布局均已人工检查。
