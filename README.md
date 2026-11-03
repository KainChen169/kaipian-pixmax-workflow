# Pixmax B13.4.35｜阶段表演与按表达选择景别

工作流：`13.4.35-prep-20261103`，沿用B34／B33／29基线精简执行。真人导演：`13.4.4-liveaction-stage-performance.9-20261103`；动画保持`1.5.1-rhythm-performance-local-20261030`。

## 本次变化

- 在现有导演指导中明确关系和情绪阶段、触发及变化，并落实到对应镜头；不增加情绪表或审核层。
- 新主示例呈现假笑、冷淡、直接反击和受辱后的控制；保留安静交流示例作为按需参考。短句和无声变化也可以是关键表演。
- 景别按表情、人物关系和动作因果选择，没有新增开场景别、大小景比例、字数或镜数门槛。
- 原话、自然时长、连续性、真实@、资产验收和保存回读保留；生产校验脚本未改。动画、其他8个随包Skill及vendor与B34字节一致。

默认Draft480P、9:16、有声音，停在视频生成前。历史画布、剧本、LOCK和工作人员编辑不动。

## 下载和校验

[发布页与同事更新指令](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.35-prep-20261103)

[完整ZIP](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.35-prep-20261103/pixmax-workflow-B13.4.35-prep-20261103.zip) · [SHA-256](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.35-prep-20261103/pixmax-workflow-B13.4.35-prep-20261103.zip.sha256) · [版本索引](versions/v13.4.35-prep-20261103.json)

ZIP：2037516字节；SHA-256：`cdda336d3c74e021c290909f46b5d1b52ec6b980aa558e605f611dbafdd70b71`。

离线回归：主流程250通过、3项FFmpeg条件跳过；真人114通过；动画104通过。565文件清单、ZIP CRC、B34隔离升级、无关定制保护及重复安装零差异通过。离线验证不代表实际成片效果。

## 安装

下载Release完整ZIP，不使用Source code。核验哈希、安全解压、阅读包内《导入时复制给Agent.txt》，先备份维护源、注册Skill和相关偏好。Python3.10以上：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
```

核对后去掉`--dry-run`安装，再确认零差异，同步维护源与注册入口。未知定制或更高版本先报告，不静默覆盖；不覆盖较新官方CLI/runtime、独立首集或其他Skills。新机按manifest确认依赖，动画已是1.5.1则不重复安装。只定点合并Pixmax偏好，不覆盖其他个人设置。

只更新，不制作、不生成媒体、不改历史画布、剧本或LOCK，不恢复视频／补修、超分、剪辑台和下载，不再次发布。历史Release和版本包保持。
