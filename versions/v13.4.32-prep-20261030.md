# Pixmax B13.4.32｜轻量站位继承

工作流：`13.4.32-prep-20261030`
真人导演：`13.4.4-liveaction-spatial-continuity.10-20261030`
动画导演保持：`1.3.0-natural-performance-20261029`
默认：Seedance 2.5 Draft / 480P / 9:16 / 有声音，停在视频生成前。

## 仅三项改动

1. 每包开场集中说明必要地标、身体朝向和相对位置，只写开始瞬间；未来走位进入实际镜头。
2. 同场接续先继承上一包末态的位置与身体朝向，再选机位；不能只接住手部、道具而重新安排站位。
3. 关键移动和遮挡写清通路、停点及谁能看见谁；普通镜头保持简洁，核对合入已有流程。

同步工作流、真人Skill、七板块模板、开场示例和少量教学摘录。不增加逐镜站位栏、检查轮次、篇幅／镜数／镜长／景别／@配额。既有原话、自然时长、按需详略、固定写稿负责人、资产复用及真实@原文可逆规则保持。动画与独立首集、历史LOCK和画布不改。

## 安装与边界

完整包包含10个Skill，仅更新工作流与真人导演；其余8个Skill和vendor与B13.4.31逐文件保持一致。旧927流程和项目模板不打包，未包含项目剧本、任务或凭据。自带两秒黑场继续仅连线。

Python 3.10以上。在解压根目录先执行`python3 verify_package.py`，然后按《导入时复制给Agent.txt》定点升级。先核对本机定制与更高版本、备份，再安装；维护源和注册入口分别核对。不要覆盖较新CLI或登录状态。

校验结果见`checks/离线校验结果.json`：原有主流程、真人、动画回归，真实@源文还原，B31→B32隔离升级、重复安装及无关定制保护。文件哈希与ZIP CRC另核验。语义示例核对是文字自洽检查，不是实际视频效果保证。

## 下载

[完整ZIP](https://github.com/KainChen169/kaipian-pixmax-workflow/raw/refs/heads/main/packages/v13.4.32-prep-20261030/pixmax-workflow-B13.4.32-prep-20261030.zip) · [SHA-256](https://github.com/KainChen169/kaipian-pixmax-workflow/raw/refs/heads/main/packages/v13.4.32-prep-20261030/pixmax-workflow-B13.4.32-prep-20261030.zip.sha256)

本次采用仓库版本化下载包，未创建Release；旧Release保留。

SHA-256：`23917e82069240036de11444e5e4fa922a23a5483ef3e3daecc6d1d2fafb932e`

## 同事Codex更新指令

```
请实际下载、备份并更新本机Pixmax工作流至13.4.32-prep-20261030，真人导演至13.4.4-liveaction-spatial-continuity.10-20261030。
仓库：https://github.com/KainChen169/kaipian-pixmax-workflow
先读取仓库versions/v13.4.32-prep-20261030.json，按其中实际下载链接取得pixmax-workflow-B13.4.32-prep-20261030.zip及校验值，不使用旧Release或Source code替代。

本次仅优化每包初始站位、同场跨包位置朝向继承、关键移动和遮挡的具体过程。普通镜头保持简洁，不增加机械限制，其他规则不变。

核对本机维护源码与Codex注册入口的实际路径、版本和定制，先备份。保留更高版本及未知定制，冲突定点合并，不整库覆盖。校验ZIP SHA-256、安全解压，读取README与安装器帮助。
Python 3.10以上，在解压根目录执行：
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
核对变更范围后去掉--dry-run安装，再dry-run确认零差异。同步维护源与注册入口；不覆盖其他Skill、全局偏好、较新CLI/runtime或登录状态。新设备先按manifest检查完整依赖。
按checks/离线校验结果.json复核测试；真人测试PYTHONPATH=scripts，主流程测试需包内vendor/pixmax-cli-runtime/vendor。报告实际版本、路径、备份、测试及冲突。

只安装，不制作、不收费、不修改历史画布或旧LOCK，不恢复视频生成、超分、剪辑台或下载，不再发布GitHub。保持Draft480P、9:16、有声音和视频前冻结。动画、独立首集及其他规则不变。
```
