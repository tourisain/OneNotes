# Changelog

## v1.0.311 (build 311 - 2026-07-07)

### 涓枃鏇存柊璇存槑

**功能优化与修复**

- 移除 Markdown 导出/导入功能。
- 全屏模式优化：移除中间右侧工具栏展开按钮，右上角退出按钮缩小且颜色统一。
- 首页快捷操作区支持在设置中隐藏/显示，开关位于设置页面文件夹与分组下方。

### English Release Notes

**Feature polish and fixes**

- Removed Markdown export/import feature.
- Focus mode polish: removed toolbar expand handle, shrunk exit button with consistent colors.
- Home quick actions strip can now be toggled in Settings under Folders & Groups.

## v1.0.310 (build 310 - 2026-07-07)

### 涓枃鏇存柊璇存槑

**核心功能增强**

- 图片编辑增强：支持透明度、边框、阴影、裁剪和锁定贴纸。
- 笔记内链接：支持创建笔记间链接，点击跳转到目标笔记。
- Markdown 导出/导入：支持手写识别转 Markdown 导出，支持导入 Markdown 文件。
- 批量导出：支持多选笔记批量导出为 PDF 或 ZIP。
- 全屏/专注模式：一键隐藏工具栏，进入沉浸式书写。
- 页面缩略图导航：侧边栏页面缩略图列表，支持快速跳转和添加/删除页面。
- 标尺/量角器增强：角度吸附、刻度数字标签、量角器角度标注。

### English Release Notes

**Core feature enhancements**

- Image editing: opacity, border, shadow, crop, and lock for stickers.
- Note links: create links between notes with tap-to-navigate.
- Markdown export/import: OCR-based handwriting-to-Markdown export and Markdown import.
- Batch export: multi-select notes to export as PDF or ZIP.
- Focus mode: hide all toolbars for immersive writing.
- Page thumbnail sidebar: thumbnail list with quick jump and add/delete pages.
- Ruler/protractor enhancement: angle snapping, tick labels, protractor degree markers.

## v1.0.309 (build 309 - 2026-07-07)

### 涓枃鏇存柊璇存槑

**版本号对齐与 BitmapFactory 降采样优化**

- 版本号与版本代码对齐，统一为 1.0.309/309。
- 优化小组件与预览中的贴纸图片加载，使用 BitmapFactory.Options.inSampleSize 进行降采样，降低内存占用。

### English Release Notes

**Version number alignment and BitmapFactory downsampling**

- Aligned versionName and versionCode to 1.0.309/309.
- Optimized sticker image loading in widgets and previews by using BitmapFactory.Options.inSampleSize for downsampling to reduce memory usage.

## v1.0.307 (build 308 - 2026-07-06)

### 涓枃鏇存柊璇存槑

**手写编辑辅助修复与构建清理**

- 修复对齐与分布：移除死代码，分布后同步选区边界。
- 修复 7 个过时单元测试，使其与当前实现一致。
- 补齐快速草稿小组件在 7 种语言中的缺失翻译。
- 清理误跟踪的 .kotlin/errors 临时日志并加入 .gitignore。
- 优化小组件与预览中的贴纸图片加载，使用 BitmapFactory.Options.inSampleSize 进行降采样，降低内存占用。

### English Release Notes

**Handwriting editor fixes and build cleanup**

- Fixed alignment and distribution: removed dead code and synced selection bounds after distribute.
- Fixed 7 outdated unit tests to match current implementation.
- Added missing quick-draft widget translations for 7 languages.
- Cleaned up tracked .kotlin/errors temp logs and added .kotlin/ to .gitignore.
- Optimized sticker image loading in widgets and previews by using BitmapFactory.Options.inSampleSize for downsampling to reduce memory usage.

## v1.0.306 (build 307 - 2026-07-05)

### 涓枃鏇存柊璇存槑

**笔刷引擎抽象与真实感渲染**

- 抽象统一笔刷引擎接口，便于后续扩展新笔刷类型。
- 提升钢笔、毛笔、书法笔、水彩、铅笔、蜡笔、荧光笔的真实感渲染效果。
- 支持压感与倾斜数据透传，手写体验更自然。
- 新增渲染异常保护与性能保护，避免极端输入导致卡顿或崩溃。

### English Release Notes

**Brush engine abstraction and realistic rendering**

- Abstracted a unified brush engine interface for easier future brush extensions.
- Improved realistic rendering for pen, brush, calligraphy, watercolor, pencil, crayon, and highlighter.
- Added pressure and tilt data pass-through for a more natural handwriting experience.
- Added rendering crash protection and performance safeguards to avoid jank or crashes from extreme input.

## v1.0.305 (build 306 - 2026-07-05)

### 涓枃鏇存柊璇存槑

**构建流程、迁移验证与 16 KB 对齐常态化**

- 新增 release.ps1，实现清理、构建、16 KB 对齐验证、产物复制与 SHA-256 校验全流程自动化。
- 新增 verify-room-migration.ps1，对 Room 迁移代码和 schema 做静态检查，并输出手动验证清单。
- 将 16 KB 对齐验证纳入发布脚本：APK ZIP 对齐通过 zipalign 检查，native 库 ELF 段对齐通过 llvm-objdump 检查。
- 升级 ML Kit digital-ink-recognition 到 19.0.0，解决 libdigitalink.so ELF 段未 16 KB 对齐的问题。
- 适配 ML Kit 19.0.0 新包路径：com.google.mlkit.vision.digitalink.recognition。
- 保持 arm64-v8a + armeabi-v7a 双 ABI 与 useLegacyPackaging = false 配置。

### English Release Notes

**Build reproducibility, migration verification, and 16 KB alignment standardization**

- Added release.ps1 to automate clean, build, 16 KB alignment verification, artifact copy, and SHA-256 checks.
- Added verify-room-migration.ps1 for static checks on Room migration code and schemas, plus a manual verification checklist.
- Integrated 16 KB alignment verification into the release script: APK ZIP alignment via zipalign and native library ELF segment alignment via llvm-objdump.
- Upgraded ML Kit digital-ink-recognition to 19.0.0 to fix libdigitalink.so ELF segment 16 KB alignment.
- Adapted to ML Kit 19.0.0 package path: com.google.mlkit.vision.digitalink.recognition.
- Maintained arm64-v8a + armeabi-v7a dual ABI and useLegacyPackaging = false configuration.

## v1.0.304 (build 305 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**移除首页快速草稿入口**

- 删除首页顶部操作条中的“快速草稿”按钮。
- 删除空状态首页中的“快速草稿”按钮。
- 首页长按空白处仍可快速创建草稿。

### English Release Notes

**Remove quick draft entry from home screen**

- Removed the “Quick draft” button from the home top action strip.
- Removed the “Quick draft” button from the empty home screen.
- Long-pressing empty space on the home screen still creates a quick draft.

## v1.0.303 (build 304 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**菜单整理与绘图工具增强**

- 将具体页面菜单中的“项目信息”移入“更多”下级菜单，文本简化为“信息”。
- 支持双指在直尺或量角器上捏合缩放，调整辅助工具大小。
- 优化曲线工具：曲线方向改为相对线段方向，绘制结果更一致。
- 优化箭头工具：箭头大小比例更合理，短箭头不再出现过大箭头头。

### English Release Notes

**Menu reorganization and drawing tools enhancement**

- Moved “Project info” from the editor menu into the “More” submenu and renamed it to “Info”.
- Added pinch-to-scale support on the ruler and protractor guides to adjust their sizes.
- Improved curve tool: curve direction is now relative to the line direction for more consistent results.
- Improved arrow tool: arrowhead size is more proportional and no longer oversized on short arrows.

## v1.0.302 (build 303 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**取消工具栏自动折叠**

- 具体页面工具栏不再自动折叠，保持常驻显示，方便随时切换笔刷和工具。
- 用户仍可手动收起或展开工具栏。

### English Release Notes

**Disable toolbar auto-collapse**

- The editor toolbar no longer auto-collapses and stays visible for quick access to brushes and tools.
- Users can still manually collapse or expand the toolbar.

## v1.0.301 (build 302 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**编辑器工具栏图标区分**

- 为不同笔刷（钢笔、铅笔、毛笔、 fountain 笔、荧光笔、书法笔、蜡笔、水彩、橡皮）配置各自不同的图标。
- 为几何工具（直线、矩形、椭圆、三角形、箭头、曲线）配置各自不同的图标。
- 为尺子和辅助工具（文本框、直尺、量角器、几何吸附、套索自由选区、套索矩形、适应内容、识别文字等）配置各自不同的图标。
- 保持现有 outlined 图标风格不变。

### English Release Notes

**Editor toolbar icon differentiation**

- Assigned distinct icons to each brush (pen, pencil, brush, fountain pen, highlighter, calligraphy, crayon, watercolor, eraser).
- Assigned distinct icons to each geometry tool (line, rectangle, oval, triangle, arrow, curve).
- Assigned distinct icons to ruler and assistant tools (text box, ruler, protractor, geometry snap, lasso freeform, lasso rectangle, fit content, recognize text, etc.).
- Kept the existing outlined icon style unchanged.

## v1.0.300 (build 301 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**恢复 armeabi-v7a 并继续支持 16 KB 页面大小**

- 恢复 armeabi-v7a ABI 支持，扩大设备覆盖范围，兼容更多中低端设备。
- 保持 arm64-v8a + armeabi-v7a 双 ABI 配置，同时继续支持 Android 15+ 16 KB 页面设备。
- AGP 8.7.2 对未压缩 native 库自动 16 KB 对齐，useLegacyPackaging = false 保持启用。
- 在兼容性与安装包体积之间取得平衡。

### English Release Notes

**Restore armeabi-v7a and continue 16 KB page size support**

- Restored armeabi-v7a ABI support to broaden device coverage and support more entry-level devices.
- Kept dual ABI configuration for arm64-v8a and armeabi-v7a while continuing support for Android 15+ 16 KB page devices.
- AGP 8.7.2 automatically aligns uncompressed native libs to 16 KB with useLegacyPackaging = false remaining enabled.
- Balanced compatibility and package size.

## v1.0.299 (build 300 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**16 KB 页面对齐与安装包体积优化**

- 遵循 Android 官方指南，为 Android 15+ 16 KB 页面设备做好兼容准备。
- AGP 8.7.2 默认使用未压缩 native 库并自动 16 KB 对齐；显式配置 useLegacyPackaging = false。
- ABI 精简为 arm64-v8a，移除 armeabi-v7a，降低 APK 体积并符合 64 位设备趋势。
- Release APK 体积进一步下降。

### English Release Notes

**16 KB page alignment and package size optimization**

- Prepared compatibility for Android 15+ devices with 16 KB page size, per the official Android guide.
- AGP 8.7.2 uses uncompressed native libs with automatic 16 KB alignment; explicitly set useLegacyPackaging = false.
- Limited ABI to arm64-v8a, removed armeabi-v7a to reduce APK size and align with 64-bit device trends.
- Release APK size is further reduced.

## v1.0.298 (build 299 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**开放高级功能与会员权益精简**

- WebDAV 同步按钮文本简化为“同步”。
- 开放所有此前高级版专属功能给普通用户：WebDAV、密码保护、贴纸、自定义模板、高级笔刷等均可免费使用。
- 高级版会员权益精简为：无限创建笔记、无广告体验。
- 设置页会员权益卡片文案与视觉更精美。

### English Release Notes

**Unlock premium features and streamline membership benefits**

- Renamed WebDAV sync button text to “Sync”.
- All previously premium-only features are now free: WebDAV, password protection, stickers, custom templates, advanced brushes, etc.
- Premium membership is now limited to: create unlimited notes and enjoy an ad-free experience.
- Refined Premium benefits card text and visuals in Settings.

## v1.0.297 (build 298 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**编辑器页面菜单重构**

- 删除页面菜单中的专注模式与删除笔记入口。
- 新增“更多”子菜单，将打印、贴纸、密码收纳其中。
- “更多”入口位于视图下方，菜单层级更清晰。

### English Release Notes

**Editor page menu restructure**

- Removed Focus mode and Delete note entries from the page menu.
- Added a “More” submenu that groups Print, Stickers, and Password.
- Placed the “More” entry below Views for a clearer menu hierarchy.

## v1.0.296 (build 297 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**编辑器工具栏精简与打印文案优化**

- 页面菜单中“下载与打印”改为“打印”。
- 精简笔盒下方的快速预设按钮行，降低工具栏高度。
- 套索形状识别默认关闭，按需手动开启。

### English Release Notes

**Editor toolbar simplification and print label refinement**

- Renamed page menu label from “Download and print” to “Print”.
- Removed the quick-preset row below the brush box to reduce toolbar height.
- Lasso shape recognition is now off by default; enable manually when needed.

## v1.0.295 (build 296 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**设置精简与隐私合规完善**

- 移除设置页面的悬浮绘画按钮及相关功能。
- 备份与恢复区域优化布局，将备份、恢复、WebDAV 同步放在同一行。
- 全面完善隐私政策和用户协议，符合 Google Play 要求。

### English Release Notes

**Settings simplification and privacy compliance**

- Removed the floating ink button and related features from Settings.
- Optimized Backup & Restore layout: backup, restore, and WebDAV sync now sit in one row.
- Comprehensively updated Privacy Policy and User Agreement to meet Google Play requirements.

## v1.0.294 (build 295 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**修复数据库迁移问题**

- 修复新建笔记时的数据库完整性校验错误。
- 更新数据库版本至 v15，移除录音相关的表字段。

### English Release Notes

**Fix database migration issue**

- Fixed database integrity verification error when creating new notes.
- Updated database version to v15, removed audio-related table columns.

## v1.0.293 (build 294 - 2026-07-03)

### 涓枃鏇存柊璇存槑

**移除录音功能与安装包进一步瘦身**

- 移除编辑器录音按钮及相关功能，简化界面。
- 安装包体积进一步降低，按 ABI 拆分后单架构 APK 更小。
- 删除未使用的生物识别依赖，优化 ProGuard 规则。
- 移除录音权限（RECORD_AUDIO），减少权限声明。

### English Release Notes

**Remove audio recording and further APK size reduction**

- Removed audio recording button and related features from the editor.
- Further reduced APK size with per-ABI splits.
- Removed unused biometric dependency and optimized ProGuard rules.
- Removed RECORD_AUDIO permission declaration.

## v1.0.292 (build 293 - 2026-07-02)

### 涓枃鏇存柊璇存槑

**会员权益升级与安装包瘦身**

- 会员权益改为无限创建笔记和无广告，原会员功能全部免费开放。
- 普通用户可免费创建 3 个笔记，会员可无限制创建。
- 安装包体积大幅减小约 35%，内存占用优化。
- 移除 Firebase 死配置，清理无用资源文件。

### English Release Notes

**Membership revamp and APK size reduction**

- Premium benefits changed to unlimited note creation and ad-free; all former premium features are now free.
- Free users can create up to 3 notes; Premium members get unlimited notes.
- APK size reduced by ~35% with improved memory usage.
- Removed unused Firebase config and dead asset files.

## v1.0.291 (build 292 - 2026-07-02)

### 涓枃鏇存柊璇存槑

**编辑器架构重构**

- 将 8800+ 行的 EditorScreen.kt 拆分为 16 个内聚文件，大幅提升可维护性。
- 按功能域分离：对话框、工具栏、画布、笔画渲染、套索选择、导出等。
- 无功能变更，纯代码重构。

### English Release Notes

**Editor architecture refactor**

- Split the 8800+ line EditorScreen.kt into 16 cohesive files for better maintainability.
- Separated by domain: dialogs, toolbar, canvas, stroke rendering, lasso selection, export, etc.
- No functional changes — pure code refactor.

## v1.0.290 (build 291 - 2026-07-02)

### 涓枃鏇存柊璇存槑

**快捷草稿小组件、收藏筛选与最近打开排序**

- 新增快捷草稿桌面小组件，一键创建新草稿笔记，无需打开应用。
- 首页 Filter 菜单新增「仅看收藏」筛选，快速查看已收藏笔记。
- 首页排序新增「最近打开」模式，按笔记的最近查看时间排序。
- 新增 9 语言国际化文案（收藏、最近打开等）。

### English Release Notes

**Quick draft widget, favorites filter and recently-opened sort**

- Added a Quick Draft home-screen widget: tap once to create a new draft note without opening the app.
- Home filter menu now has a "Show favorites only" option to quickly view favorite notes.
- Home sort adds a "Recently opened" mode that orders notes by last viewed time.
- Added 9-language i18n strings for favorites and recently-opened features.

## v1.0.289 (build 290 - 2026-07-01)

### 涓枃鏇存柊璇存槑

**主题切换、跨页撤销、生物识别解锁与 WebDAV 自动同步**

- 新增主题切换功能，支持跟随系统、浅色、深色三种模式，设置中可选。
- 跨页撤销/重做现在按页保留，切换页面后 redo 历史不再丢失。
- 集成生物识别解锁，设置密码后可用指纹/面部识别快速解锁笔记。
- WebDAV 新增自动同步开关，每 30 分钟在后台自动同步笔记。
- 新增 9 语言国际化文案（主题、生物识别、自动同步等）。

### English Release Notes

**Theme switching, cross-page undo, biometric unlock and WebDAV auto-sync**

- Added theme switching: System, Light and Dark modes selectable in Settings.
- Cross-page undo/redo now retains redo history per page instead of clearing it on page switch.
- Integrated biometric unlock: after setting a note password, use fingerprint or face to unlock quickly.
- WebDAV adds an auto-sync toggle that syncs notes in the background every 30 minutes.
- Added 9-language i18n strings for theme, biometric and auto-sync features.

## v1.0.288 (build 289 - 2026-07-01)

### 涓枃鏇存柊璇存槑

**内容搜索、多排序、手写识别与录音笔记**

- 搜索范围扩展到笔记内文本贴纸内容，可按画布上的文字检索笔记。
- 首页新增按创建时间、标题排序模式，与原更新时间排序并列可选。
- 集成 ML Kit Digital Ink Recognition，套索选择笔迹后可一键识别为文本。
- 编辑器顶部新增录音按钮，支持录制、停止、播放、暂停，录音文件与笔记关联保存。
- 新增 9 语言国际化文案（录音、停止录音、播放音频、录音失败等）。

### English Release Notes

**Content search, multi-sort, handwriting OCR and audio notes**

- Search scope expanded to text sticker content inside notes, so canvas text is now searchable.
- Home screen adds sort by created time and by title alongside the existing updated-time sort.
- Integrated ML Kit Digital Ink Recognition: lasso-select strokes and recognize them as text in one tap.
- Editor top bar adds an audio recording button with record, stop, play and pause, saved alongside the note.
- Added 9-language i18n strings for recording, stop recording, play audio and recording failure.

## v1.0.287 (build 288 - 2026-06-28)

### 涓枃鏇存柊璇存槑

**PDF 批注渲染与书法笔锋增强**

- 接入 PdfRenderer，导入 PDF 后每页自动渲染为画布背景，可直接在 PDF 上手写批注。
- 翻页时自动切换对应的 PDF 背景图，多页 PDF 批注体验完整。
- Calligraphy 笔型渲染新增倾斜与方位角支持，笔倾斜越大笔画越宽，方位角决定笔锋偏移方向。
- 小组件渲染同步支持 Calligraphy 倾斜增强，预览效果与编辑器一致。

### English Release Notes

**PDF annotation rendering and calligraphy pen tilt**

- Integrated PdfRenderer so imported PDF pages render as canvas backgrounds for direct handwriting annotation.
- PDF background images switch automatically when turning pages for a complete multi-page annotation experience.
- Calligraphy tool now consumes tilt and azimuth data: greater tilt widens the stroke, azimuth sets the nib offset direction.
- Widget rendering syncs the same Calligraphy tilt enhancement so previews match the editor.

## v1.0.286 (build 287 - 2026-06-28)

### 涓枃鏇存柊璇存槑

**Firebase 基础配置接入**

- 将 Firebase 配置文件放入应用模块根目录，供 Google services Gradle 插件处理。
- 项目级 Gradle 增加 Google services 插件声明，应用级 Gradle 应用该插件。
- 应用级 Gradle 引入 Firebase BoM，为后续按需接入 Firebase 产品 SDK 做准备。
- 补充可用的 Google Maven 镜像仓库，解决当前环境无法连接 dl.google.com 时 Gradle 同步卡住的问题。

### English Release Notes

**Firebase base configuration**

- Placed the Firebase configuration file in the app module root for the Google services Gradle plugin.
- Declared the Google services plugin at the project level and applied it in the app module.
- Added the Firebase BoM in the app module so Firebase product SDKs can be added with compatible versions later.
- Added an accessible Google Maven mirror to avoid Gradle sync stalls when dl.google.com is unreachable in this environment.

## v1.0.285 (build 286 - 2026-06-28)

### 涓枃鏇存柊璇存槑

**书写手感中心、官方速记入口与资料批注增强**

- 书写诊断增加一键应用推荐配置，会自动调整压感、稳定器和触控笔防误触设置。
- 新增 Android 官方创建笔记入口支持，为触控笔、锁屏和系统级速记入口打好基础。
- PDF 导入策略明确标记为资料批注项目，后续课件、会议资料和图片批注会走更清晰的体验路径。
- 继续把新增能力收敛到策略层，减少具体页面继续膨胀，提升后续稳定性和可维护性。
- 新增 Manifest、导入策略和书写手感策略测试，防止系统入口、资料批注和推荐调参回归。

### English Release Notes

**Writing feel center, system note entry, and annotation import**

- Added one-tap recommended writing settings in diagnostics to tune pressure, stabilizer, and stylus palm guard behavior.
- Added Android system create-note entry support as a foundation for stylus, lock-screen, and system quick-note flows.
- Marked PDF imports as annotation projects so course files, meeting documents, and image annotation can follow a clearer path.
- Kept new behavior in policy-level code to reduce editor growth and improve future stability.
- Added tests for the manifest entry, import policy, and writing-feel recommendation behavior.

## v1.0.284 (build 285 - 2026-06-28)

### 涓枃鏇存柊璇存槑

**首页快速入口、书写诊断与高级版价值展示**

- 空首页新增快速草稿、课堂笔记、会议记录三个直接入口，新用户可以更快开始书写。
- 首页入口布局改为更稳的纵向展示，减少多语言文本导致的拥挤和遮挡。
- 书写诊断建议改为统一策略判断，会优先提示触控笔防误触、低延迟和稳定器设置。
- 高级版权益展示改为三张结果卡，突出书写手感、数据安全、分享导出三类核心价值。
- 新增策略测试覆盖首页入口、书写手感建议和高级版价值卡，减少后续回归。

### English Release Notes

**Home shortcuts, writing diagnostics, and Premium value cards**

- Added direct empty-home shortcuts for quick draft, class notes, and meeting notes so new users can start writing faster.
- Changed empty-home shortcut layout to a more stable vertical presentation to reduce crowding across languages.
- Moved writing diagnostic advice into a shared policy that prioritizes stylus palm rejection, low latency, and stabilizer tuning.
- Refined Premium benefits into three value cards focused on writing feel, data safety, and sharing/export results.
- Added focused policy tests for Home shortcuts, writing recommendations, and Premium value cards to reduce regressions.

## v1.0.283 (build 284 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**六阶段吸引力与体验收束**

- 修复最新更新说明的中文编码风险，确保更新弹窗优先显示可读内容。
- 新增首页吸引力策略，第一屏聚焦继续写、快速草稿和模板中心，弱化归档、回收站和设置等次要入口。
- 新增编辑器工具栏表面策略，默认只保留笔、橡皮、套索、文本和更多，笔刷细项只在展开后出现。
- 继续围绕手写体验、导入资料、整理复用、分享传播和高级版价值进行收口。
- 补充策略测试，防止首页、工具栏和更新历史再次变得杂乱或出现乱码。

### English Release Notes

**Six-stage attraction and experience focus**

- Kept the latest update announcement readable and protected it with a text-quality regression test.
- Added a Home attraction policy so the first screen prioritizes continue writing, quick draft, and the template center instead of secondary management entries.
- Added an editor tool-surface policy so the collapsed toolbar stays focused on pen, eraser, lasso, text, and more while brush details appear only after expansion.
- Continued narrowing the product around handwriting feel, document import, organization, sharing, and clear premium value.
- Added focused policy tests to keep Home, toolbar, and update-history copy from drifting back into clutter or mojibake.

## v1.0.282 (build 283 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**八阶段精简与稳定基础升级**

- 新增八阶段完善计划文档，覆盖编辑器拆分、分块画布、触控笔体验、导入标注、首页聚焦、多语言守护、高级权益收口和发行规范。
- 为大画布增加分块渲染预算策略，低内存和极端场景会使用更严格的可见块数量与预加载半径。
- 新增触控笔体验策略，统一压感灵敏度、笔尖预测和防误触半径，为后续更丝滑书写打好基础。
- 新增文件导入抗压策略，区分 PDF、文本、文档和不支持类型，并限制普通版与高级版的大文件边界。
- 收紧首页笔记卡片动作，归档和回收站只保留必要操作，减少干扰，并修复收藏标记乱码。
- 精简高级版权益展示，聚焦书写、导出打印、模板、分享、恢复和 WebDAV 等核心价值。

### English Release Notes

**Eight-stage polish and stability foundation**

- Added an eight-stage improvement plan covering editor splitting, tile canvas, stylus experience, import annotation, focused home, language guards, premium consolidation, and release discipline.
- Added tile-rendering budget fields so low-memory and extreme cases can use stricter visible tile and preload limits.
- Added a stylus experience policy for pressure sensitivity, tip prediction, and palm-rejection radius as a foundation for smoother writing.
- Added an import pressure policy that separates PDF, text, document, unsupported, and blocked files with free and premium limits.
- Focused note-card actions so archived and deleted notes only show necessary recovery or deletion actions, and fixed a garbled favorite marker.
- Consolidated premium benefit copy around the core value of writing, export/print, templates, sharing, recovery, and WebDAV.

## v1.0.281 (build 282 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**核心体验精简、稳定性与分享性能增强**

- 扩展统一性能预算，让大笔记、多页项目、低内存场景在缩略图、分享图和后台任务中使用更稳的渲染限制。
- 分享图生成改为预算驱动采样，保留首尾关键内容，同时限制超大项目的笔画和点数，减少卡顿与内存压力。
- 优化 1% 到 640% 极端缩放下的可见区域渲染边界，降低大画布重绘负担。
- 清理分享图社交模板里的英文硬编码文案，并补全多语言模板名称，减少语言切换后的错漏。
- 新增本轮工程计划文档和测试覆盖，方便后续继续拆分编辑页、优化平板和完善专业书写体验。

### English Release Notes

**Core polish, stability, and share performance**

- Extended the shared performance budget so large notes, multipage projects, and low-memory states use safer render limits across previews, share images, and background work.
- Moved share image generation to budget-driven sampling that keeps the first and last strokes while reducing work for very large projects.
- Improved visible rendering padding for extreme 1% to 640% zoom levels to reduce unnecessary canvas redraw pressure.
- Removed hardcoded English copy from social share card rendering and completed localized share-template names.
- Added an implementation plan and focused tests for the next editor split, tablet polish, and professional writing-experience work.

## v1.0.280 (build 281 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**书写内核、性能预算与横屏稳定性增强**

- 升级笔迹数据结构，新增触控笔时间、输入工具、倾斜和方位角数据位，旧项目数据仍可兼容打开。
- 新增统一性能预算策略，大笔记、多页项目、大图片和低内存场景会自动降低后台负载。
- 优化编辑器背景图和贴纸图解码策略，减少大图和大量贴纸进入具体页面时的内存压力。
- 抽出工具栏横屏/平板侧栏和自动折叠策略，专注模式不会被自动折叠逻辑打断。
- 修复具体页面菜单中下载与贴纸入口的硬编码中文，改为跟随当前语言显示。

### English Release Notes

**Writing core, performance budget, and landscape stability**

- Extended stroke data with stylus timing, input tool, tilt, and azimuth fields while keeping old project data compatible.
- Added a shared performance budget policy so large notes, multipage projects, large images, and low-memory states reduce background load.
- Improved editor background and sticker image decoding to reduce memory pressure from large images and many stickers.
- Moved landscape/tablet side toolbar and auto-collapse decisions into tested toolbar policy code.
- Fixed hardcoded Chinese labels for download and sticker entries in the editor menu.

## v1.0.279 (build 280 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**首页模板收束与文案质量增强**

- 清理首页组织弹窗里的乱码标签和硬编码示例，标签字段现在使用完整的多语言文案。
- 项目模板中心收束为更高频、更清晰的 12 个模板，覆盖学习、工作、灵感、计划、手账、截图标注和阅读摘录。
- 修复模板中心中文判断，中文环境会显示干净中文模板，其他语言继续显示英文模板文本。
- 新增源码文案质量测试，防止首页和首次引导再次出现乱码标记或直接写死的中文按钮文本。

### English Release Notes

**Home template cleanup and text quality hardening**

- Cleaned mojibake and hardcoded examples from the home organization dialog; tag fields now use localized strings.
- Reduced the template center to 12 clearer, high-frequency templates for study, work, ideas, planning, journaling, markup, and reading.
- Fixed Chinese template language detection so Chinese users see clean Chinese templates while other languages keep English template text.
- Added a source text quality test to keep Home and onboarding screens from reintroducing mojibake or hardcoded visible Chinese text.

## v1.0.278 (build 279 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**语言完整性、会员状态与搜索稳定性增强**

- 补齐法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文中模板、贴纸、下载打印、反馈等新增文案，减少界面混入英文或空文本的情况。
- 新增语言完整性测试，后续新增文案时会自动检查各语言是否缺项，降低多语言页面错乱风险。
- 统一高级版会员状态判定入口，区分本地终身、高级版年费、Google Play 终身和异常状态，减少会员显示不一致。
- 优化首页搜索策略，限制超长查询和重复词，支持按标题、文件夹、分组和标签组合检索，提升响应稳定性。

### English Release Notes

**Language completeness, Premium state, and search stability**

- Filled missing French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese copy for templates, stickers, download/print, feedback, and related flows.
- Added a language completeness test so future UI copy changes are checked across every supported language.
- Centralized Premium entitlement resolution for local lifetime, Google Play yearly, Google Play lifetime, and inconsistent states.
- Improved home search handling by bounding long queries, removing duplicate terms, and matching title, folder, group, and tags.

## v1.0.277 (build 278 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**系统栏层次与页面适配增强**

- 系统栏新增默认、顶部栏、编辑页和编辑页全屏模式，不同页面会使用更贴合自身层级的状态栏颜色。
- 暗色模式加入最低亮度保护，避免后续主题调整时状态栏再次变成纯黑或缺少层次。
- 具体项目页面和全屏书写状态会随路由自动切换系统栏模式，退出全屏后恢复编辑页观感。
- 小组件配置页也接入统一系统栏策略，独立 Activity 的顶部视觉与主应用保持一致。

### English Release Notes

**System bar depth and page-aware polish**

- System bars now support default, elevated top bar, editor, and editor fullscreen modes so each page gets a better-matched status bar color.
- Dark mode now has minimum-luminance protection to keep future theme changes from making the status bar pure black again.
- Project pages and fullscreen writing automatically switch system-bar modes with navigation state, restoring editor styling after fullscreen exits.
- The widget configuration activity now uses the same system-bar policy, keeping its top area consistent with the main app.

## v1.0.276 (build 277 - 2026-06-27)

### 涓枃鏇存柊璇存槑

**暗色模式系统栏显示优化**

- 暗色模式下状态栏改为使用 OneNotes 的暗色表面色，不再显示为完全漆黑。
- 状态栏和导航栏图标会根据明暗主题自动切换，提升顶部信息的可读性。
- 系统栏颜色策略统一收束到应用主题层，首页、设置、更新历史和具体页面保持一致。
- 新增系统栏颜色策略测试，避免后续主题调整再次让状态栏退回纯黑。

### English Release Notes

**Dark mode system bar polish**

- Dark mode now uses OneNotes' dark surface color for the status bar instead of a fully black system default.
- Status and navigation bar icons now switch with the app theme for better readability.
- System bar styling is centralized in the app theme so Home, Settings, Update history, and project pages stay consistent.
- Added system-bar color policy tests to prevent future theme changes from regressing to a pure-black status bar.

## v1.0.275 (build 276 - 2026-06-25)

### 涓枃鏇存柊璇存槑

**保存恢复提示与大画布流畅度优化**

- 具体页面自动保存失败后会进入明确的重试状态，减少用户误以为内容已经停止保存的情况。
- 保存状态显示逻辑集中管理，保存中、重试中和失败状态更稳定，后续调整不容易互相影响。
- 大画布可见区域绘制缓冲更克制，缩放时减少不可见笔迹的额外绘制，提升书写和移动画布的流畅度。
- 新增保存状态策略测试并更新渲染策略测试，继续降低核心书写页面的回归风险。

### English Release Notes

**Save recovery feedback and canvas smoothness**

- The editor now enters an explicit retry state after autosave failures, making recovery clearer while protecting note content.
- Save status display is centralized so saving, retrying, and failed states remain stable during future changes.
- Large-canvas rendering now uses tighter visible-area padding, reducing off-screen stroke work during zooming and panning.
- Added save-status policy tests and updated render-policy coverage to keep the core writing page safer from regressions.

## v1.0.274 (build 275 - 2026-06-25)

### 涓枃鏇存柊璇存槑

**自动保存稳态与笔迹跟手优化**

- 自动保存失败后的重试策略集中管理，采用有上限的指数退避，避免失败时频繁抢占书写线程。
- 短笔画的实时发布节奏更快，减少快速写字时笔迹跟手延迟。
- 具体页面内部的旧墨水面板正式收束为套索面板，旧项目保存的 Ink 状态会自动迁移。
- 新增保存重试、笔迹发布和工具栏迁移测试，降低后续调整核心书写体验时的回归风险。

### English Release Notes

**Autosave resilience and live ink smoothness**

- Autosave retry timing is now centralized with bounded exponential backoff so failed saves do not keep competing with live writing.
- Short live strokes publish more quickly, reducing visible lag during fast handwriting.
- The editor's old internal ink panel is now folded into the lasso panel, with saved Ink state migrated automatically.
- Added tests for save retry timing, live ink publishing, and toolbar migration to reduce regressions in the writing flow.

## v1.0.273 (build 274 - 2026-06-25)

### 涓枃鏇存柊璇存槑

**工具栏收束与书写优先优化**

- 具体页面工具栏默认打开笔盒面板，让用户优先看到笔刷、橡皮、文本框、量尺和常用书写工具。
- 颜色、项目颜色和粗细滑杆并入笔盒面板，删除顶部独立墨水入口，减少工具栏来回切换。
- 旧项目保存的墨水面板状态会自动落到套索操作入口，避免升级后顶部按钮状态不一致。
- 书写结束后的后台保存冷却时间加长，连续书写时更优先保证笔迹跟手和画布流畅。

### English Release Notes

**Toolbar focus and writing-priority tuning**

- The editor toolbar now opens on the brush box by default so pens, eraser, text box, rulers, and writing tools are immediately visible.
- Ink colors, project colors, and width controls now live inside the brush box, removing the separate top-level ink button.
- Previously saved ink-panel state now maps to the lasso entry so upgraded notes keep a consistent toolbar highlight.
- Background saves wait longer after live writing, giving handwriting latency and canvas smoothness higher priority during continuous input.

## v1.0.272 (build 273 - 2026-06-24)

### 涓枃鏇存柊璇存槑

**分享图精简与设置页收束**

- 分享图弹窗移除智能文案编辑区，减少开关、输入框和生成分支，让分享流程更直接。
- 分享图样式收敛为学习总结、会议纪要、手账封面、知识卡片、极简和故事卡等精选模板。
- 旧版分享样式偏好会自动回落到精选默认模板，避免升级后出现未选中或显示异常。
- 设置页高级版权益默认只展示核心项目，并移除已精简的智能分享文案权益说明。

### English Release Notes

**Share image cleanup and Settings focus**

- Removed the smart-caption editor from the share-image dialog to reduce toggles, text fields, and generation branches.
- Focused share-image choices on curated templates: study summary, meeting minutes, journal cover, knowledge card, minimal, and story.
- Old share-style preferences now fall back to the curated default to avoid empty selection states after upgrade.
- Premium benefits in Settings now show fewer core items by default and no longer advertise the removed smart-caption option.

## v1.0.265 (build 266 - 2026-06-22)

### 涓枃鏇存柊璇存槑

**冗余功能清理与核心体验收拢**

- 清理首页已经不可达的创作教练快照、隐藏筛选和隐藏排序逻辑，减少列表加载时的无用状态计算。
- 删除旧版项目模板中心和旧模板列表残留，保留当前实际使用的模板中心，降低乱码残留和维护成本。
- 清理具体页面已经没有入口的墨迹地图、墨迹热力图、构图线、演示聚光和复习路径渲染层，让画布渲染链路更轻。
- 保留书写、套索、贴纸、量尺、视图标记、回放等核心能力，同时减少菜单和画布状态的复杂度。

### English Release Notes

**Redundant feature cleanup and core experience focus**

- Removed unreachable Home creative-coach snapshot, hidden filters, and hidden sort logic to reduce unnecessary list-state work.
- Deleted the legacy project-template center and old template list while keeping the active template center implementation.
- Removed unused editor view layers including ink map, ink heat map, composition guides, presentation spotlight, and review path overlays.
- Kept core writing, lasso, stickers, rulers, view marks, and replay features while reducing menu and canvas state complexity.

## v1.0.264 (build 265 - 2026-06-18)

### 涓枃鏇存柊璇存槑

**小组件预览与图片内存保护增强**

- 桌面小组件现在会安全渲染项目里的贴纸和文本框，项目贴到桌面后更接近真实页面内容。
- 小组件预览会把贴纸、文本框和笔迹一起纳入内容边界，减少内容只显示局部或显得过小的问题。
- 贴纸图片解码增加文件大小、像素数量和采样尺寸保护，损坏或过大的图片会被跳过，不影响小组件刷新。
- 通用图片预览缓存增加来源大小和像素边界，降低大图、异常图在首页、设置页和预览场景里的内存压力。

### English Release Notes

**Widget preview and image memory protection**

- Desktop widgets now safely render note stickers and text boxes so pinned notes look closer to the real canvas.
- Widget previews include stickers, text boxes, and ink in the content bounds to reduce cropped or overly tiny previews.
- Sticker bitmap decoding now has file-size, pixel-count, and sample-size safeguards so damaged or oversized images are skipped safely.
- Shared sampled-image preview caching now applies stronger source-size and pixel limits to reduce memory pressure across Home, Settings, and preview surfaces.

## v1.0.263 (build 264 - 2026-06-18)

### 涓枃鏇存柊璇存槑

**残留功能清理与核心体验收拢**

- 删除每日一言的执行链路、仓库绑定和首页残留判断，减少首页加载与设置状态的无用工作。
- 移除本地 7 天试用的残留接口和状态字段，高级版状态更聚焦 Google Play 购买和本地激活。
- 删除表格/图表结构化墨迹识别的残留弹窗、识别器和 ViewModel 方法，具体页面菜单更稳定、更轻。
- 更新新手引导，去掉过期功能说明，改为突出快速草稿、模板、套索、文本框、归档回收站、分享和备份。
- 精简高级版权益说明，保留用户能直接找到和感知的笔刷、纸张、分享、密码、WebDAV、悬浮速记和手势等权益。

### English Release Notes

**Residual feature cleanup and core experience focus**

- Removed the daily quote execution path, repository binding, and remaining home-state checks to reduce unnecessary home and settings work.
- Removed leftover local 7-day trial interfaces and state fields so Premium status focuses on Google Play purchases and local activation.
- Removed residual structured table/chart ink recognition dialogs, recognizer code, and ViewModel methods for a lighter and steadier editor.
- Updated onboarding copy to remove outdated feature mentions and focus on quick drafts, templates, lasso, text boxes, archive/recycle bin, sharing, and backup.
- Simplified Premium benefit text to keep visible, user-facing benefits such as brushes, paper, sharing, password tools, WebDAV, floating capture, and gestures.

## v1.0.262 (build 263 - 2026-06-18)

### 涓枃鏇存柊璇存槑

**产品减法与核心书写体验聚焦**

- 首页移除每日一言展示和设置入口，让用户更快进入笔记列表、新建和继续书写。
- 具体页面墨水菜单精简低频实验入口，保留清页、删除选区、笔迹优化和杂点清理等更直接的书写维护能力。
- 具体页面视图菜单移除墨迹地图、热力图、构图辅助、演示聚光和复盘路径等低频开关，减少菜单拥挤和误触。
- 保留分享、下载、获取、贴纸、页面跳转、多页查看、视图标记和书写诊断等与实际使用更相关的能力。

### English Release Notes

**Product simplification and focused handwriting flow**

- Removed the daily quote card and settings entry so the home page opens closer to notes, creation, and continued writing.
- Simplified the editor ink menu by removing low-frequency experimental entries while keeping clear page, delete selection, ink optimization, and stray-ink cleanup.
- Removed low-frequency view toggles such as ink map, heat map, composition guides, presentation spotlight, and review path to reduce crowding and accidental taps.
- Kept practical flows such as sharing, downloading, importing, stickers, page jump, multi-page overview, view marks, and writing diagnostics.

## v1.0.261 (build 262 - 2026-06-18)

### 涓枃鏇存柊璇存槑

**核心书写体验与低延迟写感增强**

- 围绕手写笔记软件的核心吸引力继续优化：第一笔跟手、工具少打扰、写完内容稳定保存。
- 具体页面触控笔面板新增一键写感优化，可快速切换到更适合低延迟书写的压感和稳笔组合。
- 写感优化不会自动开启仅触控笔模式，避免手机用户或无触控笔用户无法继续手指书写。
- 预设状态会跟随当前工具记忆保存，减少每次进入项目后反复调整书写参数。

### English Release Notes

**Core writing feel and low-latency tuning**

- Focused the editor on the core appeal of handwriting apps: responsive first ink, fewer tool interruptions, and stable saving.
- Added a one-tap writing-feel optimization in the stylus panel for a lower-latency pressure and stabilization setup.
- The preset does not force stylus-only mode, so phone and finger-writing users can keep drawing normally.
- The tuned feel is remembered with the current tool settings to reduce repeated adjustment after reopening notes.

## v1.0.260 (build 261 - 2026-06-18)

### 涓枃鏇存柊璇存槑

**套索工具复制与具体页面稳定性增强**

- 套索工具在有选区时新增复制按钮，可直接复制笔迹、贴纸和文本框选区。
- 复制后的内容会自动偏移并保持选中，方便继续移动、缩放或旋转。
- 复制操作增加笔画、贴纸和点数量上限，避免超大选区误操作影响具体页面稳定性。
- 文本框和贴纸颜色统一做不透明安全处理，减少异常数据导致的显示问题。

### English Release Notes

**Lasso duplication and editor stability**

- Added a duplicate action to lasso selections for ink, stickers, and text boxes.
- Duplicated content is offset and selected automatically so it can be moved, scaled, or rotated immediately.
- Added stroke, sticker, and point-count limits to protect editor stability when duplicating large selections.
- Sanitized text-box and sticker colors as opaque values to reduce rendering issues from bad data.

## v1.0.259 (build 260 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**具体页面工具栏现有工具增强**

- 套索工具栏在有选区时新增适配选区快捷操作，可快速把选中内容居中显示。
- 修复只选中贴纸时套索移动、缩放、旋转命中不稳定的问题。
- 工具栏画笔颜色、预设颜色和纸张颜色统一做不透明安全化处理，避免透明色导致笔迹或纸张显示异常。

### English Release Notes

**Existing editor toolbar tool improvements**

- Added a fit-selection shortcut to the lasso toolbar so selected content can be centered quickly.
- Fixed lasso move, scale, and rotate hit testing when only stickers are selected.
- Sanitized toolbar brush, preset, and paper colors to opaque colors to avoid invisible ink or abnormal paper rendering.

## v1.0.258 (build 259 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**调色板与长按图形标准化三轮迭代**

- 自定义画笔颜色和纸张颜色弹窗新增调色板，可直接点选常用颜色，也保留十六进制输入。
- 单指长按已有手绘形状后可确认转化为标准化图形，确认后自动进入套索选中状态。
- 长按已经标准化的几何图形会直接选中，可继续移动、缩放、旋转。
- 切页或退出套索时会清理待确认状态，减少长按转化流程中的状态残留。

### English Release Notes

**Palette and long-press shape standardization**

- Added palette swatches to custom brush and paper color dialogs while keeping hex input available.
- Long-pressing a hand-drawn shape can now ask to standardize it, then automatically selects it with lasso controls.
- Long-pressing an already standardized geometry shape selects it directly for moving, scaling, and rotating.
- Cleared pending shape actions when changing pages or leaving lasso mode to reduce stale interaction state.

## v1.0.257 (build 258 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**具体页面书写流畅度增强**

- 为实时活动笔迹增加独立小型路径缓存，减少同一帧内重复生成绘制路径。
- 优化压感笔迹绘制策略，只有明显压感变化的笔迹才逐段绘制，轻微压力抖动会走缓存路径。
- 长笔画采用自适应发布频率，减少长时间书写时复制整条笔迹点列表带来的主线程压力。
- 保持触控笔压感、笔锋和笔尖预测效果，同时提升复杂页面持续书写的稳定性。

### English Release Notes

**Editor writing smoothness improvements**

- Added a small dedicated path cache for the live active stroke to avoid rebuilding the same path within stable frames.
- Optimized pressure rendering so only strokes with meaningful pressure variation use segment rendering while minor pressure noise uses cached paths.
- Added adaptive active-stroke publishing for long strokes to reduce main-thread pressure from repeatedly copying large point lists.
- Preserved stylus pressure, stroke tapering, and tip prediction while improving sustained writing stability on complex pages.

## v1.0.256 (build 257 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**具体页面现有功能稳定性增强**

- 优化贴纸图片加载触发条件，移动或旋转贴纸时不再重复触发整组图片加载。
- 加强贴纸和文本框插入安全边界，过滤异常坐标、异常尺寸和过长文本。
- 套索移动、缩放、旋转贴纸时增加坐标保护，降低极端拖拽导致项目数据异常的风险。
- 多页纸张切页前同步当前页笔迹快照，提升多页项目保存和切换稳定性。

### English Release Notes

**Editor feature stability improvements**

- Reduced sticker image reloads by keying loads to image path and display size instead of every sticker movement.
- Hardened sticker and text-box insertion by sanitizing coordinates, size, and overly long text.
- Added coordinate protection when lasso-moving, scaling, or rotating stickers to reduce bad project data from extreme drags.
- Synced the current page stroke snapshot before paged-paper navigation for steadier saving and page switching.

## v1.0.255 (build 256 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**书写输入与大画布渲染增强**

- 为具体页面历史触控采样增加单次处理上限，避免部分设备一次性回放过多点位导致书写卡顿。
- 压感笔迹绘制加入可视区域裁剪，缩放或移动大画布时减少不可见线段的绘制开销。
- 继续保持触控笔历史点补偿、压感平滑和笔尖预测，让书写反馈更稳定、更跟手。

### English Release Notes

**Writing input and large-canvas rendering**

- Added a per-event limit for historical touch samples on the editor page to avoid stalls when devices replay too many points at once.
- Clipped pressure-sensitive stroke segments to the visible viewport to reduce off-screen rendering work on large canvases.
- Preserved stylus historical-point compensation, pressure smoothing, and tip prediction for steadier writing feedback.

## v1.0.254 (build 255 - 2026-06-17)

### 涓枃鏇存柊璇存槑

**具体页面稳定性与书写体验增强**

- 优化具体页面实时书写采样，降低近距离重复点和压感尖刺带来的抖动。
- 笔画结束后增加轻量清理，保留笔锋变化的同时减少无意义点位，提升保存和渲染稳定性。
- 优化大画布贴纸绘制，只处理当前可见区域附近内容，降低复杂项目的绘制开销。
- 继续增强缓存清理、诊断日志清理和 Google Play 更新流程的异常兜底。

### English Release Notes

**Editor stability and writing experience**

- Improved live ink sampling on the editor page to reduce jitter from duplicate nearby points and pressure spikes.
- Added lightweight finished-stroke cleanup that keeps pressure detail while reducing unnecessary points for steadier saving and rendering.
- Optimized large-canvas sticker rendering by drawing only content near the visible viewport.
- Further hardened cache cleanup, diagnostic log pruning, and Google Play update error handling.

## v1.0.253 (build 254 - 2026-06-16)

### 涓枃鏇存柊璇存槑

**跨页面稳定性与缓存性能增强**

- 增强 Google Play 更新流程的异常兜底，更新完成和恢复更新时不会因 Play 服务异常影响软件使用。
- 悬浮截图和快速捕获截图的缓存清理改为安全清理，减少文件系统异常导致的页面卡顿或失败。
- 低内存缓存清理和诊断日志清理增加扫描上限与删除容错，降低缓存过多时的后台开销。

### English Release Notes

**Cross-page stability and cache performance**

- Hardened Google Play update completion and resume handling so Play service errors do not interrupt the app.
- Made floating screenshot and quick-capture cache cleanup safer against file-system edge cases.
- Added scan limits and delete safeguards to low-memory cache cleanup and diagnostic log pruning to reduce background overhead.

## v1.0.252 (build 253 - 2026-06-16)

### 涓枃鏇存柊璇存槑

**Google Play 更新检测**

- 移除官网 JSON 远程更新配置，改为使用 Google Play 官方更新检测。
- 当 Google Play 检测到新版本时，软件会询问用户是否更新，确认后进入 Google Play 更新流程。
- 如果 Play 更新流程不可用，会兜底跳转到 OneNotes 的 Google Play 商店页面。

### English Release Notes

**Google Play update check**

- Removed the website JSON remote update configuration and switched to official Google Play update checks.
- When Google Play reports a newer version, OneNotes asks the user before starting the Play update flow.
- If the Play update flow is unavailable, OneNotes falls back to the Google Play store listing.

## v1.0.251 (build 252 - 2026-06-16)

### 涓枃鏇存柊璇存槑

**官网远程更新提示**

- 新增官网远程更新配置检查，应用会从 tourisain.cn 拉取最新版本信息。
- 当官网配置的版本号高于当前安装版本时，会弹出更新提示，用户可选择立即更新或稍后再说。
- 远程更新检查增加超时、大小限制、可信域名校验和静默失败处理，官网异常不会影响软件启动和书写。

### English Release Notes

**Official remote update prompt**

- Added an official remote update check that reads the latest OneNotes version from tourisain.cn.
- When the remote version is newer than the installed version, users can update now or choose later.
- The update check is guarded by timeouts, payload limits, trusted host validation, and silent failure handling so writing remains unaffected.

## v1.0.250 (build 251 - 2026-06-14)

### 涓枃鏇存柊璇存槑

**分享图与小组件稳定性增强**

- 增强分享图生成后的缓存目录创建、PNG 写入校验和旧文件清理容错，减少缓存异常导致的分享失败。
- 小组件渲染对无法解密或损坏的笔迹数据增加兜底处理，异常项目不会导致桌面小组件刷新失败。
- 首页、归档、回收站和搜索列表对损坏的加密字段增加安全降级，单个异常项目不会拖垮整个页面。
- 继续收紧跨页面资源处理边界，降低外部数据、缓存文件和低内存状态带来的闪退风险。

### English Release Notes

**Share image and widget stability**

- Hardened share image cache creation, PNG write validation, and old-file cleanup so cache issues are handled more gracefully.
- Widget rendering now falls back safely when preview or stroke data cannot be decrypted or parsed.
- Home, archive, trash, and search lists now degrade safely when encrypted fields are damaged, so one bad note cannot break the whole page.
- Tightened resource handling across pages to reduce crash risk from external data, cache files, and low-memory conditions.

## v1.0.249 (build 250 - 2026-06-14)

### 涓枃鏇存柊璇存槑

**全页面外部输入与预览稳定性增强**

- 增强外部分享图片进入软件时的安全处理，压缩失败后的原图复制增加大小上限和分段写入，降低超大图片导致的内存与存储压力。
- 首页快速草稿缩略图解码增加异常兜底，损坏图片、被清理的文件或低内存解码失败时不会影响首页继续显示。
- 设置页备份恢复读取改为有限读取，异常大文件会被提前拦截，避免设置页面被大文件拖慢或拖崩。

### English Release Notes

**App-wide external input and preview stability**

- Hardened shared images entering OneNotes from other apps by adding a raw-copy size cap and chunked writes when compression fallback is needed.
- Added best-effort decoding for quick-draft thumbnails so damaged images, deleted files, or low-memory decode failures do not interrupt Home.
- Changed Settings backup import to bounded text reading so oversized files are rejected early instead of being loaded fully into memory.

## v1.0.248 (build 249 - 2026-06-14)

### 涓枃鏇存柊璇存槑

**书写稳定性与每日一言无缝刷新**

- 增强具体项目页面的实时书写防护，对异常坐标、异常压力值和超长单笔进行轻量净化，减少异常设备事件造成的卡顿或崩溃风险。
- 优化贴纸图片导入流程，增加图片尺寸校验、像素上限和稳定回收，降低超大或损坏图片进入画布时的内存压力。
- 每日一言刷新时保留当前内容并平滑过渡到新内容，刷新期间不再切换按钮文本，减少首页闪动和布局抖动。

### English Release Notes

**Writing stability and seamless daily quote refresh**

- Hardened the editor writing path by sanitizing abnormal coordinates, pressure values, and unusually long single strokes to reduce device-event related jank or crashes.
- Improved sticker image import with dimension validation, a pixel cap, and reliable bitmap recycling to lower memory pressure from oversized or damaged images.
- Daily quote refresh now keeps the current line visible and crossfades into the new line while the refresh button stays layout-stable.

## v1.0.247 (build 248 - 2026-06-14)

### 涓枃鏇存柊璇存槑

**多页面稳定性与资源处理加固**

- 增强运行期缓存清理的容错能力，低内存或异常文件状态下不会影响首页、设置页和具体项目页面继续运行。
- 优化缩略图、贴纸、模板背景和悬浮按钮图标的图片解码与导入保护，减少超大图片或损坏图片导致的崩溃风险。
- 加固画布文本框的换行与预览绘制逻辑，提升不同页面预览、导出和编辑时的稳定性。

### English Release Notes

**Multi-page stability and resource hardening**

- Made runtime cache trimming fully best-effort so low-memory cleanup or abnormal cache files do not interrupt Home, Settings, or Editor pages.
- Hardened thumbnail, sticker, template-background, and floating-button icon decoding/import paths to reduce crashes from oversized or damaged images.
- Strengthened canvas text-box wrapping and preview rendering for more stable editing, previews, and exports.

## v1.0.246 (build 247 - 2026-06-13)

### 涓枃鏇存柊璇存槑

**具体页面新增文本框工具**

- 在具体页面工具栏的橡皮后面新增文本按钮，可在当前纸张上生成文本框。
- 文本框支持保存、重新打开显示、跟随画布缩放，并可被套索选择后移动、缩放和旋转。
- 首页缩略图和项目导出图片/PDF 已支持显示文本框内容，减少预览与实际内容不一致。

### English Release Notes

**Canvas text box tool**

- Added a Text button after Eraser in the editor toolbar to place text boxes on the current paper.
- Text boxes are saved with the project, reopen correctly, scale with the canvas, and work with lasso move, scale, and rotate.
- Home thumbnails and project image/PDF export now render text boxes so previews match the canvas.

## v1.0.245 (build 246 - 2026-06-13)

### 涓枃鏇存柊璇存槑

**统一弹窗视觉与缓存性能优化**

- 软件内主要弹窗统一接入 OneNotes 风格容器，圆角、色彩、文字层级和宽度限制更一致。
- 首页、设置、具体项目、更新历史、小组件尺寸等弹窗保持相同视觉语言，减少不同页面之间的割裂感。
- 运行期缓存清理覆盖更多可重新生成的分享图、快速草稿、外部分享草稿和浮窗截图缓存，降低长时间使用后的内存与存储压力。

### English Release Notes

**Unified dialog styling and cache performance polish**

- Main dialogs now use a unified OneNotes-style container with consistent shape, colors, text hierarchy, and width limits.
- Home, Settings, Editor, Update History, and widget-size dialogs now share the same visual language.
- Runtime cache trimming now covers more regenerable share, quick-draft, shared-draft, and floating-capture caches to reduce long-session pressure.

## v1.0.244 (build 245 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**开屏时长与首页首帧稳定性优化**

- 默认图标开屏最短显示时间调整为原时长的60%，进入软件更轻快。
- 首页增加首批数据加载完成标记，进入首页前保持稳定背景，减少数据首次刷新导致的闪一下。
- 首页数据继续通过 Room Flow 和后台任务刷新，避免把项目读取、快捷入口刷新等工作放到主线程。

### English Release Notes

**Splash timing and first Home frame stability**

- Reduced the default icon splash minimum duration to 60% of the previous timing.
- Added a first-load gate on Home so the first frame stays visually stable while the first data snapshot arrives.
- Home data refresh continues to use Room Flow and background work instead of blocking the main thread.

## v1.0.243 (build 244 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**首页菜单文案与排序精简**

- 首页排序菜单删除 Open count 项，仅保留最近更新排序，减少菜单干扰。
- 首页筛选菜单中的日期筛选、清除日期筛选、开始日期、结束日期和错误提示补齐多语言文案。
- 日期筛选弹窗在中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文下会显示对应语言。

### English Release Notes

**Home menu wording and sorting cleanup**

- Removed the Open count item from the Home sort menu, leaving the cleaner recent-update sort.
- Added localized labels for Date filter, Clear date filter, Start date, End date, and date-format errors.
- The date filter dialog now displays matching text in Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.

## v1.0.242 (build 243 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**套索贴纸、密码查看与备份恢复优化**

- 套索现在可以选中贴纸，并支持与笔迹一起移动、缩放、旋转和删除。
- 多页项目中的贴纸选择与显示按当前页处理，减少跨页误选和误显示。
- 视图菜单中的书写诊断及弹窗内容增加按语言覆盖，中文环境会显示中文文案。
- 项目密码设置和备份密码设置增加查看密码按钮，便于用户确认输入。
- 备份恢复改为后台解析并分块写入数据库，提升大备份恢复速度与稳定性。
- 增强保存后的刷新稳定性，避免返回首页时最新项目状态延迟显示。

### English Release Notes

**Lasso stickers, password visibility, and backup restore polish**

- Lasso can now select stickers and move, scale, rotate, or delete them together with ink.
- Sticker selection and rendering in paged projects now stay scoped to the current page.
- Writing diagnostics labels and dialog content now use language-specific overrides, including Chinese.
- Project password setup and backup password setup now include password visibility toggles.
- Backup restore now parses off the main path and writes notes in chunks for better large-backup performance.
- Improved save and refresh stability so the latest project state is less likely to appear delayed on Home.

## v1.0.241 (build 242 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**大文件抗压、排序筛选与分享图优化**

- 增强大文件导入抗压能力，超大文档会提前拦截，模板背景导入会限制解码尺寸，降低内存峰值。
- 首页初始状态不再默认显示空页面，减少进入首页时因数据加载导致的闪烁观感。
- 首页排序新增打开次数，按项目实际打开次数从高到低排序，并从筛选移动到排序菜单。
- 首页筛选新增日期筛选弹窗，可按更新时间范围快速查看符合日期条件的项目。
- 分享项目图改为透明底 PNG，去掉最底层背景图，只保留完整的内容、文案与克制 OneNotes 标识。
- 本地数据库新增打开次数字段并随打开项目自动累加，备份恢复也会保留该数据。

### English Release Notes

**Large-file resilience, sorting, filtering, and share image polish**

- Improved large-file resilience by rejecting oversized document imports early and bounding template background decoding.
- Reduced the first-home visual flash by avoiding a default empty-home state before data arrives.
- Added Open count sorting on Home, ordered by the real number of project opens from high to low.
- Added a Home date filter dialog for filtering projects by updated-date range.
- Share images now export as transparent PNG files without the lowest background layer, keeping only the designed content and subtle OneNotes mark.
- Added a persisted open-count field with migration support, automatic increments, and backup/restore preservation.

## v1.0.240 (build 241 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**启动、设置空间与提示体验优化**

- 默认图标开屏页最短显示时间调整为现有时长的 60%，减少等待感并保留稳定过渡。
- 设置页桌面小组件区域精简为标题、添加小组件和刷新小组件两个按钮，减少页面占用空间。
- 新安装用户默认关闭首页文件夹与分组，可在设置中手动开启。
- Google Play 恢复购买等设置页提示显示后会立即消费状态，避免重新进入设置页重复弹出。
- 每日一言普通用户每日刷新次数从 1 次提高到 3 次，高级版会员保持无限刷新。

### English Release Notes

**Startup, settings, and prompt polish**

- Reduced the default icon splash minimum duration to 60% of the previous value while keeping a stable transition.
- Simplified the Settings widget section to the title plus Add widget and Refresh widgets buttons.
- New installs now keep Home folders and groups off by default, with the switch still available in Settings.
- Settings messages such as restored Google Play purchases are consumed after display so they do not repeat on re-entry.
- Free users can now refresh the daily quote 3 times per day, while Premium users keep unlimited refreshes.

## v1.0.239 (build 240 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**每日一言与文件导入增强**

- 高级版会员每日一言改为无限刷新，普通用户仍保持每日一次刷新。
- 增强获取文件功能，支持更稳定地导入 TXT、Markdown、CSV、RTF、PDF、DOC、DOCX 与 ODT 文档。
- 优化文件导入的编码识别，提升中文文本、旧文档和不同来源文件的读取成功率。
- 压缩类文档改为按条目读取并限制最大读取量，降低大文件导入时的内存占用和卡顿风险。

### English Release Notes

**Daily quote and file import improvements**

- Premium users can now refresh the daily quote without a daily limit while free users keep one refresh per day.
- Improved file acquisition with more stable imports for TXT, Markdown, CSV, RTF, PDF, DOC, DOCX, and ODT documents.
- Enhanced text encoding detection for Chinese text, legacy documents, and files from different sources.
- Zip-based documents now read only the needed entries with bounded size limits to reduce memory pressure during imports.

## v1.0.238 (build 239 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**每日一言精简与书写手感优化**

- 首页每日一言卡片删除来源、标题和说明，只保留一句话与刷新按钮。
- 提升默认笔迹稳定度，收笔时增加轻量二次平滑，减少小字抖动。
- 增强触控笔压感曲线，轻压更细、重压更粗，笔锋变化更明显。
- 压感笔迹绘制跳过极短不可见线段，降低大笔记重绘开销。

### English Release Notes

**Daily quote cleanup and handwriting feel improvements**

- Simplified the home daily quote card to only the sentence and refresh button.
- Raised default stroke stabilization and added lightweight final smoothing to reduce small-handwriting jitter.
- Improved stylus pressure response so light pressure is thinner and firm pressure creates stronger stroke tips.
- Skipped invisible tiny pressure-rendered segments to reduce redraw cost in larger notes.

## v1.0.237 (build 238 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**首页问题反馈入口**

- 首页顶栏菜单在更新历史下方新增问题反馈入口。
- 问题反馈弹窗支持选择 tourisian@163.com 或 grllq458@gmail.com 两个邮箱。
- 用户确认同意后会跳转系统邮件应用，并自动填入 OneNotes 版本信息，便于反馈问题。

### English Release Notes

**Home feedback entry**

- Added a Feedback entry below Update History in the home top bar menu.
- The feedback dialog lets users choose tourisian@163.com or grllq458@gmail.com.
- After confirmation, OneNotes opens the system mail app and pre-fills version information for easier issue reports.

## v1.0.236 (build 237 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**每日一言刷新与开屏体验优化**

- 每日一言在同一天内手动刷新时会避开当前显示句子，减少刷新后看起来没有变化的问题。
- 默认图标开屏页最短显示时间再次延长一倍，让启动过渡更稳定。
- 默认图标开屏去掉图标外侧圆形容器，直接展示软件图标和名称。
- 禁用系统短启动预览，并在 Android 12 及以上隐藏系统短开屏图标，避免出现两个不同长度的开屏显示。

### English Release Notes

**Daily quote refresh and splash polish**

- Manual daily quote refresh now avoids the currently displayed line during the same day.
- The default icon splash minimum display time is doubled again for a steadier launch transition.
- The default icon splash no longer wraps the app icon in a circular container.
- Disabled the short system launch preview and hid the Android 12+ system splash icon to avoid two separate splash presentations.

## v1.0.235 (build 236 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**多语言每日一言与文档获取**

- 每日一言本地语料改为按当前软件语言筛选，支持中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文。
- 具体项目页面菜单在下载下方新增获取入口，可导入 txt、pdf 和 Word 文档并生成手写内容。
- 文档获取支持自动分页和拼接到单页两种方式，长内容会按页拆分，多页内容自动进入分页项目。
- 普通用户每天可使用一次文档获取，高级版会员不限制次数；成功导入后才消耗免费次数。
- 文档解析加入读取大小、导入页数和文本长度上限，降低大文件导入时的内存压力。

### English Release Notes

**Multilingual daily quotes and document acquire**

- Local daily quote seeds now filter by the current app language across Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.
- Added an Acquire entry below Download in the project menu for importing txt, pdf, and Word documents into handwritten content.
- Document acquire supports automatic pages and stitching into one page; long content is split into pages and inserted as a paged project.
- Free users can use document acquire once per day, while Premium members have unlimited uses. The free quota is consumed only after a successful import.
- Added file size, page count, and text length limits to reduce memory pressure during large document imports.

## v1.0.234 (build 235 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**贴画、模板中心、开屏和每日一言增强**

- 新增图钉、皇冠、火焰、咖啡、书本、云朵、目标和胶带等贴画，继续以完整 PNG 图片方式插入画布。
- 项目模板中心新增专注自习、课后整理、论文批注、实验记录、周计划、旅行手账、健身记录、财务预算、客户沟通、课程备课、灵感看板和面试准备等模板。
- 带默认图标的开屏页最短显示时间延长为原来的两倍，启动检查期间会显示 OneNotes 默认图标和名称。
- 新增约 2MB 的本地每日一言语料文件，默认先从本地读取文本和作者，网络免费 API 仅作为本地不可用时的补充。
- 每日一言本地读取采用轻量扫描，避免把完整 2MB 文件长期放进内存。
- 在首页进入已归档或回收站后，返回键会先回到首页，不再直接触发退出软件。

### English Release Notes

**Sticker, template, splash, and daily quote improvements**

- Added pin, crown, flame, coffee, book, cloud, target, and tape stickers, still inserted as complete PNG images.
- Expanded the project template center with focus study, lecture review, paper annotation, lab record, weekly plan, travel journal, fitness log, budget plan, client notes, lesson prep, creative board, and interview prep templates.
- The default-icon splash screen now stays visible for twice the previous minimum time while launch checks complete.
- Added an approximately 2 MB local daily quote seed file; quotes and authors are loaded locally first, with the free network API used only as fallback.
- Local quote reading uses lightweight scanning instead of keeping the whole 2 MB file in memory.
- Pressing Back from Archived or Recycle Bin now returns to Home first instead of exiting the app.

## v1.0.233 (build 234 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**更多贴画、方向调整与完整缩略图**

- 新增旗标、闪光、灯泡、书签、奖章、便签、箭头、日程等内置贴画，所有贴画都以完整图片形式加入画布。
- 所有用户都可以在添加贴画前调整贴画大小和方向，高级版会员继续支持导入本地图片作为自定义贴画。
- 画布显示、保存恢复、导出 PNG 和打印 PDF 均支持贴画角度，确保看到和导出的效果一致。
- 首页缩略图改为完整内容优先，合并笔迹和贴画范围进行适配，减少内容被截断或只显示局部的问题。
- 优化首页贴画预览的图片缓存和采样解码，降低大项目列表滚动时的内存占用。

### English Release Notes

**More stickers, rotation, and complete thumbnails**

- Added built-in flag, sparkle, bulb, bookmark, medal, note, arrow, and calendar stickers, all inserted as complete images.
- All users can adjust sticker size and rotation before insertion, while Premium members can still import local images as custom stickers.
- Canvas rendering, save and restore, PNG export, and PDF printing now preserve sticker rotation.
- Home thumbnails now prioritize complete content by fitting both ink and stickers into the preview area.
- Improved sticker preview caching and sampled decoding to reduce memory usage while scrolling large project lists.

## v1.0.232 (build 233 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**完整图片贴纸与本地导入**

- 贴纸改为真正的完整 PNG 图片保存和渲染，不再使用笔迹模拟贴纸。
- 高级版会员可以从本地导入图片作为贴纸，导入时会自动采样压缩，降低大图带来的内存压力。
- 贴纸弹窗新增尺寸调节，添加到画布后会按原图宽高比完整显示，避免裁切和变形。
- 项目保存、恢复、备份、完整性校验、导出 PNG 和打印 PDF 均支持贴纸数据。
- 优化贴纸预览、导入和导出时的图片解码策略，减少大画布和高清图片场景下的内存占用。

### English Release Notes

**Full-image stickers and local imports**

- Stickers are now stored and rendered as complete PNG images instead of simulated ink strokes.
- Premium members can import local images as stickers, with sampled compression to reduce memory spikes from large images.
- The sticker dialog now includes size adjustment, and stickers keep their original aspect ratio on the canvas.
- Project saving, restoring, backup, integrity checks, PNG export, and PDF printing now include sticker data.
- Improved image decoding for sticker preview, import, and export to lower memory usage on large canvases and high-resolution images.

## v1.0.231 (build 232 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**贴纸功能与编辑器菜单精简**

- 删除具体项目页面菜单里的转化入口，用户不再从菜单进入文字转手写功能。
- 在下载按钮下方新增贴纸入口，支持在当前画布中心添加星星、爱心、重点标签和完成对勾贴纸。
- 贴纸以轻量矢量笔迹写入项目，能继续参与保存、缩略图、分享图和普通笔迹渲染。
- 普通用户每个项目最多可添加 3 个贴纸，高级版会员不限制使用次数。
- 贴纸计数按项目本地保存，避免普通用户重复进入项目后绕过限制。

### English Release Notes

**Stickers and editor menu cleanup**

- Removed the Convert entry from the editor menu so users no longer enter text-to-handwriting from the project menu.
- Added a Stickers entry below Download, with Star, Heart, Highlight Label, and Check stickers placed at the current canvas center.
- Stickers are saved as lightweight vector ink, so they work with autosave, thumbnails, share images, and normal ink rendering.
- Free users can add up to 3 stickers per project, while Premium members have unlimited sticker use.
- Sticker usage is stored locally per project to keep the free limit stable across sessions.

## v1.0.230 (build 231 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**导出打印、自定义模板与缩放稳定性**

- 优化双指缩放计算，放大到 640% 上限时使用实际生效缩放比例保持中心锚点稳定，减少纸张自动跳走或滑动。
- 项目模板中心新增真正的自定义模板创建弹窗，可修改标题前缀、纸张类型、纸张颜色、笔刷颜色、粗细、文件夹、分组和标签。
- 自定义模板支持导入高清图片作为项目背景，导入时会采样压缩保存，降低大图带来的内存峰值。
- 具体项目菜单在分线下新增下载入口，支持下载模板参数 JSON、项目图片 PNG 和项目 PDF，并提供打印参数与系统打印。
- 项目信息弹窗删除项目档案高级版区域，只保留项目基础信息，减少无关计算和显示占用。

### English Release Notes

**Export, printing, custom templates, and zoom stability**

- Improved two-finger zoom math so the canvas uses the effective clamped zoom ratio and stays anchored when reaching the 640% limit.
- The project template center now has a real custom-template dialog for title prefix, paper mode, paper color, brush color, stroke width, folder, group, and tags.
- Custom templates can import high-resolution background images, with sampled compression to reduce memory spikes.
- The editor menu now includes a Download entry below the divider for template JSON, PNG image, PDF export, print settings, and system printing.
- Removed the Premium project dossier area from Project Info, keeping the dialog focused on essential project details.

## v1.0.229 (build 230 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**平板与横屏模式适配增强**

- 首页项目网格改为自适应列数，横屏手机、普通平板和大平板会分别使用更合适的两列或三列布局。
- 首页缩略图比例会根据设备宽度和横竖屏自动调整，减少宽屏下卡片过高或内容拥挤的问题。
- 具体项目页面横屏侧边工具栏启用阈值更低，并按屏幕宽度自适应宽度，给手写画布保留更多空间。
- 分享图、文字转手写、项目信息和数据识别等弹窗在横屏短高度设备上使用更保守的高度并保持滚动，减少按钮遮挡。
- 设置页修正平板内容宽度规则，横屏手机也进入宽屏约束，大平板获得更合理的内容宽度。

### English Release Notes

**Tablet and landscape adaptation improvements**

- Home now uses adaptive note grid columns, giving landscape phones, tablets, and large tablets more appropriate two- or three-column layouts.
- Home thumbnail aspect ratios now adapt to width and orientation to reduce overly tall cards or crowded previews on wide screens.
- The editor side toolbar now activates earlier in landscape and adapts its width by screen size, leaving more room for handwriting.
- Share image, text-to-handwriting, project info, and structured-ink dialogs use safer height limits on short landscape screens while remaining scrollable.
- Settings tablet width rules were corrected so landscape phones use wide constraints and large tablets get a more natural content width.

## v1.0.228 (build 229 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**编辑页菜单与小组件设置优化**

- 修复具体项目页面视图菜单中视图标记、智能视图标记、构图参考线、演示聚光灯和复盘路径相关按钮的多语言显示错乱问题。
- 专注模式进一步简化，进入专注后不再显示产出浮层，展开工具栏时只保留纸张面板和折叠按钮。
- 首页顶栏菜单删除智能清理入口和对应弹窗，并移除首页不再使用的智能清理统计计算。
- 首页排序菜单收敛为时间排序，筛选菜单收敛为打开权重筛选，减少重复入口和误触。
- 设置页小组件区域新增状态摘要，展示已添加数量、支持尺寸和添加后的选择说明，并保留添加与刷新功能。

### English Release Notes

**Editor menu and widget settings cleanup**

- Fixed multilingual text for View Marks, Smart View Marks, composition guides, presentation spotlight, and review path actions in the editor View menu.
- Focus mode is quieter: the in-focus output overlay is hidden, and expanding the toolbar now shows only paper controls plus the collapse button.
- Removed the Smart Cleanup entry and dialog from the home top-bar menu, and stopped calculating the unused cleanup insight snapshot.
- Home sorting is now limited to time sorting, and filtering is limited to the open-weight filter to reduce duplicate choices.
- Settings now shows a clearer widget summary with installed count, supported sizes, and the choose-note flow while keeping add and refresh actions.

## v1.0.227 (build 228 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**场景模板中心增强**

- 模板中心新增错题复盘、复习计划、知识卡片、读书摘录卡、项目复盘、手账封面、心情拼贴和学习总结卡。
- 新模板已预设纸张、笔刷、颜色、文件夹、分组和标签，用户新建后可以直接进入对应书写场景。
- 学习、阅读、工作和手账类项目的整理入口更清晰，后续可继续配合筛选、收藏和分享图使用。
- 补齐新增分享卡片样式的多语言兜底文本，减少切换语言后出现英文残留的可能。
- 继续复查现有快速草稿、压感书写、分享图和诊断日志能力，跳过已有功能的重复开发。

### English Release Notes

**Scenario template center improvements**

- Added Mistake Review, Study Review Plan, Knowledge Card, Reading Excerpt Card, Project Review, Journal Cover, Mood Board, and Study Summary templates.
- New templates include preset paper, brush, color, folder, group, and tags so users can start the matching writing scene immediately.
- Study, reading, work, and journal notes now have clearer organization starting points that work with filters, favorites, and share cards.
- Added localized fallback labels for the newer share card styles to reduce English leftovers after switching languages.
- Reviewed existing quick draft, pressure writing, share image, and diagnostic log capabilities and avoided duplicating already available features.

## v1.0.226 (build 227 - 2026-06-12)

### 涓枃鏇存柊璇存槑

**分享图强化与新用户快速开始**

- 分享图新增学习总结卡、会议纪要卡、手账封面卡和知识卡片四种场景模板，更贴近社交平台和学习博主风格。
- 所有分享图右下角都会保留克制的 OneNotes 标识，并优化默认分享文案，让分享更自然带来下载兴趣。
- 首次进入引导改为 30 秒快速开始：选择学习、工作、创作或手账用途，再选择手机、平板或触控笔设备。
- 完成选择后会自动生成匹配用途和设备的模板草稿，并直接进入项目页面引导用户写第一笔。
- 新用户写下第一笔后会显示“已自动保存”，并继续触发现有的新用户动画反馈。
- 引导流程会推荐并刷新桌面快捷入口，方便后续从桌面或通知栏快速新建草稿。

### English Release Notes

**Share cards and fast first-run start**

- Added four scenario share templates: Study Summary, Meeting Minutes, Journal Cover, and Knowledge Card, closer to social and study-blogger card styles.
- Every generated share image now keeps a restrained OneNotes mark in the lower-right corner and uses a more natural default share caption.
- First-run onboarding is now a 30-second start path: choose Study, Work, Creation, or Journal, then choose Phone, Tablet, or Stylus.
- After selection, OneNotes creates a matching template draft and opens it directly so users can write their first stroke.
- After the first stroke, the editor shows an auto-saved confirmation and keeps the existing new-user animation feedback.
- The onboarding path refreshes desktop quick-entry shortcuts so users can create drafts faster later.

## v1.0.225 (build 226 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**每日一言与首页精简优化**

- 删除首页高级版创作教练卡片，并停止首页无用的创作教练快照计算。
- 设置页关闭每日一言后，会同步隐藏自定义每日一言输入、保存和清除功能，减少设置页占用空间。
- 高级版每日一言手动刷新从无限次调整为每天 20 次，普通用户仍为每天 1 次。
- 手动刷新每日一言改为请求随机语句，修复刷新后内容看起来没有变化的问题。
- 每日一言刷新次数会加密保存，刷新失败不会消耗当天次数，稳定性更好。

### English Release Notes

**Daily quote and home cleanup**

- Removed the Premium creative coach card from Home and stopped unused creative-coach snapshot calculation.
- When Daily Quote is disabled in Settings, custom quote input, save, and clear controls are hidden together.
- Premium daily quote manual refresh is now limited to 20 times per day; free users remain limited to once per day.
- Manual daily quote refresh now requests a random quote so the refreshed result visibly changes.
- Daily quote refresh counts are stored in encrypted settings, and failed refresh attempts do not consume the daily quota.

## v1.0.224 (build 225 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**性能与稳定性底层优化**

- 启动阶段延后快捷方式和快速草稿通知初始化，减少首屏进入路径上的同步工作。
- 外部分享图片和图片草稿会先限尺寸压缩存储，降低大图进入项目后的内存和存储压力。
- 首页缩略图和本地预览数据改为更轻的低清优先预算，大笔记列表滚动更稳。
- 分享图后台生成继续优化，输出改为高质量 JPEG，并减少可再生成分享缓存的保留数量。
- 数据库迁移移除破坏性清库兜底，已覆盖迁移路径会按安全迁移执行，避免静默丢失用户数据。
- 低内存时会自动清理可再生成的分享图缓存，并同步收缩手写预览、图片预览和快速截图预览缓存。
- 图片草稿写入项目前会校验本地文件存在和大小，降低损坏路径影响项目打开的风险。

### English Release Notes

**Performance and stability foundation**

- Shortcut and quick-draft notification setup now runs after the first screen path to reduce startup work.
- Shared images and image drafts are downsampled and compressed before being stored in projects.
- Home thumbnails and stored preview data now use a lighter low-resolution-first budget for smoother large-note lists.
- Share image generation keeps running off the main path, now exports high-quality JPEG files and retains fewer regenerable cache files.
- Database migration no longer uses destructive fallback, preventing silent data loss when a migration issue is found.
- Low-memory callbacks now trim regenerable share caches together with handwriting, image, and quick-capture preview memory.
- Image drafts validate local file existence and size before being attached to a project.

## v1.0.223 (build 224 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**项目模板中心与首页整理增强**

- 新建项目升级为项目模板中心，内置课堂笔记、会议记录、灵感草稿、日计划、月计划、康奈尔笔记、数学草稿纸、乐谱、手账、截图标注和阅读摘录。
- 模板会自动设置标题、文件夹、分组、标签、纸张模板、纸张颜色、默认笔刷颜色和粗细。
- 高级版入口新增自定义打印模板能力预留，可基于官方模板快速创建带自定义纸张和笔刷参数的项目。
- 首页项目支持收藏、标签、最近打开记录，并在项目卡片中显示收藏标记和标签摘要。
- 首页菜单新增筛选，可按收藏夹、最近打开、未命名项目、空草稿、很久没打开、纸张和颜色快速查看。
- 首页新增智能清理分析，先筛选未命名、空草稿和久未打开项目，避免误删。
- 本地数据库升级到 v11，标签等新增组织字段继续参与本地加密和备份恢复。

### English Release Notes

**Project templates and home organization**

- The create flow is now a project template center with class notes, meetings, ideas, plans, Cornell notes, math paper, music, journal, screenshot markup, and reading excerpts.
- Templates automatically set title, folder, group, tags, paper style, paper color, default brush color, and stroke width.
- Added a Premium custom print-template entry point based on official template parameters.
- Home projects now support favorites, tags, and recent-open tracking, with favorite and tag summaries shown on cards.
- Added home filters for favorites, recent projects, unnamed notes, empty drafts, stale notes, paper, and color.
- Added smart cleanup analysis that filters risky projects first instead of deleting automatically.
- Local database upgraded to v11; new organization fields are included in local encryption and backup restore.

## v1.0.222 (build 223 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**极速入口与书写诊断增强**

- 新增通知栏快速草稿入口，系统允许通知时可从通知栏或锁屏快速进入新草稿。
- 桌面快捷方式扩展为新建草稿、截图标注和最近项目，减少进入书写前的操作步骤。
- 分享菜单继续增强，分享网页链接到 OneNotes 时会自动生成带来源域名的网页草稿。
- 具体项目页会恢复上次打开的工具面板，并保留最近 3 个画布位置，便于在大画布和多页项目中快速返回。
- 视图菜单新增书写诊断，可查看设备刷新率、低延迟路径、触控笔防误触状态和推荐设置。
- 增强笔尖预测距离和容错范围，让快速书写时笔迹跟手感更稳定。

### English Release Notes

**Quick entry and handwriting diagnostics**

- Added a notification quick-draft entry point that can also appear from the lock screen when notifications are allowed.
- Expanded launcher shortcuts with New Draft, Image Markup, and Recent Project for faster entry into writing.
- Improved share handling so shared web links create drafts titled with the source domain.
- Project pages now restore the last opened toolbar panel and keep the three most recent canvas positions for quick return.
- Added handwriting diagnostics in the View menu to show refresh rate, latency path, stylus palm-guard state, and recommended settings.
- Improved tip prediction distance and tolerance for a steadier low-latency writing feel.

## v1.0.221 (build 222 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**快速草稿入口与项目状态恢复**

- 首页新建按钮支持长按直接创建快速草稿，减少进入书写前的选择步骤。
- 新增桌面动态快捷方式“新建草稿”，可从桌面直接进入 OneNotes 快速草稿。
- 支持从系统分享文字或图片到 OneNotes 自动生成草稿；图片草稿会保存为项目背景，便于直接圈画标注。
- 每个项目会记住上次使用的笔刷、颜色、粗细、缩放和画布位置，重新打开时自动恢复到上次状态。
- 新增轻量级编辑器状态保存，单纯缩放或切换工具不会触发缩略图和笔迹重算，提升响应速度。

### English Release Notes

**Quick draft entry points and project state restore**

- Long-pressing the home create button now creates a quick draft directly, reducing steps before writing.
- Added a dynamic home-screen shortcut for creating a new draft straight from the launcher.
- Added system share support for text and images. Shared images are saved as draft backgrounds for immediate markup.
- Each project now remembers the last brush, color, width, zoom, and canvas position, then restores them when reopened.
- Added lightweight editor-state saving so tool changes and viewport movement avoid thumbnail and ink recomputation.

## v1.0.220 (build 221 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**低延迟书写与触控笔手感升级**

- 优化书写链路，正在下笔时保存任务会主动避让，笔画结束后再进行增量保存，减少写字时的卡顿感。
- 活动笔迹采用更小批次、更快发布，画布继续只绘制可见区域和当前笔迹附近内容，提升大画布跟手感。
- 新增压感曲线档位：轻、标准、重、自定义，并加入实时曲线预览；不同笔刷会记住各自的压感和稳笔参数。
- 新增稳笔档位：自然、稳定、极稳，增强小字防抖和长线平滑，同时保留真实手写感。
- 增强触控笔防误触窗口，触控笔书写时手掌触摸更不容易参与绘制；双指单击撤销、三指单击重做改为所有用户可用。

### English Release Notes

**Low-latency ink and stylus feel upgrade**

- Improved the writing path so save work backs off while ink is actively being drawn, then incremental save runs after the stroke ends.
- Active strokes now publish in smaller, faster batches while the tile canvas continues to draw only visible content and the current stroke area.
- Added pressure curve presets: Light, Standard, Heavy, and Custom, with a live curve preview. Each brush remembers its own pressure and stabilizer settings.
- Added stabilizer presets: Natural, Stable, and Extreme to reduce small-writing jitter and smooth long lines while preserving handwriting character.
- Expanded stylus palm rejection timing and made two-finger undo plus three-finger redo available to all users.

## v1.0.219 (build 220 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**删除首页创作概览**

- 删除首页创作概览卡片，不再在项目列表上方显示当前项目、今日更新、归档和回收站摘要。
- 删除设置页里的创作概览开关，并移除对应的设置仓库接口和状态字段。
- 移除首页加载时为创作概览计算归档、回收站和保护状态摘要的逻辑，降低首页刷新时的额外开销。
- 同步调整新用户引导文案，避免继续引导用户查看已删除的创作概览功能。

### English Release Notes

**Removed home writing overview**

- Removed the home writing overview card so active, updated, archive, and recycle summaries no longer appear above projects.
- Removed the writing overview switch from Settings together with its repository API and UI state fields.
- Removed the home-side summary calculations for archive, recycle-bin, and protection signals to reduce extra refresh overhead.
- Updated onboarding copy so new users are no longer guided toward the removed writing overview feature.

## v1.0.218 (build 219 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**每日一言与首页灵感卡**

- 首页顶栏下方、项目列表上方新增每日一言卡片，会根据当前语言显示对应文案。
- 接入免费在线每日语句接口，并提供本地多语言兜底文案，网络不可用时也能稳定显示。
- 设置页新增每日一言开关；普通用户每天可手动刷新一次，高级版用户可无限刷新并自定义首页文案。
- 每日一言状态、刷新日期和自定义文案写入加密设置存储，减少重复请求并提升稳定性。

### English Release Notes

**Daily quote and home inspiration card**

- Added a daily quote card below the home top bar and above the project list, localized for the current app language.
- Connected a free online daily quote API with local multilingual fallback text so the home page remains stable offline.
- Added a settings switch for daily quote. Free users can manually refresh once per day, while Premium users can refresh freely and set a custom quote.
- Stored daily quote state, refresh date, and custom text in encrypted settings to reduce repeated requests and improve reliability.

## v1.0.217 (build 218 - 2026-06-11)

### 涓枃鏇存柊璇存槑

**转化弹窗样式统一**

- 将具体项目页面菜单里的“转化”弹窗从自定义全屏 Dialog 改为与软件其它弹窗一致的标准 AlertDialog 样式。
- 保留文字转手写的输入、示范书写、风格分析、预览和高级版保存逻辑，同时让标题、正文滚动区、取消按钮和保存按钮与其它弹窗保持统一。
- 优化小屏和横屏下的弹窗高度限制，减少遮挡和视觉割裂。

### English Release Notes

**Unified conversion dialog style**

- Changed the editor menu conversion dialog from a custom full-screen Dialog to the same standard AlertDialog style used by the rest of the app.
- Kept text input, handwriting sample, style analysis, preview, and Premium save behavior while aligning the title, scrollable body, cancel button, and save button with other dialogs.
- Improved height limits for small screens and landscape mode to reduce obstruction and visual inconsistency.

## v1.0.216 (build 217 - 2026-06-10)

### 涓枃鏇存柊璇存槑

**具体页面语言错漏修复**

- 继续检查具体项目页面实际使用的菜单、工具栏、分享、套索、密码安全、文字转手写和数据识别文案，修复问号乱码、断句错误和语义错位。
- 修复中文高级版标识、分享图说明、转化相似度/完整度提示和套索删除提示中的异常文本。
- 修复日文、法文、德文、西班牙文、阿拉伯文和葡萄牙文中与具体页面相关的错误翻译、缺失重音、错误按钮含义和格式分隔问题。
- 收紧多语言字符串表初始化容量，减少语言切换和首次加载时的冗余 Map 内存占用。

### English Release Notes

**Editor language cleanup**

- Checked editor-page strings used by menus, toolbars, share image, lasso, password safety, text-to-handwriting, and data recognition, then fixed question-mark corruption, broken punctuation, and mismatched wording.
- Fixed Chinese Premium badge text, share-image description, conversion similarity/completeness labels, and lasso-delete feedback.
- Cleaned editor-related Japanese, French, German, Spanish, Arabic, and Portuguese text for wrong translations, missing accents, incorrect button meaning, and inconsistent separators.
- Tightened multilingual string-map initialization capacity to reduce extra Map memory during language switching and first load.

## v1.0.215 (build 216 - 2026-06-10)

### 涓枃鏇存柊璇存槑

**全语言完整覆盖与内存优化**

- 补齐所有语言包缺失的界面文案，中文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文现在都覆盖完整的 703 个文本 key，切换语言后不再因为缺失而回退英文。
- 校验并修复格式占位符，确保 %d、%s 和多参数文案在所有语言中保持一致，降低弹窗、统计、页码和更新内容显示错误的风险。
- 统一 Premium 徽标文本，并继续扫描乱码、问号截断和旧式转写残留。
- 降低首页速记截图和手写预览缓存上限，减少列表滚动、多图预览和低内存场景下的 Bitmap 与预览数据占用。

### English Release Notes

**Full language coverage and memory optimization**

- Filled every missing UI string across Chinese, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese so each language now covers all 703 text keys without falling back to English.
- Verified format placeholders such as %d, %s, and indexed arguments across all languages to reduce dialog, stats, page number, and update-history rendering issues.
- Normalized the Premium badge wording and rescanned for mojibake, question-mark truncation, and legacy transliteration residue.
- Reduced quick-capture screenshot and handwriting preview cache budgets to lower Bitmap and preview-data memory use during home scrolling, image previews, and low-memory pressure.

## v1.0.214 (build 215 - 2026-06-10)

### 涓枃鏇存柊璇存槑

**重写并清洗语言文本资源**

- 集中清洗 Compose 多语言文案，修复中文、日文、葡萄牙文、法文、德文和西班牙文中的残留乱码、问号截断和重音丢失问题。
- 重写原生小组件 strings.xml，补齐印地文、阿拉伯文、中文、法文和德文的小组件名称与系统提示，避免系统层继续混用英文或旧式转写。
- 增加语言资源复扫流程，区分 PowerShell 终端显示假乱码和真实文件编码问题，降低后续文本残留风险。

### English Release Notes

**Rewritten and cleaned language resources**

- Cleaned Compose multilingual copy and fixed remaining mojibake, question-mark truncation, and missing accents in Chinese, Japanese, Portuguese, French, German, and Spanish.
- Rewrote native widget strings for Hindi, Arabic, Chinese, French, and German so system UI no longer mixes English or legacy transliteration.
- Added a safer language-resource rescan flow that separates terminal display artifacts from real file encoding issues.

## v1.0.213 (build 214 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**全局检查与稳定性修复**

- 全局检查启动、设置、编辑器、删除/回收站、内购、备份、安全检测和小组件相关路径，修复检查中确认的资源与文本问题。
- 小组件配置按系统版本拆分，基础配置不再声明 Android 12+ 专用属性，高版本仍保留预览布局和目标尺寸。
- 修复德语、西班牙语和葡萄牙语中残留的乱码、缺失重音和原生小组件文案问题。
- 优化 Compose 工具栏参数顺序并移除分享图生成中的无意义系统版本判断，降低后续维护和 lint 噪声。

### English Release Notes

**Full app check and stability fixes**

- Checked startup, Settings, editor, delete/recycle-bin flow, purchases, backup, security monitoring, and widgets, then fixed confirmed resource and text issues.
- Split widget metadata by Android version so base configs avoid Android 12+ only attributes while newer devices keep preview layouts and target sizing.
- Fixed remaining garbled, missing-accent, and native widget text issues in German, Spanish, and Portuguese.
- Aligned the Compose toolbar parameter order and removed a redundant platform-version branch from share-image generation to reduce maintenance and lint noise.

## v1.0.212 (build 213 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**继续清理多语言细节**

- 继续扫描设置页和高级版相关文案，修复产品说明、分享样式、智能调色板、Google Play 商品 ID 等位置的残留乱码。
- 修正葡萄牙文、阿拉伯文、西班牙文和日文中的少量编码残留、语义误译和不自然文本。
- 补正回收站确认、页面健康建议、分享图空状态等中文短句中的标点和半截词问题。

### English Release Notes

**Further multilingual cleanup**

- Continued scanning Settings and Premium-related text, fixing leftover garbled copy in product descriptions, share styles, smart palettes, and Google Play product IDs.
- Corrected remaining encoding artifacts, mistranslations, and awkward text in Portuguese, Arabic, Spanish, and Japanese.
- Fixed punctuation and truncated Chinese text in recycle-bin confirmation, page health suggestions, and share-image empty states.

## v1.0.211 (build 212 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**完善高级版权益多语言说明**

- 重写设置页高级版会员权益说明，补齐中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文的完整权益文案。
- 修复高级版权益区域中的残留乱码、半截翻译和错误缩放符号，避免语言切换后出现错乱文本。
- 设置页权益列表补充创作洞察、智能复习计划、智能整理、页面健康、归档洞察和回收站救援等已开发高级功能。

### English Release Notes

**Completed Premium benefit translations**

- Rewrote the Premium benefits copy in Settings and completed localized benefit text for Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.
- Fixed remaining garbled text, truncated translations, and incorrect zoom symbols in the Premium benefits area.
- Added existing Premium features such as creative insights, review planner, smart organizer, page health, archive insights, and recycle rescue to the Settings benefits list.

## v1.0.210 (build 211 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**修复多语言文本**

- 修复设置页、语言选择、会员商品说明、文字转手写和小组件等区域的乱码、半截词和错误分隔符。
- 将非英文语言表改为英文安全回退，并保留恢复后的本地化文本，避免缺失或损坏文案显示为空白或乱码。
- 补正葡萄牙文、日文、印地文、阿拉伯文等语言名称和常用入口文案，提升语言切换后的稳定性。

### English Release Notes

**Fixed multilingual text**

- Fixed garbled text, truncated labels, and incorrect separators in Settings, language selection, premium product copy, handwriting conversion, and widgets.
- Updated non-English language tables to use English as a safe fallback while preserving recovered localized copy.
- Corrected Portuguese, Japanese, Hindi, Arabic, and other language names plus common navigation text for more reliable language switching.

## v1.0.209 (build 210 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**移除自定义启动页**

- 删除设置页面中的“自定义启动页”按钮、弹窗、图片导入、预览和保存链路，进一步精简设置页空间。
- 移除启动时自定义启动页展示逻辑，旧配置不再影响应用进入流程，减少启动阶段的额外图片解码和动画开销。
- 同步清理高级版权益和当前商品说明中的自定义启动页描述，避免用户看到已下线功能入口。

### English Release Notes

**Removed custom startup page**

- Removed the Custom startup page button, dialog, image import, preview, and save path from Settings.
- Removed the runtime custom startup page display so older saved configuration no longer affects app launch and startup image decoding is avoided.
- Updated premium benefit and current product copy so removed startup-page features are no longer advertised.

## v1.0.208 (build 209 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**继续精简编辑页与设置页**

- 删除具体项目页面视图菜单里的“定位密集区域”和“跳到空白处”入口，并移除对应的密集区域计算和空白跳转逻辑。
- 删除设置页面备份与恢复区域中的“一键优化”按钮，并移除旧分享图、临时缓存和代码缓存清理的执行链路。
- 保留系统低内存自动清理能力，减少手动维护入口，让设置页更简洁。

### English Release Notes

**Further editor and Settings cleanup**

- Removed Focus dense area and Jump to blank space from the editor View menu, along with the dense-area calculation and blank-space jump logic.
- Removed the One-tap optimize button from Settings and removed its old share image, temporary cache, and code cache cleanup execution path.
- Kept automatic low-memory cache trimming while reducing manual maintenance controls for a cleaner Settings page.

## v1.0.207 (build 208 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**精简编辑页视图菜单**

- 删除具体项目页面视图菜单中的创作洞察、智能整理、智能复习计划和页面健康检查入口。
- 移除这四项功能在编辑页内的弹窗、状态和本地分析逻辑，减少菜单层级和无用计算。
- 同步清理新手引导和设置页高级版权益中对已删除功能的展示引用，避免用户产生错误入口预期。

### English Release Notes

**Simplified editor View menu**

- Removed Creative insight, Smart organizer, Review planner, and Page health check from the editor View menu.
- Removed the editor-side dialogs, states, and local analysis logic for those four features to reduce menu depth and unused work.
- Updated onboarding and premium benefit presentation so removed features are no longer advertised as active editor tools.

## v1.0.206 (build 207 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**编辑页菜单与自动保存增强**

- 将墨水菜单中偏视图展示的墨迹回放、墨迹地图和墨迹热区合并到视图菜单，减少重复入口，让墨水菜单更专注于清理、识别和整理墨迹。
- 编辑页在暂停、退到后台、页面销毁和退出时会主动触发保存，降低突然切换应用或锁屏时丢失内容的风险。
- 自动保存增加串行保护、失败重试和离开前短重试，避免多次保存互相打断，并提升临时失败后的恢复能力。

### English Release Notes

**Editor menu and autosave refinement**

- Ink replay, ink map, and ink heat map were moved into the View menu so visual ink tools are grouped together and the Ink menu stays focused on cleanup, recognition, and ink edits.
- The editor now triggers a save on pause, backgrounding, disposal, and exit to reduce the chance of losing work when switching apps or locking the device.
- Autosave now uses serialized saves, retry-on-failure, and a short leave-time retry to avoid overlapping writes and recover from transient save failures.

## v1.0.205 (build 206 - 2026-06-09)

### 涓枃鏇存柊璇存槑

**新增新用户操作反馈动画**

- 新用户完成快速草稿、新建笔记、首次落笔、转化保存和分享图生成后，会看到一次性的轻量动画反馈。
- 动画采用顶部应用内状态统一调度，支持排队展示，并会避开更新弹窗、退出弹窗、评分弹窗和自定义启动页。
- 新增反馈文案已覆盖中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文。
- 增加系统低内存回调，统一收缩或清理启动页图片、首页缩略图、手写预览和悬浮截图相关缓存。

### English Release Notes

**New user action feedback**

- New users now see one-time lightweight animation feedback after creating a quick draft, creating a note, writing the first stroke, saving converted handwriting, or generating a share image.
- Feedback is coordinated at the app surface, supports queued display, and avoids update, exit, rating, and custom startup dialogs.
- Feedback copy is available in Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.
- System memory trim callbacks now shrink or clear startup image, home thumbnail, handwriting preview, and floating capture caches together.

## v1.0.204 (build 205 - 2026-06-07)

### 涓枃鏇存柊璇存槑

**转化改回紧凑弹窗**

- “转化”入口改回弹窗形式，不再占用完整页面。
- 重新整理弹窗布局，删除大段说明、底部提示和重复解释，保留输入、示范、风格、预览和保存的核心流程。
- 小屏、横屏和平板会使用紧凑尺寸和滚动内容，减少遮挡和空间浪费。
- 继续保留预览有效性校验、保存中锁定和转化结果清洗，保证保存更稳定。

### English Release Notes

**Compact Convert dialog**

- The Convert entry now opens as a dialog again instead of taking over the full page.
- The dialog layout was reorganized, with long descriptions, footer hints, and repeated explanations removed while keeping input, sample, style, preview, and save actions.
- Small screens, landscape, and tablets now use compact sizing with scrollable content to reduce occlusion and wasted space.
- Preview validation, save locking, and converted stroke sanitization remain in place for more reliable saving.

## v1.0.203 (build 204 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**强化转化稳定性**

- 转化预览现在会绑定当前文字、样式、颜色和画布落点，旧的异步预览结果不会再覆盖新内容。
- 保存时只会复用仍然匹配当前设置的预览结果，过期预览会自动重新生成，避免误保存旧内容。
- 保存过程中会锁定输入、示范书写、风格选择和预览按钮，减少状态错位和误操作。
- 转化结果写入前新增安全清洗，会过滤异常坐标、异常压力和空笔画，进一步降低保存失败或数据损坏风险。

### English Release Notes

**Strengthened conversion stability**

- Conversion preview is now bound to the current text, style, color, and canvas placement, so stale async preview results no longer overwrite newer content.
- Saving only reuses a preview that still matches the current settings. Expired previews are regenerated automatically to avoid saving old content.
- Input, sample writing, style selection, and preview actions are locked while saving to reduce state mismatch and accidental edits.
- Converted strokes are sanitized before insertion, filtering invalid coordinates, pressure values, and empty strokes to reduce save failures and data corruption risk.

## v1.0.202 (build 203 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**完善转化保存体验**

- 转化预览现在会按真实画布落点生成，保存后的手写内容会更接近用户预览到的效果。
- 保存时优先直接写入已经预览好的结果，避免预览和保存重复生成带来的等待、内存占用和轻微差异。
- 未预览直接保存时只会生成一次并立即保存，生成失败、保存失败都会走统一失败提示。
- 保存过程中会阻止返回键和关闭按钮误关闭转化页面，减少内容丢失和误操作。

### English Release Notes

**Improved conversion save flow**

- Conversion preview now uses the real canvas placement, so saved handwriting better matches what the user previewed.
- Saving now reuses the previewed result when available, avoiding duplicate conversion work, extra memory pressure, and small preview/save differences.
- Saving without preview generates once and saves immediately, with unified feedback for generation or save failures.
- The Convert page now blocks back and close actions while saving to reduce accidental dismissal and lost work.

## v1.0.201 (build 202 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**修复转化保存失败**

- 修复“转化”保存时页面提前关闭、失败反馈不明显的问题，保存成功后才会退出转化页面。
- 转化笔迹插入后会立即执行一次持久化保存，数据库写入成功才提示保存成功。
- 如果保存失败，会回滚本次转化插入，避免用户重试时出现重复笔迹。
- 转化页面新增自适应紧凑布局，小屏、横屏和平板会自动调整输入区、示范区和预览区高度，减少空间占用和遮挡。

### English Release Notes

**Fixed conversion saving**

- Fixed the Convert page closing too early during saving and making save failures hard to notice.
- Converted handwriting is now persisted immediately, and success is shown only after the database write completes.
- If saving fails, the inserted converted strokes are rolled back so retrying does not duplicate handwriting.
- Added an adaptive compact layout for Convert. Phones, landscape screens, and tablets now adjust the source, sample, and preview areas to reduce crowding.

## v1.0.200 (build 201 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**修复转化字内空隙**

- 修复“转化”生成字形中间出现空隙、像空心字的问题。
- 文字转手写由单纯采样字体轮廓改为填充字形后生成重叠墨迹线，笔画内部更饱满。
- 继续增强个人风格匹配，示范字会更明显影响墨迹密度、字距、基线起伏、轻微倾斜和笔画粗细。
- 长文本转化会根据面积自动调整墨迹密度，减少空隙同时控制大段文本的生成量。

### English Release Notes

**Fixed handwriting conversion gaps**

- Fixed hollow-looking converted glyphs where gaps could appear inside the generated handwriting.
- Changed text-to-handwriting generation from outline-only sampling to filled glyph sampling with overlapping ink strokes for fuller characters.
- Improved personal style matching so the sample sentence more strongly affects ink density, spacing, baseline movement, light slant, and stroke width.
- Long-text conversion now adapts ink density by rendered area, reducing gaps while keeping large conversions under control.

## v1.0.199 (build 200 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**转化工作台与个人风格增强**

- 将具体项目页的“转化”功能从弹窗升级为完整页面式工作台，包含原始文字、示范字、个人风格、转化结果和底部保存区。
- 平板和横屏下转化工作台会自动使用左右双栏布局，手机竖屏下保持单列滚动，减少遮挡并提升可操作空间。
- 个人风格分析新增字距、基线起伏、字形宽窄变化、轻微旋转和风格可信度，让纯文本转手写更接近用户示范笔迹。
- 提升纯文本转手写完整性，输入上限提升到 1600 字，转换过程更完整保留段落、空格和自动换行。
- 转化结果页新增相似性、完整性和笔迹统计展示，便于保存前判断效果。

### English Release Notes

**Conversion workspace and personal style improvements**

- Upgraded Convert from a dialog into a full-page workspace with source text, sample writing, personal style, result preview, and bottom save actions.
- The workspace now uses a two-pane layout on tablets and landscape screens, while phones keep a single-column scrolling layout to reduce crowding.
- Personal style analysis now captures spacing, baseline variation, glyph scale changes, light rotation, and confidence for handwriting that better matches the user's sample.
- Improved long-text completeness: the input limit is now 1600 characters and conversion better preserves paragraphs, spaces, and wrapping.
- Added similarity, completeness, and stroke statistics in the result area so users can evaluate the conversion before saving.

## v1.0.198 (build 199 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**增强转化为手写**

- 具体项目页菜单中的“文字转手写”入口已改为更简洁的“转化”。
- 转化弹窗新增示范字书写区，用户可以写一句示范，软件会提取倾斜、压感、间距和笔画节奏等轻量特征用于生成“我的风格”。
- 新增具有科技感的分析加载动画，并明确说明动画只代表特征提取进度，不代表正式笔迹鉴定或正式分析。
- 普通用户也可以输入文字并预览转化后的手写效果；保存到画布改为高级版会员权益，并在 ViewModel 层增加兜底校验。
- 补齐中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文的完整转化功能文案。

### English Release Notes

**Enhanced handwriting conversion**

- Renamed the project-page menu entry from Text to handwriting to the shorter Convert label.
- Added a sample-writing area in the conversion dialog so users can write one sentence and generate a lightweight My style profile from slant, pressure, spacing, and stroke rhythm.
- Added a technical-looking analysis animation with a clear note that it indicates feature extraction progress only, not formal handwriting analysis.
- All users can enter text and preview the converted handwriting. Saving the result to the canvas is now gated as a Premium feature with a ViewModel-level safeguard.
- Added complete localized copy for Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.

## v1.0.197 (build 198 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**新增文字转手写**

- 具体项目页主菜单新增“文字转手写”入口，位置在“分享”下方，打开后可输入或粘贴文字笔记。
- 支持清爽、自然、书法感三种手写风格，并可调整字号，生成结果会放到当前可见画布区域。
- 生成内容会转换成真实 OneNotes 笔迹数据，可保存、撤销、参与缩略图、分享图和小组件预览。
- 转换过程完全离线，使用系统字形路径生成笔迹，并限制输入长度、行数和笔迹数量，避免大段文本造成卡顿。
- 新增功能文案已补齐中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文和日文。

### English Release Notes

**Text to handwriting**

- Added a Text to handwriting entry under Share in the project-page main menu, with a dialog for typing or pasting text notes.
- Supports Neat, Natural, and Calligraphy styles plus adjustable size, placing the generated handwriting in the current visible canvas area.
- The result becomes real OneNotes ink strokes, so it can be saved, undone, shown in thumbnails, shared, and rendered in widgets.
- Conversion runs fully offline from system glyph paths and caps input length, line count, and generated stroke count to avoid stalls.
- Added localized copy for Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, and Japanese.

## v1.0.196 (build 197 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**启动页与图片预览内存优化**

- 新增通用采样图片内存缓存，启动页背景、自定义启动页预览和悬浮按钮图标预览会复用已解码的小图，减少重复解码和瞬时内存峰值。
- 图片预览统一按目标尺寸采样，背景类图片使用更省内存的 RGB_565 配置，透明图标会保留透明通道，兼顾性能和显示效果。
- 快速草稿进入编辑页时的截图背景也接入统一缓存，减少首页预览和编辑页之间重复解码同一张图片的情况。
- 应用进入后台、界面隐藏或系统内存紧张时，会自动裁剪或清空相关图片缓存，降低长时间使用后的内存压力。
- 保持原有缩略图、分享图和启动页功能不变，重点提升打开设置页、返回首页和切换启动页预览时的稳定性与响应速度。

### English Release Notes

**Startup and image preview memory optimization**

- Added a shared sampled-image memory cache so startup backgrounds, custom startup previews, and floating button icon previews can reuse decoded small images.
- Image previews now decode to the target size; background images use lower-memory RGB_565 while transparent icons keep their alpha channel.
- Quick draft screenshot backgrounds in the editor now use the same cache to avoid decoding the same image again after leaving the home preview.
- The app trims or clears these image caches when the UI is hidden, the app moves to the background, or Android reports memory pressure.
- Existing thumbnails, share images, and startup-page behavior stay unchanged while Settings, Home return, and startup preview switching become steadier.

## v1.0.195 (build 196 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**删除系统级悬浮服务权限**

- 删除 FOREGROUND_SERVICE_MEDIA_PROJECTION 和 FOREGROUND_SERVICE_SPECIAL_USE 权限及对应的系统级悬浮绘画前台服务。
- 移除依赖 MediaProjection 的跨应用截图授权页和相关服务逻辑，避免运行时继续请求屏幕捕获能力。
- 悬浮绘画按钮调整为仅在 OneNotes 应用内显示和使用，仍可用于应用内画笔、套索、截图和快速草稿。
- 同步清理不再需要的悬浮窗、前台服务和通知权限声明，并更新设置页多语言说明。

### English Release Notes

**Removed system floating service permissions**

- Removed the FOREGROUND_SERVICE_MEDIA_PROJECTION and FOREGROUND_SERVICE_SPECIAL_USE permissions plus the related system floating drawing foreground service.
- Removed the MediaProjection-based cross-app screenshot permission activity and service flow so the app no longer requests screen capture for that feature.
- The floating drawing button now works only inside OneNotes while keeping in-app pen, lasso, screenshot, and quick draft actions.
- Cleaned up no-longer-needed overlay, foreground service, and notification permission declarations, and updated multilingual Settings descriptions.

## v1.0.194 (build 195 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**具体页面工具栏布局优化**

- 点击具体页面的笔刷按钮后，底部会显示笔刷小按钮面板，常用笔刷、高级笔刷、橡皮擦和几何工具不再挤在弹出菜单里。
- 常用笔刷、快速预设、几何与辅助工具按类别分别排在同一行，横向滑动查看，减少按钮遮挡和重复占位。
- 墨水面板下方移除笔刷预设，只保留颜色、粗细和墨迹辅助能力，让颜色与粗细调整区域更紧凑。
- 保持顶部按钮未点击时以图标为主，点击后显示图标和文字，继续降低横屏和平板场景的拥挤感。

### English Release Notes

**Editor toolbar layout polish**

- Tapping the editor brush button now opens a lower brush-button panel, keeping regular brushes, premium brushes, eraser, and geometry tools out of the old long popup.
- Regular tools, quick presets, geometry tools, and guide actions are grouped into matching horizontal rows to reduce overlap and repeated space usage.
- The Ink panel no longer mixes brush presets; it now focuses on color, width, and ink assistance for a more compact adjustment area.
- Top toolbar buttons still stay icon-first until tapped, then expand to icon plus label for better landscape and tablet spacing.

## v1.0.193 (build 194 - 2026-06-06)

### 涓枃鏇存柊璇存槑

**高级版创作教练**

- 新增高级版创作教练功能，入口位于首页创作概览下方，不涉及视图、墨水或密码功能。
- 创作教练会在本地分析 7 天活跃项目、深度项目、空白草稿、文件夹和分组整理情况。
- 高级版用户可看到创作势能评分和下一步行动建议，帮助决定继续写作、整理项目或唤醒沉淀内容。
- 普通用户可看到锁定态预览，不影响新建、打开、整理、归档和删除等基础使用。

### English Release Notes

**Premium creative coach**

- Added the Premium creative coach below the home writing overview, without touching view, ink, or password features.
- The coach analyzes 7-day activity, deep projects, blank drafts, folders, and group organization locally.
- Premium members get a writing momentum score and next-step suggestions for continuing, organizing, or reviving work.
- Free users see a locked preview while all core creation, opening, organization, archive, and delete flows remain unaffected.

## v1.0.192 (build 193 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**工具栏紧凑交互优化**

- 具体项目页面的套索入口改为默认只显示图标，点击后再显示图标和文字，和画笔、墨水按钮保持一致。
- 墨水辅助工具行改为图标化布局，形状识别、橡皮擦增强、套索自由选、矩形选、清除和删除选区占用空间更少。
- 快捷笔刷预设改为颜色点加工具图标，只有当前选中的预设才展开文字，减少横向滚动压力。
- 工具栏主要按钮、颜色点和快捷预设增加轻触反馈，让点按结果更明确，手写时操作更跟手。

### English Release Notes

**Compact toolbar interaction polish**

- Changed the editor lasso entry to show only an icon by default, then expand to icon plus label after tapping, matching the brush and ink buttons.
- Converted the ink assistant row to a more icon-driven layout so shape recognition, enhanced eraser, lasso modes, clear, and delete selection take less space.
- Made quick brush presets show a color dot plus tool icon, expanding the label only for the selected preset to reduce horizontal scrolling pressure.
- Added light haptic feedback to primary toolbar buttons, color dots, and quick presets so taps feel clearer during handwriting.

## v1.0.191 (build 192 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**编辑页工具栏体验增强**

- 具体项目页面顶部工具栏拆分当前面板高亮和文字展开状态，默认保持图标化但仍能看出当前所在面板。
- 墨水面板把默认颜色和项目最近颜色合并到同一行，减少重复颜色占用的空间。
- 形状识别、橡皮擦增强、套索模式和选区操作合并为一条辅助工具行，降低工具栏高度。
- 继续优化横屏和平板上的工具栏拥挤问题，让手写区域获得更多可用空间。

### English Release Notes

**Editor toolbar experience polish**

- Separated active panel highlighting from label expansion in the editor toolbar, keeping icons compact while still showing the current panel.
- Merged default ink colors and recent project colors into one row to reduce repeated color space usage.
- Combined shape recognition, enhanced eraser, lasso modes, and selection actions into one assistant row to reduce toolbar height.
- Continued reducing toolbar crowding on landscape and tablet layouts so handwriting gets more usable space.

## v1.0.190 (build 191 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**编辑页工具栏图标化优化**

- 具体项目页面工具栏的画笔按钮默认改为只显示图标，点击后再显示图标和当前画笔名称。
- 墨水按钮默认不再占用文字宽度，用户点击墨水入口后才显示图标和墨水文本。
- 保留墨水面板默认内容，进入页面后仍可直接调整颜色、粗细和常用笔刷。
- 继续压缩顶部工具栏横向空间，降低按钮拥挤和遮挡风险。

### English Release Notes

**Editor toolbar icon cleanup**

- Changed the editor brush button to show only an icon by default, then show both the icon and current brush name after it is tapped.
- The Ink button no longer consumes text width by default and only expands to icon plus label after the user taps it.
- Kept the Ink panel content available by default so colors, width, and quick brush presets remain immediately usable.
- Further reduced horizontal toolbar pressure to lower the risk of crowded or clipped buttons.

## v1.0.189 (build 190 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**设置页高级版区域精简**

- 删除设置页 Google Play 高级版购买按钮上方的产品说明折叠区域。
- 购买一年高级版和终身高级版按钮位置更靠前，减少设置页纵向占用。
- 保留价格、购买入口、试用提示、本地激活提示和高级版会员权益。
- 继续优化设置页空间，让常用设置更容易扫视和操作。

### English Release Notes

**Premium settings cleanup**

- Removed the product description panel above the Google Play Premium purchase buttons in Settings.
- Moved the yearly and lifetime Premium purchase buttons higher by reducing vertical space usage.
- Kept prices, purchase entries, trial hints, local activation hints, and Premium benefits available.
- Continued refining Settings spacing so common options are easier to scan and use.

## v1.0.188 (build 189 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**任务式新手引导**

- 首次进入软件的新手引导升级为任务式流程，引导用户从快速草稿、笔刷、纸张、套索到分享和安全保护逐步完成第一篇手写笔记。
- 每个引导页面新增明确动作卡，让用户知道下一步应该点击什么、尝试什么，而不是只阅读功能说明。
- 新增即时反馈卡，提前展示书写概览、页面健康、智能整理、分享图和密码安全等使用后的反馈价值。
- 高级版权益改为跟真实使用场景结合展示，让用户在理解价值后再决定是否升级。

### English Release Notes

**Guided first-note onboarding**

- Upgraded first-launch onboarding into a guided task flow that walks users through quick drafts, brushes, paper, lasso, sharing, and security for their first handwritten note.
- Added a clear action card to every onboarding page so users know what to tap and try next instead of only reading feature descriptions.
- Added feedback cards that preview the value users receive after writing, including writing overview, page health, smart organization, share images, and password safety.
- Reframed Premium benefits around real usage moments so upgrades feel tied to value rather than a plain feature list.

## v1.0.187 (build 188 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**触控笔历史采样优化**

- 具体项目页优化触控笔历史采样点的压力过渡，快速书写时笔迹粗细变化更自然。
- 历史轨迹不再整段直接复用当前压力，而是按时间从上一笔尖压力平滑过渡到当前压力。
- 减少快速落笔、收笔或突然加压时的局部宽度跳变，让手写曲线更连贯。
- 继续保持项目文件结构不变，旧笔记无需迁移即可继续使用。

### English Release Notes

**Stylus historical sampling**

- Improved pressure transitions for stylus historical samples in the editor so fast handwriting changes width more naturally.
- Historical points now interpolate from the previous stylus pressure sample to the current pressure instead of reusing one pressure for the whole segment.
- Reduces local width jumps during fast downstrokes, lift-offs, and sudden pressure changes for smoother handwritten curves.
- Kept the project file structure unchanged, so existing notes continue to work without migration.

## v1.0.186 (build 187 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**自适应稳笔体验优化**

- 具体项目页的实时书写稳笔算法改为距离自适应，慢速书写时更容易压住细小抖动。
- 快速划线、圈选和速记时会自动释放一部分阻尼，让笔尖跟手感更好。
- 压感跟随也做了更轻的平滑处理，减少压力突变造成的笔迹宽度跳动。
- 不改变已有项目文件结构，旧笔记可继续正常打开和保存。

### English Release Notes

**Adaptive stroke stabilization**

- Changed live stroke stabilization in the editor to distance-aware smoothing, reducing tiny shakes during slow handwriting.
- Automatically releases some damping during fast strokes, circles, and quick notes so the pen feels more responsive.
- Lightly smooths pressure following to reduce sudden width jumps from pressure spikes.
- Kept the existing project file format unchanged so old notes continue to open and save normally.

## v1.0.185 (build 186 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**触控笔手感档位**

- 具体项目页触控笔面板新增压感/稳笔组合档位，可一键切换不同书写手感。
- 手感档位使用短数值标签显示压感和稳笔比例，不增加新的复杂入口，也适合多语言界面。
- 选择档位会同时更新压感灵敏度和笔迹稳定度，适合在速写、普通书写和慢速整理之间快速切换。
- 继续保持软件重点在手写笔记、触控笔和书写体验上。

### English Release Notes

**Stylus feel presets**

- Added pressure/stabilization presets to the editor Stylus panel for one-tap writing feel changes.
- Presets use compact numeric labels for pressure and stabilization, avoiding extra complex entries while fitting multilingual layouts.
- Selecting a preset updates pressure sensitivity and stroke stabilization together for faster switching between sketching, regular writing, and careful cleanup.
- Kept the product focused on handwritten notes, stylus input, and writing feel.

## v1.0.184 (build 185 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**常用书写预设与工具栏性能优化**

- 具体项目页墨水面板新增常用书写预设，可快速切换细笔、铅笔、荧光笔和橡皮，减少反复调整颜色和粗细。
- 常用预设会复用现有高级版权限规则，未开通高级版时高级笔刷仍保持锁定提示。
- 项目常用颜色列表改为按笔迹变化缓存，避免工具栏每次重组都重新扫描全部笔迹。
- 继续保持软件方向集中在手写笔记和书写体验，不增加偏离笔记创作的杂项入口。

### English Release Notes

**Handwriting presets and toolbar performance**

- Added quick handwriting presets to the editor Ink panel for fast switching between pen, pencil, highlighter, and eraser without repeatedly adjusting color and width.
- Quick presets reuse the existing Premium entitlement rules, so Premium brushes still show the locked flow when needed.
- Cached project ink colors by stroke-list changes to avoid rescanning all strokes on every toolbar recomposition.
- Kept the product direction focused on handwritten notes and writing experience without adding unrelated entry points.

## v1.0.183 (build 184 - 2026-06-05)

### 涓枃鏇存柊璇存槑

**工具栏滑动条与按钮精简**

- 删除具体项目页工具栏中笔刷和墨水之间的数值按钮，让第一排工具入口更清爽。
- 工具栏下方的宽度、压感和稳定度滑动条改为更低的紧凑高度，减少对画布空间的占用。
- 滑动条标签和数值区域进一步缩短，在手机横屏和平板侧边工具栏里更不容易拥挤。
- 保留滑动条完整可拖动区域，只压缩视觉高度，尽量兼顾空间和操作稳定性。

### English Release Notes

**Toolbar slider and button cleanup**

- Removed the value button between the brush box and Ink entry on the editor toolbar for a cleaner first row.
- Made the width, pressure, and stabilization sliders more compact to reduce canvas space usage.
- Shortened slider label and value areas so landscape phones and tablet side toolbars feel less crowded.
- Kept the slider drag area intact while reducing the visual height for a better balance of space and reliability.

## v1.0.182 (build 183 - 2026-06-04)

### 涓枃鏇存柊璇存槑

**编辑页工具栏与按钮优化**

- 具体项目页工具栏顶部面板切换改为图标优先布局，未选中的墨水、纸张、缩放和触控笔入口只显示图标，减少横向拥挤。
- 当前选中面板保留短文字提示，笔盒和数值胶囊增加最大宽度与省略处理，避免长语言或长笔刷名称遮挡其它按钮。
- 折叠展开按钮改为小视觉按钮加稳定触控区，按钮看起来更轻，同时点击更可靠。
- 宽度、压感和稳定度滑块改为标签与数值分列显示，给滑块和横屏工具栏释放更多空间。

### English Release Notes

**Editor toolbar and button refinement**

- Changed the editor toolbar panel switcher to an icon-first layout, so inactive Ink, Paper, Zoom, and Stylus entries use icons to reduce horizontal crowding.
- Kept short text only on the active panel and capped brush/value pill widths with ellipsis handling to prevent long labels from covering nearby buttons.
- Refined the collapse and expand control with a smaller visual button and a steadier touch area for more reliable interaction.
- Split slider labels and values into compact columns for width, pressure, and stabilization controls, leaving more room for sliders and landscape toolbars.

## v1.0.181 (build 182 - 2026-06-04)

### 涓枃鏇存柊璇存槑

**平板首页布局与内存优化**

- 首页在平板和宽屏设备上改为双列笔记网格，创作概览、文件夹、归档和回收站操作继续保持通栏显示。
- 快速草稿截图缩略图新增小型 LRU 内存缓存，按文件路径、修改时间和采样尺寸复用解码结果，减少列表滚动时重复 Bitmap 分配。
- 快速草稿缩略图解码上限从 900px 降到 720px，并接入系统低内存回调主动裁剪或清理缓存。
- 设置页在平板上收敛到居中最大宽度，横屏阅读和操作更稳定。

### English Release Notes

**Tablet home layout and memory optimization**

- Changed the home screen to a two-column note grid on tablets and wide screens while keeping overview, folder, archive, and recycle actions full-width.
- Added a compact LRU memory cache for quick draft screenshot thumbnails, keyed by file path, modified time, and sample size to avoid repeated Bitmap allocations while scrolling.
- Reduced the quick draft thumbnail decode limit from 900px to 720px and connected it to Android low-memory callbacks for proactive trimming and cleanup.
- Constrained the Settings screen to a centered tablet width so landscape reading and actions feel steadier.

## v1.0.180 (build 181 - 2026-06-04)

### 涓枃鏇存柊璇存槑

**插件功能下线与性能优化**

- 首页顶栏菜单移除插件按钮，用户不再看到插件入口。
- 删除插件中心页面、插件 ViewModel、插件仓库、插件导入安全检查和插件笔记生成逻辑。
- 移除插件相关 Hilt 注入绑定，减少应用启动和依赖图生成时的无效对象。
- 清理插件多语言文案、开发说明和示例文件，降低运行包代码体积与启动时字符串表负担。

### English Release Notes

**Plugin removal and performance optimization**

- Removed the Plugins button from the home top menu so users no longer see a plugin entry.
- Deleted the plugin center screen, plugin ViewModel, plugin repository, plugin import scanner, and plugin-generated note logic.
- Removed plugin-related Hilt bindings to reduce unnecessary app dependency graph work.
- Cleaned plugin localization text, developer guide, and sample files to reduce package size and startup string-map work.

## v1.0.179 (build 180 - 2026-06-03)

### 涓枃鏇存柊璇存槑

**插件创作指导弹窗**

- 插件创建页新增完整创作指导入口，点击后以弹窗形式展示，不占用插件页面空间。
- 创作指导按场景、动作、模板、预设、安全和导出检查六个步骤说明插件开发方法。
- 弹窗内容支持滚动，适配手机和平板，避免长文案遮挡创建表单。
- 补充中英文插件创作文案，中文模式下可直接查看完整指导。

### English Release Notes

**Plugin creation guide dialog**

- Added a full creation guide entry to the plugin creation page, shown as a dialog to avoid crowding the page.
- The guide explains plugin creation through six steps: scenario, action, template, preset, security, and export checks.
- The guide dialog is scrollable and works across phones and tablets without covering the creation form.
- Added English and Chinese plugin creation copy so Chinese mode can show the full guide directly.

## v1.0.178 (build 179 - 2026-06-03)

### 涓枃鏇存柊璇存槑

**插件安全导入与三栏插件中心**

- 增强插件导入安全校验，新增低内存保护、JSON 字段白名单、恶意可执行内容、远程链接和 Hook 特征识别。
- 插件导入通过后会写入规范化内容，并确认本地加密保存成功后才提示导入完成。
- 插件中心改为列表、创建、我的三个导航页面，分别承载官方插件、安全创建和已安装插件管理。
- 新增插件说明与用户引导卡片，导入成功提示会明确显示已安全检查并加密保存。

### English Release Notes

**Secure plugin import and tabbed plugin center**

- Enhanced plugin import security with a low-memory guard, JSON field allowlist, malicious executable-content detection, remote-link checks, and hook-signature checks.
- Imported plugins are normalized and only reported as successful after encrypted local storage is confirmed.
- Split the plugin center into List, Create, and Mine tabs for official plugins, safe creation, and installed plugin management.
- Added plugin guidance cards and import success feedback that explains security checking and encrypted storage.

## v1.0.177 (build 178 - 2026-06-03)

### 涓枃鏇存柊璇存槑

**插件预设与悬浮按钮自定义**

- 插件系统新增预设贡献协议，开发者插件现在可以声明纸张模板、分享模板、启动页、笔刷、悬浮按钮和小组件预设。
- 插件中心新增插件预设列表，安装插件后可一键应用纸张、分享、启动页、笔刷、悬浮按钮或桌面小组件配置。
- 高级版悬浮绘画按钮新增图片样式，支持导入图片或图标，并在设置弹窗中调整大小、裁剪和位置。
- 官方插件、开发者插件导出工具、示例插件和插件开发说明已同步升级，并接入默认分享图样式。

### English Release Notes

**Plugin presets and floating button customization**

- Extended the plugin system with preset contributions for paper templates, share templates, startup pages, brushes, floating buttons, and widgets.
- Added a plugin preset section so installed plugins can apply paper, share, startup, brush, floating button, or widget settings.
- Added a Premium image style for the floating ink button with imported icon/image crop, scale, and position controls.
- Updated official plugins, developer export tools, sample plugin JSON, and the plugin developer guide, plus default share-image style integration.

## v1.0.176 (build 177 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**真实创作型插件升级**

- 插件动作新增创作指导、步骤清单、检查清单和画布模板字段，导入旧插件仍保持兼容。
- 运行插件不再只创建空笔记，会自动生成带分区框、清单框、流程线和创作区域的结构化笔记。
- 官方插件升级为会议、阅读、周计划、清单、分享分镜和专注报告等不同模板。
- 高级版插件开发者中心支持选择模板并填写多行指导内容，tools 目录同步更新开发说明和示例插件。

### English Release Notes

**Guided creative plugin actions**

- Added guidance title, guidance steps, checklist, and canvas template fields to plugin actions while keeping old plugin JSON compatible.
- Running a plugin now creates a structured guided note with layout blocks, checklist boxes, process lines, and writing areas instead of a blank note.
- Upgraded official plugins with distinct templates for meetings, reading, weekly planning, checklists, share storyboards, and focus reports.
- Premium plugin developer tools can now export real guided plugins, with the developer guide and sample plugin updated in tools.

## v1.0.175 (build 176 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**安全插件系统与开发者中心**

- 首页顶栏菜单在排序下面新增插件入口，可进入插件中心管理官方插件和用户导入插件。
- 新增三个官方插件：快速创作、学习纸张、分享工作流，安装后可运行插件动作创建快速草稿或多页项目。
- 新增安全声明式插件导入系统，插件包使用 JSON 格式并会拒绝代码、脚本、dex、jar、so、命令和下载字段。
- 新增高级版插件开发者功能，高级版会员可在软件内创建并导出插件包，同时 tools 目录输出开发说明和示例插件。

### English Release Notes

**Safe plugin system and developer center**

- Added a Plugins entry directly under Sort in the home top menu for managing official and imported plugins.
- Added three official plugins: Quick Creation, Study Paper, and Share Workflow. Installed plugins can create quick drafts or paged projects through plugin actions.
- Added a safe declarative JSON plugin import system that rejects code, script, dex, jar, so, command, and download fields.
- Added a Premium plugin developer center so Premium members can create and export plugin packages, with a developer guide and sample plugin generated in tools.

## v1.0.174 (build 175 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**系统级悬浮绘画按钮**

- 悬浮绘画按钮升级为系统悬浮窗，开启权限后可以显示在桌面和其它软件上层使用。
- 新增系统悬浮前台服务，支持拖动按钮、展开工具、画笔、荧光笔、套索、清空、截图分享和保存速记。
- 跨应用截图接入 Android 屏幕捕获授权流程，用户授权后可保存带截图背景的快速草稿。
- 设置页悬浮绘画说明已更新，多语言文案同步描述桌面和其它应用上层使用能力。

### English Release Notes

**System floating ink overlay**

- Upgraded the floating ink button into a system overlay that can appear above the launcher and other apps after overlay permission is granted.
- Added a foreground overlay service with draggable button, expandable tools, pen, marker, lasso, clear, screenshot sharing, and quick capture saving.
- Connected cross-app screenshot capture to Android's user-authorized screen capture flow so quick drafts can keep a screenshot background after approval.
- Updated Settings descriptions across supported languages to describe desktop and other-app overlay usage.

## v1.0.173 (build 174 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**悬浮速记与自动诊断日志**

- 悬浮绘画按钮新增保存速记能力，截图后可直接圈画批注，并自动保存为快速草稿。
- 速记草稿会保存干净的当前界面截图作为背景，同时把圈画内容保存为可继续编辑的笔迹。
- 首页缩略图和具体项目页面现在可以显示悬浮速记截图背景，快速草稿内容更直观。
- 软件异常或闪退时会自动生成诊断日志，并在 OneNotesLog 文件夹中记录设备、版本、页面和关键操作路径。

### English Release Notes

**Floating quick capture and automatic diagnostics**

- Added floating quick capture: after taking a screenshot from the floating drawing button, annotations can be saved directly as a quick draft.
- Quick capture drafts keep a clean app-surface screenshot as the background while saving annotations as editable ink strokes.
- Home thumbnails and the editor can now display floating quick capture screenshot backgrounds for clearer draft previews.
- Crashes and abnormal errors now automatically generate diagnostic files in the OneNotesLog folder with device, version, page, and recent action context.

## v1.0.172 (build 173 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**本地试用取消与设置页收纳**

- 取消本地 7 天高级版试用，旧的本地试用状态不再参与高级版权益判断，避免与 Google Play 订阅试用混淆。
- 设置页移除本地试用卡片，保留 Google Play 购买和开发者发放激活码两种高级版开通方式。
- Google Play 高级版区域的产品说明改为默认折叠，名称、说明、图标建议和商品 ID 可按需展开查看，减少设置页占用空间。
- 首次进入软件的新手引导同步改为购买或激活码开通高级版，不再提示本地试用。

### English Release Notes

**Local trial removal and Settings cleanup**

- Removed the local 7-day Premium trial. Existing local trial state no longer contributes to Premium entitlement, avoiding confusion with the Google Play subscription trial.
- Removed the local trial card from Settings while keeping Google Play purchases and developer-issued activation codes as Premium activation paths.
- Collapsed Google Play Premium product descriptions by default. Product names, descriptions, icon guidance, and product IDs can be expanded when needed to reduce Settings page height.
- Updated first-run guidance so it points to Google Play or activation-code Premium access instead of local trial access.

## v1.0.171 (build 172 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**首页缩略图完整性修复**

- 首页缩略图预览改为覆盖项目首尾、全程均匀采样，并保留画布最左、最右、最上、最下和最大区域的代表笔画，减少大项目内容被漏掉的问题。
- 提高首页预览读取上限，新的压缩预览能展示更多真实笔迹，同时继续限制点数避免列表滑动时内存过高。
- 应用启动后的后台维护会为旧项目重新生成更完整的预览数据，旧笔记无需手动重新保存也能逐步修复首页缩略图。
- 缩略图边界计算增加压感和粗笔刷余量，减少荧光笔、毛笔、水彩、橡皮等粗笔迹在边缘被裁掉的情况。

### English Release Notes

**Home thumbnail completeness fix**

- Home thumbnails now sample across the whole project timeline, keep the first and last strokes, and preserve representative strokes from the left, right, top, bottom, and largest canvas areas to avoid missing large-note content.
- Raised the home preview read budget so compact previews can show more real ink while still capping point counts for smooth list scrolling.
- Background maintenance regenerates richer preview data for existing notes, so older projects are repaired without manually resaving them.
- Thumbnail bounds now include pressure and wide-brush padding to reduce clipping for highlighter, brush, watercolor, eraser, and other thick strokes.

## v1.0.170 (build 171 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**安全环境兼容性优化**

- 安全环境守卫改为允许普通 VPN 和系统代理，使用网络加速、校园网、公司代理或正常代理时不再被禁止进入。
- 抓包、流量检查工具以及 Xposed/Hook/Frida 等高风险框架仍会被持续低内存监控并拦截。
- 减少 VPN 和代理网络能力扫描，降低启动和前台持续监控时的系统服务调用与内存压力。

### English Release Notes

**Security environment compatibility**

- The security guard now allows normal VPNs and system proxies, so network acceleration, campus networks, company proxies, and regular proxy use no longer block entry.
- Packet-capture, traffic-inspection tools, and high-risk Xposed/Hook/Frida frameworks are still monitored with the lightweight continuous guard and blocked.
- Reduced VPN and proxy capability scans to lower system-service calls and memory pressure during startup and foreground monitoring.

## v1.0.169 (build 170 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**Google Play 试用优惠与验签**

- 1 年高级版会员支持 Play Console 配置的 7 天免费试用优惠，购买时会优先使用 yearly 基础方案下的 trial-7d 优惠。
- 加入 Google Play 创收设置提供的 Base64 RSA 公钥，购买记录在开通高级版权益前会先进行签名校验。
- 优化 Billing 商品详情缓存、优惠选择和重复查询逻辑，降低进入设置页与购买状态同步时的内存和系统服务压力。

### English Release Notes

**Google Play trial offer and verification**

- The 1-year Premium membership now supports the 7-day free trial offer configured in Play Console and prioritizes the trial-7d offer under the yearly base plan.
- Added the Base64 RSA public key from Google Play monetization settings and verifies purchase signatures before granting Premium entitlement.
- Optimized Billing product-detail caching, offer selection, and repeated query behavior to reduce memory and system-service pressure when opening Settings or syncing purchases.

## v1.0.168 (build 169 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**修复设置页稳定性问题**

- 修复部分设备点击设置后可能因为本地化格式化异常导致闪退的问题，设置页文案格式化现在会自动降级保护。
- 优化 Google Play Billing 初始化逻辑，进入设置页时不再重复启动 Billing 查询，降低无 Play 账号或 Billing 不可用设备上的压力。
- Google Play 商品详情改为按商品类型分别查询，提高订阅商品和一次性商品同时存在时的兼容性。

### English Release Notes

**Settings stability fix**

- Fixed a possible Settings crash caused by localized formatting errors on some devices; Settings text formatting now falls back safely.
- Improved Google Play Billing initialization so entering Settings no longer restarts duplicate Billing queries, reducing pressure on devices without Play accounts or Billing support.
- Google Play product details are now queried by product type for better compatibility when subscription and one-time products coexist.

## v1.0.167 (build 168 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**多语言内购商品说明**

- 为 Google Play 1 年高级版和终身高级版补齐所有已支持语言的商品名称、说明和图标建议。
- 设置页的 Google Play 高级版区域现在会展示本地化产品说明，便于核对 Play Console 商品配置。
- 同步修正多语言高级版购买提示，明确 Google Play 购买和本地激活码可并存使用。

### English Release Notes

**Localized purchase product descriptions**

- Added localized names, descriptions, and icon guidance for the Google Play 1-year and lifetime Premium products across all supported languages.
- The Google Play Premium section in Settings now shows localized product descriptions for easier Play Console configuration checks.
- Updated multilingual Premium purchase guidance to clarify that Google Play purchases and local activation codes can coexist.

## v1.0.166 (build 167 - 2026-06-02)

### 涓枃鏇存柊璇存槑

**Google Play 内购高级版**

- 接入 Google Play Billing，高级版新增 1 年订阅商品和终身一次性非消耗型商品。
- 设置页新增 Google Play 高级版购买、恢复购买和商品 ID 提示，购买成功后会自动确认并开通高级版权益。
- Google Play 购买状态接入现有高级版体系，终身购买按永久高级版处理，年费订阅会根据 Google Play 查询结果同步有效状态。

### English Release Notes

**Google Play Premium purchases**

- Integrated Google Play Billing with a 1-year Premium subscription and a lifetime one-time non-consumable product.
- Added Google Play Premium purchase actions, purchase restore, and product ID guidance in Settings. Successful purchases are acknowledged and activate Premium automatically.
- Connected Google Play purchase state to the existing Premium entitlement system. Lifetime purchases count as permanent Premium, while yearly subscriptions sync from Google Play purchase queries.

## v1.0.165 (build 166 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**修复葡萄牙文和日文乱码**

- 修复设置页切换葡萄牙文和日文后部分语言名、WebDAV、邮箱等文本显示为问号的问题。
- 清理新增语言包里的异常占位字符，让语言切换后的设置页面显示更稳定。

### English Release Notes

**Portuguese and Japanese text cleanup**

- Fixed question-mark text shown in some Portuguese and Japanese labels after switching languages.
- Cleaned abnormal placeholder characters in the new language packs for more stable Settings display.

## v1.0.164 (build 165 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**新增葡萄牙文和日文**

- 语言系统新增葡萄牙文和日文，可在设置页语言区域展开后选择。
- 系统语言跟随模式新增葡萄牙语和日语识别，设备语言匹配时会自动切换对应文案。
- 桌面小组件新增葡萄牙文和日文资源，避免小组件标题、按钮和状态文本仍固定显示英文。

### English Release Notes

**Portuguese and Japanese language support**

- Added Portuguese and Japanese to the app language system, available from the expanded language section in Settings.
- System-language mode now recognizes Portuguese and Japanese device locales.
- Added Portuguese and Japanese resources for home-screen widgets so widget titles, actions, and states localize correctly.

## v1.0.163 (build 164 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**密码安全中心与横屏专注修复**

- 重做具体项目页的密码安全中心，移除旧的信息堆叠，改为评估当前项目安全性并给出 100 分安全评分。
- 密码安全中心新增强密码生成，可重新生成、复制，也可以直接将生成的强密码应用为项目密码。
- 修复横屏进入专注模式后点击右侧展开折叠按钮时显示竖屏工具栏的问题，现在会保持横屏侧边工具栏布局。

### English Release Notes

**Password safety center and landscape focus fix**

- Rebuilt the editor password safety center by removing the old information stack and replacing it with a 100-point project safety score.
- Added strong password generation in the safety center, with regenerate, copy, and apply-as-project-password actions.
- Fixed landscape focus mode so expanding the right-side toolbar keeps the landscape side-toolbar layout instead of showing the portrait toolbar.

## v1.0.162 (build 163 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**首页卡片避让新建按钮**

- 首页内容列表新增底部安全区，最后一张内容卡片会稳定停在右下角新建按钮上方。
- 删除项目或列表重新排列后，卡片不会被悬浮新建按钮遮挡，底部操作更容易点按。
- 归档和回收站页面没有新建按钮时保持原来的紧凑布局，不额外占用空间。

### English Release Notes

**Home cards avoid the create button**

- Added a bottom safe area to the home content list so the last card stays above the bottom-right create button.
- After deleting notes or reflowing the list, cards are no longer covered by the floating create button and remain easier to tap.
- Archive and recycle bin pages keep the original compact spacing when the create button is not shown.

## v1.0.161 (build 162 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**一键优化增强**

- 增强设置页一键优化，清理范围扩展到旧分享图、悬浮绘画截图、外部缓存、代码缓存和残留临时文件。
- 一键优化会继续清空手写缩略图内存缓存，并清理空缓存目录，减少长期使用后的空间占用。
- 诊断日志只清理残留临时文件和空目录，不删除正式崩溃日志、用户项目、本地账户或高级版状态。

### English Release Notes

**One-tap optimization upgrade**

- Expanded one-tap optimization to clean old share images, floating drawing screenshots, external cache, code cache, and leftover temporary files.
- One-tap optimization still clears the handwriting thumbnail memory cache and now removes empty cache folders to reduce long-term storage growth.
- Diagnostic logs only remove leftover temporary files and empty folders; real crash logs, user projects, local accounts, and Premium state are preserved.

## v1.0.160 (build 161 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**更新历史搜索与首页组织开关**

- 更新历史页面新增搜索框，支持按版本号、版本代码、日期、标题和更新内容快速查找历史版本。
- 设置页新增首页文件夹与分组开关，可按用户需要开启或关闭首页组织功能。
- 关闭首页文件夹与分组后，首页会隐藏文件夹筛选、分组标题、笔记组织标签和卡片菜单里的文件夹按钮。

### English Release Notes

**Update history search and home organization switch**

- Added search to Update history so versions can be found by version name, version code, date, title, and release notes.
- Added a Settings switch for home folders and groups so users can turn home organization on or off.
- When home folders and groups are off, the home page hides folder filters, group headers, organization labels, and the Folder action in note card menus.

## v1.0.159 (build 160 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**首页卡片菜单整理**

- 首页笔记卡片菜单中将复制按钮移动到文件夹按钮上方，常用操作更靠前。
- 原“整理笔记”入口改名为“文件夹”，表达更直接，也和首页文件夹功能保持一致。
- 移除首页笔记卡片菜单里的添加小组件按钮，减少重复入口和误触；小组件相关功能仍保留在设置等专门入口。

### English Release Notes

**Home card menu cleanup**

- Moved Duplicate above Folder in the home note card menu so the common action is easier to reach.
- Renamed the old organize-note entry to Folder for clearer wording and consistency with home folders.
- Removed Add widget from the home note card menu to reduce duplicate entry points and accidental taps; widget features remain available from dedicated settings surfaces.

## v1.0.158 (build 159 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**专注报告与项目完整性**

- 具体项目页面退出专注模式后会生成产出报告，展示专注时长、新增笔画、新增点数、产出速度和继续创作建议。
- 修复专注模式下展开工具栏会退出专注状态的问题，现在可以在专注状态中临时展开或收起工具栏。
- 本地数据库加密继续完善，新增加密的项目完整性凭证，保存、导入、备份和旧数据迁移都会自动处理。
- 密码安全中心增强完整性状态、加密范围、风险区域和建议操作显示，并支持刷新项目完整性凭证。
- VPN、抓包、Hook 环境持续低内存监控加入弱信号连续确认机制，减少正常用户被误伤，强风险环境仍会及时拦截。

### English Release Notes

**Focus reports and project integrity**

- Added a focus output report after leaving focus mode with duration, new strokes, new points, pace, and follow-up suggestions.
- Fixed focus mode toolbar expansion so opening the toolbar no longer exits focus mode.
- Improved local database encryption with encrypted project integrity proofs handled during saving, import, backup, and legacy migration.
- Enhanced the password safety center with integrity status, encryption scope, risk areas, recommended actions, and integrity proof refresh.
- Added confirmation gating to the low-memory VPN, capture, and Hook monitor so weak signals are verified while strong risk signals are still blocked quickly.

## v1.0.157 (build 158 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**首页整理与启动页增强**

- 首页新增文件夹与分组整理：项目可设置文件夹和分组，首页支持按文件夹筛选并按分组显示。
- 新建项目弹窗新增快速草稿入口，位于无限画布上方，可直接创建临时无限画布笔记。
- 设置页新增一键优化，可清理旧分享图、旧缩略图与临时缓存；WebDAV 同步入口移动到备份与恢复区域。
- 高级版自定义启动页增加极光、工作室、晨光、动态等模板，支持动态背景和每日一句编辑，并优化弹窗空间。

### English Release Notes

**Home organization and startup page upgrade**

- Added home folders and groups so notes can be organized, filtered by folder, and displayed by group.
- Added Quick Draft above Infinite Canvas in the new project dialog for fast temporary canvas notes.
- Added one-tap optimization in Settings to clean old share images, thumbnails, and temporary cache; moved WebDAV sync into Backup and restore.
- Enhanced Premium custom startup pages with Aurora, Studio, Dawn, and Dynamic templates, animated backgrounds, editable daily quotes, and a tighter dialog layout.

## v1.0.156 (build 157 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**绘制内核升级**

- 无限画布升级为 Tile Canvas 分块索引，拖动或缩放时优先绘制当前可见区域，减少大笔记的遍历和重绘压力。
- 打开大笔记时改为后台分段解析笔迹；多页笔记保存时复用页面 JSON 缓存，追加笔画时优先增量拼接，降低序列化开销。
- 增强触控笔防误触、压感曲线和笔尖预测，配合已有压感灵敏度设置提升书写跟手感。

### English Release Notes

**Drawing engine upgrade**

- Infinite canvas rendering now uses a Tile Canvas index so panning and zooming draw the currently visible area first, reducing traversal and redraw pressure on large notes.
- Large notes are parsed in background stroke segments; paged notes reuse page JSON caches, and append-only strokes use incremental JSON stitching where possible.
- Improved stylus palm rejection, pressure shaping, and tip prediction while keeping the existing pressure sensitivity control for a smoother writing feel.

## v1.0.155 (build 156 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**内存与预览性能优化**

- 首页、搜索和小组件选择中的手写缩略图缓存改为按点数、笔画和路径综合计重，减少复杂笔记预览长期占用内存。
- 软件收到系统内存压力、退到后台或低内存回调时，会主动收缩或清空手写预览缓存，降低长时间使用后的内存峰值。
- 悬浮绘画截图改为按目标尺寸直接绘制，并使用低内存位图；桌面小组件缩略图也改为不带透明通道的位图，减少临时 Bitmap 占用。

### English Release Notes

**Memory and preview performance tuning**

- Handwriting preview cache now weighs points, strokes, and paths together so complex previews do not occupy memory for too long.
- The app trims or clears preview cache on system memory pressure, background transitions, and low-memory callbacks.
- Floating ink screenshots now render directly at the target size with a lower-memory bitmap, and widget thumbnails use opaque bitmaps to reduce temporary Bitmap cost.

## v1.0.154 (build 155 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**低内存安全持续监控**

- 安全环境守卫升级为低内存持续监控：软件前台使用时保持轻量检测，发现 VPN、代理、抓包或 Hook 风险会立即切换到禁止页。
- 普通状态下采用快速轻量检测加低频深度扫描，已拦截状态下自动加快深度复检，关闭风险环境后可重新检测并恢复进入。
- 减少重复全量扫描和无变化重组，安全状态稳定时不刷新主界面，降低持续监控对内存、CPU 和界面流畅度的影响。

### English Release Notes

**Low-memory security monitoring**

- Upgraded the security guard into low-memory continuous monitoring while the app is visible, blocking immediately when VPN, proxy, capture, or Hook risks appear.
- Uses lightweight quick checks plus low-frequency deep scans, with faster deep rescans while blocked so normal environments can re-enter after retry.
- Reduced repeated full scans and unchanged recompositions to lower memory, CPU, and UI smoothness impact.

## v1.0.153 (build 154 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**安全环境识别与拦截**

- 启动入口新增安全环境守卫，检测到 VPN、系统代理、抓包或流量检查工具时会禁止继续进入软件。
- 增强 Xposed、LSPosed、EdXposed、Substrate 等 Hook 框架识别，结合已安装包、框架类、系统文件、进程映射和调用栈信号综合判断。
- 新增安全拦截页面，提供风险原因、重新检测和退出操作，并把拦截事件写入诊断日志，便于后续排查。

### English Release Notes

**Security environment guard**

- Added a startup security guard that blocks entry when VPN, system proxy, packet capture, or traffic inspection tools are detected.
- Improved Hook framework checks for Xposed, LSPosed, EdXposed, and Substrate using package, class, file, process-map, and stack signals.
- Added a security block screen with risk reasons, retry, and exit actions, plus diagnostic breadcrumbs for troubleshooting.

## v1.0.152 (build 153 - 2026-06-01)

### 涓枃鏇存柊璇存槑

**高级版手势快捷**

- 具体项目页面新增高级版手势快捷：三指轻点可快速重做上一笔撤回内容。
- 高级版用户可三指按住进入或退出专注模式，适合书写时快速隐藏工具栏并回到沉浸创作。
- 普通双指轻点撤回、双指缩放和平移保持原有逻辑，三指手势会避免参与绘画，减少误触。

### English Release Notes

**Premium gesture shortcuts**

- Added Premium gesture shortcuts in the project editor: three-finger tap quickly performs redo.
- Premium members can three-finger hold to enter or exit focus mode for faster immersive writing.
- Existing two-finger undo, pinch zoom, and canvas pan behavior remain unchanged, while three-finger gestures avoid drawing input.

## v1.0.151 (build 152 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**悬浮绘画按钮交互优化**

- 悬浮绘画按钮现在支持在软件表面拖动调整位置，并会限制在屏幕范围内，避免遮挡主要内容。
- 设置里的悬浮绘画按钮弹窗增强颜色编辑：左侧输入十六进制颜色时，右侧圆点会实时显示对应颜色。
- 点击颜色圆点可展开滑动调色，拖动圆点或调整 H/R/G/B 滑条都能同步修改按钮颜色。

### English Release Notes

**Floating ink interaction polish**

- The floating ink button can now be dragged around the app surface while staying inside the screen bounds.
- The floating ink settings dialog now previews typed hex colors immediately in the color circle.
- Tapping the color circle reveals sliders, and dragging the circle or adjusting H/R/G/B sliders updates the button color live.

## v1.0.150 (build 151 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**内存和性能优化**

- 首页创作概览改为轻量摘要状态，减少 Compose 层持有完整归档和回收站列表带来的内存占用。
- 缩略图渲染缓存进一步减重，首页、搜索、小组件选择和多页预览使用更轻的预览采样，列表滑动更稳。
- 分享图、悬浮绘画截图和自定义启动页导入在写出后更可靠地释放 Bitmap，并限制缓存文件数量，降低大图操作内存峰值。
- 首页、搜索、项目信息和分享文案中的时间格式器复用，减少列表刷新时的短生命周期对象创建。

### English Release Notes

**Memory and performance tuning**

- Changed the home writing overview to a lightweight summary state so Compose no longer holds full archive/recycle lists for the card.
- Reduced handwriting preview cache weight and lowered preview sampling for home, search, widget picking, and multipage thumbnails.
- Share images, floating ink screenshots, and custom startup-page imports now release Bitmaps more reliably and keep bounded cache files.
- Reused date formatters across home, search, project info, and share captions to reduce short-lived allocations during UI refreshes.

## v1.0.149 (build 150 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**创作概览整合归档和回收站**

- 首页创作概览现在会统一显示当前项目、今日更新、归档项目和回收站临近清理风险，普通用户也可使用。
- 归档页面和回收站页面移除原来的独立洞察卡，避免重复占用空间，批量恢复、清理和彻底删除操作保持可用。
- 设置里的创作概览开关继续控制该功能，并从高级版权益说明中移除归档洞察和回收站救援。

### English Release Notes

**Unified home writing overview**

- The home writing overview now combines active notes, today updates, archived notes, and recycle-bin cleanup risk for all users.
- Removed the separate archive insight and recycle rescue cards from archive/recycle pages while keeping batch restore, cleanup, and permanent delete actions.
- The existing writing overview setting still controls the feature, and archive/recycle insights are no longer listed as Premium-only benefits.

## v1.0.148 (build 149 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**高级版悬浮绘画按钮**

- 新增高级版悬浮绘画按钮，可在设置中开启或关闭，并自定义按钮样式、颜色和大小。
- 开启后软件表面会显示悬浮按钮，展开后可快速使用画笔、荧光墨水、套索轨迹、清空和截图分享功能。
- 优化具体项目页工具栏自动折叠逻辑，菜单、弹窗、滑动调参、书写和套索操作期间不会自动折叠，空闲后再智能收起。

### English Release Notes

**Premium floating ink button**

- Added a Premium floating ink button that can be enabled in Settings with customizable style, color, and size.
- When enabled, the app surface shows a floating button with quick pen, marker, lasso trail, clear, and screenshot sharing actions.
- Improved editor toolbar auto-collapse so menus, dialogs, slider adjustments, writing, and lasso work keep it open until the editor is idle.

## v1.0.147 (build 148 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**高级版智能优先排序**

- 首页排序二级菜单新增高级版智能优先排序，会综合最近更新、笔迹数量、多页项目、未加密大项目、归档沉淀和回收站风险进行排序。
- 非高级版用户点击智能优先排序会获得高级版提示，不会影响现有更新时间、创建时间、标题和笔画数量排序。
- 设置页高级版权益新增智能优先排序说明，并补齐中文、英文、法文、德文、西班牙文、印地文和阿拉伯文文案。

### English Release Notes

**Premium smart priority sorting**

- Added Premium smart priority sorting in the home Sort submenu, combining recency, ink volume, multipage projects, unprotected large notes, archive rest time, and recycle-bin risk.
- Free users now see a Premium prompt when tapping smart priority sorting, while existing Updated, Created, Title, and Stroke Count sorting remain unchanged.
- Premium benefits now include smart priority sorting, with localized copy for Chinese, English, French, German, Spanish, Hindi, and Arabic.

## v1.0.146 (build 147 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**高级版智能复习计划**

- 在具体项目页面的视图菜单新增高级版智能复习计划，会根据当前手写内容的笔迹量、颜色、重点区块和隐私状态生成本地复习建议。
- 智能复习计划支持一键为识别出的重点区块生成视图标记，也可以直接聚焦到第一个重点区块，帮助用户更快复盘大画布内容。
- 设置页高级版权益新增智能复习计划说明，并补齐中文、英文、法文、德文、西班牙文、印地文和阿拉伯文文案。

### English Release Notes

**Premium review planner**

- Added a Premium review planner in the editor Views menu that creates local review advice from ink volume, colors, key areas, and privacy state.
- The planner can create view marks for detected key areas or jump straight to the first key area for faster large-canvas review.
- Premium benefits now include the review planner, with localized copy for Chinese, English, French, German, Spanish, Hindi, and Arabic.

## v1.0.145 (build 146 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**套索识别与选区编辑增强**

- 增强套索选中后的手绘表格、柱状图、折线图和饼图识别，表格会检查网格交叉，图表会更好地区分坐标轴和有效数据笔迹。
- 套索选中后新增删除选区功能，可从笔盒里的套索工具或墨水菜单删除选中的笔迹，并保留重做恢复能力。
- 增强数学符号和公式标准化，新增分数结构识别、更多数字线段识别和单笔数字识别，套索选中公式后可更稳定地整理为标准墨迹。

### English Release Notes

**Lasso recognition and selection editing**

- Improved lasso-based recognition for hand-drawn tables, bar charts, line charts, and pie charts with stronger grid, axis, and data-stroke detection.
- Added delete selection for lasso-selected ink from the lasso tools and ink menu, while keeping deleted strokes in the redo stack for recovery.
- Enhanced math standardization with fraction layout recognition plus broader digit and symbol detection for selected handwritten formulas.

## v1.0.144 (build 145 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**完整新用户功能引导**

- 首次进入时的新手引导升级为分页式功能介绍，覆盖创建项目、书写工具、纸张与画布、智能墨水、归档回收站、分享小组件、安全备份和高级版能力。
- 增加进度提示、上一页、下一页和直接开始使用入口，让新用户可以快速浏览，也可以随时跳过进入软件。
- 引导内容复用现有多语言文案和功能名称，减少新增翻译负担，同时避免长文本堆叠导致按钮或文字遮挡。

### English Release Notes

**Complete new user feature guide**

- Upgraded first-run onboarding into a paged feature guide covering project creation, writing tools, paper and canvas modes, smart ink, archive and recycle bin, sharing widgets, security backups, and Premium features.
- Added progress indicators plus back, next, and start actions so new users can scan the guide quickly or enter the app immediately.
- The guide reuses existing localized feature names and descriptions to keep language coverage stable and reduce crowded long text.

## v1.0.143 (build 144 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**手绘表格与图表识别**

- 在具体项目页的墨水菜单中新增识别表格/图表，可将套索选中的手绘表格、柱状图、折线图和饼图转为标准化内容。
- 识别后会先打开可编辑数据视图，支持修改类型、名称和数值，再确认替换为电子表格或标准图表。
- 没有套索选区时会尝试处理最近书写的一段内容；未识别成功时会保留原始笔迹并提示用户重新选择。

### English Release Notes

**Hand-drawn table and chart recognition**

- Added table/chart recognition in the editor ink menu to convert lasso-selected hand-drawn tables, bar charts, line charts, and pie charts into standardized content.
- Detected data opens in an editable data view first, so you can adjust the type, labels, and values before replacing it with a spreadsheet or standard chart.
- When no lasso selection exists, the app tries the most recent handwriting segment; if recognition is uncertain, the original ink is preserved and a prompt is shown.

## v1.0.142 (build 143 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**手写数学公式与符号标准化**

- 在具体项目页的墨水菜单中新增标准化数学功能，可将手写数学符号整理成更规整的标准墨迹。
- 支持套索选区优先处理；没有选区时会自动处理最近书写的一小段，适合快速整理公式。
- 可识别常见数学符号与简单公式片段，包括加减、等号、乘除、比较符号、根号、圆周率、箭头、括号、0 和 1；未识别内容会原样保留。

### English Release Notes

**Handwritten math and symbol standardization**

- Added Standardize math in the editor ink menu to turn handwritten math symbols into cleaner standardized ink.
- Lasso selections are handled first; without a selection, the app processes the most recent short handwriting segment.
- Recognizes common math symbols and simple formula fragments, including plus, minus, equals, multiply, divide, comparisons, square root, pi, arrows, brackets, 0, and 1 while preserving unrecognized ink.

## v1.0.141 (build 142 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**内存与大画布性能优化**

- 优化套索移动、缩放、旋转时的笔迹变换流程，减少大项目编辑中的重复计算和临时对象分配。
- 形状识别现在会对超长笔迹进行限量采样判断，降低一笔完成后的卡顿风险，同时保留识别准确度。
- 优化橡皮擦压感半径计算，减少擦除时的内存抖动，让连续书写和修改更稳定。

### English Release Notes

**Memory and large-canvas performance tuning**

- Optimized lasso move, scale, and rotate transformations to reduce repeated calculation and temporary allocations in large projects.
- Shape recognition now samples very long strokes for detection, lowering after-stroke jank while keeping recognition quality.
- Tuned eraser pressure-radius calculation to reduce memory churn during editing and improve continuous writing stability.

## v1.0.140 (build 141 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**形状识别、专注模式与深色墨迹优化**

- 新增收笔后的形状识别，可将高置信度的一笔自动修正为直线、圆/椭圆、矩形、三角形、箭头和曲线。
- 形状修正支持复用精准吸附，对齐直线角度、正圆和正形比例；同时保留撤销、缩略图、小组件和分享图兼容。
- 专注模式隐藏完整工具栏，仅保留右侧展开按钮；深色纸张下普通墨迹自动提亮，荧光笔调整为深色半透明效果。

### English Release Notes

**Shape recognition, focus mode, and dark ink tuning**

- Added after-stroke shape recognition that can turn confident one-stroke drawings into lines, circles/ovals, rectangles, triangles, arrows, and curves.
- Recognized shapes reuse precision snap for aligned angles and square/circle proportions, while staying compatible with undo, thumbnails, widgets, and share images.
- Focus mode now hides the full toolbar and leaves only the right-side expand handle; dark paper automatically lifts regular ink and makes highlighter strokes darker and translucent.

## v1.0.139 (build 140 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**套索编辑与项目页防休眠**

- 工具栏新增套索工具，支持自由圈选和矩形选中已有笔迹。
- 选中后可直接拖动移动，并通过选区控制点缩放、旋转已有内容。
- 进入具体项目页后自动保持屏幕常亮，离开页面后恢复系统休眠策略。

### English Release Notes

**Lasso editing and screen-awake editor**

- Added a Lasso tool to the toolbar with freeform and rectangular selection for existing ink.
- Selected ink can now be moved directly, then scaled or rotated from visible selection handles.
- The project editor now keeps the screen awake while open and restores the system sleep behavior when leaving.

## v1.0.138 (build 139 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**压感、橡皮擦与纸张模板增强**

- 触控笔压感曲线继续优化，轻压、重压和快速书写时的粗细变化更明显，同时加强防误触时间窗。
- 橡皮擦新增笔迹橡皮模式，可直接移除被擦到的整条笔迹；普通橡皮仍保持覆盖式擦除。
- 新增清单、月历、习惯追踪和分镜纸张模板，并同步支持首页缩略图、小组件和分享图渲染。

### English Release Notes

**Stylus pressure, eraser, and paper templates**

- Stylus pressure shaping was refined so light, firm, and fast strokes vary more naturally, with a stronger palm-rejection window.
- The eraser now includes a Stroke eraser mode that removes touched ink strokes while keeping the original cover-style eraser available.
- Added checklist, month calendar, habit tracker, and storyboard paper templates across editor, thumbnails, widgets, and share images.

## v1.0.137 (build 138 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**可操作测量工具与精准吸附**

- 具体项目页的直尺和量角器支持拖动位置，并可通过控制点旋转角度，方便按当前书写区域摆放参考线。
- 新增高级版精准几何吸附：直线按 15 度角度吸附，矩形、椭圆和三角形可按正形比例生成。
- 测量辅助层仍只作为参考显示，不会写入项目笔迹；几何笔迹继续支持保存、撤销、缩略图和分享图。

### English Release Notes

**Interactive measurement guides and precision snap**

- The ruler and protractor on the project page can now be dragged and rotated with visible handles for easier placement.
- Premium adds precision geometry snap: lines snap to 15-degree angles, while rectangles, ovals, and triangles can keep square/circle proportions.
- Measurement guides remain visual-only and are not saved as ink; geometry strokes still support save, undo, thumbnails, and share images.

## v1.0.136 (build 137 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**几何工具、直尺与量角器**

- 具体项目页的笔盒新增直线、矩形、椭圆和三角形工具，拖动画布即可生成规整图案并支持撤销和保存。
- 笔盒内新增直尺和量角器辅助层开关，可在书写和绘图时显示半透明刻度参考，不会写入项目笔迹。
- 缩略图、小组件和分享图渲染同步支持几何笔迹，确保导出和首页预览保持一致。

### English Release Notes

**Geometry tools, ruler, and protractor**

- The project pen box now includes straight line, rectangle, oval, and triangle tools that create clean shapes and support undo/save.
- Ruler and protractor guide overlays were added to the pen box for translucent measurement references without changing note ink.
- Thumbnails, widgets, and share-image rendering now support geometry strokes so previews and exports stay consistent.

## v1.0.135 (build 136 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**项目页全屏开关**

- 设置页新增项目页全屏开关，进入具体项目页面后可自动隐藏状态栏，也可关闭保留系统状态栏。
- 切换页面或关闭开关时会恢复状态栏，避免影响首页、搜索、设置和更新历史页面。
- 该偏好使用加密 DataStore 保存，并加入备份设置字段，更新后默认开启。

### English Release Notes

**Project page fullscreen setting**

- Settings now has a Project page fullscreen switch that can hide the status bar when a project page opens.
- The status bar is restored when leaving the editor or turning the switch off, so Home, Search, Settings, and Update history stay normal.
- This preference is stored in encrypted DataStore and included in backup settings; it is enabled by default after update.

## v1.0.134 (build 135 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**诊断日志与崩溃排查增强**

- OneNotesLog 新增最近页面和关键操作路径记录，崩溃日志会带上用户进入崩溃前的主要路径。
- 崩溃与诊断文本补充设备信息、系统版本、软件版本、屏幕和内存状态，排查问题更直接。
- 设置页新增导出诊断日志，可导出检查点、崩溃日历、最近路径和相关日志文件，方便反馈问题。

### English Release Notes

**Diagnostic logging and crash investigation**

- OneNotesLog now records recent pages and key actions so crash logs include the main path before a failure.
- Crash and diagnostic text now includes device, OS, app version, screen, and memory state for clearer troubleshooting.
- Settings now includes Export diagnostic log with checkpoints, crash calendar, recent path, and related log files.

## v1.0.133 (build 134 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**新手引导、回收站批量管理与性能优化**

- 新手引导页增加画布选择、归档回收站管理、安全备份和高级版能力说明，新用户更容易理解核心流程。
- 归档页新增一键全部恢复；回收站新增全部恢复、清理过期和清空回收站，并在删除前加入确认弹窗。
- 小组件缩略图优先使用压缩预览笔迹，分享图生成复用绘制对象，继续减少大内容带来的短时内存分配。

### English Release Notes

**Onboarding, recycle-bin batch tools, and performance**

- The onboarding guide now explains canvas choices, archive and recycle-bin management, safe backups, and Premium capabilities.
- Archive now supports restoring all items; Recycle bin supports restore all, clean expired items, and empty bin with confirmation before deletion.
- Widget thumbnails now prefer compact preview ink, and share image rendering reuses drawing objects to reduce short-lived allocations.

## v1.0.132 (build 133 - 2026-05-31)

### 涓枃鏇存柊璇存槑

**内存与预览性能优化**

- 启动页和设置里的自定义启动页预览改用更省内存的采样解码策略，降低大图带来的内存峰值。
- 设置页启动图预览移到后台线程加载，减少进入弹窗时的界面卡顿。
- 多页项目保存与多页查看缩略图减少重复 JSON 转换，长笔记翻页和保存更轻快。

### English Release Notes

**Memory and preview performance improvements**

- Startup images and custom startup previews now use a lower-memory sampled decode path to reduce large-image memory peaks.
- Settings startup previews now load on a background thread to reduce dialog jank.
- Multi-page saving and page-overview thumbnails now avoid repeated JSON conversions for smoother large-note handling.

## v1.0.131 (build 132 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**多页项目视图与启动页弹窗适配**

- 设置里的自定义启动页弹窗改为按屏幕高度自适应，并优化颜色、图片和偏移控件的排列，减少小屏与横屏遮挡。
- 具体项目的视图菜单新增跳转页数功能，普通用户也可以使用。
- 多页纸张项目的视图菜单新增多页查看，可通过页面缩略图快速跳转到指定页面。

### English Release Notes

**Page navigation and startup dialog polish**

- The custom startup page dialog now adapts to screen height with safer layouts for color, image, and offset controls.
- The editor View menu now includes Jump to page for all users.
- Multi-page projects now include a page overview with thumbnails for quick page switching.

## v1.0.130 (build 131 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**新增无限画布与多页纸张项目**

- 新建项目时可选择无限画布或多页纸张，老项目默认保持无限画布模式。
- 多页纸张会保存每一页的手写内容、当前页和总页数，并在具体页面提供左右翻页和页码显示。
- 备份恢复、加密保存、首页缩略图和复制项目链路已兼容新的项目类型。

### English Release Notes

**Infinite canvas and multi-page projects**

- New projects can now be created as either infinite canvas or multi-page paper, while existing projects stay on infinite canvas.
- Multi-page projects save per-page handwriting, current page, and page count, with page switching and page indicators in the editor.
- Backup, encrypted local storage, home thumbnails, and duplicate-note flows now understand the new project type.

## v1.0.129 (build 130 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**设置页语言区域精简**

- 设置页语言区域默认只显示跟随系统、中文和英文，减少设置页主体空间占用。
- 法文、德文、西班牙文、印地文和阿拉伯文折叠到更多语言中，用户点击后即可展开选择。
- 新增多语言展开与收起文案，保持各语言环境下的设置体验清晰一致。

### English Release Notes

**Compact language settings**

- The Settings language area now shows only Follow system, Chinese, and English by default to save space.
- French, German, Spanish, Hindi, and Arabic are folded under More languages and can be expanded when needed.
- Added localized expand and collapse labels so the language selector stays clear in every supported language.

## v1.0.128 (build 129 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**设置页 WebDAV 入口精简**

- 设置页里的 WebDAV 同步区域改为单个按钮，减少设置页主体空间占用。
- 点击按钮后在弹窗里编辑 WebDAV 地址、用户名、密码和同步加密密码。
- 保存与立即同步功能继续保留在弹窗内，并沿用高级版校验、HTTPS 地址校验和最近同步时间显示。

### English Release Notes

**Compact WebDAV settings**

- Replaced the full WebDAV sync section in Settings with a single compact button.
- The button opens a dialog for editing the WebDAV URL, username, password, and sync encryption password.
- Save and Sync now remain available inside the dialog with the existing Premium checks, HTTPS validation, and last-sync display.

## v1.0.127 (build 128 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**设置页启动页入口精简**

- 设置页里的自定义启动页区域改为单个按钮，减少设置页主体空间占用。
- 点击按钮后在弹窗里编辑启动页样式、标题、颜色、导入图片和图片位置等完整配置。
- 保存逻辑继续沿用原来的高级版校验、颜色校验和旧图片清理，功能行为保持一致。

### English Release Notes

**Compact startup page settings**

- Replaced the full custom startup page section in Settings with a single compact button.
- The button opens a dialog for editing startup style, title, colors, imported image, and image placement.
- Saving still uses the existing Premium checks, color validation, and old-image cleanup behavior.

## v1.0.126 (build 127 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**内存与搜索性能优化**

- 自定义启动页图片改为后台采样解码，降低大图带来的启动卡顿和内存峰值。
- 首页、搜索结果和小组件选择页的手写缩略图使用更轻量的预览精度与有界缓存，减少滑动时重复解析和绘制成本。
- 搜索页空关键字不再拉取并渲染全部项目，搜索结果限制为最相关的前 80 条，提升响应速度。

### English Release Notes

**Memory and search performance**

- Custom startup images now decode in the background with sampling to reduce startup stalls and memory spikes.
- Home, search, and widget-picker handwriting previews use lighter preview detail and a bounded cache to reduce repeated parsing and drawing.
- Search no longer loads every note for an empty query, and results are capped to the first 80 matches for faster response.

## v1.0.125 (build 126 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**设置页体验优化**

- 新增创作概览开关，用户可以自行决定首页是否显示创作概览卡片。
- 设置页移除了高级区域里的默认模板、默认纸张、默认粗细和删除笔记保留入口，让页面更简洁。
- 高级版会员权益默认只展示核心内容，点击展开后可查看完整权益，减少设置页占用空间。

### English Release Notes

**Settings experience refinement**

- Added a writing overview toggle so users can choose whether the home overview card is shown.
- Removed the advanced defaults and deleted-note retention controls from Settings for a cleaner page.
- Premium benefits now show a compact preview first, with an expand action for the full list.

## v1.0.124 (build 125 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**首页创作概览**

- 首页新增所有用户可用的创作概览，可快速查看当前项目、今日更新、总笔画和已保护项目数量。
- 创作概览会根据当前项目状态给出整理建议，提醒用户复盘、置顶、归档或为较大的私密项目添加密码。
- 新增功能不改变项目数据结构，仅基于本地列表实时计算，并同步补充多语言文案。

### English Release Notes

**Home writing overview**

- Added a home writing overview for all users with active notes, today updates, total strokes, and protected note count.
- The overview provides local suggestions for reviewing, pinning, archiving, or protecting larger private notes.
- This feature does not change note storage; it is computed from the local note list and includes multilingual text.

## v1.0.123 (build 124 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版页面健康检查**

- 具体项目页面的视图菜单新增高级版页面健康检查，可分析留白、墨迹负载、颜色复杂度和隐私状态。
- 页面健康检查会生成健康分和下一步建议，帮助用户在复盘、整理或分享前判断页面是否过密、是否需要加密。
- 健康检查支持一键定位墨迹密集区域，并同步更新高级版权益和多语言文案。

### English Release Notes

**Premium page health check**

- Added a Premium page health check in the editor View menu to analyze whitespace, ink load, color complexity, and privacy.
- The check produces a health score and next-step suggestion before reviewing, organizing, or sharing dense pages.
- The dialog can focus the densest ink area and updates Premium benefits plus multilingual text.

## v1.0.122 (build 123 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**桌面小组件规格与取消激活确认**

- 应用内添加桌面小组件时支持选择紧凑、标准、宽屏和大号四种规格，设置页也可以直接发起添加小组件请求。
- 桌面小组件刷新范围扩展到所有规格，并为渲染、解密和配置列表增加异常兜底，降低小组件无响应风险。
- 取消高级版激活前新增确认弹窗，明确提示权益会重新锁定但项目内容不会删除。

### English Release Notes

**Widget sizes and deactivation confirmation**

- In-app widget creation now supports compact, standard, wide, and large sizes, and Settings can also start a widget add request.
- Widget refresh now covers every size, with safer rendering, decryption, and configuration fallbacks to reduce unresponsive widgets.
- Added a confirmation dialog before deactivating Premium, explaining that benefits lock again while notes remain saved.

## v1.0.121 (build 122 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版启动页图片自定义**

- 高级版自定义启动页支持导入本地图片作为启动背景，并复制到应用私有目录保存。
- 新增启动页图片编辑能力，可调整图片透明度、缩放、水平位置和垂直位置，设置页预览会实时显示效果。
- 启动页设置继续使用加密 DataStore 保存，并同步更新高级版权益和多语言文案。

### English Release Notes

**Premium startup page image customization**

- Premium custom startup pages now support importing a local image as the startup background and copying it into private app storage.
- Added visual editing controls for image opacity, scale, horizontal position, and vertical position, with a live preview in Settings.
- Startup page settings continue to use encrypted DataStore storage, with updated Premium benefits and multilingual text.

## v1.0.120 (build 121 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版智能文案编辑与密码安全中心增强**

- 高级版会员在项目分享图弹窗中可以直接修改智能分享文案，并支持一键恢复自动文案。
- 具体项目页面密码菜单中的“密码安全中心 高级”已改为“密码安全中心”，减少菜单文字拥挤。
- 密码安全中心新增安全指数、泄露敏感度、恢复提醒、分享守卫和本地安全指纹，帮助分享或归档前快速判断风险。

### English Release Notes

**Premium caption editing and password safety upgrades**

- Premium members can now edit smart share captions directly in the project share image dialog and restore the automatic caption with one tap.
- The editor password menu now shows Password safety center without the extra Premium suffix to reduce menu crowding.
- Password safety center now includes a safety score, exposure level, recovery reminder, share guard, and local safety fingerprint before sharing or archiving.

## v1.0.119 (build 120 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版归档洞察与回收站救援**

- 归档页面新增高级版归档洞察，汇总归档项目数量、笔迹规模、密码保护数量和最长沉睡时间。
- 回收站页面新增高级版回收站救援，检查可恢复笔迹、受保护项目和临近自动清理的删除项目。
- 首页接入高级版状态和回收站保留天数，更新高级版权益与多语言文案，继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Premium archive insight and recycle rescue**

- Added Premium archive insight with archived note count, ink size, protected note count, and longest resting time.
- Added Premium recycle rescue with recoverable ink, protected deleted notes, and near-cleanup risk checks.
- Connected Premium state and recycle-bin retention to Home, updated Premium benefits and multilingual text, and kept release minification and resource shrinking enabled.

## v1.0.118 (build 119 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版智能分享文案**

- 项目分享弹窗新增高级版智能分享文案，可在生成分享图时自动附带项目标题、笔画、颜色、更新时间和隐私状态。
- 分享前可以预览并开关智能文案，关闭后仍按原流程只分享项目图。
- 同步更新高级版权益和多语言文案，继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Premium smart share captions**

- Added premium smart share captions to the project share dialog, including title, stroke count, color count, update time, and privacy status.
- The caption can be previewed and toggled before sharing, while image-only sharing remains available.
- Updated premium benefits and multilingual text while keeping release minification and resource shrinking enabled.

## v1.0.117 (build 118 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版专注仪表盘**

- 具体页面专注模式新增高级版专注仪表盘，可实时查看本次专注时长、新增笔画和新增点数。
- 专注仪表盘会根据本次书写状态给出继续书写、保持沉浸或整理复习的建议。
- 进入专注模式时自动收起工具栏，减少遮挡并保持原有专注模式对所有用户可用。

### English Release Notes

**Premium focus dashboard**

- Added a premium focus dashboard in editor focus mode with live session time, new stroke count, and new point count.
- The dashboard now gives contextual focus advice for starting, staying in flow, or organizing after a longer session.
- Entering focus mode now collapses the toolbar automatically while keeping the original focus mode available to all users.

## v1.0.116 (build 117 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版项目档案洞察**

- 具体页面的项目信息中新增高级版项目档案，展示项目时长、估算书写量、墨迹复杂度、颜色使用和隐私状态。
- 项目档案会根据当前内容自动给出整理、密码保护或继续创作建议。
- 同步更新高级版权益和多语言文案，继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Premium project dossier insights**

- Added a premium project dossier inside Project info with age, estimated handwriting time, ink complexity, color usage, and privacy status.
- The dossier now gives contextual advice for organization, password protection, or continued writing.
- Updated premium benefits and multilingual text while keeping release minification and resource shrinking enabled.

## v1.0.115 (build 116 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版密码安全中心**

- 具体页面新增高级版密码安全中心，可查看项目是否受密码保护、内容规模和本地加密说明。
- 设置或修改项目密码时新增密码强度提示，帮助用户选择更稳妥的密码。
- 高级版权益和多语言文案同步更新，继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Premium password safety center**

- Added a premium password safety center in the editor to review protection status, content scale, and local encryption details.
- Added password strength feedback when setting or changing a project password.
- Updated premium benefits and multilingual text while keeping release minification and resource shrinking enabled.

## v1.0.114 (build 115 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**好评跳转链接调整**

- 将好评提醒中的去好评按钮固定跳转到 Google Play 应用商店链接。
- 使用 https://play.google.com/store/apps/details?id=com.tourisain.onenotes 作为评价入口。
- 继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Rating link update**

- Updated the rating prompt button to open the Google Play store listing directly.
- Uses https://play.google.com/store/apps/details?id=com.tourisain.onenotes as the review entry.
- Release minification and resource shrinking remain enabled.

## v1.0.113 (build 114 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版自定义启动页**

- 新增高级版会员自定义启动页功能，可设置启动页标题、副标题、样式、背景色和强调色。
- 设置页面新增启动页预览，保存前即可查看大致效果。
- 启动页配置会保存在本地，并使用本地加密偏好存储保存自定义文案和颜色。
- 非高级版用户可以看到入口，但需要激活高级版后才能保存和启用。
- 继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Premium custom startup page**

- Added a Premium custom startup page with editable title, subtitle, style, background color, and accent color.
- Added a startup page preview in Settings so users can review the look before saving.
- Startup page settings are stored locally with encrypted preference storage for custom text and colors.
- Free users can see the entry, but saving and enabling requires Premium.
- Release minification and resource shrinking remain enabled.

## v1.0.112 (build 113 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**随机好评提醒**

- 新增用户进入软件后 30 秒到 3 天之间随机时间触发的好评提醒。
- 提醒仅在用户完成隐私协议和引导页后才会调度，避免打断首次进入流程。
- 用户可选择去好评、稍后提醒或不再提醒；选择去好评或不再提醒后不会继续打扰。
- 选择稍后提醒会重新随机延后，提醒状态会保存在本地。
- 继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Random rating reminder**

- Added a rating reminder that appears at a random time between 30 seconds and 3 days after entering the app.
- The reminder is scheduled only after privacy consent and onboarding are completed, avoiding first-run interruption.
- Users can rate now, be reminded later, or stop future reminders; rating now and never ask again both stop future prompts.
- Later reschedules the reminder locally with another random delay.
- Release minification and resource shrinking remain enabled.

## v1.0.111 (build 112 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**分享弹窗滚动修复**

- 修复具体页面分享图弹窗中模板过多时无法滑动查看全部分享样式的问题。
- 分享弹窗正文现在会限制最大高度并支持垂直滚动，底部取消和创建按钮保持可见。
- 继续保持 release 混淆和资源压缩开启。

### English Release Notes

**Share dialog scrolling fix**

- Fixed the editor share image dialog so all share styles can be viewed when many templates are available.
- The share dialog content now has a maximum height and vertical scrolling while keeping action buttons visible.
- Release minification and resource shrinking remain enabled.

## v1.0.110 (build 111 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**更多分享图版式**

- 继续新增封面书、故事卡、票据和分栏海报四种分享图模板。
- 新增模板使用不同的内容层级、边框、标题区域和信息栏，不再只是颜色变化。
- 票据模板加入撕纸边和虚线信息结构，故事卡模板更适合竖屏分享。
- 封面书和分栏海报模板强化标题展示，适合展示完整项目主题。
- 同步补齐新增模板的多语言名称，并继续保持 release 混淆和资源压缩开启。

### English Release Notes

**More share image layouts**

- Added four more share image templates: Cover book, Story card, Receipt, and Split poster.
- The new templates use different content hierarchy, frames, title areas, and info bars instead of color-only changes.
- Receipt adds torn edges and dashed metadata sections; Story card is tuned for vertical sharing.
- Cover book and Split poster emphasize the project title for stronger topic presentation.
- Added localized names for the new templates and kept release minification and resource shrinking enabled.

## v1.0.109 (build 110 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**分享图版式增强**

- 分享图模板不再只是颜色变化，新增杂志分栏、拍立得、胶片条和便签墙四种不同构图。
- 不同模板现在会使用不同的标题位置、预览区域、边框和装饰结构。
- 继续保留原有分享模板，并新增更多模板预览色，方便快速识别不同风格。
- 多语言文案同步补齐新增分享模板名称。
- 发行版继续保持混淆和资源压缩开启。

### English Release Notes

**Share image layout upgrades**

- Share image templates now change layout, not only colors, with Magazine split, Polaroid, Film strip, and Sticky wall designs.
- Different templates now use different title placement, preview areas, frames, and decorative structures.
- Existing share templates remain available, with added preview colors for the new styles.
- Added localized names for the new share templates.
- Release minification and resource shrinking remain enabled.

## v1.0.108 (build 109 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**笔刷、手势与分享增强**

- 新增书法笔、蜡笔和水彩笔三种高级版笔刷，并为笔盒补充更多常用墨水颜色。
- 高级版会员现在可以在具体页面直接输入自定义笔刷颜色。
- 增强双指单击撤回上一笔的识别逻辑，降低缩放和平移时误触撤回的概率。
- 新增画廊相框、霓虹笔记和便签纸三种分享图模板。
- 同步更新首页缩略图、小组件和分享图的新增笔刷渲染效果。

### English Release Notes

**Brushes, gestures, and sharing**

- Added three Premium brushes: Calligraphy, Crayon, and Watercolor, plus more common ink colors in the pen box.
- Premium members can now enter a custom brush color directly in the editor.
- Improved two-finger tap undo detection to reduce accidental undo while pinching or panning.
- Added Gallery frame, Neon note, and Memo sheet share image templates.
- Updated home thumbnails, widgets, and share image rendering for the new brush styles.

## v1.0.107 (build 108 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**高级版智能整理**

- 具体页面新增高级版智能整理功能，可本地分析当前画布并拆分为可复盘的内容区块。
- 智能整理会显示笔迹数量、点数、颜色数量和区块数量，帮助快速判断项目结构。
- 支持在智能整理面板中直接聚焦某个区块，快速跳转到重点内容。
- 支持一键把分析出的区块生成视图标记，便于后续复盘和讲解。
- 设置页高级版权益同步加入智能整理说明，继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium smart organizer**

- Added a Premium smart organizer in the editor to locally analyze the canvas into reviewable content sections.
- The organizer shows stroke count, point count, color count, and section count for a quick structure read.
- Added direct section focusing from the organizer panel for faster navigation to key content.
- Added one-tap view mark creation from the analyzed sections for review and walkthroughs.
- Updated the Premium benefits list and kept release minification and resource shrinking enabled.

## v1.0.106 (build 107 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**WebDAV 同步增强**

- WebDAV 同步会在目标云盘位置自动创建 OneNotes 文件夹。
- 加密备份固定同步到 OneNotes/onenotes-backup.json，避免用户误填文件名导致同步位置混乱。
- 兼容旧的 WebDAV 文件地址设置，若检测到文件地址会自动使用其上级目录作为同步目标。
- 改用更稳定的网络请求实现，提升 MKCOL、下载和上传在不同 WebDAV 服务上的兼容性。
- 保存和同步入口增加 HTTPS 地址校验，继续保留 release 混淆和资源压缩。

### English Release Notes

**WebDAV sync improvements**

- WebDAV sync now creates a OneNotes folder in the target cloud drive location.
- Encrypted backups are synced to OneNotes/onenotes-backup.json to keep the remote location predictable.
- Existing WebDAV file URL settings remain compatible by using their parent folder as the sync target.
- Switched to a more reliable network implementation for MKCOL, download, and upload compatibility.
- Added HTTPS validation to the save and sync actions, while keeping release minification and resource shrinking enabled.

## v1.0.105 (build 106 - 2026-05-30)

### 涓枃鏇存柊璇存槑

**稳定性增强**

- 增强崩溃日志写入的防重入保护，避免异常处理过程中再次异常导致日志丢失。
- 优化 OneNotesLog 写入流程，使用临时文件写入后替换，降低日志半写入风险。
- 限制重复检查点写入频率和单个日志大小，减少启动阶段频繁写入带来的额外负担。
- 本地笔记数据解析失败时记录非致命日志，并跳过异常项目，避免影响其它项目加载。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Stability improvements**

- Added re-entry protection for crash logging so logs are less likely to be lost if handling fails.
- Improved OneNotesLog writes by using temporary files before replacing the final log file.
- Limited repeated checkpoint writes and individual log size to reduce extra startup overhead.
- Added non-fatal diagnostics when local note parsing fails, while allowing other projects to keep loading.
- Kept release minification and resource shrinking enabled.

## v1.0.104 (build 105 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**高级版复盘路径**

- 新增高级版复盘路径，可根据主要笔迹区域高亮画布流向并用节点连接重点内容。
- 在具体页面视图菜单中加入复盘路径开关，适合讲解、复盘和整理大画布笔记。
- 复盘路径仅作为本地视觉辅助，不改变项目内容和保存数据。
- 设置页高级版权益同步增加复盘路径说明。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium review path**

- Added a Premium review path that highlights the main canvas flow with connected nodes across key ink areas.
- Added a View menu toggle for walkthroughs, review sessions, and organizing large canvas notes.
- The review path is a local visual aid and does not change project data.
- Updated the Premium benefits list with review path support.
- Kept release minification and resource shrinking enabled.

## v1.0.103 (build 104 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**搜索结果缩略图**

- 搜索结果新增手写内容缩略图，所有用户都可以更快通过内容外观找到项目。
- 搜索结果同步显示更新时间，减少打开错误项目的概率。
- 受密码保护和空白项目会显示清晰状态，不暴露受保护内容。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Search result thumbnails**

- Added handwriting thumbnails to search results so all users can identify projects by their visual content faster.
- Search results now show the last updated time to reduce accidental openings.
- Protected and blank notes show clear states without exposing protected content.
- Kept release minification and resource shrinking enabled.

## v1.0.102 (build 103 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**触控笔压感增强**

- 增强触控笔压感曲线，轻压、重压和快速书写时的线宽变化更自然。
- 加入触控笔速度补偿与压感平滑，减少压感跳变，让连续书写更稳定。
- 触控笔书写后短时间过滤非触控笔输入，降低手掌或误触干扰。
- 同步优化编辑器、首页缩略图、小组件和分享图的压感渲染效果。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Enhanced stylus pressure**

- Improved the stylus pressure curve so light, heavy, and fast strokes vary width more naturally.
- Added speed compensation and pressure smoothing for steadier continuous handwriting.
- Filtered non-stylus input briefly after stylus writing to reduce palm and accidental touches.
- Aligned pressure rendering across the editor, home thumbnails, widgets, and share images.
- Kept release minification and resource shrinking enabled.

## v1.0.101 (build 102 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**内存优化与项目颜色**

- 优化编辑器撤回/重做缓存，限制重做栈规模，减少长时间书写后的内存占用。
- 清理离开、删除、优化笔迹等流程中的触摸点缓冲，避免大笔迹后保留过大的临时数组。
- 新增所有用户可用的项目颜色，在墨水工具栏中快速复用当前项目最近使用的颜色。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Memory optimization and project colors**

- Optimized editor undo and redo caching by limiting the redo stack size to reduce memory use after long writing sessions.
- Released touch-point buffers after leaving, deleting, and optimizing notes so large temporary arrays are not retained.
- Added project colors for all users, making recently used project ink colors available directly in the Ink toolbar.
- Kept release minification and resource shrinking enabled.

## v1.0.100 (build 101 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**高级版演示聚光灯**

- 新增高级版演示聚光灯，可在具体页面突出中央讲解区域并轻微压暗画布边缘。
- 在视图菜单中加入演示聚光灯开关，适合展示笔记、复盘内容和会议讲解。
- 演示聚光灯仅作为本地视觉辅助，不改变项目内容和保存数据。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium presentation spotlight**

- Added a Premium presentation spotlight that highlights the central explanation area and gently dims canvas edges.
- Added a View menu toggle for note walkthroughs, review sessions, and meeting presentations.
- The spotlight is a local visual aid and does not change project data.
- Kept release minification and resource shrinking enabled.

## v1.0.99 (build 100 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**高级版构图辅助线**

- 新增高级版构图辅助线，可在具体页面画布上叠加三分线、黄金比例线、边距框和对角参考线。
- 在视图菜单中加入构图辅助线开关，用于排版、分栏、复盘整理和视觉平衡。
- 构图辅助线只作为本地显示辅助，不改变项目内容和保存数据。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium composition guides**

- Added Premium composition guides with thirds, golden-ratio, margin, and diagonal references.
- Added a View menu toggle for layout, grouping, review organization, and visual balance.
- Composition guides are local visual aids and do not change project data.
- Kept release minification and resource shrinking enabled.

## v1.0.98 (build 99 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**高级版智能调色板**

- 新增高级版智能调色板，可根据当前纸张颜色和已有笔迹生成多组书写配色。
- 在具体页面墨水菜单中加入智能调色板入口，点击色块即可切换当前画笔颜色。
- 设置页高级版权益同步增加智能书写配色说明。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium smart palettes**

- Added Premium smart palettes generated from the current paper color and existing ink.
- Added a Smart palette entry under the editor Ink menu, with one-tap color application.
- Updated the Premium benefits list with smart writing palettes.
- Kept release minification and resource shrinking enabled.

## v1.0.97 (build 98 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**双指撤回与会员安全增强**

- 增强具体页面双指轻点撤回，短按且没有缩放或移动意图时才触发撤回。
- 本地项目密码盐和密码哈希纳入内容加密，旧数据会在后台自动加密升级。
- 高级版会员状态增加账号、设备、激活码哈希和本地完整性凭证校验，减少误判和篡改风险。
- 继续保留 release 混淆和资源压缩，并优化本地安全校验的兼容迁移。

### English Release Notes

**Two-finger undo and Premium security**

- Improved two-finger tap undo on the editor page so it only triggers on a short non-pan, non-zoom tap.
- Encrypted local note password salts and password hashes, with automatic background migration for old data.
- Added account, device, activation-hash, and local integrity proof checks for Premium entitlement recognition.
- Kept release minification and resource shrinking enabled while preserving migration compatibility.

## v1.0.96 (build 97 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**退出确认与工具栏合并**

- 新增退出软件确认弹窗，在首页返回或退出入口会先询问是否退出。
- 具体页面工具栏将笔盒、笔宽和墨水分组移动到同一行。
- 工具栏右侧折叠展开按钮同步移动到同一行右侧，减少占用空间。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Exit confirmation and toolbar merge**

- Added an exit confirmation dialog when leaving the app from the home/root flow.
- Merged the pen box, stroke width, and ink toolbar group into one row on the editor page.
- Moved the toolbar collapse/expand control to the same right-side row to save space.
- Kept release minification and resource shrinking enabled.

## v1.0.95 (build 96 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**高级版获取方式提示**

- 在设置页高级版定价下方新增醒目的获取方式提示。
- 明确高级版本唯一获取方式是通过邮箱联系开发者。
- 提供两个联系邮箱：tourisain@163.com 和 grllq458@gmail.com。
- 继续保留 release 混淆和资源压缩。

### English Release Notes

**Premium contact notice**

- Added a prominent Premium access notice below Premium pricing in Settings.
- Clarified that Premium can only be obtained by contacting the developer by email.
- Added both contact emails: tourisain@163.com and grllq458@gmail.com.
- Kept release minification and resource shrinking enabled.

## v1.0.94 (build 95 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**崩溃日历日志与稳定性优化**

- 新增 OneNotesLog 崩溃日历记录，崩溃后会按日期文件夹自动生成日志文本。
- 每月自动追加 crash_calendar 索引，便于按日期快速定位崩溃记录。
- 日志抓取脚本同步适配 OneNotesLog 目录，方便连接设备后一键导出。
- 限制历史崩溃日志数量并清理空日期目录，降低长期使用的存储和内存压力。

### English Release Notes

**Crash calendar logs and stability improvements**

- Added OneNotesLog crash calendar records with date-based crash log folders.
- Added monthly crash_calendar index files for quicker diagnostics by date.
- Updated the log collection script to export the OneNotesLog directory.
- Limited retained crash logs and cleaned empty date folders to reduce long-term storage pressure.

## v1.0.93 (build 94 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**彻底修复多语言导致的开屏崩溃**

- 将 260 多项文案容器从超长 data class 改为 Map 背后存储，避免生成超长构造函数和 copy 方法。
- 各语言文案改为按需 lazy 初始化，降低开屏内存占用并避免静态初始化过大。
- 继续保留 release 混淆和资源压缩，不通过关闭正式包保护来规避问题。
- 保留崩溃日志和抓取脚本，便于后续继续定位真实设备问题。

### English Release Notes

**Fixed multilingual startup verifier crash**

- Reworked the 260+ key localized text container from a huge data class to a map-backed class.
- Changed language tables to lazy initialization to reduce startup memory and avoid oversized static initialization.
- Kept release minification and resource shrinking enabled instead of disabling production protection.
- Kept crash logging and the capture script for future real-device diagnostics.

## v1.0.92 (build 93 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**修复 release 开屏闪退**

- 抓取并定位 release 开屏页闪退日志，确认为多语言字符串容器经 R8 优化后触发 ART VerifyError。
- 对多语言字符串容器添加精准 keep 规则，保留 release 混淆和资源压缩，同时避免开屏校验崩溃。
- 保留早期崩溃日志记录和抓取脚本，后续异常可直接导出 logcat 与本地崩溃文件。
- 继续增强启动、首页、搜索、设置和具体页面的数据流稳定性。

### English Release Notes

**Fixed release splash crash**

- Captured and identified the release splash crash as an ART VerifyError caused by R8 optimizing the large localized string container.
- Added targeted keep rules for the i18n string container while keeping release minification and resource shrinking enabled.
- Kept early crash logging and the capture script for future logcat and local crash-file collection.
- Further hardened launch, home, search, settings, and editor state flows.

## v1.0.91 (build 92 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**开屏闪退日志与稳定性增强**

- 恢复 release 混淆和资源压缩，保持正式包体积与安全策略。
- 新增应用最早期崩溃日志记录，开屏页闪退也会写入本地日志并输出到 logcat。
- 为启动、首页、搜索、设置和具体页面的数据流增加异常兜底，降低旧数据或异常状态导致的闪退风险。
- 继续减少启动阶段不必要的失败扩散，提升正式包稳定性和内存表现。

### English Release Notes

**Splash crash logging and stability hardening**

- Restored release minification and resource shrinking for production size and protection.
- Added earliest-stage crash logging so splash-time crashes are written locally and emitted to logcat.
- Added defensive fallbacks for launch, home, search, settings, and editor state flows.
- Reduced failure propagation during startup to improve release stability and memory behavior.

## v1.0.90 (build 91 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**Release 启动稳定性修复**

- 临时关闭 release 混淆和资源压缩，排除混淆导致开屏页崩溃的风险。
- 继续保留开屏页 DataStore、系统语言和更新弹窗的安全兜底。
- 优先保证发行版能稳定进入软件，后续再在确认稳定后重新压缩体积。

### English Release Notes

**Release launch stability fix**

- Temporarily disabled release minification and resource shrinking to rule out splash-time crashes caused by obfuscation.
- Kept safe fallbacks for DataStore, system locale, and update dialogs on launch.
- Prioritized stable release startup first; package size optimization can be reintroduced after stability is confirmed.

## v1.0.89 (build 90 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**开屏页闪退修复**

- 增加设置 DataStore 损坏文件自动恢复，避免开屏阶段读取偏好时闪退。
- 系统语言解析改为安全读取，避免部分设备 locale 异常导致首屏崩溃。
- 更新弹窗读取和写入增加保护，首屏状态异常时回退到默认英文文案。

### English Release Notes

**Splash screen crash fix**

- Added automatic recovery for corrupted settings DataStore files to prevent splash-time crashes.
- Made system language resolution safe for devices with unusual locale data.
- Protected update dialog read/write paths and fall back to default English text when launch state is abnormal.

## v1.0.88 (build 89 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**全面降低启动闪退风险**

- 主入口不再提前打开笔记数据库，启动阶段只加载必要设置。
- 数据库迁移失败时允许安全重建数据库，避免旧库损坏导致无法进入软件。
- 继续收紧启动链路，减少旧数据、旧版本升级和数据库异常对进入软件的影响。

### English Release Notes

**Lower launch crash risk**

- The app entry point no longer opens the notes database before it is needed.
- Database migration failures can now safely rebuild the database instead of blocking launch.
- Further reduced launch-time dependency on old data, upgrade state, and database integrity.

## v1.0.87 (build 88 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**继续修复启动闪退**

- 旧数据库迁移改为幂等补列，避免重复加列或缺列导致启动崩溃。
- 首页笔记列表读取增加异常兜底，单条旧数据异常不会拖垮首页。
- 旧笔记后台加密迁移增加保护，迁移失败不会导致软件进入即退出。

### English Release Notes

**Additional launch crash fixes**

- Made old database migrations idempotent to avoid launch crashes from duplicate or missing columns.
- Hardened home note list loading so a single bad legacy row cannot crash the home screen.
- Protected the background legacy note encryption upgrade so migration failures do not close the app on launch.

## v1.0.86 (build 87 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**启动闪退修复**

- 修复旧版本偏好数据与新版加密字段类型不一致时，进入软件即闪退的问题。
- 增加旧数据库 1 到当前版本的兼容迁移，降低老安装包升级后的启动风险。
- 继续增强启动阶段设置、试用、高级版激活相关数据的读取容错。

### English Release Notes

**Launch crash fix**

- Fixed a launch crash caused by old preference data using different types than the newer encrypted fields.
- Added a compatibility migration from database version 1 to the current schema for older installs.
- Further hardened launch-time loading for settings, trials, and Premium activation data.

## v1.0.85 (build 86 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**完整多语言与启动稳定性修复**

- 法文、德文、西班牙文、印地文和阿拉伯文现在覆盖软件内完整文案。
- 修复新增语言只翻译部分页面、部分按钮仍显示英文的问题。
- 增强设置偏好读取容错，避免旧数据或异常偏好导致进入软件时闪退。

### English Release Notes

**Complete localization and launch stability**

- French, German, Spanish, Hindi, and Arabic now cover the full in-app text set.
- Fixed new languages falling back to English on some pages and buttons.
- Hardened settings preference loading to prevent launch crashes from old or invalid data.

## v1.0.84 (build 85 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**多语言与安全增强**

- 语言系统新增法文、德文、西班牙文、印地文和阿拉伯文。
- 备份密码升级为强密码要求，并提高备份加密迭代强度。
- 备份导入增加文件大小、版本、盐值和密文边界校验。
- 本地账户、7 天试用和高级版激活增加仓库层校验与失败次数限制。

### English Release Notes

**More languages and security hardening**

- Added French, German, Spanish, Hindi, and Arabic language options.
- Upgraded backups to require strong passwords and stronger encryption iterations.
- Added backup import checks for file size, version, salt, IV, and payload bounds.
- Hardened local account, 7-day trial, and Premium activation validation with attempt limits.

## v1.0.83 (build 84 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**缩略图、工具栏与搜索优化**

- 修复首页缩略图内容偏向右下角且显示过小的问题。
- 具体页面工具栏折叠按钮并入第一行，不再独占一行空间。
- 搜索输入响应更快，并限制超长搜索词减少无效计算。

### English Release Notes

**Thumbnail, toolbar, and search improvements**

- Fixed home thumbnails appearing too small and shifted to the lower-right corner.
- Moved the editor toolbar collapse button into the first toolbar row.
- Made search input respond faster and limited very long queries to reduce unnecessary work.

## v1.0.82 (build 83 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**账户校验与首页菜单优化**

- 首页顶栏菜单调整为排序、归档、回收站、更新历史。
- 本地账户名称仅允许文字或汉字，禁止符号、数字和空格。
- 邮箱必须符合邮箱规范，否则不能保存账户、开启 7 天试用或激活高级版。
- 继续加强账户校验的仓库层防护，避免非法账户绕过界面限制。

### English Release Notes

**Account validation and home menu cleanup**

- Reordered the home top bar menu to Sort, Archive, Recycle Bin, and Update History.
- Local account names now allow letters only and reject symbols, numbers, and spaces.
- Email addresses must be valid before saving the account, starting the trial, or activating Premium.
- Added repository-level account validation to prevent invalid accounts from bypassing the UI.

## v1.0.81 (build 82 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**更新记录与性能优化**

- 新增更新完成后首次进入的软件更新内容弹窗。
- 首页顶栏菜单新增更新历史入口，可随时查看版本记录。
- 页面状态改为生命周期感知收集，减少后台无效刷新和内存占用。
- 继续优化首页与小组件缩略图的居中显示和预览性能。

### English Release Notes

**Update history and performance improvements**

- Added a first-launch update dialog after installing a new version.
- Added update history to the home top bar menu.
- Changed screen state collection to lifecycle-aware collection to reduce background work.
- Continued optimizing centered note previews for the home page and widgets.

## v1.0.80 (build 81 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**缩略图和桌面小组件增强**

- 首页缩略图按手写内容居中并合理放大显示。
- 桌面小组件预览改为完整适配显示，减少裁切。
- 设置页新增桌面小组件数量提示和刷新入口。

### English Release Notes

**Thumbnail and widget improvements**

- Centered and scaled handwriting thumbnails on the home page.
- Changed widget previews to fit content instead of cropping.
- Added widget count and refresh controls in settings.

## v1.0.79 (build 80 - 2026-05-29)

### 涓枃鏇存柊璇存槑

**工具栏布局收敛**

- 修复高级版会员权益文本前缀乱码。
- 精简具体页面工具栏重复按钮，笔刷统一放入笔盒。
- 减少工具栏内边距和重复入口，提升可用空间。

### English Release Notes

**Toolbar layout cleanup**

- Fixed garbled bullet text in Premium benefits.
- Removed duplicate editor toolbar buttons and kept tools in the pen box.
- Reduced toolbar spacing and duplicate entry points.

