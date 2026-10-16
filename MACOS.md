# macOS 使用说明

0.3.5 macOS 预览包已完成 Universal 构建核验，支持 Intel 与 Apple Silicon，最低 macOS 12.0；6 个原生 Mach-O 均为 x86_64+arm64，Info.plist 版本为 0.3.5。ZIP 大小 94,604,128 bytes，SHA-256：`B099BF924218991A0D0B0CAFBD4E402CC7FD1CF55BE714E0C2E2C183B42085AF`。Mac 实机、Developer ID 签名、公证和跨设备联机仍待验证。

1. 解压 `ShinjukuDuel-0.3.5-macos-universal.zip`，保留完整的 `ShinjukuDuel.app` 包内容。
2. 将 `.app` 拖到“应用程序”文件夹，或放到自己的用户文件夹中。
3. 双击启动即可，不需要安装 Unity 或其他运行环境。

鼠标左键普攻、右键格挡，中键锁定目标。触控板没有实体中键时，建议进入设置重新绑定锁定键；也可在那里调整鼠标灵敏度、音乐和音效音量。

Relay 邀请码和 LAN 联机使用与 Windows/Android 配套的 `shinjuku-lan-035-v1` 协议，双方必须使用同一版本，旧端会被拒绝。0.3.5 移动纠偏已在 Windows 最终构建主验收中验证；macOS 包本身已完成构建核验，但当前没有 Mac 实机或跨平台联机验证，因此 macOS 联机体验仍待确认。

当前 macOS 预览包没有 Apple Developer ID 签名和公证。首次打开若被系统拦截：

1. 先尝试正常打开一次。
2. 打开“系统设置 > 隐私与安全性”（macOS 12 使用“系统偏好设置 > 安全性与隐私 > 通用”）。
3. 在安全性区域选择“仍要打开”，再按系统提示确认。

这是针对该应用的一次性例外，不需要关闭 Gatekeeper，也不要对整个应用目录批量执行 `xattr`。

如果某个解压工具丢失了 Unix 执行权限，只修复应用自身的主程序权限。先将下面的 `APP` 改成实际安装位置；主程序名从包内 `Info.plist` 读取：

```bash
APP="$HOME/Applications/ShinjukuDuel.app"
EXEC=$(/usr/libexec/PlistBuddy -c 'Print :CFBundleExecutable' "$APP/Contents/Info.plist")
chmod +x "$APP/Contents/MacOS/$EXEC"
```

Apple 的 Gatekeeper 说明：[Safely open apps on your Mac](https://support.apple.com/en-au/102445)。
