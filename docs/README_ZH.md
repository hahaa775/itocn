# Ito 简体中文版本

此仓库基于 [AtiinLabs/Ito](https://github.com/AtiinLabs/Ito) Fork，新增简体中文界面。原版英文保留，系统语言不是简体中文时自动回退英文。

## 在 Xcode 中打开和安装

1. 在 GitHub 的 **Code → Download ZIP** 下载完整工程，解压（不要只下载某个文件）。也可以使用 `git clone https://github.com/hahaa775/itocn.git`。
2. 双击根目录下的 **`Ito.xcodeproj`**。原项目要求 **Xcode 26.2 或更新版本**。
3. 等待 Swift Package Manager 自动完成依赖解析（首次打开需要网络）。
4. 选中 `Ito` Target → **Signing & Capabilities**，打开 **Automatically manage signing**，选择你自己的 Apple Developer Team。若提示 Bundle ID 冲突，可以改为独有的 ID（例如 `com.hahaa775.itocn`），但这会被系统视为另一款 App，不会自动继承原版的数据。
5. 选择 iPhone 或 iPad 真机，按 **⌘R** 构建安装。

## 自动切换语言

- 当 iPhone / iPad 的首选语言是 **简体中文**，Ito 显示中文。
- 使用英语或其他未提供翻译的语言时，App 显示英文。
- 不需要在 App 内设置语言开关。可以在 iOS「设置 → App → Ito → 语言」（若系统提供）单独调整 App 语言。
- 插件返回的作品标题、简介、来源描述等内容不属于 App 的固定文案，仍由插件和数据源决定。

## 翻译文件

- `Localization/zh-Hans.lproj/Localizable.strings`：中文界面文案。
- `Localization/zh-Hans.lproj/Localizable.json`：数量与复数形式。
- `Localization/zh-Hans.lproj/InfoPlist.strings`：文件类型名称。

原项目已经具备 `Install translations` 构建阶段；新语言会在编译时写入 `Ito.app/zh-Hans.lproj`，未翻译内容回退英语。无需把中文直接写入 Swift 视图文件或修改 `.xcstrings` 英文源目录。

### 验证

```bash
python3 .github/scripts/localization.py check
```

中文版仅新增本地化文案与 Xcode 项目的语言声明，未修改插件、网络与阅读器逻辑。翻译欢迎反馈校正。项目遵守原仓库 MPL-2.0 协议。
