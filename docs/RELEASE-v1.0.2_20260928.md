# HaloSSH v1.0.2_20260928

## 简体中文

本次修复集中解决在 SSH 终端运行 Codex CLI 时，标签移出窗口后无法滚动及输出闪烁的问题。

- **CLI 滚动恢复：**移动标签时保留 SGR 鼠标编码，使新窗口的鼠标滚轮继续到达远端 CLI；方向键与 PageUp/PageDown 继续遵循 CLI 自身的操作方式。
- **消除分包重绘闪烁：**支持 DEC 2026 同步输出，将跨 SSH 数据包的清屏和绘制作为完整画面呈现。大量输出继续使用流量控制；程序遗漏结束标记时自动恢复绘制。
- **窗口迁移状态：**保留历史阅读位置、滚动区域、保存的光标和光标可见性/样式，支持移到新窗口及移回已有窗口。
- **普通日志浏览：**支持鼠标滚动、Shift+↑/↓ 逐行和 Shift+PageUp/PageDown 翻页；阅读历史时持续输出不再因迁移而把视图带回底部。

### 安装

- Intel Mac：`HaloSSH-1.0.2_20260928-x64.dmg`
- Apple Silicon / M 系列：`HaloSSH-1.0.2_20260928-arm64.dmg`
- 校验文件：`SHA256SUMS.txt`

需要 macOS 13+。保存编辑中的文件，退出旧版 HaloSSH，将新版本拖到 Applications 替换。原有会话配置继续保留。

### 验证范围

56 项单元测试通过。Intel 安装包从 DMG 复制到隔离目录后验证 Codex 风格终端协议、双 SSH 服务持续日志、标签往返迁移、大量日志滚动与复制粘贴。旧版迁移后滚轮事件丢失，且分包绘制出现空白帧；修复版相同采样中未出现空白或残缺帧。

Codex 场景采用离线协议夹具，覆盖备用屏幕、SGR 鼠标、应用方向键、同步输出与滚动区域，未调用模型服务，也未使用用户真实服务器；不代表已测试所有 Codex CLI 版本。

Apple Silicon 包已做架构、依赖、签名和镜像校验，尚未在 M 系列真机运行验证。应用仍使用本地 ad-hoc 签名，未完成 Apple Developer ID 公证。安装步骤见 [安装说明](INSTALL.md)。

---

## English

This maintenance release fixes mouse scrolling after detaching a Codex CLI tab and visible flicker during streaming terminal redraws.

- Preserve SGR mouse encoding so wheel events still reach the remote CLI after a window transfer. Application cursor keys and paging remain under the CLI's control.
- Support DEC 2026 synchronized output, keeping a clear-and-redraw operation visually atomic across SSH packets. Parsing and flow-control acknowledgements continue during a frame, with a watchdog for missing end markers.
- Preserve the history viewport, scrolling margins, saved cursors and cursor visibility/style when moving a tab out and back.
- Add Shift+Up/Down and Shift+PageUp/PageDown history navigation in normal terminals; reading history remains stable while output continues.

### Install and validation

Requires macOS 13+. Download the `x64` DMG for Intel or `arm64` DMG for Apple Silicon. Save open edits, quit HaloSSH and replace it in Applications. Existing connection settings are retained. Checksums are in `SHA256SUMS.txt`.

56 unit tests passed. The Intel installer was copied from its DMG into an isolated directory for Codex-style protocol, dual-SSH streaming, tab transfer and heavy-output/clipboard tests. The old build lost wheel reports after transfer and displayed blank redraw frames; the fixed build had no blank or partial frames in the same sampling checks.

The Codex tests use an offline protocol fixture, without model requests or access to user servers, and do not establish compatibility with every CLI version. Apple Silicon received static architecture, dependency, signature and image checks, without a hardware runtime test. The app remains ad-hoc signed and is not Apple-notarized. See [installation notes](INSTALL.md).

---

SHA-256:

```text
594eff9d5a56ab2cedbd3052b2ded1b63a5be90909c8358c0d4372ba2fd27ede  HaloSSH-1.0.2_20260928-x64.dmg
067ab6720e247a847d04fa928fd9decde551634c005e33a690bcbf7b44e9751f  HaloSSH-1.0.2_20260928-arm64.dmg
```
