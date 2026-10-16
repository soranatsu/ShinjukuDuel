# 0.3.5-preview 联机验收状态

0.3.5-preview 修正客户端接收权威坐标后的纠偏顺序：先写入权威 Transform，再调用 `Physics.SyncTransforms`，最后重放待处理的 `motor.Move`；网络重绑时同时 reset 移动/纠偏状态。本地移动使用单一预测步进，重放会消耗冲刺、硬直和冷却时长。远端快照按槽位使用独立序号和 `Unreliable` 传输，超过 2 m 直接纠偏，否则以 18 的跟随参数插值。此前一次 Relay 观测受旧版测量/纠偏指标问题影响，不能作为本版的数值基线；修复后的结果待本版复测。

0.3.5 联机协议为 `shinjuku-lan-035-v1`，双方必须使用同一版本，旧协议端应拒绝。术式飞行速度为：苍 40 m/s、赫 48 m/s、茈（Purple）52 m/s；解 80 m/s、捌 90 m/s、开（Fuga）42 m/s。苍与赫索敌时长均为 1.2 s；伤害、范围、冷却和转向不变。

Windows 最终构建 `F67B174C856CA41C4C45BE382EECEA426E9CEA9A9783D7D73CF60699547073FB` 的 Core 101、Reconciliation 6、LAN 角色 29、真实 Relay 连续移动 GojoHost 45 + SukunaHost 45 和完整 Relay 集成 203 项均通过，共 429 项。持续 Ready 035 Sukuna LAN Impaired 压力场景 35/37 项通过，仅 2 项快照新鲜度最大值 0.867 s 超过 0.5 s 限值；两侧 Light EF 命中、静态误差 ≤4e-6 和 native 误差为 0 的检查通过，因此不宣称该压力场景全绿。不得把 0.3.4 的 261 项结果计入本版。Android 0.3.5 已完成 ARM64 构建与元数据核验（`com.shinjuku.fanduel`、versionCode 20、API 26—36、INTERNET 已启用），APK SHA-256 为 `070166081B7D871BF415714CFDCD6867543424AADA5483B7BF4EAC2F468C15FF`；Android 真机、跨设备联机仍未验证。macOS Universal 已完成构建核验（6 个原生 Mach-O 为 x86_64+arm64、Info.plist 版本 0.3.5、最低 macOS 12.0），ZIP SHA-256 为 `B099BF924218991A0D0BCAFBD4E402CC7FD1CF55BE714E0C2E2C183B42085AF`；Mac 实机、Developer ID 签名、公证和跨设备联机仍未验证。

验证报告：[Network-Verification-0.3.5.md](Verification/0.3.5/Network-Verification-0.3.5.md)

# 0.3.4-preview 联机验收状态

0.3.4-preview 修正开房前角色预选，并保留创建 LAN/Relay 房间时的角色选择。加入已有房间后分配房主尚未选择的另一角色，可请求对方同意换位；不改战斗规则。

Windows 同机双进程 LAN 角色预选、角色互斥、分配与换位专项共 58 项全部通过；公网 Relay 双 Windows 进程通用集成 203 项全部通过。Relay 结果覆盖建房、加入、准备和对局链路，Relay 建房后的角色预选未作为单独专项宣称。两组结果使用 managed SHA `443DDB1F2FB48D4F8014FCD30CC7E29B2EDFC5AB76943E406947FB3659619AF3`。Android 0.3.4 编译产物为 ARM64、API 26—36、versionCode 19，使用既有 Android Debug 证书（SHA-256 `0f3b7fc7871f6eb012258a53c85c74119d0e3c38f7ffdfd9160389af55a2048e`），APK SHA-256 为 `E221FCA3EF2B594C35CAE4C4B5D7DA65D6E81559055B59AE6AA125C5BACF0D6A`。

Android ARM64（versionCode 19）和 macOS Universal 已完成编译；macOS Universal 原生 x86_64+arm64 架构已核验。Android 真机、macOS 实机签名公证及跨设备联机仍未验证。

# 0.3.3-preview 联机网络验收记录

## 0.3.3-preview 当前状态

0.3.3-preview 已关联 Unity Cloud Project，并提供 Relay 邀请码与 LAN 联机入口。最终 Windows 构建已完成两种角色主机方向的 Relay 双进程验收：每种角色主机 153 项、客户端 50 项，共 406 项；LAN 角色与操作专项也已完成验收。

本轮操作更新包含移动收速、墙跳输入缓冲、有界楼沿辅助，以及玩家有效出手后的 E/F/R/领域后摇取消和约 0.22 秒输入缓冲；已发射飞弹独立继续，伤害与技能冷却未改变。AI 跳跃随机对战观测有一次未触发，独立同构建四项复测通过，未确定根因，也不证明 15 秒内必跳。跨异地、Android 真机和连续体验仍待验证。

最终 APK 元数据：`com.shinjuku.fanduel`，versionName `0.3.3`，versionCode `18`，ARM64，API 26—36；使用既有 Android Debug 证书，真机尚未验证。

本记录只使用相同 Publish managed SHA 的四场 `Publish032-*` 2×2 本机双进程矩阵。此前 Transport/Canonical/Delivery/Verified 结果保留为历史，不与本矩阵合并。

- 构建 SHA-256：`DE6E689463B66EED8CF39443EB662F49413D4BE3C173B348B9F6C06AB6C75D60`
- Publish managed SHA-256：`477E6375DACD7A8A2CC10FBC6F6450D45F0F86960BE46393D32566EB2E46BE74`
- 四场矩阵：149+46 checks 全部通过，共 780 项。
- 两个领域专项：各 18+6 checks 通过，共 48 项；不计入四场矩阵。
- LAN：同机双进程直连本机端口。Impaired：UDP 代理，单向延迟约 70 ms、抖动约 20 ms、丢包率 3%、seed=8137。
- position/HP 比较是各 stage 末端、非同时采样的样本；位置差不能估计连续帧 prediction error、网络 latency 或竞技手感。
- 快照设计：压缩 fighter/domain 快照优先 UnreliableSequenced（不超过 1100 B），大消息回退可靠通道；终局快照强制可靠并保持终局顺序。

## Publish032-Impaired-GojoHost

- 主机角色：Gojo；客户端角色：Sukuna
- 条件：Impaired（70 ms 单向延迟、20 ms 抖动、3% 丢包）
- 场次：complete=True，passed=True
- host：149 checks，complete=True，passed=True，failed=0
- client：46 checks，complete=True，passed=True，failed=0
- UDP 计数：C→S received/dropped/delivered=2411/85/2325；S→C=6876/204/6667；deliveredBytes=4210892。
- 同 stage observation（末端、非同时样本）：28 个双方均有记录的末端样本；记录 health、targetHealth 和 stage 末端位置差；该指标不用于估计 prediction error、latency 或连续手感。
  - position error 范围：0.000000–11.508552。

## Publish032-Impaired-SukunaHost

- 主机角色：Sukuna；客户端角色：Gojo
- 条件：Impaired（70 ms 单向延迟、20 ms 抖动、3% 丢包）
- 场次：complete=True，passed=True
- host：149 checks，complete=True，passed=True，failed=0
- client：46 checks，complete=True，passed=True，failed=0
- UDP 计数：C→S received/dropped/delivered=2426/81/2344；S→C=6932/211/6718；deliveredBytes=4215481。
- 同 stage observation（末端、非同时样本）：28 个双方均有记录的末端样本；记录 health、targetHealth 和 stage 末端位置差；该指标不用于估计 prediction error、latency 或连续手感。
  - position error 范围：0.000000–11.234547。

## Publish032-LAN-GojoHost

- 主机角色：Gojo；客户端角色：Sukuna
- 条件：LAN 直连
- 场次：complete=True，passed=True
- host：149 checks，complete=True，passed=True，failed=0
- client：46 checks，complete=True，passed=True，failed=0
- UDP：直连本机传输，未生成代理统计。
- 同 stage observation（末端、非同时样本）：28 个双方均有记录的末端样本；记录 health、targetHealth 和 stage 末端位置差；该指标不用于估计 prediction error、latency 或连续手感。
  - position error 范围：0.000000–9.898153。

## Publish032-LAN-SukunaHost

- 主机角色：Sukuna；客户端角色：Gojo
- 条件：LAN 直连
- 场次：complete=True，passed=True
- host：149 checks，complete=True，passed=True，failed=0
- client：46 checks，complete=True，passed=True，failed=0
- UDP：直连本机传输，未生成代理统计。
- 同 stage observation（末端、非同时样本）：28 个双方均有记录的末端样本；记录 health、targetHealth 和 stage 末端位置差；该指标不用于估计 prediction error、latency 或连续手感。
  - position error 范围：0.000000–9.901362。

## 领域专项

- `Publish032-Domain-GojoHost` 与 `Publish032-Domain-Impaired-SukunaHost`：各 18+6 checks PASS。

## 离线专项

- `Final033-Feel`：air 14、movement 9、actions 7，tutorial suite 通过；`Final033-Core`：domains 81、projectiles 70、mobile 14，AI jump 原始随机观测一次未触发，独立同构建四项复测通过，未确定根因。

## 历史与限制

- Transport/Canonical/Delivery/Verified 早期失败批次保留在当前目录，属于历史测试夹具/观察记录，不混入本 Publish 矩阵。
- 主机退出结束对局，没有主机迁移。
- Publish032、Transport032 等早期批次保留为历史；本页开头的 0.3.3-preview Relay 结果来自最终 Windows 构建。0.3.4-preview 的 LAN 角色专项为同机双进程，Relay 通用集成为公网双 Windows 进程；结果不扩展为 Android 真机、macOS 实机或跨平台体验证明。
- 机器可读明细：[Network-Verification-0.3.2.summary.json](Verification/0.3.2/summary.json)。
