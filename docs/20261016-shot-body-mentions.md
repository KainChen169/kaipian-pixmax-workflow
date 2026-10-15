# B13.4.14｜逐镜正文关键资产引用更新

## 实际修改

- 新增scripts/shot_body_mentions.py：只处理显式、按子镜头／字段选定的源文锚点，或精确Python Unicode源跨度；保护引号内对白，限制在时间线构图／画面内容，核对名称／审核过的别名、类别用途、同镜重复、重叠和明显O.S.／V.O.误用。脚本不识图、不代替Agent判断实际入画或正确造型。
- scripts/fast_bind.py新增compile_for_policy及v2显式body_mentions编译，保留前置三项引用，正文只插入相同已绑定资产token和必要分隔空格；记录精确差异与范围、逆向还原原文，重复引用不增加输入／连线。
- scripts/submit_saved_batch.py识别v2并从权威源和锚点计划重编译全部内容，resolve_saved_batch.py沿用这一门禁；不再把已登记正文重复引用误报为重复资产，但未登记、多／漏、错UUID／编号／标签和叙事改动仍拦截。旧v1逻辑与测试保留。
- 新增references/shot-body-mentions.md与tests/test_shot_body_mentions.py。同步主流程SKILL.md、AGENTS.md、fast-binding-and-state.md、saved-batch-runner.md、seedance25-30s-workflow.md、optimized-execution.md。
- 默认导演SKILL.md、references/generator_role_binding.md及opening_staging_and_background.md同步“前置＋正文关键引用”，普通MD不输出机器token。主流程VERSION=13.4.14-prep-20261016；导演VERSION=13.4.4-shot-detail-body-mentions-20261016。
- 备份后同步本地维护源、Codex注册两个Skills及全局AGENTS新增窄范围偏好。完整包其他7组件沿用上一发布，不覆盖其他会话定制。

## 本次不改

昼夜策略尚未确认，本次不改；不新增昼夜锁、不重新计算或改写已有昼夜文本。站位、首镜全景、每镜背景、逐镜细写、回忆效果交后期、轻微状态免机械补图、真实资产检查、防重及冻结边界不变。不操作历史画布／LOCK，不创建测试项目，不生成图片或视频。

## 本地测试

新增19项，覆盖：三类正文引用、跨子镜重复UUID只用4个输入、CRLF与原文逆向还原、原台词及夜内描述不改、编译确定性、保存解析平台重分配UUID、未登记／缺少／错编号／错标签拦截、源变更／伪造差异失败、同镜重复失败、中英引号保护、只允许子镜头字段、纯画外用途失败、显式O.S.误标失败、英文短名字不绑定较长他人姓名、别名须显式映射、v1严格兼容、v2不静默迁移旧角色、去重输入／容量仍检查。

主流程162项：159通过、3项FFmpeg未配置跳过。导演42项通过。打包还验证493文件哈希、B13.4.13→B13.4.14隔离安装、重复安装和只更新两项且保留无关定制；以checks/离线校验结果.json为最终实跑记录。

quick_validate.py缺PyYAML，Ruby YAML基础frontmatter解析通过。离线测试不证明语义映射或平台保存／生成效果；首次重复引用保存回读留给当次授权的准备任务，不为本次Skills维护擅自操作远端画布。没有收费实测，也不保证人物一定不漂移。

## 安装与兼容

修改前备份：Skill_packages/backups/20261016_逐镜正文引用更新前（source、registered和global-AGENTS.md）。新任务明确用v2与body_mentions；缺省旧计划仍走v1以兼容历史，不能把旧v1PASS冒充新正文绑定完成。安装器选择升级这两个Skills，AGENTS与维护源由Agent定点同步，不覆盖其他规则。历史包与Release保留。

发布：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.14-prep-20261016
ZIP哈希见Release及versions/latest.json；复制指令在导入时复制给Agent.txt。
