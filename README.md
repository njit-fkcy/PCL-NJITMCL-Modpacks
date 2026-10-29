# PCL-NJITMCL-Modpacks

NJIT MCL 社团 **整合包** 与 **服务器存档** 的发行仓库，隶属 GitHub 组织 [njit-fkcy](https://github.com/njit-fkcy)。

> 启动器（PCL 定制版）在 [PCL-NJITMCL](https://github.com/njit-fkcy/PCL-NJITMCL)。
> 早期地址 `github.com/xwan5840/PCL-NJITMCL-Modpacks` 会 301 跳转到本仓库。

## 目录

- [一眼看懂](#一眼看懂)
- [整合包](#整合包12)
- [存档](#存档5)
- [客户端如何使用](#客户端如何使用)
- [发布流程](#发布流程)
- [常见问题](#常见问题)
- [接手须知](#接手须知)

## 一眼看懂

| 类别 | Tag 格式 | 数量 | 说明 |
|---|---|---|---|
| 整合包 | `<serverId>-<包版本>` | 12 | 整包 + 增量补丁资产 |
| 存档 | `saves-<serverId>` | 5 | 单文件超过 2 GB 时按 `.part01`… 分片 |

## 整合包（12）

| 服务器 | 包版本 | Tag | 资产 | 大小 | 发布 |
|---|---|---|---|---|---|
| changzhu | 1.0.0 | `changzhu-1.0.0` | 20 | 599.5 MB | 2026-10-22 |
| cjzd | 1.0.0 | `cjzd-1.0.0` | 1 | 119.8 MB | 2026-10-23 |
| hardcore-tech | 1.0.0 | `hardcore-tech-1.0.0` | 1 | 2.9 MB | 2026-10-23 |
| hello-xzc | 1.0.0 | `hello-xzc-1.0.0` | 1 | 124.2 MB | 2026-10-23 |
| hgjh | 1.0.0 | `hgjh-1.0.0` | 1 | 32.0 MB | 2026-10-23 |
| lgg | 1.0.0 | `lgg-1.0.0` | 1 | 64.9 MB | 2026-10-23 |
| mechanomania-aero-0012 | 1.0.0 | `mechanomania-aero-0012-1.0.0` | 1 | 5.8 MB | 2026-10-25 |
| tfcr2 | 1.0.0 | `tfcr2-1.0.0` | 1 | 466.7 MB | 2026-10-23 |
| thefool | 1.0.0 | `thefool-1.0.0` | 1 | 706.4 MB | 2026-10-22 |
| vanilla-age | 1.0.0 | `vanilla-age-1.0.0` | 1 | 351.2 MB | 2026-10-23 |
| wxcs | 1.0.0 | `wxcs-1.0.0` | 1 | 88.1 MB | 2026-10-23 |
| zshh | 1.0.0 | `zshh-1.0.0` | 1 | 159.3 MB | 2026-10-23 |

- 整包：`<serverId>-<包版本>.zip`（或 `.mrpack`），首次安装下载。
- 增量补丁：同一 Release 的附加资产，命名 `patch-r<rev>-<文件名>`，客户端按 revision 逐个应用。
- `changzhu` 共 20 个资产（1 个整包 + 历史增量补丁），是修订次数最多的包；其余包多数只有 1 个整包。

## 存档（5）

| 服务器 | Tag | 文件数 | 大小 | 发布 |
|---|---|---|---|---|
| cjzd | `saves-cjzd` | 2 | 2005.7 MB | 2026-10-23 |
| hello-xzc | `saves-hello-xzc` | 2 | 2535.3 MB | 2026-10-23 |
| hgjh | `saves-hgjh` | 1 | 58.2 MB | 2026-10-23 |
| wxcs | `saves-wxcs` | 1 | 1693.8 MB | 2026-10-23 |
| zshh | `saves-zshh` | 1 | 693.6 MB | 2026-10-23 |

超过 2 GB 的存档按 `name.part01`、`name.part02`… 顺序分片，客户端会自动解压到对应版本目录。

## 客户端如何使用

- 启动器「社团服务器」页读取 `https://njitmc.club/api/launcher/servers`，拿到每个服务器的整合包与存档条目（含 5 个下载源、sha256、size、revision、patches）。
- 安装整合包时写入 `versions\<实例>\PCL\njitmcl-pack.json` 记录 `packId / revision / sha256`。
- 之后每次刷新按 sha256（没有则按 revision）比对是否需要更新；点「立即更新」时按补丁链先下载新增文件到暂存区、校验 sha256，再删旧增新，最后写标记。
- 因此**整包被重新上传但 revision 未递增**会导致「服务端没有可用的增量补丁」；处理方式是补一条 `note` 非空的空补丁并递增 revision。

## 发布流程

发布工具：本地 `发布工具\发布工具.py`（GUI）——整合包修订、存档分片上传、登记中控数据都在里面。

1. 用发布工具构建/修订整合包（自动读清单、增删条目、重建 zip、记录 sha256 与大小）。
2. 上传整包到本仓库对应 Release（tag `<serverId>-<包版本>`）与内网 `/var/www/modpacks/<serverId>/`。
3. 增量补丁的每个新增文件必须有 **5 个下载源**（校内组网 + GitHub + 3 个公共中转），空源会导致玩家更新超时。
4. 用 `POST /api/admin/launcher/packs` 登记中控（`sha256`、`size`、`sources`、`revision`、`patches`），必要时补空补丁。
5. 验证：`GET /api/launcher/servers` 中 revision / patches / manifest 正确；抽查各源 `curl -r 0-1023`。
6. 建档：`档案-04-社团官网njitmc-club.md` §三。

存档同理：分片上传 → 登记 `saves[]`（含文件名、sha256、size、sources）→ 验证。

## 常见问题

| 现象 | 处理 |
|---|---|
| 玩家报「没有可用的增量补丁」 | 整包换了但 revision 没递增；补一条 `note` 非空的空补丁并递增 revision |
| 更新卡住 / 超时 | 补丁 `add[]` 的 `sources` 为空或指向失效中转；补齐 5 源 |
| 内网文件名带 `+` 下载 404 | URL 里的 `+` 必须编码成 `%2B` |
| 存档解压失败 | 检查分片顺序与 sha256；分片必须按序号命名 |
| 资产超过 2 GB 传不上 | GitHub 单资产上限 2 GB，存档必须分片 |

## 接手须知

- 中控数据存于官网服务器 `/var/lib/blockdimension/data/website.sqlite3`，一律通过 `storage.Store.mutate("servers", fn)` 修改，先备份再改，改完重启 `blockdimension`。
- 积分/下载统计与服务器在线状态由官网后端提供，不在本仓库。
- 权威档案：`档案-05-NJITMCL启动器.md`（整体流程）与 `档案-04-社团官网njitmc-club.md`（服务端数据）。
- 不要修改已有 tag 名：所有已分发链接都基于 tag 路径。

---

_清单由 GitHub API 生成于 2026-10-29，以 Releases 列表为准。_
