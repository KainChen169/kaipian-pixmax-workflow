# Pixmax B13.4.21｜内置补图后备

工作流13.4.21-prep-20261023；默认批量导演仍13.4.4-liveaction-landmarks.3-20261022。本次仅调整必要图片失败恢复与导入规范，不修改导演、提示词标准或视频模型。

## 改动

Pixmax确实无法完成必要图片时，可在当次图片授权、预算及共享尝试额度内改用Codex内置图片生成器，不必先耗完平台重试，也不必为这个已授权后备渠道逐项询问。读取当前可用imagegen Skill及工具说明，使用实际母图，保留身份／当前形态、场景布局与道具实例；生成图保存项目内，看图验收后正式上传目标画布，回读真实资产及承载节点UUID，完成适用人像检测，再编译真实@及有序连线。

平台和内置共享同一需求键、唯一认领及首次加最多2次追加总数；排队、运行或响应未知先对账，不双发。不因内置来源放宽验收；只上传失败只恢复导入，不重新生图。内置不可用不自动使用API Key／CLI或其他付费服务，不绕内容审核、身份、权限或参考隐私限制。轻微状态免补图、合格母图优先复用继续有效。

这是Agent执行规范，不是自动跨平台重试程序。没有调用图片／视频工具、操作线上画布或做成片效果测试；视频、补修、超分、剪辑台及成片下载继续冻结。旧LOCK、历史任务、导演三镜开场、480P／9:16／有声音规格均保持；独立首集Skill不修改、不打包。

## 修改文件

仅pixmax-codex-pipeline：SKILL.md、AGENTS.md、VERSION；新增references/builtin-image-fallback.md；更新references/asset-generation-recovery.md、shared-asset-coordination.md、post-import-asset-analysis.md、bounded-retries-and-live-canvas.md、optimized-execution.md。脚本及校验器不改，保留全部验收。完整包其余8项Skill与runtime逐文件沿用B13.4.20；两个927旧流程和旧项目模板继续不打包。

## 校验与安装

运行原回归及隔离升级／重复安装／定点安装保留无关定制测试，实际结果见checks/离线校验结果.json。图片后备分支另做离线人工行为推演，见checks/内置补图行为复核.md，不将文档检查冒称工具自动化测试或线上生成效果验证。

下载入口：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.21-prep-20261023

下载完整附件pixmax-workflow-B13.4.21-prep-20261023.zip，不是Source code，核对Release及versions/v13.4.21-prep-20261023.json的ZIP SHA-256。先备份注册Skill、维护源及相关AGENTS，检查未知定制和本机更高版本。Python3.10以上执行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --dry-run
```

核对范围后去掉--dry-run安装，同步维护源并定点合并跨会话规则，不整份覆盖个人AGENTS。原有依赖／runtime／其他Skill不替换；新电脑按包内安装器帮助及依赖说明完整安装。仅更新，不制作、不返修历史项目、不恢复冻结、不再次发布。
