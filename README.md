# NJIT MCL 发布仓库

> 本仓库是 **启动器、社团整合包、服务器存档** 的唯一发布入口（`PCL-NJITMCL` 已归档，仅存启动器 1.0.3～1.4.6）。

## 一眼看懂

| 类别 | Tag 格式 | 数量 | 说明 |
|---|---|---|---|
| 启动器 | `v<版本>` | 4 | 最新 `v1.5.3` |
| 整合包 | `<服务器>-<版本>` | 12 | 整包 + 增量补丁 |
| 存档 | `saves-<服务器>` | 5 | 超过 2 GB 按 `.part01`… 分片 |

## 启动器

- 最新版本：**v1.5.3**（启动器 v1.5.3，22.9 MB）
- 更新清单：https://njitmc.club/update/njitmcl.json
- 每个 Release 固定 10 个资产：
  `PCL-NJITMCL.exe`、`PCL-NJITMCL.exe.config`、`PCL-NJITMCL.xml`、`MeloongCore.dll`、
  `MeloongCore.Wpf.dll`、`Microsoft.Win32.Registry.dll`、`PCLCS.dll`、`wg.exe`、`wireguard.exe`、
  `PCL-NJITMCL-<版本>.zip`
- 下载源顺序：GitHub 直链 → `gh-proxy.com` → 校园内网 `https://wg.njit-fkcy.top/modpacks/`

| 版本 | Tag | 主程序大小 | 发布时间 |
|---|---|---|---|
| 1.5.3 | `v1.5.3` | 5.8 MB | 2026-10-28 |
| 1.5.2 | `v1.5.2` | 5.8 MB | 2026-10-28 |
| 1.5.1 | `v1.5.1` | 5.8 MB | 2026-10-28 |
| 1.5.0 | `v1.5.0` | 5.8 MB | 2026-10-28 |

## 整合包（12）

| 服务器 | Tag | 资产 | 大小 | 发布 |
|---|---|---|---|---|
| changzhu | `changzhu-1.0.0` | 整包 1 + 补丁 19 | 599.5 MB | 2026-10-22 |
| cjzd | `cjzd-1.0.0` | 整包 1 | 119.8 MB | 2026-10-23 |
| hardcore | `hardcore-tech-1.0.0` | 整包 1 | 2.9 MB | 2026-10-23 |
| hello | `hello-xzc-1.0.0` | 整包 1 | 124.2 MB | 2026-10-23 |
| hgjh | `hgjh-1.0.0` | 整包 1 | 32.0 MB | 2026-10-23 |
| lgg | `lgg-1.0.0` | 整包 1 | 64.9 MB | 2026-10-23 |
| mechanomania-aero | `mechanomania-aero-0012-1.0.0` | 整包 1 | 5.8 MB | 2026-10-25 |
| tfcr2 | `tfcr2-1.0.0` | 整包 1 | 466.7 MB | 2026-10-23 |
| thefool | `thefool-1.0.0` | 整包 1 | 706.4 MB | 2026-10-22 |
| vanilla | `vanilla-age-1.0.0` | 整包 1 | 351.2 MB | 2026-10-23 |
| wxcs | `wxcs-1.0.0` | 整包 1 | 88.1 MB | 2026-10-23 |
| zshh | `zshh-1.0.0` | 整包 1 | 159.3 MB | 2026-10-23 |

## 存档（5）

| 服务器 | Tag | 分片/文件 | 大小 | 发布 |
|---|---|---|---|---|
| cjzd | `saves-cjzd` | 2 | 2005.7 MB | 2026-10-23 |
| hello-xzc | `saves-hello-xzc` | 2 | 2535.3 MB | 2026-10-23 |
| hgjh | `saves-hgjh` | 1 | 58.2 MB | 2026-10-23 |
| wxcs | `saves-wxcs` | 1 | 1693.8 MB | 2026-10-23 |
| zshh | `saves-zshh` | 1 | 693.6 MB | 2026-10-23 |

## 命名与发布规范

- 启动器：`v<主>.<次>.<修订>`，版本号单调递增，发布 10 个固定资产。
- 整合包：`<serverId>-<包版本>`；增量补丁作为同一 Release 的附加资产，命名 `patch-r<rev>-<文件名>`。
- 存档：`saves-<serverId>`，单文件 ≤ 2 GB，超出用 `name.part01`、`name.part02`…
- 不要在已有 Release 上改 tag（会断开所有已分发链接）；改内容请新增版本号。
- 完整发布流程（九步 + 四项验证）见社团档案 `档案-05-NJITMCL启动器.md` §三。

---

_本页清单由 API 生成于 2026-10-29；以 Releases 列表为准。_
