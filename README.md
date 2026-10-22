# OpenDictionary · APK 预发布更新源

本仓库只存放 OpenDictionary Android 应用的可安装包（APK）与更新元数据，**不放源码**。
源码在独立的软件代码仓库中；本仓库不使用正式 release，只发布 **prerelease（预发布）**。

## 安装

从 [Releases](https://github.com/XHR666/OpenDictionary-apk/releases) 页面选择最新预发布，下载 `.apk` 安装（Android 13+）。

## 更新机制

应用内"检查更新"只读取本仓库的 GitHub Releases，并要求：

- Release 标记为 **prerelease**（预发布）；
- 资产中包含 **`update.json`** 和 **`.apk`**；
- `update.json` 合法且 `versionCode` 高于当前安装版本。

因此修改 README、提交代码或 push 分支**不会**触发更新；只有按契约发布的预发布版本才会被检测到。详细契约见 `UPDATE.md`。

## 资产说明

| 资产 | 说明 |
|---|---|
| `opendictionary-<version>.apk` | 安装包 |
| `update.json` | 版本、包名、sha256、大小、更新说明 |

校验方式：下载后比对 `update.json` 中的 `sha256` 与文件哈希。

## 许可

APK 为 GPL-3.0-or-later 软件的构建产物；本仓库中的元数据（README/UPDATE.json 等）按 CC BY 4.0 提供。
