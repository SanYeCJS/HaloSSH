# 安装说明 / Installation notes

## 简体中文

需要 macOS 13 或更新版本。Apple 菜单 → 关于本机显示“芯片 / Apple M…”时选择 arm64；显示 Intel 处理器时选择 x64。

打开 DMG，将 HaloSSH 拖入 Applications，然后从应用程序目录启动。当前发布使用 ad-hoc 本地签名，尚未完成 Apple Developer ID 签名或公证。如果系统阻止打开，请先确认文件来自本仓库的 Release，并核对校验值，再按 macOS“系统设置 → 隐私与安全性”中提供的选项允许打开。不同系统版本的提示可能不同；不要关闭 Gatekeeper 或 SIP。

校验安装包：在终端进入下载目录，并将 `SHA256SUMS.txt` 与两个 DMG 放在同一目录，运行：

```sh
shasum -a 256 -c SHA256SUMS.txt
```

若只下载一个 DMG，可以运行 `shasum -a 256 文件名.dmg`，与 Release 的对应值对照。校验值一致说明文件与发布文件一致，不代表 Apple 公证。

首次设置可跳过。SSH 在终端中完成密码、私钥口令等交互认证；右侧文件树在 SSH 登录成功后复用认证，服务器需启用 SFTP 子系统。如果文件树不可用，可先检查服务器是否允许 SFTP。

## English

Requires macOS 13 or later. In Apple menu → About This Mac, choose arm64 for an Apple M-series chip, or x64 for an Intel processor.

Open the DMG, drag HaloSSH into Applications, then launch it from there. This release is ad-hoc signed, without Apple Developer ID signing or notarization. If macOS blocks it, first verify that the download came from this repository's Release and check its checksum. Then use the available option in System Settings → Privacy & Security to allow the app. Wording varies by macOS version. Do not disable Gatekeeper or SIP.

To verify both installers, place them and `SHA256SUMS.txt` in the same directory and run the command above. If you downloaded only one installer, run `shasum -a 256 filename.dmg` and compare the result with the corresponding published value. A matching checksum confirms file integrity; it does not mean the app is notarized.

The initial setup is optional. SSH password and key-passphrase prompts are handled in the terminal. The file tree reuses the authenticated SSH connection and requires the server's SFTP subsystem.
