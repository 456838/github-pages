# ASO 官网路书

最后更新：2026-07-05

## 目标

本仓库用于在 `www.salton123.com` 下托管多个 App 的静态官网和 ASO 落地页。

站点需要从当前单模板页面逐步扩展成多 App 官网结构，同时保持路由归属、App 包名、ASO 素材来源和法务链接清晰可追溯。

## 维护门禁

新增、删除、重命名或重新定位页面时，必须在同一次变更中更新本路书。

每个面向用户的 App 官网 HTML 页面，都应在页面顶部附近添加可检索的中文注释：

```html
<!-- 【页面中文名】50字以内功能描述 -->
```

后续对话中可以通过中文页面名快速定位页面。

## 当前仓库事实

| 项目 | 当前状态 |
| --- | --- |
| 托管方式 | GitHub Pages 静态文件托管 |
| 域名 | `CNAME` 指向 `www.salton123.com` |
| 技术栈 | 普通 HTML、Bootstrap CSS、自定义 CSS、Font Awesome |
| 构建步骤 | 无 |
| 服务端运行时 | 无 |
| JavaScript | 允许前端-only JavaScript |
| 当前根首页 | 已改为 App 聚合页，首屏直接引导到 Uninstaller 官网 |
| 当前未跟踪状态 | `.idea/` 未跟踪，不属于站点内容 |

## 目标信息架构

```text
www.salton123.com
  ├── /                         根聚合页，或用户批准的主推 App 官网页
  ├── /uninstaller/
  │   └── AppUninstaller origin 官方落地页
  ├── /uninstaller-lite/
  │   └── AppUninstaller Lite 官方落地页
  ├── /<app-slug>/
  │   └── 未来 App 官方落地页
  ├── /privacy-policy.html      共享或历史隐私政策页
  ├── /terms-of-service.html    共享或历史服务条款页
  ├── /app-ads.txt              广告声明文件
  └── /404.html                 静态错误页
```

推荐素材目录：

```text
images/
  ├── apps/
  │   ├── appuninstaller-origin/
  │   ├── appuninstaller-lite/
  │   └── <app-slug>/
  └── shared/
```

## 产品路由登记

| 产品 | 路由 | 包名 | 权威资料来源 | 状态 |
| --- | --- | --- | --- | --- |
| 站点聚合页 | `/` 或 `index.html` | 不适用 | 本仓库 | 已实现 App 聚合页，首屏主入口指向 Uninstaller 官网 |
| AppUninstaller origin | `/uninstaller/` | `com.hello.uninstaller` | origin 项目资料 | 已实现 |
| AppUninstaller Lite | `/uninstaller-lite/` | `com.hello.uninstaller.lite` | lite 项目资料 | 已实现 |
| 未来 App | `/<app-slug>/` | 按 App 确认 | 按 App 仓库确认 | 未创建 |

## App 提案索引

| App | 提案文件 | 必须同步的变更 |
| --- | --- | --- |
| AppUninstaller origin | `docs/proposals/appuninstaller-origin.md` | `/uninstaller/` 页面、origin 素材、origin SEO/ASO 文案、origin Play 链接、共享首页中 origin 展示 |
| AppUninstaller Lite | `docs/proposals/appuninstaller-lite.md` | `/uninstaller-lite/` 页面、lite 素材、lite SEO/ASO 文案、lite Play 链接、共享首页中 lite 展示 |
| 未来 App | `docs/proposals/<app-slug>.md` | 该 App 页面、素材、文案、跳转、共享入口 |

## 页面路书

### 当前页面

| 中文名 | 路由 | 文件路径 | 归属 | 功能 |
| --- | --- | --- | --- | --- |
| 首页 | `/` | `index.html` | 共享站点 | App 聚合页，首屏展示 Uninstaller 名称、官网入口和 Google Play 入口 |
| 关于页 | `/about.html` | `about.html` | 历史/共享 | 当前模板关于页；尚未绑定具体 App |
| 联系页 | `/contact.html` | `contact.html` | 历史/共享 | 当前模板联系页；尚未绑定具体 App |
| 常见问题页 | `/faq.html` | `faq.html` | 历史/共享 | 当前模板 FAQ；后续可在批准后替换成 App FAQ |
| 定价页 | `/pricing.html` | `pricing.html` | 历史/共享 | 当前模板定价页；只有在产品价格策略确认后才能使用 |
| 隐私政策页 | `/privacy-policy.html` | `privacy-policy.html` | 法务/共享 | 隐私政策内容；除非用户要求，不要修改法务文案 |
| 服务条款页 | `/terms-of-service.html` | `terms-of-service.html` | 法务/共享 | 服务条款内容；除非用户要求，不要修改法务文案 |
| 错误页 | `/404.html` | `404.html` | 共享站点 | 静态 404 页面 |
| 广告声明文件 | `/app-ads.txt` | `app-ads.txt` | 共享站点 | Google AdMob app-ads 声明 |

### App 页面

| 中文名 | 路由 | 文件路径 | 归属 | 功能 |
| --- | --- | --- | --- | --- |
| Origin官网页 | `/uninstaller/` | `uninstaller/index.html` | AppUninstaller origin | 完整版官网页，承接 ASO 文案、截图、安全说明和 Google Play 下载入口 |
| Lite官网页 | `/uninstaller-lite/` | `uninstaller-lite/index.html` | AppUninstaller Lite | Lite 官网页，承接 Lite 项目资料中的 ASO 文案、截图和 Google Play 下载入口 |
| App聚合页 | `/` | `index.html` | 共享站点 | 当两个或更多 App 官网上线后，根首页作为多 App 聚合入口 |

## AppUninstaller Origin 页面契约

| 字段 | 值 |
| --- | --- |
| 产品名 | `Uninstaller - App Cleaner` |
| 中文名 | `卸载大师 - 应用清理` |
| 包名 | `com.hello.uninstaller` |
| Play 链接 | `https://play.google.com/store/apps/details?id=com.hello.uninstaller` |
| 定位 | Android app uninstaller、app remover、app manager、batch remove apps、batch uninstall、APK backup、storage cleanup |
| ASO 优先级 | 最高优先级：`uninstaller`；高潜力精准词：`app uninstaller`；短描述主轴：`App uninstaller, batch remove apps, APK backup, storage cleanup` |
| 安全表达 | 使用 Android 官方确认流程、无需 root、本地优先处理 |
| 主要素材 | origin 项目资料中的英文市场图与截图归档 |
| 网站素材 | `images/apps/appuninstaller-origin/` |

推荐页面结构：

1. 首屏：App 名称、Google Play CTA、主截图。
2. 核心能力：batch remove apps、batch uninstall、app remover、APK backup、storage cleanup、app manager、no root。
3. 安全与隐私：Android confirmation、本地优先、系统应用限制。
4. 截图展示。
5. 使用流程。
6. FAQ。
7. 最终 Google Play CTA 和法务链接。

## AppUninstaller Lite 页面契约

| 字段 | 值 |
| --- | --- |
| 产品名 | `Uninstaller Lite` |
| 包名 | `com.hello.uninstaller.lite` |
| Play 链接 | `https://play.google.com/store/apps/details?id=com.hello.uninstaller.lite` |
| 定位 | Lightweight app uninstaller、app remover、batch remove apps、batch uninstall、APK backup、storage cleanup |
| 与 origin 的差异 | 无广告；除非用户改变策略，否则 ASO 和核心应用管理定位与 origin 保持一致 |
| 主要素材 | lite 项目资料中的市场图版本归档与 Fastlane metadata |
| ASO 关键词 | 与 origin 共用项目关键词池；最高优先级是 `uninstaller` 和 `app uninstaller`，并同步覆盖 `batch remove apps`、`APK backup`、`storage cleanup`；页面写入推荐英文词、扩展英文词和本地化候选词，排除 `Avoid` 高风险词 |

推荐页面结构：

1. 首屏：Lite 名称、经批准的无广告定位、Google Play CTA、主截图。
2. 与 origin 对齐的核心能力，重点覆盖 app uninstaller、batch remove apps、APK backup、storage cleanup。
3. Lite 差异说明。
4. 安全与隐私。
5. 截图展示。
6. FAQ。
7. 最终 Google Play CTA 和法务链接。

## 未来 App 接入清单

新增 App 路由前，必须确认：

- App 名称和包名。
- Google Play 链接或目标商店链接。
- 源代码仓库和商店文案权威来源。
- 截图和 feature graphic 来源。
- 隐私政策与服务条款归属。
- 根首页继续作为聚合页，还是主推该 App。
- 是否需要本地化，以及目标语言范围。
- 是否存在禁止表达、合规限制、价格表达、广告/IAP 限制。

## SEO 与 ASO 规则

- 先保证自然文案，关键词用于支撑页面，不要主导页面。
- 页面应包含 App 名称、包名身份、核心使用场景和安全边界。
- AppUninstaller origin 与 lite 共用同一套项目 ASO 关键词池；如果更新关键词研究文档，两个页面都要同步更新。
- 2026-07-05 起，官网与商店详情同步把 `uninstaller` 定为最高优先级，把 `app uninstaller` 定为高潜力精准词；首页、origin 页面和 lite 页面都要自然覆盖 `batch remove apps`、`APK backup`、`storage cleanup`。
- 避免不受支持的承诺，例如保证释放多少空间、绕过 Android 限制、删除受保护系统应用或修改系统区域。
- 除非用户针对具体商店政策明确批准，否则避免价格或促销类表达。
- 每个 App 页面应配置：
  - `<title>`
  - meta description
  - canonical URL
  - Open Graph title、description、image
  - Twitter Card metadata
  - App 事实确认后再加入 `SoftwareApplication` JSON-LD

## 导航规则

- 根首页应链接到每一个已上线 App 官网。
- App 官网页应能返回根首页。
- App 官网页只能链接到对应包名的 Play Store 页面。
- 每个 App 页面页脚都要保留法务链接。
- 不要用容易混淆包名身份的方式互链 origin 与 lite；如需互链，必须清楚说明差异。

## 验证清单

每次路由变更后确认：

- 路由已出现在本文档中。
- 受影响 App 的 `docs/proposals/<app-slug>.md` 已同步更新。
- HTML 文件存在于登记路径。
- 图片路径可访问。
- Play 链接使用正确包名。
- 法务链接可访问。
- 除非用户明确要求，否则 `CNAME` 未被修改。
- 页面无需构建步骤即可运行。
- 发布前已人工检查桌面端和移动端布局。
