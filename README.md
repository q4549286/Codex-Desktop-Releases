# Codex Desktop 管理器

这是 Codex Desktop 管理器的公开下载页和自动更新源。

源码仓库不在这里发布；本仓库只保存安装包、`latest.json` 自动更新清单和校验文件，方便用户无需登录 GitHub 就能下载和更新。

## 下载

正式最新版本请到 [Releases](https://github.com/q4549286/Codex-Desktop-Releases/releases/latest) 下载。

当前测试包：[manual-test-2026-07-02](https://github.com/q4549286/Codex-Desktop-Releases/releases/tag/manual-test-2026-07-02)

| 平台 | 文件 |
| --- | --- |
| Windows x64 | `CodexAppManager_x64-setup.exe` |
| macOS Apple Silicon | `CodexAppManager_aarch64.dmg` |
| macOS Intel | `CodexAppManager_x86_64.dmg` |

## macOS 首次打开

免费构建没有 Apple Developer ID 公证，macOS 可能提示“已损坏，无法打开”。安装到 `/Applications` 后运行：

```bash
sudo xattr -dr com.apple.quarantine "/Applications/Codex Desktop 管理器.app" && open "/Applications/Codex Desktop 管理器.app"
```

如果应用名称仍显示为旧名称：

```bash
sudo xattr -dr com.apple.quarantine "/Applications/Codex App Manager.app" && open "/Applications/Codex App Manager.app"
```

## 自动更新

应用内自动更新读取：

```text
https://github.com/q4549286/Codex-Desktop-Releases/releases/latest/download/latest.json
```

请保持本仓库公开，否则普通用户的客户端无法无登录检查更新。

## 校验

Release Assets 中的 `SHA256SUMS` 可用于校验下载文件。

Windows:

```powershell
Get-FileHash .\CodexAppManager_x64-setup.exe -Algorithm SHA256
```

macOS:

```bash
shasum -a 256 CodexAppManager_aarch64.dmg
```
