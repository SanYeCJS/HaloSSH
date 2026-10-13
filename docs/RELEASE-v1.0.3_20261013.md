# HaloSSH v1.0.3_20261013

## 简体中文

新增 SSH 记住密码与下次自动登录，并修复超时后刷新的恢复流程。

- **可选记住密码：**服务器要求密码时，勾选「记住密码，下次自动登录」。常用会话、最近使用、侧栏及刷新重连共用保存的密码；仍可选择在终端中输入。
- **成功后才保存：**密码通过 macOS 钥匙串保护的系统加密存储在本机，不写入终端日志、连接参数或导出配置。每个会话独立绑定实际主机、端口、用户与认证配置。
- **失效后重新询问：**保存的密码被拒绝后只自动尝试一次，随后重新询问；新密码登录成功才替换旧凭据。多台服务器的登录框按顺序展示，不相互覆盖。
- **超时刷新重连：**终端刷新会重新连接当前服务器，有保存密码则自动登录，无保存密码则再次询问。右侧文件树断开后点击刷新也会恢复 SSH 登录和目录，复用同一次认证。
- **忘记密码：**右键会话或打开编辑会话，选择「忘记已保存密码」，确认后移除；取消确认保留原密码，当前连接不受影响。
- **快速断开与手动登录：**成功登录后立即断开仍完成密码保存；刷新时不再让旧终端的自动焦点报告干扰手动密码输入。
- **常用会话恢复：**修复断开后点击常用会话只切回失效标签的问题。手动刷新保留当前终端 ID、历史和分屏布局。

主机密钥校验仍由系统 OpenSSH 完成；首次连接仍需核对。私钥口令、MFA 与跳板链继续在终端交互输入；跳板链暂不自动保存密码，避免误用目标服务器凭据。

### 安装

需要 macOS 13+。保存编辑中的文件，退出旧版 HaloSSH，将新版本拖入 Applications 替换；已有会话与设置保留。

- Intel：`HaloSSH-1.0.3_20261013-x64.dmg`
- Apple Silicon / M 系列：`HaloSSH-1.0.3_20261013-arm64.dmg`
- SHA-256 校验文件：`SHA256SUMS.txt`

### 验证与限制

使用独立回环 SSH 服务和合成密码验证首次保存、完整重启后自动登录、密码失效与更新、地址变更、并发登录、取消与忘记密码、配置导出及实际保活超时后的刷新恢复；不使用用户真实服务器或密码。

应用仍使用本地 ad-hoc 签名，尚未完成 Apple Developer ID 签名与公证。Apple Silicon 安装包进行架构、依赖、签名和镜像检查，尚未在 M 系列真机运行验证。详见 [安装说明](INSTALL.md)。

---

## English

This release adds optional remembered SSH passwords and automatic login, and fixes reconnecting after a session timeout.

- **Remember passwords:** select “Remember password for automatic login” when SSH requests a password. Favorites, Recent, sidebar sessions and reconnect share the saved credential. Manual terminal input remains available.
- **Save only after success:** credentials are encrypted locally using macOS Keychain-backed system storage. They are excluded from terminal logs, command-line arguments and configuration exports, and bound to the session’s resolved destination, port, user and authentication settings.
- **Recover from expired credentials:** a rejected saved password is tried automatically only once, then a fresh password is requested. Replacement credentials are saved only after successful authentication. Concurrent login dialogs are queued and clearly identify their server.
- **Refresh after timeout:** the terminal refresh button reconnects the current server, automatically using a saved password or prompting for one. Refreshing a disconnected file tree also reconnects SSH and restores its directory listing through the same login.
- **Forget credentials:** use the session context menu or editor. Removing a saved password requires confirmation; cancelling preserves it and existing connections remain open.
- **Quick disconnects and manual input:** verified passwords finish saving after a quick disconnect, and stale terminal focus reports no longer interfere with password input during reconnect.
- **Favorites:** opening a disconnected favorite now starts a new connection. Manual refresh retains terminal identity, history and split layout.

OpenSSH host-key verification remains enabled. Key passphrases, MFA and jump routes retain interactive terminal input; automatic password storage is not enabled for jump routes to avoid confusing jump-host and destination credentials.

### Install and validation

Requires macOS 13+. Save open edits, quit HaloSSH and replace it in Applications. Existing sessions and settings are retained. Choose `x64` for Intel or `arm64` for Apple Silicon. SHA-256 checksums are included in `SHA256SUMS.txt`.

Tests use independent loopback SSH servers and synthetic credentials, covering restart persistence, expired passwords, destination changes, concurrent logins, cancellation, forgetting, exports and refresh after a real keepalive timeout. No user servers or credentials are used.

The app remains ad-hoc signed and is not Apple-notarized. Apple Silicon receives architecture, dependency, signature and disk-image checks, without M-series hardware runtime validation. See [installation notes](INSTALL.md).

## SHA-256

```text
2b31925d8b3031958f1718b8cc7d584431674e16374aa6a3b27db3400fde5134  HaloSSH-1.0.3_20261013-x64.dmg
2cc23b95bf3ba8cda32b14184cdd4a434866f5fbaec09cac1d72cc7614a16963  HaloSSH-1.0.3_20261013-arm64.dmg
```
