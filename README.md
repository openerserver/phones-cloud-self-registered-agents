# Phones Cloud 自注册被控端

Phones Cloud 自注册被控端让你把自己的 Windows 电脑、Mac 或 Android 真机注册到统一设备列表，并通过 Web 控制台或 iOS 客户端发起远程访问。

[中文官网](https://www.phones-cloud.cn/) · [自注册被控端总览](https://www.phones-cloud.cn/self-registered-device) · [设备控制台](https://www.phones-cloud.cn/dashboard/devices) · [问题反馈](https://github.com/openerserver/phones-cloud-self-registered-agents/issues)

> [!IMPORTANT]
> 本仓库是 Phones Cloud 客户端的官方分发与公开文档仓库，不包含 Windows、macOS 或 Android 客户端源代码。当前客户端均为测试阶段的专有软件；仓库公开可见不表示客户端已经开源，也不自动授予修改或再分发权。下载和使用前请阅读[服务条款](https://www.phones-cloud.cn/terms)与[隐私政策](https://www.phones-cloud.cn/privacy)。

## 支持状态

| 客户端 | 当前版本 | 状态 | 系统要求 | 签名状态 |
| --- | --- | --- | --- | --- |
| Windows Agent | v0.1.0 | 测试中 | Windows 10 1809+ / Windows 11 x64 | 暂未代码签名 |
| Mac Agent | v0.2.7 | 测试中 | macOS 13+，Apple Silicon / Intel | Developer ID 签名、Apple 公证 |
| Android Tunnel Client | v1.1.1 | 测试中 | Android 12+ | 测试签名 |

> 三个客户端仍在持续优化，请勿用于关键生产业务。各平台独立发布版本，版本号不要求保持一致。

## 下载

| 客户端 | 安装包 | SHA-256 |
| --- | --- | --- |
| Windows Agent v0.1.0 | [下载 Windows ZIP](https://api2.phones-cloud.cn/apks/phonescloud-windows-agent-0.1.0-test-win-x64.zip) | [查看校验值](./CHECKSUMS.txt) |
| Mac Agent v0.2.7 | [下载 Universal DMG](https://api2.phones-cloud.cn/apks/phonescloud-mac-agent-0.2.7.dmg) | [查看校验值](./CHECKSUMS.txt) |
| Android Tunnel Client v1.1.1 | [下载 Android APK](https://api2.phones-cloud.cn/apks/phonescloud-android-1.1.1.apk) | [查看校验值](./CHECKSUMS.txt) |

始终指向最新测试版的下载地址：[Windows ZIP](https://api2.phones-cloud.cn/apks/phonescloud-windows-agent-last-win-x64.zip) · [Mac DMG](https://api2.phones-cloud.cn/apks/phonescloud-mac-agent-last.dmg) · [Android APK](https://api2.phones-cloud.cn/apks/phonescloud-android-last.apk)

## 快速开始

1. 在需要被远程控制的设备上下载对应客户端。
2. 安装或完整解压客户端，使用 Phones Cloud 账号登录。
3. 为当前设备命名，完成首次设备注册和中继区域选择。
4. 按系统提示授予屏幕、输入、音频或后台运行等必要权限。
5. 确认设备在线、中继连接正常，再从 [Web 设备控制台](https://www.phones-cloud.cn/dashboard/devices) 或 iOS 客户端发起远控。

## 平台说明

### Windows Agent

1. 下载 ZIP 后完整解压到固定文件夹，不要直接在压缩包内运行。
2. 双击 `PhonesCloud.WindowsAgent.App.exe` 启动管理界面。
3. 安装包为自包含版本，无需另外安装 .NET Runtime、Windows App SDK 或 Visual C++ 运行库。
4. 当前版本尚未代码签名，也无需申请测试资格。Windows SmartScreen 可能显示“未知发布者”；核对下载域名与 SHA-256 后，可选择“更多信息 → 仍要运行”。
5. 登录并注册本机，保持交互式用户会话和 Agent 运行。

[查看 Windows Agent 完整说明](https://www.phones-cloud.cn/self-registered-device/windows-agent)

### Mac Agent

1. 打开 DMG，将 Phones Cloud Mac Agent 拖入“应用程序”文件夹。
2. 启动应用并登录 Phones Cloud 账号。
3. 按提示开启“屏幕与系统音频录制”和“辅助功能”权限。
4. 确认中继连接正常后，可关闭主窗口并让 Agent 在菜单栏保持在线。

v0.2.7 已完成 Developer ID 签名、Apple 公证和 stapling。

[查看 Mac Agent 完整说明](https://www.phones-cloud.cn/self-registered-device/mac-agent)

### Android Tunnel Client

1. 下载 APK，仅对下载所用浏览器临时允许“安装未知应用”。
2. 安装完成后登录账号并添加当前手机。
3. 允许通知、后台运行和开机启动，将电池策略设置为“不限制”。
4. 首次启动远控时推荐使用无线调试配对；无法使用时，可通过电脑 USB ADB 开启 5555 端口。
5. 当客户端同时显示设备在线、隧道已连接和远控已就绪时，接入完成。

当前 APK 使用测试签名。若出现签名冲突，请先联系支持，不要直接卸载，以免本地状态丢失。

[查看 Android Tunnel Client 完整说明](https://www.phones-cloud.cn/self-registered-device/android-tunnel-client)

## 已知限制

- 三端目前均为测试版，功能、协议和界面可能继续调整。
- Windows 测试包暂未代码签名，SmartScreen 警告属于当前已知情况。
- Android APK 使用测试签名，后续切换正式签名时会提前提供迁移说明。
- 网络质量、中继区域和系统权限会直接影响连接稳定性与可用功能。
- 退出登录、删除设备或卸载客户端后，可能需要重新完成设备注册。

## 安全与隐私

- 仅从本仓库列出的 Phones Cloud 官方域名下载安装包。
- 安装前请核对 [CHECKSUMS.txt](./CHECKSUMS.txt) 中的 SHA-256；校验值可以发现下载损坏，但不能代替系统签名验证。
- 只授予实际需要的系统权限，不使用客户端时可在系统设置中撤销。
- 安全漏洞、远控绕过或凭据泄露请按 [SECURITY.md](./SECURITY.md) 私下报告，不要创建公开 Issue。
- 公开 Issue 中请勿粘贴访问令牌、设备标识、账号信息或未经处理的完整日志。

## 支持与反馈

- 可公开讨论的安装问题、兼容性问题和功能建议：提交 [GitHub Issue](https://github.com/openerserver/phones-cloud-self-registered-agents/issues)。
- 账号、订单、付款或包含隐私数据的问题：通过[联系页面](https://www.phones-cloud.cn/contact)处理。
- 文档修改方式见 [CONTRIBUTING.md](./CONTRIBUTING.md)。
- 当前公开版本记录见 [CHANGELOG.md](./CHANGELOG.md)。

## 商业服务

客户端可免费下载。设备注册、远程连接服务的可用方案、有效期和付费规则请以[官网价格方案](https://www.phones-cloud.cn/self-registered-device#pricing)与控制台下单页为准。

## 仓库范围与许可

本仓库用于发布使用文档、版本信息、校验值和官方下载入口，不是客户端源代码仓库。本仓库公开可见不代表客户端软件已经开源；除非另有书面说明，客户端的修改、再分发和商业使用均应遵守 Phones Cloud 服务条款。若未来开放源代码或调整许可，将通过独立文件和正式公告说明。
