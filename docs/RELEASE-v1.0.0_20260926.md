# HaloSSH v1.0.0_20260926

## 简体中文

HaloSSH 是为 macOS 打造的 SSH 终端与远程文件工作区。作为一名 iOS 开发者，我一直希望在 Mac 上拥有一款符合自己工作习惯和审美的 SSH 工具，因此开发了 HaloSSH，希望补上自己日常工作流里的这块空白。

本次发布提供：

- SSH 终端、登录后自动出现的 SFTP 文件树、文本只读预览与编辑保存。
- 会话文件夹、收藏、最近使用时间、连接状态与服务器计数。
- 多标签、分屏、标签排序与移窗、可拖动调整和折叠的面板。
- 六套主题、字体设置与导入、亚克力背景、自定义工作台图片。
- 简体中文 / English 和简洁的首次启动引导。
- 隧道、快捷命令、脚本、日志及更多协议工具；详见项目说明中的功能与兼容范围。

### 附件选择

- **Apple Silicon / M 系列：**`HaloSSH-1.0.0_20260926-arm64.dmg`
- **Intel Mac：**`HaloSSH-1.0.0_20260926-x64.dmg`
- **完整性校验：**`SHA256SUMS.txt`

需要 **macOS 13+**。打开 DMG 后将 HaloSSH 拖入 Applications。无需额外安装 Xcode、Node.js 或 Python。

当前使用 ad-hoc 本地签名，**尚未进行 Apple Developer ID 签名和公证**。Intel 版本已在本机运行验证；arm64 版本已检查架构、依赖、签名与磁盘映像，**尚未在 M 系列真机运行验证**。自动文件树需要服务器支持 SFTP；文本编辑支持 ≤2 MiB UTF-8 文件。高级协议和硬件场景仍需要更多真实环境测试。

如果喜欢 HaloSSH，欢迎给仓库一个 **Star ⭐**。感谢你的使用、建议与支持！

---

## English

HaloSSH brings SSH terminals and remote files into one macOS workspace. As an iOS developer, I wanted an SSH tool that matched my daily workflow and visual preferences, so I built HaloSSH to fill that gap in my own work.

This release includes:

- SSH terminals, an SFTP tree that reuses your login, read-only text previews and explicit editing/saving.
- Session folders, favorites, recent connection times, connection status and server counts.
- Tabs, split panes, tab reordering and detachable windows, resizable and collapsible panels.
- Six themes, font settings and imports, acrylic backgrounds and custom workbench images.
- Simplified Chinese / English and a short first-run setup.
- Tunnels, quick commands, scripts, logs and additional protocol tools; see the README for details and compatibility limits.

### Choose your asset

- **Apple Silicon / M-series:** `HaloSSH-1.0.0_20260926-arm64.dmg`
- **Intel Mac:** `HaloSSH-1.0.0_20260926-x64.dmg`
- **Checksums:** `SHA256SUMS.txt`

Requires **macOS 13+**. Open the DMG and drag HaloSSH into Applications. No separate Xcode, Node.js or Python installation is needed.

This release is ad-hoc signed, **without Apple Developer ID signing or notarization**. The Intel build has been run and tested locally. The arm64 build has passed architecture, dependency, signature and disk-image checks, but **has not yet been tested on M-series hardware**. The automatic file tree requires server SFTP support. Text editing supports UTF-8 files up to 2 MiB. Advanced protocols and hardware setups need further real-world validation.

If you like HaloSSH, please give the repository a **Star ⭐**. Thank you for trying it, sharing feedback and supporting the project!

---

Author / 作者：[SanYeCJS](https://github.com/SanYeCJS) · [742377690@qq.com](mailto:742377690@qq.com)

SHA-256:

```text
982b7573bb590edecb0d9ea9b046261c6e3b0730550022bc6ea11c62bc3a8f30  HaloSSH-1.0.0_20260926-x64.dmg
cc1026e6969a7aa071b9afcc05d258ec5aa758eb7575fdf1ba7db02ac725ce5f  HaloSSH-1.0.0_20260926-arm64.dmg
```
