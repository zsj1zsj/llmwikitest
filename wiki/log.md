# Wiki Log

Append-only chronological record of all wiki activity.

Format: `## [YYYY-MM-DD] <operation> | <description>`

Operations: `ingest` | `query` | `lint` | `init`

---

## [2026-05-17] ingest | 批量入库（刘义宣、如何评价孝武帝、元嘉三大家、戴法兴、柳元景、王僧达、颜竣）

新建 source 页：刘义宣、如何评价宋孝武帝（知乎）、元嘉三大家（国学网）、戴法兴、柳元景、王僧达、颜竣（共7页）。
新建 entity 页：刘义宣、戴法兴、王僧达、颜竣（共4页）。
重写 entity 页：柳元景（补入新亭大捷全程、顾命始末、赴死细节）。
更新 entity 页：宋孝武帝刘骏（补入雍州时期、颜竣/王僧达关联、幸臣转折节点）。
更新 index.md（+9条 source、+6条 entity）。
跳过（无新增实质内容）：元嘉三大家（entity已覆盖，仅建source页）。

## [2026-05-17] query | 撰写分析页：宋孝武帝刘骏

新建 `wiki/analyses/宋孝武帝刘骏.md`，约2500字，六节：从边缘到中心→系统性集权→寒人掌机要→对北守势→殷淑仪与晚年溃散→遗产与阴影。
更新 index.md（+1条 analysis）。

## [2026-05-17] lint | 断链修复（backslash转义、路径错误、无实体页链接）

**修复断链（7个文件，共12处）：**
- `concepts/汉武帝时代的悲剧将领.md` 第29-31行：`\|` 转义错误 → `|`（李广、李陵、司马迁）
- `concepts/南朝宗室相残.md` 第27-32行：`\|` 转义错误 → `|`（6处：刘义康、刘劭、刘子业、义嘉之乱、宋明帝刘彧、刘休仁）
- `sources/风云南北朝：刘宋.md` 第80行：同上（刘义隆）
- `entities/宋孝武帝刘骏.md`：`[[wiki/entities/宋文帝刘义隆|宋文帝]]` → `[[wiki/entities/刘义隆|宋文帝]]`（路径错误）
- `entities/柳元景.md`：`[[wiki/entities/垣护之|垣护之]]` → 纯文本（无对应entity页）
- `entities/刘义宣.md`：同上（垣护之）
- `sources/王华-轶事.md`：`[[wiki/entities/王弘|王弘]]` → 纯文本（无对应页）
- `sources/延年-汉朝.md`：`[[wiki/entities/李夫人]]` → 纯文本（无对应页）
- `sources/刘宋20名将.md`：`[[wiki/entities/王镇恶]]` `[[wiki/entities/王猛]]` → 纯文本（无对应页）

无孤立页面。无缺失index条目。冯太后、陈霸先已在index中。

## [2026-05-17] ingest | 批量入库（刘义恭、宗悫、殷淑仪、薛安都、颜师伯）

新建 source 页：刘义恭、宗悫、殷淑仪、薛安都、颜师伯（共5页）。
新建 entity 页：刘义恭、宗悫、殷淑仪、薛安都、颜师伯（共5页）。
更新 entity 页：
  - 宋孝武帝刘骏（新增"核心功臣"节、"殷淑仪与晚年悼亡"节、"驾崩与顾命"节；更新sources字段）
  - 刘义宣（殷淑仪wikilink补全，叛乱动机补充）
更新 concept 页：义嘉之乱（薛安都降魏机制补入蔡兴宗预警细节）。
更新 index.md（+5条 source、+5条 entity）。
跳过（已入库，Unicode误报）：为什么汉武帝时期有很多名叫"延年"人？.md、义嘉之乱对南北局势的影响.md、刘休仁.md、刘子业.md、刘子勋.md、刘昱.md（维基版）、刘昱.md（百度版）、南北朝历史趣历史.md、宋明帝.md。

## [2026-05-17] ingest | 批量入库（南北军事关系-孝武帝以降、宋孝武时代文学新变书介）

新建 source 页：南北军事关系-孝武帝以降（2019年学术论文）、宋孝武时代文学新变-书介（赫兆丰2024专著序与后记）（共2页）。
更新 entity 页：宋孝武帝刘骏（新增"对北政策"节：总体和平、互市争论详细名单、周朗弃徐齐论、青州防线演变；新增"文学与才学"节）。
更新 index.md（+2条 source）。
跳过：无。

## [2026-05-17] ingest | 批量入库（宋孝武帝、搜狐版南北朝概述）

新建 source 页：宋孝武帝刘骏（维基百科）、南北朝概述-搜狐（共2页）。
新建 entity 页：宋孝武帝刘骏（1页）。
更新 index.md（+2条 source、+1条 entity）。
跳过（Unicode 归一化误报，实已入库）：刘昱.md（百度百科版）、为什么汉武帝时期有很多名叫"延年"人.md。

## [2026-05-17] query | 撰写分析页：刘彧与刘昱时代

新建 `wiki/analyses/刘彧与刘昱时代.md`，约5000字，含：义嘉之难、五州沦陷、顾命格局瓦解、474年刘休范之乱、477年弑帝与四贵集议、袁粲殉节、宋齐禅代全程。
嵌入地图：刘宋建立版图（图3）、南齐时期南北格局（图9）、南朝建康城详图（图6）。
更新 index.md（+1条 analysis）。

## [2026-05-17] lint | 交叉引用修复，新建四贵概念页

**修复断链（7处文件，共11处链接）：**
- `[[raw/articles/刘昱]]` → `[[wiki/entities/刘昱|刘昱]]`（张兴世、刘景素、宋顺帝刘准、阮佃夫、袁粲）
- `[[宋前废帝刘子业]]` → `[[wiki/entities/刘子业|宋前废帝刘子业]]`（王敬则）
- `[[宋后废帝刘昱]]` → `[[wiki/entities/刘昱|宋后废帝刘昱]]`（王敬则×2、刘秉×1）
- `[[宋顺帝]]` → `[[wiki/entities/宋顺帝刘准|宋顺帝]]`（刘休范）

**新建概念页：**
- `wiki/concepts/四贵.md`（被蔡兴宗、刘秉等页引用，此前无对应页面）

**更新 index.md**（+1条概念）。

无孤立页面，无重复条目，无 sources/ 未收录文件。

## [2026-05-17] ingest | 批量入库（蔡兴宗、刘勔、王敬则、刘秉）

新建 source 页：蔡兴宗、刘勔、王敬则、刘秉（共4页）。
新建 entity 页：蔡兴宗、刘勔、王敬则、刘秉（共4页）。
更新 index.md（+4条 source、+4条 entity）。
跳过：无。

## [2026-05-17] ingest | 批量入库（杨运长）

新建 source 页：杨运长。新建 entity 页：杨运长。
更新 entities/刘昱（杨运长纯文本升级为 wikilink）。
跳过：刘昱.md（百度百科版，已入库）；杨长亚（现代人，上次已跳过）。
更新 index.md（+1条 source、+1条 entity）。

## [2026-05-17] ingest | 批量入库（王道隆、褚渊）

新建 source 页：王道隆、褚渊（共2页）。
新建 entity 页：王道隆、褚渊（共2页）。
扩充 entity 页：刘昱（补入政治格局：幸臣三人组 vs 顾命五大臣 vs 四贵、两次宗室叛乱）。
跳过：杨长亚（现代陕西政治人物，误抓取）；刘昱.md（百度百科版，内容远少于已入库维基版）。
更新 index.md（+2条 source、+2条 entity）。

## [2026-05-17] ingest | 批量入库（张兴世、袁粲、萧道成、刘休范、刘景素、宋顺帝、阮佃夫）

新建 source 页：张兴世、袁粲、萧道成-维基、刘休范、刘景素、宋顺帝、阮佃夫（共7页）。
新建 entity 页：张兴世、袁粲、刘休范、刘景素、宋顺帝刘准、阮佃夫（共6页）。
重写 entity 页：萧道成（大幅扩充崛起路径七阶段，补入顾命大臣名单、荀伯玉献计、平刘休范策略）。
更新 index.md（补入7条 source、7条 entity 条目）。
跳过（已存在）：无。

## [2026-05-17] ingest | 批量入库（宋明帝、前废帝、后废帝、刘子勋、刘休仁、义嘉之乱）

新建 source 页：宋明帝刘彧、宋前废帝刘子业、义嘉之乱分析、晋安王刘子勋、建安王刘休仁、宋后废帝刘昱、趣历史南北朝门户（共7页）。
新建 entity 页：宋明帝刘彧、刘子业、刘子勋、刘休仁、刘昱（共5页）。
新建 concept 页：义嘉之乱（含五州沦陷始末与战略影响）。
更新：南朝宗室相残（补充刘子业、义嘉、刘彧杀弟、刘昱各案）；萧道成（补充义嘉之乱后崛起路径）；index.md。
跳过（已存在）：无。

## [2026-05-15] query | 刘义隆时代介绍

归档为 analyses/刘义隆时代.md。六节：坐稳帝位→元嘉之治→主相之争→三次北伐→衰落与终结→历史评价。更新 index.md。

## [2026-05-15] ingest | 批量入库（刘义康、范晔、拓跋焘、元嘉之治、谢灵运、颜延之）

新增 sources：刘义康、范晔、魏太武帝、元嘉之治、谢灵运、颜延之（共6个）。新增 entities：刘义康、范晔、拓跋焘、谢灵运、颜延之（共5个）。新增 concepts：元嘉之治。更新 index.md。跳过：地图上的南北朝（已入库）、南北朝历史导航页（无实质内容）。

## [2026-05-09] ingest | 批量入库（刘宋20名将、魏晋南北朝基本史料目录、维基百科人物页）

新增 sources：刘宋20名将、魏晋南北朝基本史料目录。新增 entities：柳元景、沈攸之。更新 analyses/元嘉北伐梗概（柳元景 wikilink 补全）；更新 index.md。跳过：地图上的南北朝（已入库）、南北朝历史导航页（无实质内容）。

## [2026-05-15] ingest | Meetrics 个人指标追踪博客

新增 sources/meetrics-个人指标追踪。要点：自定义标签+可调lag相关性分析（发现化疗副作用8天滞后）、贝叶斯习惯追踪、Claude驱动AI分析师。更新 index.md。

## [2026-05-15] ingest | 地图上的南北朝（14幅地图，嘻嘻网·地图帝）

新增 sources/地图上的南北朝。更新 concepts/建康城格局（补入外郭篱、西州城、丹阳郡城、乐游苑、百官府舍、东晋四帝陵区；更新来源）。更新 index.md。
关键地图：刘裕北伐路线、第一/二次元嘉北伐进退路线、南朝建康城详图、北魏洛阳城、六镇起义分布、隋灭南陈。

## [2026-05-15] ingest | 建业城与建康城平面图（古建筑图册）

新增 sources/建业-建康城（地图解读）、concepts/建康城格局（台城/石头城/东府城/清溪/秦淮河布局及与刘宋史事的对应）。更新 index.md。

## [2026-05-09] lint | 补全第三次北伐叙事与人物wikilink

analyses/元嘉北伐梗概：第三次北伐段落补入萧思话、鲁爽、臧质、沈庆之wikilink，补入刘兴祖建议细节；图表补萧思话wikilink及鲁爽降将参战条目；关联描述修正。

## [2026-05-08] ingest | 沈庆之（维基百科）

新增：sources/沈庆之、entities/沈庆之。更新 analyses/元嘉北伐梗概与人物关系（补入沈庆之"步不敌骑"wikilink、第二次北伐副手条目、关联）；sources/元嘉北伐（补入沈庆之链接）；index.md。

## [2026-05-08] lint | 断链修复、缺失实体补全、交叉引用补入

修复：① entities/鲁爽 引用的 entities/鲁轨 不存在 → 新建 entities/鲁轨；② sources/盖吴起事 中 [[wiki/entities/薛安都]] 无对应页面 → 改为纯文本；③ concepts/南朝宗室相残 两处 [[刘裕]] [[高洋]] 缺路径前缀 → 补全；④ concepts/南朝宗室相残 刘劭弑父无链 → 补 [[wiki/entities/刘劭]]；⑤ entities/刘义隆 [[刘裕]] 缺前缀、王玄谟无链 → 补全；⑥ sources/元嘉北伐 王玄谟、萧斌、臧质 无链 → 补实体链接；⑦ index.md 补入 entities/鲁轨 条目。

## [2026-05-08] ingest | 批量入库（盖吴起事、王玄谟、臧质、刘康祖、陈宪、江湛、徐湛之、萧斌、鲁爽、刘劭）

新增 sources：盖吴起事、王玄谟、臧质、刘康祖、陈宪、江湛、徐湛之、萧斌（刘宋）、鲁爽、刘劭。新增 entities：盖吴、王玄谟、臧质、刘康祖、陈宪、江湛、徐湛之、萧斌、鲁爽、刘劭。更新 analyses/元嘉北伐梗概与人物关系（补入第二次北伐人物：王玄谟、萧斌、臧质、刘康祖、陈宪、江湛、徐湛之、鲁爽）。更新 index.md。跳过已入库：30个文件。

## [2026-05-07] lint | 交叉引用补全、日期修正、误导链接清除

修复：① analyses/元嘉北伐梗概 补入北魏方司马楚之、长孙道生、崔浩wikilink；② sources/元嘉北伐 关联补全（8个实体链接）；③ entities/王慧龙 补入到彦之评语；④ entities/檀道济 补入长孙道生关联；⑤ concepts/世家大族 补入王慧龙、司马楚之典型案例；⑥ index.md、entities/到彦之 updated 日期修正为2026-05-07；⑦ 删除 entities/赫连定 和 sources/赫连定 中误链接到南北朝对应关系的条目（赫连定为十六国人物）。

## [2026-05-07] ingest | 批量入库（姚耸夫、司马楚之、鲁轨、韩延之、长孙道生、赫连定）

新增：sources/姚耸夫、sources/司马楚之、sources/鲁轨、sources/韩延之、sources/长孙道生、sources/赫连定；entities/姚耸夫、entities/司马楚之、entities/韩延之、entities/长孙道生、entities/赫连定。更新 entities/到彦之（补充评人语录及关联）、index.md。跳过已入库：24个文件。

## [2026-05-07] ingest | 刘义庆（维基百科）

新增：sources/刘义庆、entities/刘义庆。更新 entities/鲍照（补充刘义庆门客关联）、index.md。跳过已入库：22个文件。

## [2026-05-06] ingest | 崔浩（维基百科）

新增：sources/崔浩、entities/崔浩。更新 entities/王慧龙（补充崔浩关联）、index.md、overview.md（移除崔浩遗留问题标记）。

## [2026-05-06] lint | 孤立链接修复、index 补全、overview 更新

修复：index.md（updated 日期、两处链接前缀、田延年 entity 补入 Entities 区）；刘义隆.md（[[裴松之]]孤立链接改为纯文本，到彦之/檀道济加 wikilink）；高洋.md（nanbeichao-stories 和杨愔链接补前缀）；南朝宗室相残.md（三处关联链接补前缀）；overview.md（大幅更新：补入元嘉北伐/汉武帝/田延年等主题，更新来源数量与 evolution notes）。标记新发现问题：崔浩尚无 entity 页。

## [2026-05-06] ingest | 批量入库（檀道济、到彦之、王仲德、段宏、萧承之、萧思话、王慧龙）

新增：sources/檀道济、sources/到彦之、sources/王仲德、sources/段宏、sources/萧承之、sources/萧思话、sources/王慧龙；entities同上七人。更新 entities/萧道成（补充父亲萧承之）、index.md。跳过已入库13个。

## [2026-05-06] ingest | 田延年（维基百科）

新增：sources/田延年、entities/田延年。更新 index.md。

## [2026-05-06] query | 元嘉北伐梗概与人物关系

归档为 analyses/元嘉北伐梗概与人物关系.md。更新 index.md。

## [2026-05-06] ingest | 批量入库 raw/articles（鲍照、何无忌、元嘉北伐）

新增：sources/鲍照、sources/何无忌、sources/元嘉北伐、entities/鲍照、entities/何无忌。更新 entities/刘裕、index.md。跳过已入库：为什么中国的钱庄票号干不过西方银行.md、为什么汉武帝时期有很多名叫"延年"人？.md、风云南北朝 南宋.md、风云南北朝 南陈.md、风云南北朝 南齐.md、李广_李陵与卫青_李广利.md、八一八南北朝的奇葩小故事_71-72.md、刘义隆.md、王华的轶事典故有哪些？王华趣事介绍-趣历史网.md（共9个）。

## [2026-04-29] ingest | 李广、李陵与卫青、李广利

新增：sources/李广-李陵-卫青-李广利、entities/李广、entities/李陵、entities/司马迁、concepts/汉武帝时代的悲剧将领。更新 index.md。

## [2026-04-28] ingest | 王华轶事典故（趣历史网）

新增：sources/王华-轶事、entities/王华。更新 entities/刘义隆（补充王华关联）、index.md。

## [2026-04-28] ingest | 刘义隆（宋文帝）维基百科

新增：sources/刘义隆、entities/刘义隆。更新 entities/刘裕（补充子嗣关联）、sources/风云南北朝：刘宋（补充刘义隆链接）、index.md。

## [2026-04-25] query | 票号与现代银行异同

归档为 analyses/票号与现代银行异同.md。更新 index.md。

## [2026-04-25] ingest | 为什么中国的钱庄票号干不过西方银行

新增：sources/qianzhuang-vs-yinhang；concepts/特许银行制度。更新 index.md、overview.md。

## [2026-04-23] ingest | 为什么汉武帝时期有很多名叫"延年"人？

新增：sources/yanmian-han（《汉书》二十位延年人物）；concepts/汉代命名风俗。更新 index.md、overview.md。

## [2026-04-22] query | 高洋评价

归档为 analyses/高洋评价.md。

## [2026-04-21] ingest | 风云南北朝 南宋/南齐/南陈（批量）

新增：sources/fengyun-nanbeichao-liusong、nanqi、nanchen；entities/刘裕、萧道成、陈霸先、拓跋宏、冯太后；concepts/南朝宗室相残。更新 entities/高洋（补充555年后堕落记录）、index.md、overview.md。跳过已入库：八一八南北朝的奇葩小故事_71-72.md。

## [2026-04-21] ingest | 八一八南北朝的奇葩小故事 第71-72条

新增：sources/nanbeichao-stories-71-72，entities/高洋、杨愔、崔甗、魏收，concepts/世家大族、南北朝对应关系。更新 index.md、overview.md。

## [2026-04-21] init | Wiki initialized

Created vault structure: `raw/`, `wiki/`, `CLAUDE.md`, `wiki/index.md`, `wiki/log.md`, `wiki/overview.md`.
Based on the llm-wiki pattern. Ready to ingest first source.
