# Gettr Desktop 下载

Gettr Desktop 安装包与 Tauri updater 清单的公开分发仓库。本仓库只存放构建产物，
不包含源码。

## 下载

下面的地址永久指向最新正式版本，不随版本号变化：

| 平台 | 下载 |
| --- | --- |
| Windows x64 (MSI) | [Gettr_x64_en-US.msi](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/Gettr_x64_en-US.msi) |
| Windows x64 (安装程序) | [Gettr_x64-setup.exe](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/Gettr_x64-setup.exe) |
| macOS Apple Silicon | [Gettr_aarch64.dmg](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/Gettr_aarch64.dmg) |

历史版本见 [Releases](https://github.com/flamecast-pc/gettr-desktop-releases/releases)。
标记为 pre-release 的版本是内部测试版，不会出现在上面的地址中。

## 校验安装包

每个 Release 都带 `SHA256SUMS.txt`，覆盖该版本全部带版本号的资产：

```bash
curl -fsSLO https://github.com/flamecast-pc/gettr-desktop-releases/releases/download/v0.1.8/SHA256SUMS.txt
sha256sum --check SHA256SUMS.txt
```

macOS 上把 `sha256sum --check` 换成 `shasum -a 256 --check`。

## 自动更新

已安装的客户端通过 Tauri updater 读取
[`latest.json`](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/latest.json)
检查更新，并用内置公钥验证更新包签名。更新是整包冷更新，安装前需要先离开房间并停止
全部媒体源。

---

# Gettr Desktop Downloads

Public distribution repository for Gettr Desktop installers and the Tauri updater
manifest. Build outputs only — no source code here.

The `releases/latest/download/` links above always resolve to the newest stable
release. Pre-releases are internal test builds and are excluded from them.
