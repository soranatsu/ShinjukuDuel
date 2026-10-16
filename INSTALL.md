# 安装与操作

## Windows

1. 下载 `ShinjukuDuel-0.3.1-windows-x64.zip`。
2. 完整解压到一个文件夹，不要在压缩包中直接运行，也不要只复制 EXE。
3. 运行 `ShinjukuDuel.exe`。同目录中的 `ShinjukuDuel_Data`、`MonoBleedingEdge` 和 DLL 等文件需要保留。
4. 在首页选择角色、难度或引导教学。可以先进入设置降低音乐音量并调整鼠标灵敏度。

0.3.2-preview、0.3.3-preview、0.3.4-preview 和 0.3.5-preview 联机包：下载表中的对应 preview ZIP，完整解压后运行同名 EXE。0.3.5-preview 必须双方使用同一构建，协议为 `shinjuku-lan-035-v1`，旧端会被拒绝；Windows 主验收 429 项已通过，受限压力场景仍有 2 项快照新鲜度超限。

最新联机预览版请下载 `ShinjukuDuel-0.3.6-windows-x64.zip`，按上述方式解压运行。双方必须使用 0.3.6。手机默认布局已重新适配；原有自定义布局会保留，可在布局设置选择“默认”启用新版排列。

Windows 自动检查共 415 项通过。Android 与 macOS 包体核验已完成，真机与跨设备联机体验尚未验证，详见 [验证记录](Verification/0.3.6/Network-Verification-0.3.6.md)。

## Android

- 下载并安装 `ShinjukuDuel-0.3.1-android-arm64.apk`。
- 要求 Android 8.0（API 26）及以上，ARM64 设备，横屏。
- 系统提示时允许当前下载/文件管理应用安装此 APK。
- 左侧摇杆移动，右侧空白区域转向，右侧按钮释放术式、治疗或防御。
- 设置 → 操作设置 → 编辑按键布局，可拖动按钮和摇杆，并将尺寸调整为 70%—160%；手机与平板分别保存布局。
- 若覆盖安装提示签名冲突，先确认旧包来源及是否需要保留本地设置；卸载旧版会清除其本地数据。不要为了更新而直接删除整个游戏目录。

当前稳定 APK 为 0.3.1、versionCode 为 16，使用既有 Android Debug 签名。公开 0.3.1 为离线单人版本。0.3.5-preview Android APK 已完成 ARM64 构建与元数据核验，versionName 为 0.3.5、versionCode 为 20；Android 真机及跨设备联机仍待验收。证书 SHA-256：`0f3b7fc7871f6eb012258a53c85c74119d0e3c38f7ffdfd9160389af55a2048e`；APK SHA-256：`070166081B7D871BF415714CFDCD6867543424AADA5483B7BF4EAC2F468C15FF`。

0.3.6-preview Android versionCode 为 21，目标 ARM64、API 26—36，包含当前战斗参数、R 蓄力网络恢复、移动端特效和按屏幕适配的默认手游布局；APK 构建核验已完成（SHA-256 `5DADC3FDE2A19EC97A65BDE958FD68037B268C23E01A4C49DC87A0EFF6EDA093`），Windows 触控预览与截图通过，Android 真机及跨设备联机仍待验证。

0.3.2-preview Android 包面向 ARM64、API 26—36。尚未进行 Android 真机验证；遇到安装或触控问题请优先使用稳定版 0.3.1。预览包不是应用商店签名版本。

## macOS Universal 预览包

- 0.3.6-preview 更新战斗、联机和世界同步范围；协议为 `shinjuku-lan-036-v1`，macOS Universal 已构建并核验 x86_64+arm64 架构、版本 0.3.6、最低 macOS 12.0；Mac 实机、Developer ID 签名、公证和跨设备联机仍未验证。

- 下载 `ShinjukuDuel-0.3.6-macos-universal.zip`，解压后保留完整的 `ShinjukuDuel.app`。
- 支持 Intel 与 Apple Silicon，最低 macOS 12.0；可将 `.app` 拖到“应用程序”或用户文件夹，不需要安装 Unity。
- 0.3.5 的 Relay/LAN 功能使用 `shinjuku-lan-035-v1` 协议与 Windows、Android 配套；macOS Universal 已完成构建并核验原生 x86_64+arm64 Mach-O、最低 macOS 12.0。ZIP 大小 94,604,128 bytes，SHA-256：`B099BF924218991A0D0B0CAFBD4E402CC7FD1CF55BE714E0C2E2C183B42085AF`；尚无 Mac 实机或跨平台联机测试，且无 Developer ID 签名和公证。
- 当前预览包没有 Apple Developer ID 签名和公证。首次被拦截时，先尝试打开一次，再到“系统设置 > 隐私与安全性”选择“仍要打开”。不需要关闭 Gatekeeper。
- 详细操作、触控板按键重绑和权限修复见 [MACOS.md](MACOS.md)。

## 0.3.2-preview 局域网联机

1. 两台设备连接到同一局域网。
2. 主机在主界面选择“联机对战”，选择角色后选择 LAN 创建，并记下显示的本机地址和端口。
3. 另一端选择 LAN 加入，输入主机 IP 和端口；Android 端使用屏幕键盘手动输入。
4. 双方分别选择角色并点击准备。双方准备完成后才会进入对战。
5. 对战结束后，双方都同意再战才会开始下一局；断线后可返回联机房间重新连接。

Relay 创建/加入使用邀请码；云配置不可用时应明确返回不可用状态，不应显示虚假连接。角色互斥，换位须双方同意并重新准备。主机退出会结束对局。

## 0.3.3-preview 操作衔接

最新预览加入移动收速、墙跳输入缓冲、有界楼沿辅助，以及玩家有效出手后的技能后摇取消。约 0.22 秒的略早输入缓冲只改善衔接，不改变伤害或技能冷却；已发射飞弹会继续独立飞行。

## 教学与设置

教学分为基础、术式、机制三个章节，可从主界面直接选择，也可以连续学习全部内容；每步完成后停留 1.5 秒。G 跳过当前步骤，V 重新练习；教学结束返回主界面。音乐默认音量为 18%，主菜单和暂停菜单均可进入设置。每局开始默认锁定对手，可通过锁定按钮或自定义锁定键切换自由瞄准。

默认键位见首页；X 按下后展开防御结界 2 秒并自动结束，冷却 30 秒。空中再次按空格可二段跳，按住空格可短暂滞空。

主菜单和暂停菜单都有“退出游戏”入口。浏览器 WebGL 无法由网页关闭标签页，页面会给出提示。

## 核对下载完整性

在 PowerShell 中对下载的文件运行：

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\ShinjukuDuel-0.3.1-windows-x64.zip'
Get-FileHash -Algorithm SHA256 -LiteralPath '.\ShinjukuDuel-0.3.1-android-arm64.apk'
```

结果应与同版本 `SHA256SUMS.txt` 完全一致。Windows 压缩包内部还有一份清单，可核对解压后的各文件。
