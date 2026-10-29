# PCL-NJITMCL-Modpacks

NJIT MCL 社团 **整合包** 与 **服务器存档** 发行仓库。

> 启动器（PCL 定制版）在 [PCL-NJITMCL](https://github.com/xwan5840/PCL-NJITMCL)。

## 一眼看懂

| 类别 | Tag 格式 | 数量 | 说明 |
|---|---|---|---|
| 整合包 | `<服务器>-<版本>` | 12 | 整包 + 增量补丁资产 |
| 存档 | `saves-<服务器>` | 5 | 单文件超过 2 GB 时按 `.part01`… 分片 |

## 整合包（12）

| 服务器 | Tag | 资产 | 大小 | 发布 |
|---|---|---|---|---|
| 整合包 · changzhu 1.0.0 | `changzhu-1.0.0` | 20 | 599.5 MB | 2026-10-22 |
| 整合包 · cjzd 1.0.0 | `cjzd-1.0.0` | 1 | 119.8 MB | 2026-10-23 |
| 整合包 · hardcore-tech 1.0.0 | `hardcore-tech-1.0.0` | 1 | 2.9 MB | 2026-10-23 |
| 整合包 · hello-xzc 1.0.0 | `hello-xzc-1.0.0` | 1 | 124.2 MB | 2026-10-23 |
| 整合包 · hgjh 1.0.0 | `hgjh-1.0.0` | 1 | 32.0 MB | 2026-10-23 |
| 整合包 · lgg 1.0.0 | `lgg-1.0.0` | 1 | 64.9 MB | 2026-10-23 |
| 整合包 · mechanomania-aero-0012 1.0.0 | `mechanomania-aero-0012-1.0.0` | 1 | 5.8 MB | 2026-10-25 |
| 整合包 · tfcr2 1.0.0 | `tfcr2-1.0.0` | 1 | 466.7 MB | 2026-10-23 |
| 整合包 · thefool 1.0.0 | `thefool-1.0.0` | 1 | 706.4 MB | 2026-10-22 |
| 整合包 · vanilla-age 1.0.0 | `vanilla-age-1.0.0` | 1 | 351.2 MB | 2026-10-23 |
| 整合包 · wxcs 1.0.0 | `wxcs-1.0.0` | 1 | 88.1 MB | 2026-10-23 |
| 整合包 · zshh 1.0.0 | `zshh-1.0.0` | 1 | 159.3 MB | 2026-10-23 |

增量补丁作为同一 Release 的附加资产，命名 `patch-r<rev>-<文件名>`；客户端按 revision 逐个应用。

## 存档（5）

| 服务器 | Tag | 文件数 | 大小 | 发布 |
|---|---|---|---|---|
| cjzd | `saves-cjzd` | 2 | 2005.7 MB | 2026-10-23 |
| hello-xzc | `saves-hello-xzc` | 2 | 2535.3 MB | 2026-10-23 |
| hgjh | `saves-hgjh` | 1 | 58.2 MB | 2026-10-23 |
| wxcs | `saves-wxcs` | 1 | 1693.8 MB | 2026-10-23 |
| zshh | `saves-zshh` | 1 | 693.6 MB | 2026-10-23 |

## 命名与发布规范

- 整合包：`<serverId>-<包版本>`，例如 `changzhu-1.0.0`。
- 存档：`saves-<serverId>`，单文件 ≤ 2 GB，超出用 `name.part01`、`name.part02`… 顺序分片。
- 不要在已有 Release 上改 tag（会断开所有已分发链接）；内容变化请新增版本号或 revision。
- 增量补丁的每个新增文件必须同时提供 5 个下载源，空源会导致玩家更新超时。
- 完整发布流程与故障排查见社团档案 `档案-05-NJITMCL启动器.md`。

---

_本页表格由 GitHub API 生成于 2026-10-29，以 Releases 列表为准。_
