# Unity Relay 接入状态与设置

2026-10-16：工程已接入 Multiplayer Services 2.4、Netcode for GameObjects 2.13 和 Unity Transport。远程房间使用匿名登录、私有双人会话、Relay 和邀请码；当前 `Application.cloudProjectId` 为空，尚未进行真实云端双人连接。局域网连接不需要云项目。

## 需要你在 Unity 中完成的设置

1. 使用已登录的 Unity Editor 打开本工程。
2. 在 `Edit > Project Settings > Services` 中选择自己的组织，创建或关联一个云项目。只需要项目 ID，不需要把密码、访问令牌交给助手。
3. 在对应 Unity Dashboard 项目检查 Multiplayer Services、Relay 和 Authentication 可用，并启用匿名认证。
4. 关联后重新构建游戏。云项目 ID 来自构建设置，当前 SDK 不支持在游戏运行时填写一个 ID 替代关联。
5. 两端使用同一构建：主机在“联机 > 在线房间”创建邀请码，另一端填写邀请码加入；选择互斥角色后双方准备。

当前未关联的构建会说明在线房间暂不可用，不会显示一个虚假的可用邀请码。关联完成后还需要真实网络测试，不能以局域网测试代替 Relay 测试。

Relay 负责转发连接；对局仍由开房玩家的游戏进程结算。主机退出会结束对局，本阶段没有主机迁移或独立服务器。

## 官方参考

- [开始使用 Multiplayer Services](https://docs.unity.com/en-us/mps-sdk/get-started)
- [创建会话与 Relay 网络选项](https://docs.unity.com/en-us/mps-sdk/create-session)
- [会话网络的自动建立流程](https://docs.unity.com/en-us/mps-sdk/session-networking)
- [Relay 与 NGO](https://docs.unity.com/en-us/mps-sdk/tutorials/relay-and-ngo)

免费额度和服务区域以你的 Dashboard 实际显示为准；尚未以本账号验证配额或跨地区可达性。
