# Pixmax B13.4.31｜自然讲戏与固定写稿负责人

工作流：`13.4.31-prep-20261030`
真人导演：`13.4.4-liveaction-natural-storytelling.9-20261030`
动画导演保持：`1.3.0-natural-performance-20261029`
默认规格：`PIXDANCE_2_5_DRAFT / 480P / 9:16 / includeAudio=true`
默认终点：视频生成前。

## 本次更新

- 每部剧固定一个写稿 Agent，按剧情顺序逐集写作与修订。上下文续跑使用既有状态记录；辅助校对、公共资产与确定稿画布准备仍可并行，每画布唯一写入者。
- 真人正文用自然语言连起镜头、动作与情绪；普通镜头清楚即可，关键表演和复杂动作按剧情需要展开。删除无叙事作用的防错套话，保留人物有意义的拒绝、必要输出约束与技术检查。
- 同步导演指导、画面＋表演模板和普通／关键／复杂动作示例。参考只在开写或校准时按需读取，不每集重读全部、不贴进成稿、不当句式模板。
- 写稿负责人核对内容，工具核对对白、格式及真实 @；两种结果分开。绑定确定稿只插原生引用，不重新润色源文。
- 包含此前本地 B13.4.30 的批量执行修复：内容交接、动态状态、校准和重复描述疑点工具。疑点不作为新硬门槛。

不增加字数、扩写倍数、镜数、镜长、景别或否定句数量限制。保留七板块、独立开场站位、原话、自然时长、镜数参考、连续性、资产复用及真实 @ 原文可逆机制。动画写作规则、独立首集、历史 LOCK 与画布不改。只维护 Skills，不操作制作画布或生成媒体。

## 安装与兼容

完整包包含10个 Skill；本次只替换主工作流与真人导演，其余8个 Skill 和 vendor 与 B13.4.29 字节一致。旧927流程及项目模板仍不打包；无真实项目稿、账号凭据和项目媒体（工作流自带两秒黑场除外）。

先阅读 `导入时复制给Agent.txt`，备份、核对定制后执行：
```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
```
确认差异后去掉 --dry-run 安装，再执行 dry-run 检查零差异。维护源与注册入口分别核对；不覆盖较新官方 CLI/runtime。新设备应先检查完整依赖，不能把定点升级当作完整环境安装。

## 校验

结果见 `checks/离线校验结果.json`：主流程、真人和动画回归，当前自然语言示例的真实 @ 编译／原话保护／源文还原，B13.4.29→B13.4.31隔离升级、重复安装及保留无关定制测试；完整文件 SHA-256 与 ZIP CRC。离线验证不等于实际平台或成片效果验证。

发布：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.31-prep-20261030
请实际下载、备份并更新本机 Pixmax 工作流：
https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.31-prep-20261030

下载 Release 附件 pixmax-workflow-B13.4.31-prep-20261030.zip 及同名 .zip.sha256，不用 Source code 替代。核对 ZIP SHA-256 和仓库 versions/v13.4.31-prep-20261030.json，安全解压，阅读 README、更新说明和安装器帮助。
目标工作流 13.4.31-prep-20261030；真人导演 13.4.4-liveaction-natural-storytelling.9-20261030。动画导演保持 1.3.0-natural-performance-20261029。

本次每部剧由一个固定 Agent 从头顺序写到底，辅助核对、资产和确定稿画布准备可分工。真人正文把镜头观察、人物动作与情绪用自然语言串起来，普通镜头清楚即可，关键表演按需展开；减少无关防御描述，不加字数、镜数或否定句数量门槛。

先核对本机维护源码与 Codex 注册入口的真实路径、版本及定制，备份待覆盖文件。保留未知定制与更高版本，冲突定点合并，不整库覆盖。
Python 3.10 以上，在解压根目录执行：
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
核对范围后同命令去掉 --dry-run 执行，再 dry-run 确认零差异。同步本机维护源及注册入口，不覆盖无关 Skills、全局偏好、较新官方 CLI/runtime 或登录状态。新设备先按 manifest 核对完整依赖。
按 checks/离线校验结果.json 执行测试；真人测试需 PYTHONPATH=scripts，主流程测试需包内 vendor/pixmax-cli-runtime/vendor 依赖。结构通过与内容核对分开，离线通过不代表实际画面效果。

仍默认 Seedance 2.5 Draft、480P、9:16、有声音，停在视频生成前。只安装，不制作、不收费、不改历史画布或旧 LOCK，不恢复视频、超分、剪辑台及下载，不再次发布 GitHub。报告实际版本、安装路径、备份、测试和剩余冲突。


ZIP SHA-256: `af6c18e3123215a9b8752e2c07696ded0daa599871d32dbd98ee0b1d0f40b4c6`
