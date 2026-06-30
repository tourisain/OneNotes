<div align="center">

# OneNotes

**私密、安全、流畅的手写笔记工具**
**Private, secure, and fluid handwriting notes**

[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://www.android.com)
[![Language](https://img.shields.io/badge/Language-Kotlin-orange.svg)](https://kotlinlang.org)
[![UI](https://img.shields.io/badge/UI-Jetpack%20Compose-blue.svg)](https://developer.android.com/jetpack/compose)
[![License](https://img.shields.io/badge/License-Proprietary-lightgrey.svg)](#license)

</div>

---

## 中文介绍

OneNotes 是一款面向手写记录、灵感整理和长期项目沉淀的 Android 本地笔记应用。它围绕「写得顺手、找得方便、数据更安心」设计，适合课堂笔记、会议记录、草稿推演、读书摘录、日常计划和创意整理。

### 核心特性

- **低延迟手写引擎** — 支持触控笔压感、倾斜、方位角，笔迹跟手流畅，防误触优化
- **无限画布与多页项目** — 自由缩放、移动、分页，适合长篇笔记和大型推演
- **专业工具集** — 直尺、量角器、几何工具、套索选择、形状识别、手绘表格识别
- **数学笔迹标准化** — 手写数学公式与符号自动标准化
- **多语言支持** — 中文、英文、法文、德文、西班牙文、印地文、阿拉伯文、葡萄牙文、日文
- **本地隐私优先** — 笔记内容加密存储，支持项目级密码保护
- **加密备份与恢复** — 本地加密备份，WebDAV 加密同步（高级版）
- **桌面小组件** — 多种尺寸的桌面快捷笔记小组件
- **分享图生成** — 精美分享图片，多种版式与社交模板
- **性能预算策略** — 大画布分块渲染、低内存自动降级、后台任务智能调度

### 高级版功能

- 更多笔刷与纸张模板
- 自定义纸张颜色
- 精准缩放与项目密码
- WebDAV 加密同步
- 智能复习计划与专注仪表盘
- 创意洞察与归档分析
- 精美分享图与智能文案
- 演示聚光灯与构图辅助线

---

## English Introduction

OneNotes is a local Android note-taking app designed for handwriting, idea organization, and long-term project building. It is built around three principles: **smooth writing, easy finding, and data safety** — ideal for class notes, meeting records, draft reasoning, reading excerpts, daily planning, and creative work.

### Key Features

- **Low-latency writing engine** — Stylus pressure, tilt, and azimuth support with palm rejection and live ink smoothing
- **Infinite canvas & multi-page projects** — Free zoom, pan, and pagination for long notes and complex diagrams
- **Professional toolset** — Ruler, protractor, geometry tools, lasso selection, shape recognition, hand-drawn table recognition
- **Math ink normalization** — Handwritten math formulas and symbols are automatically standardized
- **Multilingual support** — Chinese, English, French, German, Spanish, Hindi, Arabic, Portuguese, Japanese
- **Local-first privacy** — Note content is encrypted at rest; project-level password protection supported
- **Encrypted backup & restore** — Local encrypted backups; WebDAV encrypted sync (Premium)
- **Home screen widgets** — Multiple widget sizes for quick note access
- **Share image generation** — Beautiful share images with multiple layouts and social templates
- **Performance budget policy** — Tile-based canvas rendering, automatic low-memory degradation, smart background scheduling

### Premium Features

- More brushes and paper templates
- Custom paper colors
- Precision zoom and project passwords
- WebDAV encrypted sync
- Smart review planner and focus dashboard
- Creative insights and archive analysis
- Premium share images and smart captions
- Presentation spotlight and composition guides

---

## 下载 / Download

最新版本请前往 [Releases](../../releases) 页面下载 APK 文件。

For the latest version, please visit the [Releases](../../releases) page to download the APK.

### 系统要求 / System Requirements

- Android 8.0 (API 26) 或更高版本 / or higher
- 支持触控笔的设备体验更佳 / Stylus-supported devices recommended

---

## 技术栈 / Tech Stack

| 技术 / Technology | 说明 / Description |
|---|---|
| Kotlin | 主要开发语言 / Primary language |
| Jetpack Compose | 声明式 UI 框架 / Declarative UI framework |
| Hilt | 依赖注入 / Dependency injection |
| Room | 本地数据库 / Local database |
| DataStore | 加密偏好存储 / Encrypted preferences |
| Coroutines | 异步编程 / Asynchronous programming |
| OkHttp | 网络通信 / Network communication |
| Google Play Billing | 内购支付 / In-app purchases |
| Firebase | 基础服务 / Base services |
| R8 / ProGuard | 代码混淆与压缩 / Code shrinking and obfuscation |

---

## 构建 / Build

### 环境要求 / Prerequisites

- Android Studio (Ladybug 或更高版本 / or later)
- JDK 17
- Android SDK 35
- Gradle 9.0+

### 构建步骤 / Build Steps

```bash
# 克隆仓库 / Clone the repository
git clone https://github.com/your-username/OneNotes.git
cd OneNotes

# 配置签名 / Configure signing
# 在项目根目录创建 local.properties，添加：
# Create local.properties in project root with:
# sdk.dir=path/to/android/sdk
# onenotes.release.storeFile=path/to/keystore
# onenotes.release.storePassword=your_password
# onenotes.release.keyAlias=your_alias
# onenotes.release.keyPassword=your_password

# 编译 Release 版本 / Build release
./gradlew :app:assembleRelease :app:bundleRelease --no-daemon --console=plain
```

构建产物位于 / Build outputs are at:
- APK: `app/build/outputs/apk/release/app-release.apk`
- AAB: `app/build/outputs/bundle/release/app-release.aab`

---

## 项目结构 / Project Structure

```
app/src/main/java/com/tourisain/onenotes/
├── MainActivity.kt              # 根 Activity / Root activity
├── NotesApplication.kt           # Application 入口 / Application entry
├── core/                         # 核心策略 / Core policies
├── data/
│   ├── billing/                  # Google Play 内购 / Billing
│   ├── local/                    # Room 数据库 / Database
│   ├── logging/                  # 崩溃日志 / Crash logging
│   ├── repository/               # 数据仓库 / Repositories
│   ├── security/                 # 加密与安全 / Crypto & security
│   ├── settings/                 # 设置存储 / Settings storage
│   ├── sync/                     # WebDAV 同步 / Sync
│   └── update/                   # 应用更新 / App update
├── di/                           # Hilt 依赖注入 / DI
├── domain/                       # 领域模型 / Domain models
├── ui/
│   ├── changelog/                # 更新历史 / Update history
│   ├── components/               # 通用组件 / Shared components
│   ├── editor/                   # 编辑器 / Editor
│   ├── home/                     # 首页 / Home screen
│   ├── i18n/                     # 多语言 / Internationalization
│   ├── onboarding/               # 新手引导 / Onboarding
│   ├── search/                   # 搜索 / Search
│   ├── settings/                 # 设置 / Settings
│   └── theme/                    # 主题 / Theme
└── widget/                       # 桌面小组件 / Home screen widgets
```

---

## 隐私与安全 / Privacy & Security

### 中文

OneNotes 重视本地隐私与数据安全：

- 笔记内容、本地账户、高级版激活信息以加密方式保存
- 重要项目可设置独立密码
- 备份和恢复使用加密传输
- WebDAV 同步使用加密通道
- 不收集不必要的用户数据
- 不包含第三方追踪 SDK

### English

OneNotes prioritizes local privacy and data security:

- Note content, local accounts, and premium activation data are encrypted at rest
- Important projects can be protected with individual passwords
- Backups and restores use encrypted transfer
- WebDAV sync uses encrypted channels
- No unnecessary user data collection
- No third-party tracking SDKs

---

## 支持的语言 / Supported Languages

| 语言 / Language | 代码 / Code |
|---|---|
| 中文 | zh |
| English | en |
| Français | fr |
| Deutsch | de |
| Español | es |
| हिन्दी | hi |
| العربية | ar |
| Português | pt |
| 日本語 | ja |

---

## 更新记录 / Changelog

详细的版本更新记录请参阅 [CHANGELOG.md](CHANGELOG.md)。

For detailed version history, please see [CHANGELOG.md](CHANGELOG.md).

---

## 开源说明 / License

本项目为专有软件，源代码公开供参考学习，但不允许未经授权的商业使用。

This project is proprietary software. Source code is publicly available for reference and learning, but unauthorized commercial use is not permitted.

---

<div align="center">

**OneNotes** — 写得顺手，找得方便，数据更安心

*Write smoothly. Find easily. Keep data safe.*

</div>
