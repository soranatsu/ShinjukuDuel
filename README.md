# 新宿决战 · Shinjuku Duel

当前版本：**0.4.4 · 2026-10-19**，免费游玩。

选择五条悟或两面宿傩，在可破坏的新宿街区中进行第一人称近战、术式与领域对决。

| 平台 | 下载 / 游玩 |
| --- | --- |
| Windows x64 | [下载 ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.4.4/ShinjukuDuel-0.4.4-windows-x64.zip) |
| macOS Intel / Apple Silicon | [下载 Universal ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.4.4/ShinjukuDuel-0.4.4-macos-universal.zip)，macOS 12+ |
| Android ARM64 | [下载 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.4.4/ShinjukuDuel-0.4.4-android-arm64.apk)，Android 8+，版本代码 33 |
| 网页 | [itch.io 直接玩](https://soranatsu.itch.io/shinjuku-duel)，触屏请横屏 |

[0.4.4 发布页](https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.4.4) · [安装与操作](INSTALL.md) · [联机](NETWORK.md) · [SHA-256](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.4.4/SHA256SUMS.txt) · [历史版本](https://github.com/soranatsu/ShinjukuDuel/releases)

0.4.4 修复网页版打开联机菜单崩溃，以及高于对手时锁定方向不稳定、容易踩在对手头顶的问题。近乎垂直时保持稳定的水平朝向，落到对手头顶会向旁边滑落；正常跳跃和侧向移动保持有效。

双方联机均须更新到本次 0.4.4，协议 `shinjuku-lan-044-v1-fixed60`。不同网络与网页版使用在线邀请码；原生局域网填写主机 IPv4、端口 7777，Windows 首次局域网连接可运行包内防火墙工具。

防踩头、移动、空中控制与网络回归检查通过；同机 LAN 217 项、真实 Relay 持续对战 63 项，以及网页与 Windows 的 Relay 联机 64 项检查通过。详细范围见 [0.4.4 验证说明](Verification/0.4.4/Verification-0.4.4.md)。本次没有新的 Android / Mac 实机测试，Mac 未做 Apple 公证。

本仓库保存发布说明与下载入口。GitHub 自动生成的 Source code ZIP/TAR 是说明文档快照，游玩请下载平台包。素材来源随包保留，并见 [来源记录](CREDITS.md)。
