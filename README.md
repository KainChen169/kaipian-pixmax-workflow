# Pixmax B13.4.33｜29版基线精简执行

工作流：`13.4.33-prep-20261031`。以B13.4.29为基线，只做执行精简与职责合并，不叠加30—32增补。

真人导演：`13.4.4-liveaction-adaptive-detail.8-20261028`；动画：`1.3.0-natural-performance-20261029`。两者质量标准、模板、示例与29版逐文件保持一致。

## 本次变化

- 内容由写稿者一次核对，资产负责人确认适用性，画布负责人做精确保存比对；主Agent处理接口与异常，职责可以合并。
- 复用未变化的观察与核对结果，不默认重复全文审读、看图或第二轮线上审查。
- 局部修改复核实际影响；校验器支持可选章节／状态条目依赖，相关变化仍拦截，旧记录保持原严格检查。
- 精简默认入口、历史上下文、重复报告与轮询；没有新增审核层、字数、镜数或其他创作配额。

默认仍为Seedance2.5 Draft480P、9:16、有声音，停在视频生成前。历史画布、锁定稿、独立首集及其他Skill不修改。

## 下载和校验

[发布页与同事更新指令](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.33-prep-20261031)

[完整ZIP](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.33-prep-20261031/pixmax-workflow-B13.4.33-prep-20261031.zip) · [SHA-256](https://github.com/KainChen169/kaipian-pixmax-workflow/releases/download/v13.4.33-prep-20261031/pixmax-workflow-B13.4.33-prep-20261031.zip.sha256) · [版本索引](versions/v13.4.33-prep-20261031.json)

ZIP：1992464字节，SHA-256：`1def31f3a43b1427da428b44293efcb7b57e5d143f81955587331e3b6eb78f8f`。

离线测试390通过、3项因FFmpeg条件跳过；546文件校验、ZIP CRC、29→33／32→33隔离安装、定点安装保留无关定制及重复安装验证通过。离线验证不是成片效果或效率收益保证。

## 安装

下载Release完整ZIP，不使用Source code。先核对哈希、安全解压、读取包内《导入时复制给Agent.txt》，备份实际维护源、注册Skill及相关偏好。使用Python3.10以上：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --skill seedance25-animation-director --dry-run
```

核对范围后去掉`--dry-run`安装，再确认零差异，同步维护源与注册入口。已知30—32版按本次明确29基线切换；未知定制或更高版本先报告，不静默覆盖。安装器保留额外文件，已知旧增补按交接归档，不删除未知文件。只合并Pixmax偏好，其他个人偏好、较新官方CLI/runtime及无关Skill保持。

只更新，不制作、不收费、不改历史画布或LOCK、不恢复视频生成／超分／剪辑台／下载、不再次发布。历史Release与版本化包仍保留。
