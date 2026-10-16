# 0.3.2 Publish 联机网络验收记录

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

- `Publish032-Offline`：domains 81、projectiles 70、air 9、mobile 14、jump 4、relay 6 均 fresh/pass；tutorial 独立结果 `passed=true, failures=0`（内部 93 checks）。总 JSON checks=184；tutorial runner 的 JSON checks 字段为 0。

## 历史与限制

- Transport/Canonical/Delivery/Verified 早期失败批次保留在当前目录，属于历史测试夹具/观察记录，不混入本 Publish 矩阵。
- 主机退出结束对局，没有主机迁移。
- 当前证据仅来自本机双进程；没有真实异地、跨设备、Android 真机或 Relay/云项目连接证据。
- 机器可读明细：[Network-Verification-0.3.2.summary.json](Verification/0.3.2/summary.json)。
