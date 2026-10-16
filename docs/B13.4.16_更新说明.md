# Pixmax B13.4.16｜情绪意图转译

工作流：13.4.16-prep-20261016。默认导演：13.4.4-shot-detail-emotion-intent-20261016，仍为B13.4.4逐镜细写版。

## 本次改动

只在默认导演的 references/dialogue_performance_engine.md「人物意图与情绪」中增加一条通用原则：情绪描写按表演意图转译，不机械落实文学性修辞；结合上下文利用本场已有的目光、语气、动作和反应呈现，不默认转成明显的身体颜色变化或夸张生理效果。剧情明确成立且承担叙事作用的身体状态保留。不堆砌无关微动作，不跨多个字段重复强化同一细节。

原则仅作用于新写及获授权修订的表演说明，不改原话、源事件或历史LOCK。不设“红眼”禁词表，不把人物统一演成克制或迟疑，不自动删除哭泣、伤势、醉态或剧情变身。仅同步两项VERSION，其他导演规则、模板、脚本、主流程正文均不变。

## 保留范围

沿用B13.4.15的欧美资产与完整生成规则、原母图复用、轻微状态免补图、身份及场景连续性、正文真实@、有序绑定、防重和次数边界。其他七个Skills与CLI运行时固定沿用上一发布包，不引入其他会话定制。视频生成／补修、超分、剪辑台和自动下载仍冻结；不返修历史项目或媒体。

## 安装

发布：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.16-prep-20261016
下载完整附件ZIP，不要下载Source code，核对Release与versions/latest.json公布的SHA-256。

先备份注册Skills、本地维护源和相关偏好，读取导入时复制给Agent.txt。运行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
```

检查未知定制／更高版本冲突后去掉--dry-run安装，并同步实际维护源；不覆盖其他Skills、个人设置或全局AGENTS。新电脑缺依赖时先读install_upgrade.py --help，按实际需要做全套备份、dry-run及安装。仅更新、不制作、不再次发布本包。

## 验证边界

离线回归、文件哈希、隔离升级、重复安装和选择升级保留其他定制的实际结果见checks/离线校验结果.json。未改校验器，没有新增正则禁词；数值校验不能证明表演审美或AIGC生成效果。本次不操作Pixmax、不收费生成或审片。

备份已保存在本机Skill_packages/backups/20261016_情绪转译规则前，备份和个人数据不进入交接包。

实跑：导演42项通过，主流程162项中159通过、3项FFmpeg缺失跳过；495文件哈希、隔离升级／重复安装／保留其他定制通过。系统Python3.9不兼容现有click，改用已配置的bundled Python和包内vendor后通过。quick_validate.py缺PyYAML未运行，Ruby YAML基础解析通过。
