# Pixmax B13.4.29｜动画自然画面与表演

工作流：`13.4.29-prep-20261029`
动画导演：`1.3.0-natural-performance-20261029`
真人导演保持：`13.4.4-liveaction-adaptive-detail.8-20261028`
默认视频模型与规格：`PIXDANCE_2_5_DRAFT / 480P / 9:16 / includeAudio=true`
当前终点：视频生成前。

## 本次范围

只更新主流程的动画接入／真实@兼容与动画导演；完整包内其余8个Skill和vendor沿用B13.4.28原字节，不覆盖本机较新或定制版本。动画基于本机1.2.0，而不是将其退回上一完整包的1.1.1；原有角色演法、主体覆盖与快运镜保留。

1. 时间线前增加简短导演指导，交代叙事重心与观看重点。
2. 逐镜采用自然语言画面＋表演／动作；原话仍使用原标签。
3. 普通镜头清楚即可，关键表演与复杂动作按需要详写，不加字数或倍数门槛。
4. 正文描述实际发生的事，减少无效否定句；必要声源／口型、原话及输出约束保留。

保留动画风格总纲、声音档案、原话标签、物种身体表演、自然时长、镜数参考、空间／道具连续性。真人、独立首集、历史LOCK与画布不迁移。只修改Skills，不生成媒体或操作制作画布。

## 格式与绑定

新稿用动画校验器`--format natural`；默认auto用于兼容旧确定稿，不改源文。新旧字段均可编译原生@，同镜跨栏去重、输入去重及源文逐字还原保持。原话整行含长姓名／声部／对象／声线阶段均受保护，风格总纲、导演指导和站位不插引用。当前只做离线编译与模拟保存回读测试，不声称在真实画布或成片上验证效果。

## 校验与升级

动画40项通过；主流程233项中230通过、3项FFmpeg条件跳过；真人导演110项回归不变。完整包文件哈希、ZIP CRC、B13.4.28→B13.4.29隔离升级、选择安装保留无关定制及重复安装结果见checks/离线校验结果.json。

发布页：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.29-prep-20261029

执行前先按`导入时复制给Agent.txt`核对定制与备份。用Python3.10以上运行`verify_package.py`，再用`install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill seedance25-animation-director --dry-run`检查，仅对这两个Skill定点升级，不更新较新官方CLI/runtime。新设备先核对完整依赖，未知定制不自动覆盖。

完整包不含项目剧本／资产、账号凭证或历史项目模板，不包含两套停用927流程。动画示例为虚构离线用例。


## 附件 SHA-256

`c25b37234a9aab240be2df7bdd3a947b0532cf67a83ce89ba179125721a163fd`

## 同事 Codex 更新指令

```text
请实际下载、备份并更新本机Pixmax工作流：
https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.29-prep-20261029

下载Release附件pixmax-workflow-B13.4.29-prep-20261029.zip及同名.zip.sha256，不要用Source code替代。核对ZIP SHA-256和仓库versions/v13.4.29-prep-20261029.json，安全解压，阅读README、更新说明和安装器帮助。

目标工作流13.4.29-prep-20261029；动画导演1.3.0-natural-performance-20261029。真人导演仍为13.4.4-liveaction-adaptive-detail.8-20261028，不在本次定点升级中覆盖。
动画新稿增加简短导演指导，逐镜画面＋表演／动作，普通镜头清楚即可，关键表演及复杂动作按需展开，减少无效防错否定句。保留动画风格总纲、声音档案、原话标签和所有其他规则。旧构图格式兼容；真实@保护原话整行、指导和站位，同镜跨栏去重、源文可逆。

先核对本机源码与Codex注册入口的实际路径、版本和定制，备份待覆盖文件。保留未知定制及更高版本，冲突定点合并，不整库覆盖。
Python3.10以上，在解压根目录执行：
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill seedance25-animation-director --dry-run
核对范围后同命令去掉--dry-run执行，再dry-run确认零差异；同步本机维护源及注册入口，不覆盖无关Skills、全局偏好、较新官方CLI/runtime或登录状态。新设备先按manifest检查完整依赖。
运行动画scripts/test_animation_prompt.py；主流程测试按包内checks记录及所带vendor依赖执行。只核对文本与绑定，不把离线通过当成实际画布或成片效果通过。

仍默认Seedance2.5 Draft480P、9:16、有声音，停在视频生成前。只安装更新，不制作、不收费、不改旧LOCK／历史画布，不恢复视频、超分、剪辑台或下载，不再次发布GitHub。完成后报告实际版本、路径、备份、测试结果和剩余冲突。

```
