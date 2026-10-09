# Pixmax 工作流｜B13.4.2｜生成前准备版
快照：2026-10-10。包含9个Skill、配套CLI运行时、安装器、交接说明及逐文件SHA-256。只打包现行规则，不启动远端或收费任务。

## 当前终点
默认只做到视频生成前：资产补缺与验收 → 分集画布和完整当集剧本附件 → 未运行视频节点及完整提示词／参数 → 有序连线、真实@ → 保存回读和生成前检查。交付“已准备，未生成”；有缺项如实列明。
自动视频生成／补修、1080P超分、剪辑台汇总、下载／导出均已冻结。“完整制作”不自动解除；必须当次明确恢复指定阶段。

本次仅修对白漏检和P02旧案例：解析兼容直引号及常见括号／冒号，格式错误的明确发言不再静默跳过；案例改为实际台词片段进入镜头。新增15项回归测试。其他制作标准不变，详见[本次更新说明](docs/20261010-dialogue-fix.md)。

## 安装与更新
使用Python 3.10+，在解压目录运行：
```text
python -B verify_package.py
python -B install_upgrade.py --dry-run
python -B install_upgrade.py
python -B run_pixmax.py --version
```
仅更新Skills用 `--skills-only`。先看dry-run；遇更高版本或独立定制不要盲目降级。安装器备份被覆盖文件，保留额外文件，不切换全局CLI活动版本，不复制登录态，不自动修改全局AGENTS.md。
请把“导入时复制给Agent.txt”交给同事的Agent，按“跨会话规则_合并片段.md”合并偏好，不覆盖其他个人规则。重新加载会话发现Skills。

Windows可用一键安装.cmd／安装升级.ps1。CLI覆盖层仅匹配build100012／1.3.0；其他CLI版本必须重新确认兼容。安装不等于目标机登录或在线制作验证。

## 下载、版本及安全
GitHub：公开仓库 `KainChen169/kaipian-pixmax-workflow`，无需邀请即可下载。[获取最新完整安装包](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/latest)。请选择Release附件ZIP，不是Source code归档。每次更新下载最新版本，再做校验、dry-run、安装；不要直接覆盖个人配置或把旧项目执行记录当模板。
本包不含账号凭据、登录态、剧本／媒体／项目UUID／任务记录；两个927旧流程和旧项目模板不打包。包内历史后处理参考仅待明确恢复时使用，不能覆盖顶部冻结规则。来源日期前缀与S编号、公共资产认领和真实@标准均保留。
