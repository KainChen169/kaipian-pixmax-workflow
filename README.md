# Pixmax B13.4.36｜人物表演底色接入

[下载完整工作流与安装指令](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.36-prep-20261104)

# B13.4.36：人物表演底色接入

工作流：13.4.36-prep-20261104。真人导演：13.4.4-liveaction-character-baseline.10-20261104。

- 真人项目人物底色建立一次：优先复用现有人设，缺少时由主Agent或指定写稿者依据人物小传与已读剧情整理，存入既有角色记录或一份项目人物表演底色文件。
- 分集交接附权威路径与相关角色；写稿者读取当前相关内容，与当集剧本共同用于原有导演指导和表演栏。新角色或明确成长局部补充。
- 同步工作流、并行交接、真人Skill、模板和虚构示例。普通镜头清楚即可，关键变化按需展开，不给每镜追加性格解释。
- 不新增审查、评分、必填表、字数门槛或生产校验项；资产与画布负责人直接复用确定稿，不重复研读人物档案。生产校验与绑定脚本保持原字节。
- 动画1.5.1、独立首集、其他Skill与CLI/runtime保持原样。沿用B35／33／29基线与Draft480P、9:16、有声音、视频生成前冻结边界。

未修改项目剧本、历史画布或LOCK，未生成媒体。本包使用虚构教学例，不含《我的保镖有獠牙》项目试写、剧本或素材。离线检查验证安装、格式和绑定兼容，不代表实际批量表演效果已经验证；由后续项目测试。

## 校验值

SHA-256：`56cef63859109d69f443e4dfc91fb77cfade3d1de02abcbfe8bf0b1cf666970f`

## 同事Codex更新指令

```text
请从此Release下载并更新本机Pixmax工作流：
https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.36-prep-20261104

下载附件pixmax-workflow-B13.4.36-prep-20261104.zip及同名.zip.sha256，不使用Source code。核对SHA-256，安全解压，先读更新说明及安装器帮助。先备份现有维护源、Codex注册入口与相关Pixmax偏好；未知定制或更高版本先报告，不静默覆盖。

使用Python3.10以上，在解压根目录运行：
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
确认范围后去掉--dry-run安装，再dry-run确认零差异；同步实际维护源与注册入口，按包内片段定点合并Pixmax偏好。

目标工作流13.4.36-prep-20261104，真人导演13.4.4-liveaction-character-baseline.10-20261104。人物表演底色每剧建立一次，写稿者按相关角色读取并直接用于现有表演栏；不增加人物档案复核、评分、每集报告或全剧重复读稿。动画与独立首集规则不变。

保留较新官方CLI/runtime、登录、其他个人偏好、历史画布、剧本与LOCK。默认Draft480P、9:16、有声音，停在视频生成前。这里只安装，不制作、不生成媒体、不恢复冻结阶段，也不再次发布。新机缺少依赖时按manifest补齐；完成后报告实际版本、备份、安装路径和校验结果。
```


离线回归：主流程250通过、3项FFmpeg条件跳过；真人114通过；动画104通过。566文件清单、ZIP CRC、B35隔离升级、无关定制保护及重复安装零差异通过。生产校验与绑定脚本不变，未验证真实成片效果。
