# Pixmax B13.4.17｜两秒黑场仅连线

工作流13.4.17-prep-20261019；默认导演保持13.4.4-shot-detail-emotion-intent-20261016。

## 唯一制作变化

后续授权范围内，每个GENERATE_VIDEO节点在既有上游末尾追加同一两秒黑场BASE_VIDEO，每节点一次、每画布复用。原文件随包位于skills/pixmax-codex-pipeline/assets/black-2s.mp4，不依赖同事Downloads路径，不重生成／剪裁／转码。

只连接，不在提示词加黑场@、说明、台词或镜头；不当首尾帧，不拼片头片尾，不增加生成时长、不进剪辑台。原图片顺序／连线／编号、全文、参数及其他标准不变。历史项目不自动回填／重生成，所有冻结保持。

## 实际文件修改

- SKILL.md、AGENTS.md、VERSION：新入口与13.4.17标识。
- references/black-video-reference.md：共享原文件、仅连线例外、计划格式、容量／保存核验。
- references/fast-binding-and-state.md、saved-batch-runner.md、reference-input-limits.md、pre-generation-asset-visual-review.md：新视频末项与图片规则兼容。
- scripts/black_video_reference.py（新增）：固定源哈希、两秒声明、真实BASE_VIDEO及asset UUID、视频及组合容量、追加顺序。
- scripts/fast_bind.py：计划顶层connection_only_video应用全部镜头，仅追加prevNodeUuids和剪贴板边，不改图片bindings／token或参数。
- scripts/submit_saved_batch.py：保存预检和实际视频资产回查；resolve_saved_batch.py继承验证而不改代码。
- scripts/asset_visual_review.py：仍完整检查原图片，黑场不伪造图片／人物状态板观察。
- tests/test_black_video_reference.py（新增13项）、assets/black-2s.mp4。

没有修改导演；其他8项Skills及runtime逐文件沿用B13.4.16，不引入其他本机定制。未打包旧927／项目模板、项目剧本／凭据；唯一新增媒体是用户指定共享使用的黑场原文件。

## 文件与验证

源28788字节，SHA-256：b7ae7afdd2f44519b01e6852d5c8bb5589cdd4be90e70d3a1810bc01b235add1。ffprobe：2.000000秒、H.264、1920×3414、30fps、60帧，AAC双声道。完整解码blackdetect核对黑场，末帧覆盖至2秒；volumedetect静音。未改原文件。

主流程175项：172通过、3项FFmpeg未配置跳过；导演42项通过。13项新增测试覆盖整批一次附加、原参数／原词／token／时长不变、剪贴板边、漏／重／乱序／错视频拒绝、容量分组、平台目标UUID解析、旧清单兼容及原图审查仍生效。媒体检测使用本机现有ffmpeg，与默认未配置FFMPEG的跳过项分开。

文件哈希、B13.4.16隔离升级、重复安装和仅升级主Skill保留其他定制结果见checks/离线校验结果.json。quick_validate.py缺PyYAML无法运行；Ruby YAML基础解析通过。不以离线测试代替平台能力或成片效果验证。

2026-10-19只读Pixmax CLI build100014查询PIXDANCE_2_5允许视频10、组合50；输出未披露参考视频最短时长／完整属性约束，不能保证两秒文件已被服务端接受。下次授权画布准备内首次保存回读核对；本次不创建测试画布、不上传Pixmax、不收费生成。实际不支持时说明，不暗改原文件、原词、模型或时长。

## 安装与交接

发布：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.17-prep-20261019
从Release附件下载完整ZIP，不下载Source code，核对Release及versions/latest.json哈希。备份注册Skills、维护源和相关AGENTS后运行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --dry-run
```

检查未知定制／更高版本冲突后去掉--dry-run安装，同步维护源，仅定点合并黑场规则，保留其他设置。新电脑缺依赖按--help走完整安装dry-run与备份。黑场随主Skill安装，不用另找素材。

本机备份Skill_packages/backups/20261019_黑场视频连线前。历史Release保留。仅更新安装不制作、不返修旧项目、不再次发布本包；可复制指令在导入时复制给Agent.txt。
