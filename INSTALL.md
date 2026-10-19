# 安装与操作

新宿决战 0.4.5 使用说明

Windows：完整解压 windows-x64.zip，运行 ShinjukuDuel.exe，保留数据目录和运行库。
macOS：解压 macos-universal.zip，打开 ShinjukuDuel.app；支持 macOS 12+ 的 Intel / Apple Silicon。未做 Apple 公证，首次打开说明见 macOS-使用说明.md。
Android：安装 android-arm64.apk，Android 8.0+ ARM64，版本代码 34，与之前安装包签名一致。
网页：https://soranatsu.itch.io/shinjuku-duel ，手机和平板请横屏。
下载：https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.4.5

WASD 移动，鼠标转向，中键锁定，左键普攻，右键格挡，Shift 闪避，空格跳跃，E/F 术式，R 大招，Q 治疗，C 领域，X 简易领域/弥虚葛笼，Esc 暂停。设置内可调整键位和灵敏度。
触屏左摇杆移动、右侧空白区域滑动转向，屏幕按钮攻击和使用技能；触控布局可在设置中调整。

联机双方必须都更新到 0.4.5，不能与 0.4.4 混用。协议为 `shinjuku-lan-045-v1-fixed60`。
不同网络和网页版使用在线邀请码；原生局域网填写主机实体 Wi-Fi / 以太网 IPv4、端口 7777，不填写 127.0.0.1 或虚拟网卡地址。
Windows 首次局域网连接可右键以管理员身份运行包内“修复局域网连接.cmd”，只为当前游戏放行 UDP 7777；移动游戏目录后需重新运行工具。
代理不是联机的强制要求。若要直连，请关闭系统代理；游戏只清理自身进程继承的本地代理变量，不修改全局设置。

本次回归最终检查 448/448 项通过。Android 包验包通过；本次没有新的 Android / Mac 实机测试。Toy / B站版本不属于本次发布，待单独制作且不超过 50 MB。
