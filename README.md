# Pixmax B13.4.34｜动画导演1.5.1

工作流：`13.4.34-prep-20261103`。沿用B13.4.33／29基线精简执行，仅升级动画导演和必要接入，不叠加30—32增补。

动画导演：`1.5.1-rhythm-performance-local-20261030`（用户2026-11-03提供的包，内部日期沿用原包）；真人导演保持 `13.4.4-liveaction-adaptive-detail.8-20261028`。

## 本次变化

- 动画从唯一设计记录编译正文、调度及交接，保留原包的expressive_animation_v3、物种表演、动态摄影、自然节奏与镜头密度要求。
- 主流程核验统一设计来源、独立英文源、声音、当前设计哈希绑定的语义复核、确定性正文及同源调度；带设计文件不得删除policy降级绕检。
- 原话、真实@、有序输入、保存回读和旧稿兼容保留；旧LOCK不迁移。真人、其他8个随包Skill及vendor与B33逐字节保持。
- 未实施此前仅讨论的省Token优化。默认Draft480P、9:16、有声音，停在视频生成前，历史画布与冻结后处理不动。

## 下载和校验

[发布页与同事更新指令](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.34-prep-20261103)

[完整ZIP](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.34-prep-20261103/pixmax-workflow-B13.4.34-prep-20261103.zip) · [SHA-256](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.34-prep-20261103/pixmax-workflow-B13.4.34-prep-20261103.zip.sha256) · [版本索引](versions/v13.4.34-prep-20261103.json)

ZIP：2015984字节；SHA-256：`a76eda08ea573b7a5d239bd06c0d620b7966a4750d5cbd7e379fbeb58b8c59a3`。

离线回归：主流程249通过、3项FFmpeg条件跳过；动画104通过；真人110通过。560文件清单、ZIP CRC、B33隔离升级、无关定制保护及重复安装零差异通过。离线验证不代表实际成片效果。

## 安装

下载Release完整ZIP，不使用Source code。核验哈希、安全解压、阅读包内《导入时复制给Agent.txt》，先备份维护源、注册Skill和相关偏好。Python3.10以上：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill seedance25-animation-director --dry-run
```

核对后去掉`--dry-run`安装，再确认零差异，同步维护源与注册入口。未知定制或更高版本先报告，不静默覆盖；不覆盖较新官方CLI/runtime、真人定制、独立首集或其他Skills。若尚非B33／29基线，先核对差异；新机按manifest确认依赖。只定点合并Pixmax偏好，不覆盖其他个人设置。

只更新，不制作、不生成媒体、不改历史画布、剧本或LOCK，不恢复视频／补修、超分、剪辑台和下载，不再次发布。历史Release和版本包保持。
