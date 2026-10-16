# 0.3.3-preview 验证资料

此目录来自最终构建的验证记录副本。仅将开发机绝对路径、运行输出位置和邀请码文件位置替换为公开相对位置；检查名称、数值、通过状态和失败详情保持不变。

- [汇总报告](Network-Verification-0.3.3.md)
- [结构化结果](Network-Verification-0.3.3.summary.json)
- [发布包核验](package-verification.json)
- [Android 编译与签名](android-verification.json)
- [源代码文件哈希](source-manifest.json)：用于追溯本地冻结版本，不代表本仓库包含完整 Unity 源工程。

Relay 测试真实经过公共 Unity Relay，但两端在同一台 Windows 电脑运行。跨设备、跨网络体验和 Android 真机尚未验证；界面尚未做像素级验收。

Final033-Core/jump.json 保留一次随机 AI 战斗未触发双方起跳的原始结果；Final033-Jump-Recheck/jump.json 是相同构建的独立复测，通过四项。根因未确定，不能据此保证每次15秒对战都发生起跳。