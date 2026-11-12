# USB Camera 官网提案

最后更新：2026-11-12

## 提案目标

为 USB Camera: UVC Viewer & OTG 建立官方落地页，核心定位为《Supported USB Cameras, Endoscopes & OTG Troubleshooting Guide》（兼容设备与排障指南）。精准承接 Google Web 搜索中“内窥镜连不上手机”“Android 14/15 UVC 权限”“MS2109 采集卡手机软件”“OTG View 替代软件”等极客与买家意图，直接导流至 Google Play 官方下载。

## 页面身份

| 项目 | 值 |
| --- | --- |
| 页面中文名 | USB Camera兼容与排障官网页 |
| 公开地址 | `https://www.salton123.com/usb-camera/` |
| 文件路径 | `usb-camera/index.html` |
| 产品名 | `USB Camera: UVC Viewer & OTG` |
| 中文名 | `USB摄像头 - UVC相机与内窥镜排障工具` |
| 包名 | `com.hello.usbcamera` |
| Google Play | `https://play.google.com/store/apps/details?id=com.hello.usbcamera` |
| 素材目录 | `images/apps/usb-camera/` |
| 当前状态 | 已通过本地检查和用户验收；上线状态以 GitHub Pages 部署结果为准 |

## 权威资料来源

- 应用核心能力：`usb-camera-cli/android/config.gradle`（最低 API 26）、`lib/src/features/device_connection/presentation/video_mode_tools.dart`（MJPEG/YUYV 模式）及 Google Play 官方商店页（UVC、OTG、照片和 MP4、数字缩放与硬件限制）。不将 AndroidManifest 当作具体设备型号兼容证据。
- 视觉素材：`usb-camera-cli` 项目的 `docs/design/usb-camera-icon-02-1024.png` 与 `docs/design/feature_graphic_en-US.png`（1024×500）。
- 网站路书与导航规范：本站 `docs/site-route-book.md` 与 `AGENTS.md`。

## 页面范围

范围内：

- 首屏产品定位与信任标签（No Root Required、Android 9 ~ 15 Ready、Zero Ads、Low Latency UVC）。
- Google Play 官方下载主 CTA 与直达链接。
- 常见连接排障向导（Troubleshooting Guide）：系统 OTG 开启指引（针对 OPPO / Vivo / OnePlus 等品牌）、Android 14/15 官方 UVC 授权、补光灯大电流 Hub 供电建议。
- 主流品牌与芯片兼容矩阵（Compatibility Matrix）：
  - 内窥镜/管道镜：Depstech、Teslong、Inskam、Kerui、Seesii 等通用 OTG 蛇形管；
  - 电子显微镜：Jiusion、Mustool、Plugable 等 USB 检验显微镜；
  - HDMI 视频采集卡：MacroSilicon MS2109 / MS2130 芯片采集卡、Cam Link、UGREEN 等便携监视设备；
  - 外接网络摄像头：Logitech C920/C930e 系列及所有遵循 USB Video Class (UVC) 协议的设备。
- 核心功能展示（1080P/4K 高画质、20倍数字变焦、无水印录制、低延迟监视）。
- 结构化问答 FAQ 及页脚法务链接。
- SEO 元信息：`title`、`description`、`keywords`、`canonical`、Open Graph、Twitter Card、`SoftwareApplication` 与 `FAQPage` 复合 JSON-LD。

范围外：

- 不引入 React/Vue 等打包工具，保持纯原生静态 HTML/CSS。
- 不提供直接的第三方 APK 外链下载（一律导流 Google Play 正版商店）。
- 不篡改现有 Uninstaller 与 Mobile Matrix 落地页已有功能与文案。

## 实施与规划记录

- 新增提案：`docs/proposals/usb-camera.md`
- 新增页面：`usb-camera/index.html`
- 新增页面样式：`css/usb-camera-site.css`
- 新增品牌素材：`images/apps/usb-camera/icon-1024.png`（从 `usb-camera-cli/docs/design/usb-camera-icon-02-1024.png` 复制）
- 新增产品配图：`images/apps/usb-camera/feature-graphic.png`（`1024 × 500`，从 `usb-camera-cli/docs/design/feature_graphic_en-US.png` 复制）
- 站点路书：`docs/site-route-book.md` 登记 `/usb-camera/` 路由。
- 站点地图：`sitemap.xml` 增加 `https://www.salton123.com/usb-camera/`。
- 根首页入口：`index.html` 顶部导航栏与产品卡片网格增加 USB Camera 入口。

## 2026-11-12 实现约束与验收

### 视觉与交互

- 深色硬件工具风：背景 `#0d1117`、卡片 `#161b22`、青色 `#00d2ff` 用于下载与引导、金色 `#ffd700` 仅标识 Pro。
- 系统字体，无远程字体请求。桌面首屏文案与真实产品配图双栏；移动端单栏，导航保持可见，所有下载入口均为普通链接。
- 兼容分类为两列卡片，手机单列；排障是三个有顺序的步骤；FAQ 使用原生可折叠组件，正文与 JSON-LD 一致。
- 主下载按钮至少 54px 高，导航链接至少 44px 高，保留键盘焦点、跳过导航入口及减少动态效果支持。
- `.uc-site` 样式与原官网隔离。首页复用原产品卡片，并用 `.apps-hub` 小范围处理新增导航后的换行；不改其他 App 专属页。
- 首页卡片的键盘处理仅响应卡片本身，避免 Enter 点击内部 Google Play 链接时被卡片详情跳转截走。

### 内容边界

- 品牌/型号只是 UVC 设备系列查找索引，尚无逐型号真机验收记录；明确 Wi-Fi-only、专有协议、USB 带宽、供电与手机差异。首屏不使用“所有设备必定兼容”的绝对承诺。
- 1080p/4K 取决于摄像头实际 USB 输出模式；采集卡 HDMI 输入标称 4K 不等于 USB 输出 4K。数字缩放不增加光学细节。
- 输入格式描述为 MJPEG、YUYV/YUY2；不将 MP4/H.264 录像编码等同于支持 H.264-only USB 输入。
- 部分 OPPO/Vivo/OnePlus 系统有 OTG 开关，位置与自动关闭行为因型号/系统而异；USB 权限错误不直接等同于用户拒绝授权。
- 广告与内购分别说明：无广告，不代表全部 Pro 功能免费。引用素材为营销配图，不标为真实预览截图。
- 法务内容和备案信息不修改；保持相对链接跳转。

### 搜索与资料

- 完整 title/description/canonical、Open Graph、Twitter Card，含图像尺寸和替代文案。
- `SoftwareApplication` 与 `FAQPage` 同时写入 JSON-LD；无虚构评分、测试认证、价格或下载量。
- Google 已于 2026 年停止展示 FAQ 富搜索结果，保留 FAQPage 仅作为内容语义，不承诺搜索折叠卡或排名。
- 核对来源：[Google Play 产品页](https://play.google.com/store/apps/details?id=com.hello.usbcamera)、[Google Search 文档更新](https://developers.google.com/search/updates#removing-faq-rich-result)、[OnePlus OTG 用户手册](https://service.oneplus.com/content/dam/support/user-manuals/common/OnePlus_10_Pro_User_Manual_EN.pdf)。

### 验收记录

- 本地预览：`python3 -m http.server 4187 --bind 127.0.0.1`，产品页 `/usb-camera/`，聚合页 `/`。
- 两页 HTML 标签、重复 ID、相对资源/链接、锚点与 HTTP 200 检查通过；sitemap XML 解析通过，USB Camera 路由仅登记一次。
- 4 个产品页 Google Play CTA 包名均为 `com.hello.usbcamera`；浏览器实点主 CTA 和首页卡片内 Google Play 链接（Enter）均到达正确商店页，首页内部链接未被卡片详情事件截走。
- SoftwareApplication / FAQPage JSON-LD 解析通过，4 条 FAQ 与页面问答逐条一致；未使用虚构评分。
- 产品页浏览器核对 360、390、768、1024、1440、1920px 宽度，未发现横向溢出；人工查看手机/平板/桌面布局、设备卡片、排障、功能和 FAQ。
- 聚合页核对 360、768、1440px 布局；新增配图保持 1024:500 比例，Apps 锚点标题不被固定导航遮住，原有轮播及产品入口保留。
- FAQ 鼠标展开与键盘 Enter 展开均有效；产品页图片正常加载，浏览器未记录错误或警告。
- 变更完成后自查：样式按页面隔离、无新运行时/构建依赖、法务与域名未改、素材复用既有文件；`git diff --check` 与新增文件尾随空白检查通过。
- 首轮完成实现与本地预览；2026-11-12 用户验收通过，并授权提交、推送至官网仓库。GitHub Pages 上线状态单独核对。
