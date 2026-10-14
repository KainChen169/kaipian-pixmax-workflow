# B13.4.12／导演B13.4.4修改与验证

## 实际改变

1. SKILL主入口、UI入口、模板及篇幅模块统一“每个子镜头细写”，相对同镜短稿约2–3倍；不是整稿乘倍。
2. 自然语言细写动作起点、发力、身体／表情变化、构图与背景、摄影路径／速度／焦点及落幅；固定镜、基础镜、短插镜不再只写提纲。模板首镜示例已具体展开，另有近景前后对照。
3. 将“P0可简洁”改为“不必加情绪转折，但既有过程须具体”，防止基础镜一直短写。
4. 取消校验器默认5500／7000字按秒预算及±6%上限；明确用户--length-target时保留其检查。--profile保留参数兼容，不再改变默认预算。
5. 新增逐镜正文量统计及可选--baseline-prompt：同镜号／同时间对应比较，少于2倍为REVIEW，超过3倍不失败；原话、前置、概述、声音和输出锁不计入。数字不能证明描述有效，语义审查仍执行。
6. 主流程及2.5路由同步B13.4.4；清理相关路由里旧字数预算，并统一已生效的轻微状态母图复用规则，不再索要所有伤情状态板。
7. 更新器新增--skill选择安装，本次可只装导演与主入口，不覆盖其他会话的资产／选角定制；默认完整安装行为不变。

## 修改文件

默认导演ab-test-seedance25-director-compiler-v13-4-0：
- SKILL.md、VERSION、agents/openai.yaml。
- references/length_and_density.md、prompt_compiler.md、quality_gates.md。
- references/dialogue_performance_engine.md、affirmative_visual_language.md、shot_orchestration_engine.md。
- references/combat_camera.md、vfx_design.md、action_scene_enhancement.md、duration_modules.md。
- scripts/validate_director_prompt.py。
- tests/test_v13_4.py，新增tests/test_shot_detail.py。

主流程pixmax-codex-pipeline：
- SKILL.md、AGENTS.md、VERSION。
- references/seedance25-30s-workflow.md、workflow-modules.md、optimized-execution.md。

另：定点更新本机全局AGENTS中的当前导演与篇幅偏好；新包install_upgrade.py、README、交接、说明、合并片段及打包脚本。源目录／注册副本备份后同步；其他7个组件沿用B13.4.11，未把无关本机新改纳入此次发布，不覆盖独立v13.3。

## 保持不变

自然时长与镜数参考；原话、说话者、剧情事件与结果；七板块、独立开场站位、整场MD／JSON及一致性报告、首镜全程全景、逐镜背景、原回忆与对白模块；不生成站位图。既有轻微状态免机械补图、关键身份与资产核验、真实@／有序连线、源文可逆绑定、防重和授权规则继续执行。

描述更长不会带来更多台词／动作，也不能把同一动作在不同机位重演；可并行表情与动作仍在同窗，不因为写得长硬拖到30秒。历史LOCK和画布不自动重写，本次未操作Pixmax或生成媒体，冻结阶段不恢复。

## 测试结果与边界

导演42项全通过（新增12项），覆盖：
- 各镜单独比较，一镜变长不能补另一镜短写。
- 长前置／概述／输出锁及重复台词不能伪造镜头描述增长。
- 合并构图模式可统计；不匹配时间／镜号不伪造比例；无基线不声称倍率；超过3倍不截断。
- 默认无整稿字数闸门，明确用户字数仍校验。
- 扩写后原时间线和原话一致，改说话者、改台词及时间空缺仍拦截。

主工作流143项：140通过，3项未配置FFmpeg跳过，资产复用、防重、原文锁等回归保留。包验证含临时B13.4.11→B13.4.12升级、重复安装、选择更新两项且保留无关定制；详细结果见checks/离线校验结果.json。

quick_validate.py因缺PyYAML不可用，Ruby YAML基础frontmatter核对通过；不冒称原工具成功。自动测试是文本解析与记录行为测试，不证明所有细节有艺术价值，不证明未来生成或口型／视觉效果，也不承诺平台无限字数。实际生成器仍按真实能力保存并全文回读，不能为适配限制静默截断原文。

## 备份与安装

修改前备份：Skill_packages/backups/20261015_逐镜细写策略更新前（源、注册及全局AGENTS）。本版版本号为工作流13.4.12-prep-20261015／导演13.4.4-shot-detail-20261015。

已有完整工作流优先使用--skills-only加两次--skill，仅更新主流程和默认导演。其他未知定制或更高版本先比较，定点合并相关偏好，安装器不会代替Agent合并AGENTS／维护源。回滚依据实际installation.json，保护安装后编辑，新增文件归档不粗暴清目录。

GitHub入口：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.12-prep-20261015
下载／校验／更新复制指令在同包“导入时复制给Agent.txt”；实际发布状态以页面及版本索引为准。保留B13.4.11历史包，不覆写旧Release。
