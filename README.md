# Pixmax B13.4.18｜电影实拍与三镜开场

工作流 `13.4.18-prep-20261021`；默认导演 `13.4.4-shot-detail-emotion-intent-opening-liveaction.1-20261020`。

## 本次更新

完整采用用户《Seedance25_电影实拍导演_20261020》包内同名导演，文件原样同步，不另造导演规则，不替换独立v13.3。

- 每包首镜全程全景无对白，第二镜优先近景／特写且无对白，第三镜起英文对白；前两镜限制含画外对白，源独立旁白保留。跨包联合设计，不加等待／重复动作或加速台词，锁定冲突只报告。
- 意识、梦境、抽象及穿越空间也保持真人电影实拍，不改成线稿、二维头像或图解。
- 不指令眼部亮光、反射、高光或“眼神一亮”；剧情实际眼睛发光需具名源事件与局部证据。
- 发声仅英文、不附中文对照，镜头说明可中文。已有英文逐字保留，只有中文时先忠实翻译并保存独立英文发声源及来源关系，不回写权威剧本。
- 不生成字幕／时间地点卡／悬浮身份标签；必要手机／电脑实体屏幕信息仅英文，信件等实体道具必要英文按原规则。未能承载的信息如实登记，不假称完成。
- 结构与live-action内容检查都执行，文本PASS不证明成片质量或空间正确。

主流程SKILL、AGENTS、双模块及2.5参考和新增director-live-action-update.md同步入口。英文源在写稿／授权改写阶段确定；绑定阶段只追加许可真实@，不临场翻译、删字幕、挪台词或重写旧稿。历史LOCK、画布与任务不自动迁移。

## 保持不变

逐镜2–3倍细写、自然时长、30秒默认12–16镜、七板块、整场站位MD／JSON及索引／一致性报告、逐镜背景、正文资产@、回忆视觉交后期、不制作站位图。轻微状态免补图、正确母图复用、共享资产、紧凑布局、团队项目分配及每集完整剧本／提示词阅读附件保留。

两秒黑场仍只追加连线，不加@、说明、镜头或时长；源SHA-256仍为b7ae7afdd2f44519b01e6852d5c8bb5589cdd4be90e70d3a1810bc01b235add1。本次不向Pixmax上传或实测。

默认停视频生成前，视频生成／补修、超分、剪辑台及下载冻结。仅安装、离线核验与GitHub发布，不操作历史画布或收费。

## 范围与核验

完整包9项Skills及原便携runtime；本次只更新主流程和上述导演，其他7项及runtime逐文件沿用B13.4.17。不打包两个927旧流程、旧项目模板、项目剧本／媒体／账号凭据；黑场是既有共享素材。

checks/离线校验结果.json记录主流程／导演回归、CLI版本、从B13.4.17隔离升级、重复安装及选择升级保留无关定制。PACKAGE_MANIFEST.json逐文件SHA-256，ZIP整体哈希在Release与versions/latest.json。官方quick_validate.py因本机缺PyYAML无法运行；实际可用YAML基础解析另检，不声称官方工具已通过。离线通过不等于平台或成片验证。

## 下载与安装

Release：https://github.com/KainChen169/kaipian-pixmax-workflow/releases/tag/v13.4.18-prep-20261021

下载附件pixmax-workflow-B13.4.18-prep-20261021.zip，不是Source code。核对Release及versions/latest.json整体哈希，阅读本说明／跨会话规则／导入指令，备份注册Skills、维护源及相关AGENTS。

```sh
python3 verify_package.py
python3 install_upgrade.py --skills-only --skill pixmax-codex-pipeline --skill ab-test-seedance25-director-compiler-v13-4-0 --dry-run
```

检查未知定制／更高版本冲突后去掉--dry-run安装；同步对应维护源，定点合并新导演偏好，不整份覆盖个人AGENTS。已有依赖与runtime不重装；新电脑缺依赖按--help先完整dry-run再备份安装。导演测试将其scripts加入PYTHONPATH，旧结构API不能替代内容检查。刷新会话核对两项VERSION，保留备份，不操作历史项目、不恢复冻结、不重新发布本包。
