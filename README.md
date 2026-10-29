# NJIT MCL 统一发布仓库

本仓库是 NJIT MCL 启动器、社团整合包与存档的**唯一发布入口**。

## 发布内容

| Tag 形式 | 内容 |
|---|---|
| `v<启动器版本>` | 启动器发行资产（固定 10 个文件） |
| `<serverId>-<包版本>` | 社团整合包整包，增量补丁为同 Release 下的 `patch-r<rev>-*` |
| `saves-<serverId>` | 服务器存档，超过 2 GB 时按 `.part01`… 分片 |

## 启动器资产清单（每个 `v*` Release 固定 10 个）

`PCL-NJITMCL.exe`、`PCL-NJITMCL.exe.config`、`PCL-NJITMCL.xml`、
`MeloongCore.dll`、`MeloongCore.Wpf.dll`、`Microsoft.Win32.Registry.dll`、
`PCLCS.dll`、`wg.exe`、`wireguard.exe`、`PCL-NJITMCL-<版本>.zip`

客户端下载顺序：GitHub 直链 → gh-proxy → 校园内网（`https://wg.njit-fkcy.top/modpacks/`）。
更新清单：`https://njitmc.club/update/njitmcl.json`。

## 沿革

- 2026-10-21 创建 `PCL-NJITMCL`，承载启动器 1.0.3 ～ 1.4.6。
- 2026-10-22 创建本仓库，承载整合包与存档；自 1.5.0 起启动器也发布在这里。
- 旧仓库已归档，仅作历史留存，**不要再向它发布**。

发布流程见社团档案 `档案-05-NJITMCL启动器.md` §三（九步 + 四项验证）。
