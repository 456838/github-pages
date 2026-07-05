# AppUninstaller Lite 官网提案

最后更新：2026-07-05

## 提案目标

为 AppUninstaller Lite 建立独立官网页，承接 Lite 版本的 Google Play ASO 流量、搜索流量和品牌访问流量，并避免与 origin 完整版的包名、下载入口和素材混淆。

## 页面身份

| 项目 | 值 |
| --- | --- |
| 页面中文名 | Lite官网页 |
| 公开地址 | `https://www.salton123.com/uninstaller-lite/` |
| 文件路径 | `uninstaller-lite/index.html` |
| 产品名 | `Uninstaller Lite` |
| 包名 | `com.hello.uninstaller.lite` |
| Google Play | `https://play.google.com/store/apps/details?id=com.hello.uninstaller.lite` |
| 素材目录 | `images/apps/appuninstaller-lite/` |
| 当前状态 | 已实现首版静态官网，并已改用 Lite 项目资料素材与描述 |

## 权威资料来源

- 商店文案：lite 项目资料
- Fastlane metadata：lite 项目资料
- Lite 生图说明：lite 项目资料
- Lite 关键词调研：lite 项目资料
- Lite 市场图版本归档：lite 项目资料
- 网站路书：本站项目资料

## 首版实现记录

- 新增页面：`uninstaller-lite/index.html`
- 复用官网样式：`css/uninstaller-site.css`
- 新增素材目录：`images/apps/appuninstaller-lite/`
- 素材来源：Lite en-US fastlane metadata 中的 `featureGraphic.png` 与 5 张 `phoneScreenshots`。
- 根首页入口：`index.html` 已加入 Lite 官网入口和 Google Play 入口。
- 页面文案：已按 Lite en-US 商店资料中的 `title.txt`、`short_description.txt`、`full_description.txt` 调整。
- ASO 关键词索引：已把项目关键词池中的 74 个推荐英文词、258 个扩展英文词和 298 个本地化候选词写入页面；`Avoid` 高风险词不进入官网页面。
- 2026-07-05 ASO 同步：根据 Google Play 表现报告，把 `uninstaller` 定为最高优先级，把 `app uninstaller` 定为高潜力精准词，并在 title、description、首屏、结构化数据中同步 `batch remove apps`、`APK backup`、`storage cleanup`；本次不更新 Lite 截图、feature graphic 或素材路径。
- 公开路径：`https://www.salton123.com/uninstaller-lite/`
- Origin 互链：Lite 页导航可回到 `/uninstaller/`，并明确两者是不同包名。
- 页脚链接：保留 Home、隐私政策、服务条款等用户入口，不在页面底部暴露 `app-ads.txt`。

## 页面范围

范围内：

- 首屏 Lite 产品定位、Google Play CTA、主截图。
- 功能区：app uninstaller、batch remove apps、batch uninstall、app remover、APK backup、storage cleanup、app manager、no root。
- Lite 差异说明：无广告定位，且核心应用管理能力与 origin 对齐。
- 安全区：Android 官方确认流程、本地优先处理、系统应用限制。
- 截图展示、使用流程、FAQ、最终 CTA、法务链接。
- SEO/ASO 元信息：title、description、canonical、Open Graph、Twitter Card、SoftwareApplication JSON-LD。

范围外：

- 不修改 Android App 代码。
- 不上传 Google Play。
- 不修改价格、订阅、隐私政策正文或服务条款正文，除非用户明确要求。
- 不承诺绕过 Android 限制、删除受保护系统应用或保证释放固定空间。

## 跳转规则

```text
/
  └── /uninstaller-lite/
      ├── Google Play: com.hello.uninstaller.lite
      ├── 完整版: /uninstaller/
      ├── 隐私政策: /privacy-policy.html
      └── 服务条款: /terms-of-service.html
```

- `/uninstaller-lite/` 的 canonical 必须指向 `https://www.salton123.com/uninstaller-lite/`。
- 该页面只能把主下载 CTA 指向 `com.hello.uninstaller.lite`。
- 可以在对比或页脚位置链接到 `/uninstaller/`，但必须清楚说明完整版是另一个包名。

## 文案与 ASO 规则

- Lite 可以与 origin 保持相同 ASO 主轴：`uninstaller`、`app uninstaller`、`batch remove apps`、`app remover`、`batch uninstall`、`bulk uninstall`、`APK backup`、`storage cleanup`、`reclaim storage`、`app manager`、`no root`。
- 关键词优先级：`uninstaller` 最高，`app uninstaller` 次高；`batch remove apps`、`APK backup`、`storage cleanup` 作为 title、description、首屏和结构化数据的常驻主轴。
- Origin 与 Lite 共用同一套项目 ASO 关键词池，页面差异只体现在产品名、包名、Play 链接和素材来源。
- Lite 差异表达必须清楚，但不使用容易触发价格或促销风险的表达，除非用户明确批准并更新本提案。
- 不做关键词墙。
- 安全表达必须包含 Android confirmation、no root、local-first processing。

## 变更同步门禁

修改以下内容时，必须同步更新本提案：

- `/uninstaller-lite/` 页面结构、导航、CTA、SEO 元信息。
- lite 图片、截图、feature graphic 或资源命名。
- lite Play 链接、包名、产品名、标题或 ASO 文案。
- 根首页中 lite 的展示卡片或跳转。
- 与 origin 的互链、对比或差异描述。
- 页脚链接展示策略。

## 验证清单

- 页面能在 GitHub Pages 静态环境运行，无构建步骤。
- Google Play 链接包名为 `com.hello.uninstaller.lite`。
- canonical 为 `https://www.salton123.com/uninstaller-lite/`。
- 图片路径从 `images/apps/appuninstaller-lite/` 读取。
- 页脚包含隐私政策和服务条款。
- 桌面端和移动端布局均已人工检查。
