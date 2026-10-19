# 0.4.3 验证范围

0.4.3 最终发布验证（2026-10-19）

Windows networkfix4：127 项回归检查通过；关闭系统代理且继承失效本地代理时，51 项建房、加入、35 秒持续对战检查通过，未观察到连接本地代理端口。
用户实测：Windows / Android MatePad 局域网成功；发布前用户明确确认“测试完毕，裸连直连完全成功，收工整理发布”。此项记录来源为用户实测反馈。
Android networkfix3：版本 0.4.3 / 32，Android 8+ ARM64，签名与 16 KiB 对齐检查通过。Windows 追加修改仅作用于 Windows 启动环境，无需因该修改重建 APK。
Web networkfix3：构建与真实 Relay 运行检查通过，Web 客机与原生主机连接通过。
Mac：本次补建 Universal；构建及验包结果以最终发布清单为准。没有 Mac 实机测试，不将 Windows 测试当作 Mac 验证。

macOS Universal 构建成功，6 个 Mach-O 文件均包含 x86_64 与 arm64，最低 macOS 12.0。所有包已核验文件校验值，最终清单与 GitHub 附件摘要一致后发布。
