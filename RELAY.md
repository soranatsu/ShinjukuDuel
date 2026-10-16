## 0.3.6-preview 状态

两端升级至 0.3.6 后，可通过在线房间的邀请码加入对局。本版协议为 `shinjuku-lan-036-v1`；修复安卓联机蓄力显示、建筑同步、联机菜单滚动和关闭按钮。

最终 Windows 公网 Relay 集成 203 项、连续移动 45 项均通过，另有 LAN 与核心检查，合计 415 项。验收由同机两个 Windows 进程完成；Android/Mac 包体已核验，真机与跨设备体验尚未验证。详见 [NETWORK.md](NETWORK.md) 和 [原始检查结果](Verification/0.3.6/Network-Verification-0.3.6.md)。

## 0.3.5-preview 状态

0.3.5 使用 `shinjuku-lan-035-v1` 联机协议，双方必须使用同一版本，旧协议端拒绝连接。客户端纠偏现在先写入权威 Transform，再调用 `Physics.SyncTransforms`，然后重放 `motor.Move`；网络重绑时 reset 相关状态。本地预测避免预测与渲染帧重复推进，远端快照按槽位使用独立序号和 `Unreliable` 传输，超过 2 m 直接纠偏，否则以 18 的跟随参数插值。此前一次 Relay 观测受旧版测量/纠偏指标问题影响，不能作为本版的数值基线；Windows 最终构建主验收已完成，压力场景仍保留新鲜度限制。

Windows 最终构建的 Core 101、Reconciliation 6、LAN 角色 29、真实 Relay 连续移动 GojoHost 45 + SukunaHost 45 和完整 Relay 集成 203 项均通过，共 429 项。持续 Ready 035 Sukuna LAN Impaired 压力场景 35/37 项通过，仅 2 项快照新鲜度最大值 0.867 s 超过 0.5 s 限值；该压力场景不宣称全绿。Android 0.3.5 已完成 ARM64 构建与元数据核验（versionCode 20，APK SHA-256 `070166081B7D871BF415714CFDCD6867543424AADA5483B7BF4EAC2F468C15FF`），但 Android 真机、跨设备联机仍未验证。macOS Universal 已完成构建核验（原生 x86_64+arm64、最低 macOS 12.0，ZIP SHA-256 `B099BF924218991A0D0B0CAFBD4E402CC7FD1CF55BE714E0C2E2C183B42085AF`），但 Mac 实机、签名、公证和跨设备联机仍未验证。

# Unity Relay 接入状态与设置

## 0.3.4-preview 玩家流程

创建 LAN 或 Relay 房间时可以先预选角色并保留该选择。加入已有房间后，加入方分配房主尚未选择的另一角色；如需交换，可在大厅请求对方同意换位。Windows 同机双进程 LAN 角色流程专项共 58 项全部通过；公网 Relay 双 Windows 进程通用集成 203 项全部通过。Relay 建房后的角色预选未作为单独专项宣称。

2026-10-16：工程已接入 Multiplayer Services 2.4、Netcode for GameObjects 2.13 和 Unity Transport。远程房间使用匿名登录、私有双人会话、Relay 和邀请码；Unity Cloud 项目已关联。局域网连接不需要云项目。

## 开发者重建/部署设置

已发布的 0.3.3-preview 玩家直接运行 Windows 包即可创建 Relay 房间或使用邀请码加入，无需安装 Unity Editor、关联项目或手动配置云服务。以下步骤只适用于开发者自行重建或部署工程。

1. 使用已登录的 Unity Editor 打开本工程。
2. 在 `Edit > Project Settings > Services` 中选择自己的组织，创建或关联一个云项目。只需要项目 ID，不需要把密码、访问令牌交给助手。
3. 在对应 Unity Dashboard 项目检查 Multiplayer Services、Relay 和 Authentication 可用，并启用匿名认证。
4. 关联后重新构建游戏。云项目 ID 来自构建设置，当前 SDK 不支持在游戏运行时填写一个 ID 替代关联。
5. 两端使用同一构建：主机在“联机 > 在线房间”创建邀请码，另一端填写邀请码加入；选择互斥角色后双方准备。

构建会在云配置不可用时明确报告在线房间不可用，不会显示虚假的邀请码。Relay 与局域网使用同一套角色互斥、双方准备和主机权威流程；换位须双方同意并重新准备。

## 已确认与限制

0.3.3-preview 的历史 Windows Relay 验收按原记录保留；0.3.4-preview 新增公网 Relay 双 Windows 进程通用集成 203 项全部通过，另有 LAN 角色流程专项 58 项全部通过。AI 跳跃随机对战观测有一次未触发，独立同构建四项复测通过，未确定根因，不证明 15 秒内必跳。Android 0.3.4 已完成 ARM64 编译（versionCode 19，API 26—36），真机和跨设备体验尚未确认；macOS Universal 原生 x86_64+arm64 架构已核验，实机签名、公证和联机体验仍待确认。

Android 0.3.3 历史配套包元数据按原记录保留；0.3.4 Android 构建使用既有 Android Debug 证书，真机仍未验证。

Relay 负责转发连接；对局仍由开房玩家的游戏进程结算。主机退出会结束对局，本阶段没有主机迁移或独立服务器。

## 官方参考

- [开始使用 Multiplayer Services](https://docs.unity.com/en-us/mps-sdk/get-started)
- [创建会话与 Relay 网络选项](https://docs.unity.com/en-us/mps-sdk/create-session)
- [会话网络的自动建立流程](https://docs.unity.com/en-us/mps-sdk/session-networking)
- [Relay 与 NGO](https://docs.unity.com/en-us/mps-sdk/tutorials/relay-and-ngo)

免费额度和服务区域以你的 Dashboard 实际显示为准；本仓库不公布邀请码、令牌或本地认证信息。跨地区可达性仍需单独验证。
