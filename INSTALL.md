# 安装与操作

## Windows

1. 下载 `ShinjukuDuel-0.3.1-windows-x64.zip`。
2. 完整解压到一个文件夹，不要在压缩包中直接运行，也不要只复制 EXE。
3. 运行 `ShinjukuDuel.exe`。同目录中的 `ShinjukuDuel_Data`、`MonoBleedingEdge` 和 DLL 等文件需要保留。
4. 在首页选择角色、难度或引导教学。可以先进入设置降低音乐音量并调整鼠标灵敏度。

## Android

- 下载并安装 `ShinjukuDuel-0.3.1-android-arm64.apk`。
- 要求 Android 8.0（API 26）及以上，ARM64 设备，横屏。
- 系统提示时允许当前下载/文件管理应用安装此 APK。
- 左侧摇杆移动，右侧空白区域转向，右侧按钮释放术式、治疗或防御。
- 设置 → 操作设置 → 编辑按键布局，可拖动按钮和摇杆，并将尺寸调整为 70%—160%；手机与平板分别保存布局。
- 若覆盖安装提示签名冲突，先确认旧包来源及是否需要保留本地设置；卸载旧版会清除其本地数据。不要为了更新而直接删除整个游戏目录。

当前 APK 版本号为 0.3.1、versionCode 为 16，使用既有 Android Debug 签名。尚未进行安卓真机性能和兼容性验收。公开 0.3.1 为离线单人版本，联机功能仍在开发。

## 教学与设置

教学分为基础、术式、机制三个章节，可从主界面直接选择，也可以连续学习全部内容；每步完成后停留 1.5 秒。G 跳过当前步骤，V 重新练习；教学结束返回主界面。音乐默认音量为 18%，主菜单和暂停菜单均可进入设置。每局开始默认锁定对手，可通过锁定按钮或自定义锁定键切换自由瞄准。

默认键位见首页；X 按下后展开防御结界 2 秒并自动结束，冷却 30 秒。空中再次按空格可二段跳，按住空格可短暂滞空。

## 核对下载完整性

在 PowerShell 中对下载的文件运行：

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\ShinjukuDuel-0.3.1-windows-x64.zip'
Get-FileHash -Algorithm SHA256 -LiteralPath '.\ShinjukuDuel-0.3.1-android-arm64.apk'
```

结果应与同版本 `SHA256SUMS.txt` 完全一致。Windows 压缩包内部还有一份清单，可核对解压后的各文件。
