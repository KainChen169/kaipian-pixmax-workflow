# Pixmax B13.4.15｜欧美资产与AIGC完整生成

工作流13.4.15-prep-20261016；默认导演未改：13.4.4-shot-detail-body-mentions-20261016。

## 从B13.4.14改变了什么

1. 所有新补／派生／修复的人物、场景、道具按项目既定欧美国家／时代设计，不采用亚洲演员面孔，无中文／中国视觉元素。补图Prompt正文英文，必要画面文字英文；无文字需求不添字，中文工作说明、文件名及阅读附件保留。欧美不等于自动排除所有其他族群，不把美、英、欧洲大陆或现代／年代戏混搭。
2. 剧情必要的英文文字、数字／数据、图表和静态效果尽量AIGC生成／编辑直接完成，不默认留白等人工P字或合成。关键内容按来源核对，乱码、错误金额不算完成，不虚构证据。动画等时间过程写入对应已授权动态任务，当前只准备必要资产／完整词，不提交冻结视频，静态图不冒充动画。
3. 规则贯穿选参考、写词、原导入分析／资产看图、失败重试；不新增第二轮风格审片或收费样张。覆盖Pixmax内通用资产规则的“默认精确文字后期排版／合成”，不修改通用Skill在其他流程中的行为。

## 实际文件

- pixmax-codex-pipeline/SKILL.md、AGENTS.md：新增两条要求及入口。
- references/western-asset-localization.md、complete-asset-generation.md：新增详细规则。
- references/script-driven-workflow.md：补资产入口、文字和效果完整生成。
- references/post-import-asset-analysis.md、pre-generation-asset-visual-review.md：合并已有看图检查。
- references/asset-generation-recovery.md：参考排障、针对性修正及原额度不变。
- VERSION：13.4.15-prep-20261016。

没有修改Python执行脚本／视觉证据schema。脚本不识图、不OCR、不自动判族裔或审美，新规则由Agent在既有选参考／写词／看图环节执行。人物选型依据已确认人设和参考，不臆断真人实际族裔。完整包9个Skills＋既有runtime，仅主流程有变，其余8项固定沿用B13.4.14，不引入其他会话定制。旧927和项目模板不打包。

## 边界保留

正确原母图优先，轻微状态用镜头词，无意义细节不补图。身份、必要变身、场景布局、道具实例和连续性检查保留。原无可读文字／无Logo、台词／LOCK、正文真实@、昼夜策略与回忆效果分工不静默改动；关键来源冲突只暂停受影响项并说明。无新增图片预算或次数，不批量返修历史资产／画布，视频／超分／剪辑台／自动下载仍冻结。未完成如实列缺，不以“后期再补”假标READY。

## 安装

从下方Release附件下载完整ZIP，不要下载Source code，核对Release及versions/latest.json的SHA-256。先备份注册Skills、维护源和相关AGENTS，读跨会话规则片段，然后运行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --dry-run
```

核对未知定制／更高版本冲突后去掉--dry-run安装；同步实际维护源，只定点合并新增规则，保留其他设置。新电脑缺依赖才按--help做全套dry-run、备份和安装。仅更新安装不制作、不改历史项目、不再次发布本包。

## 验证及限制

主流程162项：159通过，3项FFmpeg未配置跳过；导演42项通过。使用既有包内runtime/vendor依赖，未安装新依赖。裸系统／bundled Python缺click的初次测试未通过，补入已有vendor路径后完整回归通过，不隐瞒初次失败。隔离B13.4.14升级、重复安装、选择升级保留其他Skill定制及文件哈希实际结果见checks/离线校验结果.json。

10个策略案例人工推演见checks/策略案例复核.md，不是模型生成测试或自动语义判断。未操作Pixmax／历史画布，未生成图片或视频；规则不保证AIGC一次成功。正文重复原生@的在线保存及效果仍待具体授权准备任务验证。quick_validate.py的实际结果另记；不以其他解析通过冒称原工具通过。

备份：Skill_packages/backups/20261016_004812_欧美补资产规则前，含源、注册版及全局AGENTS。历史Release保留。

发布：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.15-prep-20261016
复制安装指令：导入时复制给Agent.txt。校验值：Release及versions/latest.json。
