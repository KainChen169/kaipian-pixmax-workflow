# Pixmax B13.4.22｜会说话动物的声音身份

工作流13.4.22-prep-20261023；默认批量导演13.4.4-liveaction-animal-voice.4-20261023。

## 本次改动

有动物口语、内心传音或动物旁白时，先继承来源／用户／项目既有声音设定；没有则按剧情设计简短的声音性别与年龄感、主要音色和演绎底色，例如年轻女性声线清亮利落、成年男性声线温厚直接、老年男性声线沉稳睿智。这些只是选声示例，不按物种套固定声音，也不改变动物剧情性别、形态或新增人类身份。

声音底色在项目既有角色／表演记录保存一次并跨集／跨Agent复用。每个该动物实际发声的包，人物指定在状态后加一句声音身份，声音安排简述同一声线和声部；时间线原话前写当下说法，说明放引号外，不重复台词或新增第八板块。情绪可改变力度／气息，基础性别、年龄感和音色不无故改变；源确有变声则记录阶段，不机械全剧一声。

纯叫声不新增人类语言；传音／旁白不改成张嘴说话。文字引导不等于精确声纹锁定；没有实际参考不声称克隆／音色绑定，不自动生音频、添加用户本人声音或提交收费任务。新写／获授权改写生效，绑定阶段只编译真实@，不改已确定源稿、旧LOCK、历史画布或任务；独立首集Skill不自动修改、不打包。

图片后备、三镜开场、中文地标、480P／9:16／有声音、两秒黑场、回忆视觉交后期和所有冻结保持。本次没有生成图片／声音／视频或操作Pixmax画布。

## 修改文件与验证

主流程：SKILL.md、AGENTS.md、VERSION。默认导演：SKILL.md、VERSION、references/dialogue_performance_engine.md、prompt_compiler.md、quality_gates.md；另加结构示例及英文原话JSON和4项解析兼容回归。不增加物种／性别关键词硬拦截或自动声纹验收，其他7项Skills及runtime逐文件沿用B13.4.21。

导演90项通过（新增4项覆盖声音说明不混入台词／人类说话者、说明变化不影响逐字原话、错说话者／改词仍拦截、内心声部保留）；主流程186项中183通过、3项FFmpeg未配置跳过。完整包校验、隔离升级、重复安装及定点升级保留无关定制的实际结果见checks/离线校验结果.json。动物声线跨集选择等策略另在checks/动物声音行为复核.md人工离线推演，不冒称自动语义或实际声音效果测试。quick_validate.py缺PyYAML，另做Ruby YAML基础解析。

## 下载与安装

https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.22-prep-20261023

下载完整附件pixmax-workflow-B13.4.22-prep-20261023.zip，不是Source code；核对Release及versions/v13.4.22-prep-20261023.json的ZIP SHA-256。先备份注册Skills、维护源及相关AGENTS，检查未知定制和本机更高版本。Python3.10以上执行：

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
```

确认范围后去掉--dry-run安装，同步维护源并定点合并新增跨会话规则，不整份覆盖个人AGENTS。已有runtime与其他Skill不替换，新电脑缺依赖按包内安装器帮助完整安装；刷新会话核对VERSION和哈希。只更新，不制作、不改历史稿／LOCK／画布，不恢复冻结，不再次发布。
