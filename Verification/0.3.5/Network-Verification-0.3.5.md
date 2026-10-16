# 0.3.5 网络验证记录

本报告记录同一 managed 构建上的网络与离线证据。所有已列场景均来自当前 `Ready035` 目录；旧 `Final035` 结果只作为历史证据保留。六个常规/Relay/回归分组共 429 项通过；另有一组独立受损 LAN 压力观测 37 项，其中 35 项通过、2 项 freshness 失败。

## 构建身份

- managed SHA-256：`F67B174C856CA41C4C45BE382EECEA426E9CEA9A9783D7D73CF60699547073FB`
- Windows 构建 SHA-256：`DE6E689463B66EED8CF39443EB662F49413D4BE3C173B348B9F6C06AB6C75D60`
- 所有下列 Ready035 场景均声明相同 managed SHA；Reconciliation 结果本身不带 SHA，但 runner input 与实际执行文件 hash 已核对。

## 执行结果

| 场景 | 结果 | 检查数 | 证据 |
|---|---:|---:|---|
| Ready035-Core | 通过 | 101 | [run.json](Ready035-Core/run.json) |
| Reconciliation035-Ready | 通过 | 6 | [result.json](Reconciliation035-Ready/result.json) |
| Ready035-LAN-Roles | 通过 | 29 | [run.json](Ready035-LAN-Roles/run.json) |
| Ready035-Gojo-Relay | 通过 | 45 | [summary.json](continuous-Ready035-Gojo-Relay/summary.json) |
| Ready035-Sukuna-Relay | 通过 | 45 | [summary.json](continuous-Ready035-Sukuna-Relay/summary.json) |
| Ready035-Relay-Integration | 通过 | 203（主机153、客户端50） | [run.json](Ready035-Relay-Integration/run.json) |

Core 的 101 项由 projectiles 71、air 14、movement 9、actions 7 组成。LAN 角色场景为主机17、客户端12。Relay Integration 的两端报告均为 complete/passed，且没有失败项。

## Relay 角色观测

下表是两轮连续 Relay 报告中的实际字段。主机的 snapshot age 为 0（权威端）；客户端的 age 是客户端以 `Time.unscaledTime - lastSnapshotAt[slot]` 计算的本地“收到快照后经过时间”，不是服务器到客户端的单向网络时延。客户端的 `pendingDeltaTime` 是尚未确认输入（包括在途输入）的累计时间。

| 场景/端 | 命中（五条普攻/小术式，宿傩普攻/小术式） | 总命中 | raw local max/P95 (m) | remote max (m) | 静止距离差 (m) | native 对齐 (m) | max snapshot age (s) |
|---|---:|---:|---:|---:|---:|---:|---:|
| Gojo Relay / host | 9 / 4，9 / 4 | 26 | 0 / 0 | 0 | 0 | 0 | 0 |
| Gojo Relay / client | 0 / 0，0 / 0（客户端不作权威命中计数） | 0 | 14.452 / 4.250 | 1.651 | 1.43e-6 | 0 | 0.1333 |
| Sukuna Relay / host | 8 / 4，9 / 4 | 25 | 0 / 0 | 0 | 0 | 0 | 0 |
| Sukuna Relay / client | 0 / 0，0 / 0（客户端不作权威命中计数） | 0 | 6.555 / 3.000 | 1.092 | 0 | 0 | 0.1335 |

表中“小术式”对应测试字段 `gojoQHits/sukunaQHits`，统计 E/F 小术式的命中合计，与治疗 Q 无关。客户端的 0 命中计数是客户端报告字段的语义，不表示主机没有命中；权威 `HitLanded` 命中由对应 host 报告记录。位置列是阶段末端/连续采样统计，不能当作同一时刻的同步帧误差、延迟或竞技公平性证明。

## quiet 位置指标

测试代码只把前 6 s 且满足以下实际条件的本地样本计入 `quietEligible`：`snapshot.verticalVelocity <= .05`、`snapshot.dashVelocity.sqrMagnitude <= .0025`、`snapshot.externalVelocity.sqrMagnitude <= .0025`、`!view.IsAttacking`、`view.DodgeRemaining <= .001`。代码没有额外用 grounded 或平面速度条件筛选，因此报告不添加这些未执行的判据。

这些样本使用：

```text
horizontalRawLead <= moveSpeed * (pendingDeltaTime + snapshotAge) + 0.25 m
```

其中 `moveSpeed` 从角色实际字段读取（本场景为 15 m/s），`pendingDeltaTime` 覆盖未确认/在途输入，`snapshotAge` 是客户端本地收到快照后的时间。raw lead 是预测相对旧快照向前积分的量，不等于坐标错误；Dash、击退、攻击等样本保留原始 lead、速度和状态，不套用 quiet 上界。

Gojo Relay 客户端 quiet raw max/P95 为 3.470/2.750 m；Sukuna Relay 客户端为 3.000/2.600 m。两轮最终静止距离差分别为 1.43e-6 m 和 0 m，native center alignment 均为 0。连续报告仍保留最大 raw lead，避免用静止收敛掩盖预测期间的前视量。

## 独立受损 LAN 观测

`continuous-Ready035-Sukuna-LAN-Impaired` 是独立的受损 LAN 压力观测组。该组 37 项中两项 freshness 失败：`snapshot_freshness_slot0`（`maxAge=0.867s`）和 `snapshot_freshness_slot1`（`maxAge=0.867s ack=2493`）；原始证据保留在[run.json](continuous-Ready035-Sukuna-LAN-Impaired/run.json)。该观测不被转换成通过，也不代表上述正常 Relay 场景失败。

## 历史 Final035 证据

此前 `Final035` 目录中的 quiet/raw 记录仅用于追溯测试时序与指标解释，不作为本次 Ready035 结果来源；本报告不以旧目录覆盖当前 immutable raw 或重新定义本次通过条件。

## 限制

合计 466 项检查中 464 项通过、2 项 freshness 失败。这组证据覆盖本机双进程、公共 Relay 运行和离线检查；不证明异地设备、Android/macOS 真机、连续帧手感、公平性或跨网 Relay 质量。GUI 像素与真实移动设备输入也未由这些报告验证。
