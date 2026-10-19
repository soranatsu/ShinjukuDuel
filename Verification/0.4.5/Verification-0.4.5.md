# 0.4.5 验证范围

本次行为修复：闭合御厨子碰撞，防止施法后后退进入门洞碎骨，同时保留实体碰撞和屋顶站立。

回归摘要来自 `test-summary.json`，未在该文件中确认的结果不写成通过：

```json
{
  "version": "0.4.5-candidate2",
  "build": "Builds/Release-0.4.5-candidate2/Windows/ShinjukuDuel.exe",
  "exeSha256": "DE6E689463B66EED8CF39443EB662F49413D4BE3C173B348B9F6C06AB6C75D60",
  "assemblyCSharpSha256": "280C0F0594A491634159DA91DDCE811276D467971793FC2CED32E1651004033B",
  "passed": true,
  "tests": [
    {
      "name": "shrine-retreat",
      "flag": "--shrine-retreat-test",
      "checks": 45,
      "passed": true,
      "evidence": "shrine-retreat.json"
    },
    {
      "name": "shrine-solid",
      "flag": "--shrine-solid-test",
      "checks": 12,
      "passed": true,
      "evidence": "shrine-solid.json"
    },
    {
      "name": "head-spacing",
      "flag": "--head-spacing-test",
      "checks": 21,
      "passed": true,
      "evidence": "head-spacing.json"
    },
    {
      "name": "movement",
      "flag": "--movement-test",
      "checks": 10,
      "passed": true,
      "evidence": "movement.json"
    },
    {
      "name": "air-movement",
      "flag": "--air-movement-test",
      "checks": 16,
      "passed": true,
      "evidence": "air-movement.json"
    },
    {
      "name": "network-reconciliation",
      "flag": "--network-reconciliation-test",
      "checks": 127,
      "passed": true,
      "evidence": "network-reconciliation-rerun.json"
    },
    {
      "name": "lan-acceptance-quiet",
      "flag": "--net-test-host/--net-test-client",
      "checks": 217,
      "passed": true,
      "hostChecks": 161,
      "clientChecks": 56,
      "evidence": "../Verification-Network/Release045-Quiet/run.json"
    }
  ],
  "totalChecks": 448,
  "totalExecutedChecks": 665,
  "history": {
    "initialRuns": [
      {
        "name": "lan-acceptance-resource-contention",
        "checks": 217,
        "passed": false,
        "hostChecks": 161,
        "clientChecks": 56,
        "evidence": "../Verification-Network/Release045-Final/run.json",
        "note": "首次运行期间存在 Unity/WebGL 资源争用；随后安静时段对照通过。"
      }
    ]
  },
  "notes": [
    "The first reconciliation run had one timing-sensitive projectile interpolation failure (tickMotion=0.000); an immediate rerun passed all 127 checks.",
    "同机 LAN 首次验收端口 22775 在 Unity/WebGL 资源争用期间失败；随后暂停资源争用后用端口 22776 完成安静时段对照，host 161/161、client 56/56 全部通过。两次原始证据均保留。",
    "This is Windows runtime evidence only; Android, macOS and browser runtime were not revalidated here."
  ]
}
```

Android 包验证：已由最终清单确认通过。
macOS 包验证：已由最终清单确认通过。
Web 包验证：已由最终清单确认通过。

协议为 `shinjuku-lan-045-v1-fixed60`，双方必须更新到 0.4.5，不能与 0.4.4 混用。
