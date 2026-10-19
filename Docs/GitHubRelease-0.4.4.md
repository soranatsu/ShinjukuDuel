《新宿决战》0.4.4 修复两个问题：

- 网页版打开“联机对战”时的 `WebAssembly null function` 崩溃。
- 高于对手时锁定朝向不稳定、角色容易停在对手头顶。现在近乎垂直时保持稳定的水平朝向，落到对手头顶会向旁边滑落，正常跳跃与侧向移动仍可使用。

双方联机请更新到本次 **0.4.4**，不能与 0.4.3 混用。

| 平台 | 文件 |
| --- | --- |
| Windows x64 | `ShinjukuDuel-0.4.4-windows-x64.zip`，完整解压后运行 EXE |
| macOS Intel / Apple Silicon | `ShinjukuDuel-0.4.4-macos-universal.zip`，macOS 12+ |
| Android ARM64 | `ShinjukuDuel-0.4.4-android-arm64.apk`，Android 8+，版本代码 33 |
| 网页 | [itch.io 直接玩](https://soranatsu.itch.io/shinjuku-duel)，触屏请横屏 |

防踩头的 21 项碰撞检查、移动和空中控制 26 项、网络校正等 127 项回归检查通过；同机 LAN 全流程 217 项及真实 Relay 持续对战 63 项通过。网页版另核验联机菜单和真实 Relay 连接，详细范围见发布清单。

本次没有新的 Android / Mac 实机测试。Mac 包未做 Apple 公证，首次打开说明见包内文档。0.4.3 的用户实测结果作为上一版记录保留。

免费发布。安装与操作见 `INSTALL.txt`，校验值见 `SHA256SUMS.txt`，素材来源记录随包保留。
