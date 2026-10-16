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
