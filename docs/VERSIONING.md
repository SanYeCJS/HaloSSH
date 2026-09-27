# 版本管理 / Versioning

公开版本采用 `v主版本.次版本.修订版本_YYYYMMDD`，例如 `v1.0.1_20260927`。macOS 应用内部使用数值版本 `1.0.1`；界面、安装包文件名和 GitHub Release 使用完整版本标识。

- 修复兼容性和缺陷时增加修订版本；新增兼容功能时增加次版本；重大不兼容调整时增加主版本。
- 同一天再次发布不同安装包也增加版本号，避免同一版本指向不同文件。
- 每个 Release 对应独立 Git tag、更新说明、Intel / Apple Silicon DMG 和 SHA-256 校验文件。
- 已公开的标签和安装包保留，不用新包覆盖旧包；新发布验证完成后设为 Latest。
- 本仓库发布产品文档、截图与二进制安装包；Git tag 指向该版本的发布文档提交。

## English

Public versions use `vMAJOR.MINOR.PATCH_YYYYMMDD`, such as `v1.0.1_20260927`. The macOS numeric version is `1.0.1`; the interface, installer names and GitHub Release use the full identifier.

- Increment PATCH for fixes, MINOR for compatible features and MAJOR for breaking changes.
- A different installer gets a new version even when released on the same date.
- Each Release has its own Git tag, release notes, Intel / Apple Silicon DMGs and SHA-256 checksums.
- Keep published tags and assets intact. Mark a validated new release as Latest.
- This repository hosts product documentation, screenshots and binary releases. Tags identify the associated release-documentation commit.
