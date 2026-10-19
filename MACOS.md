# macOS 使用说明

0.4.4 macOS 包为 Universal 构建，支持 Intel 与 Apple Silicon，最低 macOS 12.0。

1. 解压下载的 ZIP，保留完整的 `ShinjukuDuel.app` 包内容。
2. 将 `.app` 拖到“应用程序”文件夹，或放到自己的用户文件夹中。
3. 双击启动即可，不需要安装 Unity 或其他运行环境。

鼠标左键普攻、右键格挡，中键锁定目标。触控板没有实体中键时，建议进入设置重新绑定锁定键；也可在那里调整鼠标灵敏度、音乐和音效音量。

Relay 邀请码和 LAN 联机使用与 Windows/Android 配套的 `shinjuku-lan-044-v1-fixed60` 协议，双方必须使用同一 0.4.4 版本。macOS 实体设备与跨平台实机联机尚未验证，构建与验包结论见本版最终清单。

当前 macOS 包没有 Apple Developer ID 签名和公证。首次打开若被系统拦截：

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
