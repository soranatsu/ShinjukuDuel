# 新宿决战 · Shinjuku Duel

基于 Unity 制作的第一人称单人人机对战游戏。选择五条悟或两面宿傩，在可破坏的城市街区中使用近战、术式、领域和防御技能进行战斗。

**稳定版：0.3.1 · 2026-10-16**  
**预览版：0.3.5-preview · 联机移动纠偏与角色流程修复预览**

公开发布的 0.3.1 是稳定的离线单人版本。0.3.2-preview、0.3.3-preview 和 0.3.4-preview 链接继续保留；0.3.5-preview 修正联机移动权威纠偏与网络重绑状态，并保留角色预选流程。Windows 最终构建的 429 项主验收已通过；受限压力场景仍有 2 项快照新鲜度超限，范围与平台限制见 [NETWORK.md](NETWORK.md)。

## 下载与安装

| 平台 | 下载 | 使用方式 |
| --- | --- | --- |
| Windows x64 | [下载 Windows ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.1/ShinjukuDuel-0.3.1-windows-x64.zip) | 完整解压后运行 `ShinjukuDuel.exe`，保留旁边的数据目录和 DLL，无需安装 Unity。 |
| Android ARM64 | [下载安卓 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.1/ShinjukuDuel-0.3.1-android-arm64.apk) | Android 8.0 及以上，下载后安装，横屏游玩。 |
| Windows x64（0.3.2-preview） | [下载 Windows ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.2-preview/ShinjukuDuel-0.3.2-windows-x64.zip) | 联机预览包；完整解压后运行 `ShinjukuDuel.exe`。 |
| Android ARM64（0.3.2-preview） | [下载安卓 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.2-preview/ShinjukuDuel-0.3.2-android-arm64.apk) | 联机预览包；Android 8.0 及以上，横屏游玩。 |
| Windows x64（0.3.3-preview） | [下载 Windows ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.3-preview/ShinjukuDuel-0.3.3-windows-x64.zip) | Relay/LAN 联机与操作衔接预览；完整解压后运行。 |
| Android ARM64（0.3.3-preview） | [下载安卓 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.3-preview/ShinjukuDuel-0.3.3-android-arm64.apk) | 配套预览包；最终 APK 已完成编译，发布附件与签名状态以发布流程核验为准，Android 真机尚未验证。 |
| macOS Universal（0.3.3-preview） | [下载 macOS ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.3-preview/ShinjukuDuel-0.3.3-macos-universal.zip) | Intel 与 Apple Silicon 预览包；尚无 Mac 实机或跨平台联机验证，无 Developer ID 签名和公证。 |
| Windows x64（0.3.4-preview） | [下载 Windows ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.4-preview/ShinjukuDuel-0.3.4-windows-x64.zip) | LAN/Relay 角色流程已验收，详细范围见 NETWORK.md。 |
| Android ARM64（0.3.4-preview） | [下载安卓 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.4-preview/ShinjukuDuel-0.3.4-android-arm64.apk) | versionCode 19，ARM64，API 26—36；真机尚未验证。 |
| macOS Universal（0.3.4-preview） | [下载 macOS ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.4-preview/ShinjukuDuel-0.3.4-macos-universal.zip) | 原生 x86_64+arm64 架构已核验；ZIP、实机签名、公证或联机验收仍待确认。 |
| Windows x64（0.3.5-preview） | [下载 Windows ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.5-preview/ShinjukuDuel-0.3.5-windows-x64.zip) | 必须双方使用同一 0.3.5 构建；Windows 主验收 429 项通过，受限压力场景仍有 2 项快照新鲜度超限。 |
| Android ARM64（0.3.5-preview） | [下载安卓 APK](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.5-preview/ShinjukuDuel-0.3.5-android-arm64.apk) | 已完成 ARM64 构建与元数据核验，versionName 0.3.5、versionCode 20、API 26—36；Android 真机及跨设备联机尚未验证。 |
| macOS Universal（0.3.5-preview） | [下载 macOS ZIP](https://github.com/soranatsu/ShinjukuDuel/releases/download/v0.3.5-preview/ShinjukuDuel-0.3.5-macos-universal.zip) | Universal 包已构建并核验 x86_64+arm64 原生 Mach-O、Info.plist 版本 0.3.5、最低 macOS 12.0；Mac 真机、Developer ID 签名、公证和跨设备联机仍未验证。 |

[全部发布文件](https://github.com/soranatsu/ShinjukuDuel/releases/latest) · [安装与操作说明](INSTALL.md) · [macOS 说明](MACOS.md) · [更新说明](CHANGELOG.md) · [LAN 联机指南](LAN.md) · [Relay 状态](RELAY.md) · [NETWORK 验证说明](NETWORK.md) · [SHA-256 校验](SHA256SUMS.txt)

[0.3.3-preview 发布页](https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.3.3-preview) · [预览包 SHA-256](SHA256SUMS-0.3.3.txt) · [0.3.2-preview 发布页](https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.3.2-preview)

[0.3.4-preview 发布页](https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.3.4-preview) · [SHA-256 校验](SHA256SUMS-0.3.4.txt)

[0.3.5-preview 发布页](https://github.com/soranatsu/ShinjukuDuel/releases/tag/v0.3.5-preview) · [SHA-256 校验](SHA256SUMS-0.3.5.txt)

GitHub 自动生成的 `Source code` ZIP/TAR 是本仓库的说明文档快照。游玩请下载上表中对应平台的文件。

## 游戏机制简介

### 五条悟 VS 两面宿傩

选择两位角色进行 **3D 第一人称人机对战**。双方基础生命值均为 2000，每局开始默认锁定对手，也可以用锁定按钮或自定义锁定键切换自由瞄准。开局两人在相距约 120 米的楼顶对峙，AI 会先进行 5 秒远程交锋，再寻找贴身战的机会。

| 按键 | 五条悟 | 两面宿傩 |
| --- | --- | --- |
| E | **苍**：蓝色引力球，短暂追踪并牵引目标 | **解**：白色飞行斩击，可穿透并切割建筑 |
| F | **赫**：红色斥力球，短暂追踪并击退目标 | **捌**：红色强斩击，带有更强的击退效果 |
| R | **茈**：紫色高能球，命中后大范围爆发 | **开**：火焰弓箭，命中后爆炸 |
| C | **无量空处**：展开封闭结界，命中时造成伤害并控制敌人 | **伏魔御厨子**：展开开放领域，命中时造成伤害并持续斩击 |
| Q | 反转术式：一次性治疗 | 反转术式：一次性治疗 |
| X | 简易领域 | 弥虚葛笼 |

苍、赫通常追踪约 1 秒，之后仍有走位躲开的机会。术式伤害会随距离适度衰减，35 米及更远处降为近距离的 75%。

### 新宿真的能拆

楼体、地标、路边招牌、公交站棚顶等都可以被攻击破坏。擦到建筑边角会先产生局部碎屑并积累结构损伤；失去支撑的楼体会逐层坍塌，保留短暂的站立与踏墙机会。

留下的废墟可以继续打碎，约 25 秒后自动清理。街区采用压缩后的布局，让楼顶、街道和建筑间隙都成为战场，并设有外围防坠边界。

### 地上打完，天上接着打

冲刺贴身、二段跳越障、踏墙起跳，再利用短暂滞空调整出手角度。支持闪避和目标锁定，**空中近战伤害为地面的 1.5 倍**，AI 也会主动跳跃参与战斗。

五条位于自己的无量空处内时，近战伤害额外提高 30%。普攻有出手间隔，连续点击也需要遵守攻击节奏。

### 大招可以蓄力

R 键短按释放，长按蓄力，最高达到 **200% 伤害倍率**。蓄力期间累计承受 50 点实际伤害才会被打断；普通受击不会直接封住普攻与 E/F 出手。

茈与开的最大射程为 150 米，爆炸也会对范围内的施法者造成 20% 自伤。这两招不能只靠闪避无敌帧硬吃，必须真正离开爆炸范围。

### 术式可以正面突破

对手放出飞行术式时，可以用更强的术式迎击：**赫/捌可以迎击苍/解**，剩余伤害为两者伤害之差；**茈/开可以突破较低阶的飞行术式**，保留自身伤害。领域效果不能用这种方式抵消。默认 PC 键位见上表，也可在设置中修改。

### 格挡、反击与回血

按住右键格挡可减少 **50% 伤害**，御厨子的持续斩击也可以防御。抓住对手近战出拳开始后的 **0.3 秒窗口**，按下格挡可自动打出基础 30 点伤害的反击。

双方都能用 Q 施展反转术式，一次恢复 **240 HP**，通常冷却 **15 秒**。回血有时机和冷却成本，不能无限使用。

### 领域可以对拼

大领域围绕**施法者展开时的位置**生成。无量空处能控制敌人，伏魔御厨子会持续斩击；领域计时、对局计时与技能冷却照常推进。

单独领域生效时，对范围内敌人的 E/F/R 具有必中追击效果；领域对冲时，双方的必中效果中和，主动打出的近战和术式仍能造成伤害。

宿傩的开放领域会持续切割无量空处的外壳。五条可以利用自己的近战增益抢攻；宿傩成功展开领域时会立即刷新 E/F，领域期间新施放的 **E 冷却为 1 秒、F 为 1.6 秒**，领域结束后恢复普通施放冷却。

### 破域、熔断与黑闪

领域对抗中，进攻本体和破坏结界都很重要：

- **击溃御厨子**：通过非领域攻击累积对宿傩的破域分数。宿傩在领域期间实际承伤减半，但破域计分使用这次领域减伤前的伤害；治疗不会清空已积累的分数。无量空处的开场伤害不计入这项分数。
- **击溃无量空处**：可以由御厨子侵蚀外壳，但要通过这一路径破域，宿傩还需实际命中过五条本体；也可以通过对五条本体造成足量非领域伤害，触发独立的破域条件。
- **从结界外攻击**：宿傩在外部时可以攻击无量空处的外壳；五条的术式不能穿出自己的结界去攻击外部目标。宿傩在结界内部施放的普通术式攻击本体，不直接削减外壳。
- **抓住破域后的机会**：御厨子破碎时，若宿傩仍处于未破的无量空处内，会受到最多 3 秒的残余控制，并受领域剩余时间限制。

领域被击溃后，拥有者进入约 **3.33 秒术式熔断**；自然到期不会触发熔断。熔断期间仍能肉搏、回血和使用 X 防御结界。

普攻有 **20% 概率触发黑闪**，基础伤害为 **72**，带有击退效果，实际伤害仍受空中、领域加成及防御影响。黑闪实际造成生命值伤害后，会立即修复自己的术式熔断并刷新 Q 冷却；本版黑闪不会使对方进入熔断。

0.3.3-preview 增加玩家有效出手后的 E/F/R/领域后摇取消，约保留 0.22 秒的略早输入缓冲；已发射飞弹独立继续飞行，伤害与技能冷却规则不变。F 仍对应宿傩的捌/五条悟的赫。

### 简易领域与弥虚葛笼

按 X 展开，**持续 2 秒，冷却 30 秒**，结界会跟随角色移动，松开按键不会提前取消。

大领域中，它可以抵御必中斩击、必中追击和控制，但对手正常主动攻击仍能命中。宿傩被无量空处控制时，若 X 已就绪，可以用弥虚葛笼解除本次控制，等结界结束后恢复进攻；X 不会阻止御厨子继续侵蚀无量空处的外壳。

没有大领域时，X 提供 **60 点护盾**，并阻止外面的敌人进入结界；护盾耗尽会提前结束。维持期间只能移动，不能进攻、治疗、格挡、跳跃或闪避，需要选好展开时机。

### 教学、难度与操作设置

包含基础、术式、机制三个章节的 **22 步引导教学**，可从主界面直接选择，也可以连续学习全部内容；当前实战课程使用五条悟视角。教学逐步练习移动、术式、领域对抗、黑闪和防御结界。教学敌人生命值为 1000，伤害和攻击频率降低，技能冷却最多 3 秒；每步完成后停留 1.5 秒，G 可跳步、V 可重练，结束后返回主界面。安卓教程使用苍、赫、茈、解、捌、开及领域和防御术式名称，PC 仍保留键位提示。

提供三档 AI 难度。较低难度的攻击欲望、小技能频率和反应速度更低；更高难度的敌人会更积极地交战，敌方领域的控制、耐久或持续时间也会按角色与难度调整。起跳后保留水平惯性，普通空中移动和滞空不会被 WASD 即时转向；二段跳、踏墙跳和闪避仍可改变路径，落地后恢复正常移动。

首页和暂停菜单均可调整音量、按键、视角灵敏度、镜头动态和伤害飘字。手机和平板使用左侧摇杆、右侧技能按钮，可以拖动位置并缩放至 70%—160%，分别保存布局。

### 0.3.3-preview 联机预览

主界面进入“联机对战”后，可以选择局域网创建或加入。创建者先选择 Gojo 或 Sukuna 并创建房间；加入者输入主机 IP 和端口后加入，再选择另一角色。双方都点击准备后才会开始对战。房间内显示的地址可用于同一局域网设备连接，Android 端可手动输入地址。

Relay 云房间使用邀请码创建或加入；局域网仍支持输入主机 IPv4。双方角色互斥，换位须双方同意并重新准备。主机退出会结束对局，当前没有主机迁移。预览版主菜单和暂停菜单提供“退出游戏”按钮，浏览器 WebGL 版本无法关闭浏览器标签页，会显示相应提示。

**快来打一场酣畅淋漓的新宿决战吧！**

## 默认键位

| 操作 | 按键 |
| --- | --- |
| 移动 / 转向 | WASD / 鼠标 |
| 普攻 / 格挡 | 左键 / 右键 |
| 小术式 / 大招 | E、F / R（可长按蓄力） |
| 领域 / 治疗 / 防御结界 | C / Q / X |
| 闪避 / 跳跃 | Shift / 空格 |
| 锁定 / 暂停 | 鼠标中键 / Esc |
| 教学跳步 / 重练 | G / V |

## 验证范围

0.3.3-preview 的历史 Windows Relay 验收仍按原记录保留。0.3.4-preview 在同一 managed SHA 上新增 Windows 同机双进程 LAN 角色流程专项 58 项全部通过，并完成公网 Relay 通用集成 203 项全部通过；Relay 建房后的角色预选未作为单独专项宣称。AI 跳跃随机对战观测有一次未触发，独立同构建四项复测通过；未确定根因，也不证明 15 秒内必跳。Android 预览包目标为 ARM64、API 26—36，最终 APK 已完成编译，发布附件与签名状态以发布流程核验为准，Android 真机性能、触控、发热和兼容性尚未验收。APK 使用既有 Android Debug 证书，属于直接安装的测试构建，并非应用商店签名版本。

最终 APK：`com.shinjuku.fanduel`，versionName `0.3.3`，versionCode `18`，ARM64，API 26—36；使用既有 Android Debug 证书（SHA-256 `0f3b7fc7871f6eb012258a53c85c74119d0e3c38f7ffdfd9160389af55a2048e`），可覆盖同签名版本。真机尚未验证。

本仓库用于保存发布包说明，安装包位于 Releases。源工程、模型原件、私人照片、开发工具和历史版本归档不随仓库上传。

## 素材说明

这是《咒术回战》同人游戏，非官方作品。当前角色采用用户提供的 Tripo02 模型；模型来源声明不等于角色 IP、音乐或漫画素材的公开分发授权。项目尚未建立这些素材的完整公开传播授权记录。

仓库不为第三方素材另行授予使用或再分发许可。原有来源和许可文件保留在 Windows 包内，当前素材说明见 [CREDITS.md](CREDITS.md)。
