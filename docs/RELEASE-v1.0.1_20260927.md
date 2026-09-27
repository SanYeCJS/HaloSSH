# HaloSSH v1.0.1_20260927

## 简体中文

本次更新集中修复 SSH 连接、日志浏览和复制粘贴体验，并增加会话备注名。

- **SSH 握手与最近使用：**移除固定 15 秒连接超时，默认跟随系统 OpenSSH 配置。可在「编辑会话 → SSH 认证与连接选项」设置超时（0 跟随系统，1–300 为秒数）。最近使用优先读取最新保存的主机、端口和认证设置；握手超时明确提示尚未进入密码验证。
- **终端日志：**大量输出采用分块与流量控制，改善滚动体验；右侧显示滚动条，后台标签恢复后能够滚到最新内容。
- **复制粘贴：**统一 ⌘C / ⌘V、系统菜单和右键路径；立即复制再粘贴会等待剪贴板写入，避免丢失或重复发送。多行粘贴仍需确认。
- **多服务器与重连：**各服务器的终端与文件树保持独立；手动断开后可以重连，并保留标签、分屏和终端历史。
- **断线提示：**同一会话每次断线只提醒一次，优先显示备注名，否则显示 IP / 主机名；成功重连后才重新允许下一次提醒。
- **备注名：**右键左侧会话或连接子项即可设置，顶部标签和其他窗口同步更新，重启后保留。

### 下载与升级

- **Apple Silicon / M 系列：**`HaloSSH-1.0.1_20260927-arm64.dmg`
- **Intel Mac：**`HaloSSH-1.0.1_20260927-x64.dmg`
- **校验文件：**`SHA256SUMS.txt`

需要 **macOS 13+**。保存正在编辑的文件，正常退出旧版，将新应用拖入 Applications 替换；原有工作区配置继续保留。旧版安装包仍可在历史 Release 中获取。

### 验证与已知限制

56 项单元测试通过；Intel 安装包通过延迟 18 秒握手、最近使用登录、8 个独立测试 SSH 服务并发连接、日志隔离、复制粘贴、备注与单次断线提示等运行回归。测试服务使用隔离的本机环境，并不代表全部公网或企业服务器配置。

Apple Silicon 安装包完成架构、依赖、签名和镜像校验，**尚未在 M 系列真机运行验证**。应用仍为 ad-hoc 本地签名，未完成 Apple Developer ID 签名和公证。安装方法见 [安装说明](INSTALL.md)。

握手超时发生在密码验证之前；本次调整避免软件过早退出，但无法保证解决服务器或网络不响应。自动文件树仍要求服务器启用 SFTP。

---

## English

This maintenance release improves SSH connections, log browsing and clipboard behavior, and adds persistent session labels.

- **SSH handshakes and recent sessions:** removed the fixed 15-second timeout. Connections follow system OpenSSH settings by default. In **Edit session → SSH authentication & connection options**, use 0 to inherit the system setting or 1–300 seconds for an explicit timeout. Recent entries use the latest saved connection settings. Banner timeouts now explain that password authentication has not started.
- **Terminal logs:** chunked output and flow control improve scrolling under heavy output. The scrollbar remains visible, and background tabs can scroll to their newest output when reopened.
- **Copy and paste:** unified ⌘C / ⌘V, application menus and context menus. Immediate paste waits for the preceding clipboard write, preventing missing or duplicate input. Multiline paste still requires confirmation.
- **Multiple servers and reconnect:** terminal and file channels stay isolated per server. Manual reconnect retains tabs, split panes and terminal history.
- **Disconnect notices:** one notice per session outage, identified by its label or host address. A successful reconnection resets the notification state.
- **Session labels:** right-click a session or live connection to set a label. Tabs and detached windows update immediately, and labels persist after restart.

### Download and upgrade

- **Apple Silicon / M-series:** `HaloSSH-1.0.1_20260927-arm64.dmg`
- **Intel Mac:** `HaloSSH-1.0.1_20260927-x64.dmg`
- **Checksums:** `SHA256SUMS.txt`

Requires **macOS 13+**. Save your remote edits, quit the previous version, then replace HaloSSH in Applications. Existing workspace settings are retained. Previous installers remain available in earlier Releases.

### Validation and limitations

56 unit tests passed. The Intel installer passed runtime checks for an 18-second delayed handshake, recent-session login, eight independent SSH test services, output isolation, clipboard actions, labels and once-per-outage notifications. These checks use isolated local services and do not establish compatibility with every public or enterprise server.

The Apple Silicon installer passed architecture, dependency, signature and disk-image checks, but **has not been run on M-series hardware**. The app remains ad-hoc signed, without Apple Developer ID signing or notarization. See [installation notes](INSTALL.md).

A banner timeout occurs before password authentication. This update prevents an unnecessarily early timeout; it cannot guarantee recovery when a server or network does not respond. The automatic file tree still requires server SFTP support.

---

SHA-256:

```text
b6c6b8cadd6a1839b770284f19d4934d499b369ffceebd7f23a4396e8732d53c  HaloSSH-1.0.1_20260927-x64.dmg
f6d4d99427ca01d5f53d61cb747f958f5622492a8e86bf1dffec310991dfb80a  HaloSSH-1.0.1_20260927-arm64.dmg
```
