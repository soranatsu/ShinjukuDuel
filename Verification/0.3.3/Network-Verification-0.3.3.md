# 0.3.3 最终网络与操作验收汇总

生成时间：2026-10-16T18:43:31.5398718+08:00
managed SHA-256：F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE

## 最终场景

| 场景 | 类型 | 状态 | run.json | Build | managed SHA | 套件 |
| --- | --- | --- | --- | --- | --- | --- |
| Final033-Feel | offline-feel | passed | Verification/0.3.3/Final033-Feel/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | air:14, movement:9, actions:7, tutorial:suite |
| Final033-Core | offline-core | passed_with_observation | Verification/0.3.3/Final033-Core/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | domains:81, projectiles:70, mobile:14, jump:4 |
| Final033-Relay-GojoHost | relay | passed | Verification/0.3.3/Final033-Relay-GojoHost/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | host:153, client:50 |
| Final033-Relay-SukunaHost | relay | passed | Verification/0.3.3/Final033-Relay-SukunaHost/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | host:153, client:50 |
| Final033-Roles-LAN | roles-lan | passed | Verification/0.3.3/Final033-Roles-LAN/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | host:13, client:8 |
| Final033-Roles-Impaired | roles-impaired | passed | Verification/0.3.3/Final033-Roles-Impaired/run.json | builds/Release-0.3.3/ShinjukuDuel.exe | F228E0E3E464074D6A9E1FC3FD1EF4F3DFB85A90A4043465B24CC2E9CA8DF9EE | host:13, client:8 |

## 证据边界

- Relay 为真实公共 Relay 双进程证据，但仍是同机双进程；未证明跨设备或跨网体验。
- Android 编译、签名和真机验证另由发布流程登记。
- 未进行 GUI 实际像素级验收。
- 角色交换与移动/后摇场景的检查项来自原始 JSON；脚本不会硬编码通过结果。
- Core 的随机对战跳跃观测若使用独立复测，仅标记为 `passed_with_observation`：原始一次观测未触发，复测通过；不证明 15 秒内必跳。

## 历史结果

- `Feel033-r5`：测试时序/动作衔接夹具问题，原始失败保留。
- `Relay033-GojoHost-r1`：空 ProjectID 导致初始化超时，原始失败保留。

- `Final033-Core` 原始 jump 结果保留：passed=False，exitCode=1，reportedChecks=4；独立复测 source：`Verification/0.3.3/Final033-Jump-Recheck/jump.json`。
