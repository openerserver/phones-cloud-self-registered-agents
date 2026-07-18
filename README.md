# Phones Cloud 自注册被控端

本仓库集中提供 Phones Cloud（蜂壳云）自注册被控端的使用说明与官方下载入口。

自注册被控端安装在你自己的 Windows 电脑、Mac 或 Android 真机上。登录 Phones Cloud 账号并注册本机后，设备会出现在统一设备列表中，可从 Web 控制台或 iOS 客户端进行远程访问。

> 当前 Windows、Mac 和 Android 客户端均处于测试阶段，功能、稳定性和使用流程仍在持续优化，请勿用于关键生产业务。

## 快速下载

| 客户端 | 当前版本 | 系统要求 | 安装包 | 下载 | 校验文件 |
| --- | --- | --- | --- | --- | --- |
| Windows Agent | v0.1.0 测试版 | Windows 10 1809+ / Windows 11 x64 | 未签名 ZIP，约 96 MiB | [下载 Windows ZIP](https://api2.phones-cloud.cn/apks/phonescloud-windows-agent-last-win-x64.zip) | [SHA-256](https://api2.phones-cloud.cn/apks/phonescloud-windows-agent-0.1.0-test-win-x64.zip.sha256) |
| Mac Agent | v0.2.7 测试版 | macOS 13+，Apple Silicon / Intel | 已签名、公证的 Universal DMG，约 2.8 MB | [下载 Mac DMG](https://api2.phones-cloud.cn/apks/phonescloud-mac-agent-last.dmg) | [SHA-256](https://api2.phones-cloud.cn/apks/phonescloud-mac-agent-0.2.7.dmg.sha256) |
| Android Tunnel Client | v1.1.1 测试版 | Android 12+ | APK，约 6.5 MB | [下载 Android APK](https://api2.phones-cloud.cn/apks/phonescloud-android-last.apk) | — |

## 使用流程

1. 在需要远程控制的设备上下载对应客户端。
2. 安装或解压客户端，并使用 Phones Cloud 账号登录。
3. 为当前设备命名，完成首次设备注册和中继区域选择。
4. 按系统提示授予屏幕、输入、音频或后台运行等必要权限。
5. 确认设备在线和中继连接正常，再从 [Web 设备控制台](https://www.phones-cloud.cn/dashboard/devices) 或 iOS 客户端发起远控。

## Windows Agent

1. 下载 ZIP 后完整解压到固定文件夹，不要直接在压缩包内运行。
2. 双击 `PhonesCloud.WindowsAgent.App.exe` 启动管理界面。
3. 此包为自包含版本，无需另外安装 .NET Runtime、Windows App SDK 或 Visual C++ 运行库。
4. 当前版本尚未进行代码签名。Windows SmartScreen 可能显示“未知发布者”；请确认下载域名和 SHA-256 一致后，选择“更多信息 → 仍要运行”。
5. 登录账号并完成本机注册，保持交互式用户会话和 Agent 运行。

详细说明：[Windows Agent 页面](https://www.phones-cloud.cn/self-registered-device/windows-agent)

## Mac Agent

1. 下载并打开 DMG，将 Phones Cloud Mac Agent 拖入“应用程序”文件夹。
2. 启动应用并登录 Phones Cloud 账号。
3. 按提示开启“屏幕与系统音频录制”和“辅助功能”权限。
4. 确认中继连接正常后，可关闭主窗口并让 Agent 在菜单栏保持在线。

v0.2.7 已完成 Developer ID 签名、Apple 公证和 stapling。

详细说明：[Mac Agent 页面](https://www.phones-cloud.cn/self-registered-device/mac-agent)

## Android Tunnel Client

1. 在 Android 手机上下载 APK，并仅对下载所用浏览器临时允许“安装未知应用”。
2. 安装完成后登录账号并添加当前手机。
3. 允许通知、后台运行和开机启动，并将电池策略设置为“不限制”。
4. 首次启动远控时，推荐使用无线调试配对；无法使用时，可通过电脑 USB ADB 开启 5555 端口。
5. 当客户端同时显示设备在线、隧道已连接和远控已就绪时，接入完成。

当前 APK 使用测试签名。若出现签名冲突，请先联系支持，不要直接卸载以免本地状态丢失。

详细说明：[Android Tunnel Client 页面](https://www.phones-cloud.cn/self-registered-device/android-tunnel-client)

## 安全说明

- 仅从本仓库列出的 Phones Cloud 官方域名下载安装包。
- Windows 测试包未签名，请使用 SHA-256 校验完整性。
- Mac 测试包已使用 Developer ID 签名并通过 Apple 公证。
- Android APK 当前使用测试签名，升级时请继续使用官网最新版本。
- 退出登录、删除设备或卸载客户端可能需要重新完成设备注册。

## 相关入口

- [自注册被控端总览](https://www.phones-cloud.cn/self-registered-device)
- [统一下载中心](https://www.phones-cloud.cn/download)
- [价格方案](https://www.phones-cloud.cn/self-registered-device#pricing)
- [联系与反馈](https://www.phones-cloud.cn/contact)

## 费用

客户端下载免费。自注册被控端的远程服务续费支持免费续期、包月和包年方案；当前中文站推荐包年套餐，最终价格、有效期和支付方式以控制台下单页为准。
