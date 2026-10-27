# Pixmax B13.4.25：自然画面与表演

工作流：`13.4.25-prep-20261027`。真人批量导演：`13.4.4-liveaction-natural-performance.6-20261027`。动画导演仍为 `1.1.1-pixmax-routing-20261026`，内容未修改。

## 本次仅调整三项

1. 原七板块内，“导演指导”替代“整段剧情概述”。自然语言说明本包的叙事、关系变化及观看重点，不多加一层概要，不加入全局提示词。
2. 逐镜“画面＋表演”，纯物件可用“动作／动作与表演”。取消独立构图栏、强制“背景：”标签和机械逐镜复述站位；必要机位、背景、遮挡及空间变化自然写入画面。表演写具体动作、表情、听者与原话，两栏同窗发生。原2–3倍逐镜细写要求保持。
3. 模板、新示例、校验器及真实@一起适配。原话从新旧允许正文栏提取，不漏掉表演栏；台词引号保护、指导／站位排除、同镜跨栏去重、输入连线去重、源哈希与逐字可逆还原继续。旧格式保留回归用例，不自动重写旧稿。

未改：原话／说话者、自然时长和镜数、开场自由、整场MD／JSON调度、480P／9:16／有声音、模型选择、轻微状态免补图、资产复用、两秒黑场仅连线、原回忆分工、视频生成前冻结、动画规则与独立首集Skill。

此完整包继承本机已安装B13.4.24的动画／真人项目分流。GitHub上原最新为B13.4.23，因此从B13.4.23升级也会收到已存在的B13.4.24分流能力，不是本次新改动画导演。其他8个随包Skill与B13.4.24逐文件一致。

## 验证与边界

导演106项测试、主流程220项测试（其中3项FFmpeg环境条件跳过）；新加17项自然语言格式／原话／真实@回归。另复跑随包动画33项测试。新示例以独立英文源运行严格校验，空间和表演按文本语义复核，不声称模型实测或成片质量通过。

完整包检查逐文件SHA-256、ZIP完整性、旧版临时目录升级、重复安装零差异，以及仅选指定Skill安装时保留无关定制。具体实际结果见 `checks/`。

没有操作Pixmax画布、图片／视频任务，没有改旧LOCK，也没有恢复生成／补修／超分／剪辑台／成片下载阶段。旧案例仅作设计及格式兼容参考，新稿优先看 `assets/examples/natural_performance.prompt.md`。

## 下载与安装

发布页：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.25-prep-20261027

下载附件 `pixmax-workflow-B13.4.25-prep-20261027.zip` 和同名 `.zip.sha256`，不要只下载GitHub自动生成的Source code。用Python 3.10以上，在解压根目录运行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --skill seedance25-animation-director --dry-run
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --skill seedance25-animation-director
```

先确认ZIP与外部SHA-256一致，再检查已安装版本、实际注册路径和定制差异、备份。未知定制不覆盖；遇本机更高版本不降级。安装器为所改文件保留备份，完成后重跑dry-run确认零差异。已经安装且一致的动画Skill会跳过；本次本机只需更新主流程及真人导演。

此为已有工作流升级。全新设备先检查依赖清单，补齐缺失Skill，不据此覆盖其他已定制依赖。用`--skills-only`保持现有官方Pixmax CLI／runtime；随包历史兼容runtime不是推荐升级版本，不能覆盖较新的官方CLI。不要重置登录或凭据。

定点合并 `跨会话规则_合并片段.md`，保留其他偏好；刷新会话并核对实际VERSION。交付下载来源、包哈希、实际安装版本、备份与校验结果。仅安装更新，不制作项目、不收费、不改历史内容、不再发布一次GitHub。
