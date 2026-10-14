# B13.4.11修改与验证｜2026-10-14

## 判断

修复合理。严重、持续的形态或伤情通常已有前期资产，应先复用；画布阶段只处理真实漏项，不为轻微状态机械补图。问题有两个来源：下游文档推翻上游免生成判断；旧15秒validate_character_states.py把每次状态变化强制绑定不同state_image。后者已实际修复，不只是换措辞。

## 修改文件

| 文件（相对Skills父目录） | 修改 |
| --- | --- |
| pixmax-codex-pipeline/SKILL.md | 必要性主规则贯穿下游；完整状态板适用前提；维护任务一并GitHub发布偏好 |
| pixmax-codex-pipeline/AGENTS.md | 连续性、导入和验收区不再索要所有状态图 |
| pixmax-codex-pipeline/VERSION | 实际工作流13.4.11-prep-20261014 |
| pixmax-codex-pipeline/references/post-import-asset-analysis.md | 按资产职责观察；无图轻微状态可准备，只统计真实图片缺口 |
| pixmax-codex-pipeline/references/continuity-self-review.md | 区分事实／可见性／独立图；旧伤提及、换装和时域不扩散；不提前带伤 |
| pixmax-codex-pipeline/references/pre-generation-asset-visual-review.md | 母图身份／造型与镜头状态分开，不伪造图片已有伤情 |
| pixmax-codex-pipeline/references/character-state-board-quality.md | 四视图只约束确需完整板；局部组件按用途，不放大伤口凑板式 |
| pixmax-codex-pipeline/references/asset-generation-recovery.md | 每次追加先复核必要性；非必要图退出当前依赖，历史失败／费用／计数保留 |
| pixmax-codex-pipeline/references/shared-asset-coordination.md | 判断确需图后才认领；免生成不建虚拟READY图，已接受／未知仍对账 |
| pixmax-codex-pipeline/references/script-driven-workflow.md | 移除“特殊状态无图必须生成” |
| pixmax-codex-pipeline/references/fast-binding-and-state.md | 新旧记录兼容说明；提示词状态不判绑定缺失 |
| pixmax-codex-pipeline/references/optimized-execution.md | 按实现方式盘点，取消旧三视图机械要求 |
| pixmax-codex-pipeline/references/integrated-production-flow.md | 统一入口按职责核对，不强制微小状态图 |
| pixmax-codex-pipeline/references/six-panel-storyboard-images.md | 兼容文档中轻微状态可交图词／镜头表达，不重新启用927 |
| pixmax-codex-pipeline/scripts/validate_character_states.py | 增加显式prompt／tolerance实现方式，免独立state_image；原默认检查保留 |
| pixmax-codex-pipeline/tests/test_minor_state_preparation.py | 新增19项离线行为与回归测试 |
| tiktok-custom-drama-production/SKILL.md | 普通轻微状态不需先收费试制，输入方案与效果验证分开 |
| tiktok-custom-drama-production/references/资产规划与按需生成规则.md | 唯一必要性来源，补充轻微／关键／时域判断，不新建第二套分类 |

本机全局AGENTS只定点添加上述轻微状态及一并发布规则，其他个人偏好保留。包内发布材料、跨会话合并片段和安装指令同步更新；本次完整包两套相关Skill取实际维护源，不再取旧包中的资产规划副本，避免下次安装回退。

## 代码审查结论与兼容

asset_visual_review.py只核实际连接图片、来源／账本／提示词哈希和有效观察，不按伤情文字索要独立状态图；state_board_review.py仅对明确完整板或既有state_board_required声明检查四视图；submit_saved_batch.py只对真实绑定依赖做预检。因此这三个脚本不需改逻辑，也没有全局关闭验收。

2.5沿用原schema及现有字段，不新增每个状态独立JSON。旧15秒记录未写implementation时仍按state_image检查实际母图／状态图及哈希、五项review；新prompt或tolerance沿用状态发生时段和母图字段，reason说明必要性／可见性，prompt另填prompt_state。不修改旧FAIL；新方案另存本次复核记录。完整板缺视图、错身份／侧别仍失败，局部组件不能冒充完整板。

必要性、美术观察、微小标记是否关键及公共资产认领仍是执行助手判断，不是像素识别器或自动状态分类程序。代码通过只说明记录有效，不能证明生成效果、真实伤情或现场制作已验收。

## 本地验证

主工作流143项：140通过，3项因未配置FFMPEG_BINARY跳过本地裁切测试；新增19项全部通过。覆盖：

- 正确母图＋非特写小擦伤：可准备，无新状态图依赖。
- 非叙事袖口裂口／污渍：容差，不自动排图。
- 对白仅提及旧伤：不增加现时痕迹图依赖。
- 连续救援少量血迹：提示词保留，不强制整板。
- 段中划伤：前态／触发／后态保留，无图可准备。
- 精确辨认标记缺参考：对应UNCERTAIN仍阻塞。
- 重要变身／腹部轮廓／严重伤病姿态缺口：NEEDS_FIX仍阻塞。
- 错脸、主要服层、场景／时域：不按小状态容差放行。
- 真实完整板错脸、错侧别或缺视图：不通过。
- 非必要旧FAIL：当前母图方案不被阻塞，历史文件字节不变。
- 已排队／未知提交：分别复用／要求对账，均未重发。
- 所有新准备测试使用Fake接口，只有只读查询，无生图、生成、超分或剪辑台写入。

既有回归继续验证原文可逆绑定、对白／表演文字不可暗改、有序输入及真实UUID、动态数量容量、参数向上取整、来源变更失效及防重复提交。默认导演30项测试通过，并与B13.4.10目录逐文件哈希一致（整个文件集未改）。

使用包内原安装器验证临时目录B13.4.10→B13.4.11升级及重复安装ALREADY_CURRENT；逐文件核验安装结果。结果见checks/离线校验结果.json。本机注册副本同步后也跑同一回归。quick_validate.py因本机缺PyYAML无法运行；用Ruby标准YAML解析检查两套Skill frontmatter名称、描述及长度，结果通过，不冒称原工具通过。

## 备份、发布与边界

修改前本地源／注册两套Skill及全局AGENTS备份：
Skill_packages/backups/20261014_轻微状态规则修复前。
旧B13.4.10源包与ZIP保留，不覆盖；新完整包工作流B13.4.11，默认导演B13.4.3未改。新增GitHub发布授权仅适用于工作流维护内容，不上传这个问题涉及的实际剧本、媒体、任务或私密记录。

版本发布入口：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.11-prep-20261014
实际在线发布状态以该页面与外部发布记录为准；本说明只说明包内容与离线验证。

本次未操作历史画布，未生成图片或视频，未恢复视频／超分／剪辑台／下载导出。没有启用旧927、修改独立v13.3或B13.4.3的七板块、首镜全景、逐镜背景、对白及回忆。

## 同事更新

复制“导入时复制给Agent.txt”；校验ZIP→verify_package→skills-only dry-run→备份定制冲突→安装并同步维护源→合并相关偏好→本地回归→刷新会话核对。安装器不自动合并AGENTS／同步任意维护源，不声称其他设备已自动更新。回滚按installation.json恢复实际覆盖文件，先保留安装后的工作人员更改，新增文件另归档。
