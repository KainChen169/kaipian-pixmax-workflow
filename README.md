# Pixmax B13.4.28：默认Seedance 2.5 Draft 480P

工作流：`13.4.28-prep-20261028`
默认视频模型：`PIXDANCE_2_5_DRAFT`
规格：`480P / 9:16 / includeAudio=true`
真人导演保持：`13.4.4-liveaction-adaptive-detail.8-20261028`
动画导演保持：`1.1.1-pixmax-routing-20261026`

## 改动

1. 后续新建／获授权配置的Seedance2.5节点，真人与动画统一默认Draft 480P。模型与分辨率分别检查，不将普通版480P当作Draft。
2. 新执行副本缺省模型补为Draft；显式普通版或错误规格拦截，不静默覆盖源计划或回退普通版。保存回读和获授权提交前同样检查，计划与回读同时写错普通版也不通过。
3. 同步真人／动画时长校验、连续性触发、显式清单默认值、示例、路由和Agent规则；Draft自己的当前schema用于时长、参考容量核对。
4. 历史普通版任务仍可只读对账，不批量迁移、重新生成或伪改服务端videoStage。旧普通版videoEdit是历史路线；Draft当前未列该模式，不硬套、不自动回退。

2026-10-28官方CLI1.5.0/build100019只读确认Draft未受限，支持所选规格、4–30秒整数时长，图片30、视频／音频各10、多媒体合计50；此为查询快照，实际执行仍核验当前模型。schema里的1080P不改变本工作流480P标准。记录见checks。

只修改主工作流，另9个随包Skill及runtime与B13.4.27逐文件一致。导演提示词、原话、自然时长、镜数、真实@、资产复用、黑场仅连线和视频生成前冻结保持。本次未操作Pixmax制作画布或提交媒体任务。选择Draft不自动恢复样片生成或generate-final成片转换。

## 校验与安装

工作流228项中225通过、3项FFmpeg条件跳过；8个新增用例覆盖Draft默认、普通版拒绝、回读漂移、真人／动画一致性、显式清单默认及历史状态只读。另复跑未改的真人导演110项。完整包哈希、ZIP CRC、从B13.4.27隔离升级、选择安装保留无关定制和重复安装验证见checks。

发布页：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.28-prep-20261028

先备份并核对本机定制，使用Python3.10以上运行verify_package.py，再按《导入时复制给Agent.txt》进行skills-only定点安装和零差异复核；不覆盖较新的官方Pixmax CLI/runtime，新设备先核对完整依赖。安装不触发制作或收费任务。


## 完整附件SHA-256

`4109c25841c6283754064f08a5c0a7c81545780f56bbb93eaf85e6f59177c940`

## 给同事Codex的更新指令

```text
请实际下载、备份并更新本机Pixmax工作流：
https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.28-prep-20261028

下载附件pixmax-workflow-B13.4.28-prep-20261028.zip及同名.zip.sha256，不要用Source code替代。核对ZIP SHA-256和仓库versions/v13.4.28-prep-20261028.json，安全解压后阅读README、本次更新说明、导入时复制给Agent.txt与安装器帮助。

目标工作流13.4.28-prep-20261028；真人导演保持13.4.4-liveaction-adaptive-detail.8-20261028，动画导演保持1.1.1-pixmax-routing-20261026。
本版后续新建／获授权配置的Seedance2.5节点，真人与动画一律默认PIXDANCE_2_5_DRAFT、480P、9:16、有声音；普通版480P不等于Draft。模型与规格须保存回读核对，不沿用普通版模板，Draft不可用不自动回退。

先核对实际源码／Codex注册路径、版本与定制并备份，保留未知定制及更高版本。
Python3.10以上在解压根目录执行：
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --skill seedance25-animation-director --dry-run
核对范围后执行同命令去掉--dry-run，再dry-run确认零差异；同步维护源与注册入口，定点合并跨会话规则，不覆盖无关偏好或较新官方CLI/runtime，不重置登录。新设备先核对完整依赖。常规升级自行完成，不逐项停问。

只更新Skills，不制作、不收费生成、不批量改历史节点／任务或旧LOCK；不恢复视频生成、generate-final成片转换、超分、剪辑台和下载，不再次发布GitHub。原话、自然时长、真实@与资产标准不改，提示词按需详略规则保持。完成后报告实际版本、安装位置、备份、校验结果和剩余冲突。

```
