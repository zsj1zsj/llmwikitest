# Wiki Log

Append-only chronological record of all wiki activity.

Format: `## [YYYY-MM-DD] <operation> | <description>`

Operations: `ingest` | `query` | `lint` | `init`

---

## [2026-08-13] ingest | 八王之乱分析改论：三时间尺度与杨骏定位

- 新增 raw 资料：`raw/articles/晋书-卷040-杨骏传摘录.md`（“夹辅王室”原案、藏诏、段广张劭掌机密禁兵、孙楚劝谏）
- 更新 `raw/articles/资治通鉴-卷082至086-八王之乱摘录.md`，补入和峤谏言、司马遹五岁轶事、“帝知太子不才，然恃遹明慧”、夹辅原案细节
- 新建来源页：`wiki/sources/晋书-卷040-杨骏传摘录.md`
- 改写分析页 `八王之乱：制度失控与西晋崩解`：
  - 核心论点改为“司马炎同时解决三个时间尺度的问题（皇权安全、惠帝过渡、终点司马遹）而未连成一套制度”
  - 新增“司马遹：被设计的继承终点”一节（和峤、恃遹明慧、为遹高选僚佐）
  - 新增“杨骏：从过渡期辅政者到控制皇帝的人”一节，明确“夹辅”原案被杨骏破坏、辅政者异化为控制者
  - 太子废杀一节补入“继承终点被清除”的分析；结论更新为“三个时间尺度没有连成一套制度”
- 更新：`wiki/index.md`（新增杨骏传来源条目）

## [2026-08-13] ingest | 抽出八王之乱人物关系独立笔记

- 新建 `wiki/analyses/八王之乱人物关系.md`，将原分析页的司马氏世系、外戚后妃、权力更替、非司马氏关键人物、世系考订独立成篇
- 原分析页 `八王之乱：制度失控与西晋崩解.md` 的关系图部分替换为指向新笔记的简注
- 更新：`wiki/index.md`

## [2026-08-13] ingest | 八王之乱人物关系世系考订

- 新增 raw 资料：`raw/articles/晋书-卷037-038-031-宗室后妃世系摘录.md`
- 新建来源页：`wiki/sources/晋书-宗室后妃世系摘录.md`
- 更新分析页 `八王之乱：制度失控与西晋崩解` 的“附：人物关系图”，补入司马氏九子、司马孚/司马馗支脉、后妃外戚世系，并加世系考订
- 考订：司马亮为宣帝第四子（非第三子）；司马颙为司马孚之孙；司马越为司马馗之孙；司马冏兼承景帝、文帝两脉
- 更新：`wiki/index.md`

## [2026-08-13] ingest | 八王之乱补充史料与综合分析

- 新增 raw 资料：`晋书-卷004-惠帝纪摘录.md`、`晋书-卷059-八王传摘录.md`、`资治通鉴-卷082至086-八王之乱摘录.md`、`八王之乱现代研究书目与论点.md`
- 新建来源页：对应四份史料与研究书目摘要页
- 新建分析页：`wiki/analyses/八王之乱：制度失控与西晋崩解.md`
- 更新：`wiki/index.md`、`wiki/overview.md`
- 结论：八王之乱是宗室军政化、宫廷合法性竞争、地方军镇化、流民武装化和边疆族群政治叠加形成的中央崩解过程，不宜写成单一人物或单一制度的线性因果

## [2026-08-13] ingest | 八王之乱 - 维基百科，自由的百科全书

- 新建来源页：`wiki/sources/八王之乱.md`
- 新建概念页：`wiki/concepts/八王之乱.md`
- 新建实体页：司马亮、司马玮、司马伦、司马冏、司马乂、司马颖、司马颙、司马越
- 更新：`wiki/index.md`、`wiki/overview.md`
- 主题：291—306年西晋宗室政变与内战，以及其对西晋崩溃、五胡十六国和东晋南渡的影响

## [2026-06-22] lint | 断链与歧义短链修复

修复：① analyses/刘彧与刘昱时代 表格中被反斜杠污染的 wikilink；② sources/nanbeichao-stories、刘义隆、风云南北朝：刘宋 中缺失或误指向链接；③ 刘宋后期多个人物页中的裸短链歧义，统一指向 `wiki/entities/...` 或 `wiki/concepts/...`；④ concepts/南北朝对应关系、汉代命名风俗 的来源短链。复扫正文：缺失链接0，歧义链接0；index缺项0。历史 `wiki/log.md` 旧记录按 append-only 规则未回改。

## [2026-06-22] ingest | 酒文化历史集粹

新增：sources/酒文化历史集粹、concepts/酒文化轶事。更新 index.md、overview.md。该来源为张发财历史饮酒轶事合集，主要用于观察豪饮、醉态、酒局社交与权力场叙事模式。

## [2026-05-27] batch-ingest | 12篇剩余文章入库（Economist地缘/AI系列 + 工具类）

### 新建来源页（13篇）
- `america-wakes-up-ai-power.md` — Anthropic Mythos事件，美国AI政策转向
- `china-nationalist-spy-thriller.md` — 主旋律电影票房从53%跌至12%
- `china-tea-brands-america.md` — 霸王茶姬/喜茶/蜜雪冰城进军美国
- `iran-war-taiwan-risk.md` — 美伊战争消耗美军，2028-2032窗口期风险上升
- `how-china-wins-from-war.md` — 北京视美伊战争为美国重大失误
- `pakistan-gulf-broker.md` — 穆尼尔元帅促成美伊停火
- `cheap-energy-china-ai.md` — 中国电网容量美国两倍，"电子鸿沟"或弥补芯片短板
- `music-brain-benefits.md` — 音乐训练增加灰质、7岁前训练胼胝体更大
- `why-china-worries-ai.md` — OpenClaw事件暴露中国AI治理三重困境
- `openclaw-prompts.md` — 10个经过压力测试的OpenClaw提示词
- `china-public-opinion-taiwan.md` — 卡特中心6500人调查：对美台态度硬化
- `skilluse-ai-agent-skills.md` — AI Agent技能注册中心
- `china-property-rotten-tail.md` — 2000万套烂尾楼、17万亿元财富锁死

### 新建概念页
- `openclaw-china-ai-craze.md` — OpenClaw热潮与监管困境（综合两篇来源）

### 跳过（已入库）
- `为什么汉武帝时期有很多名叫"延年"人？.md` → 已有 `延年-汉朝.md`
- `刘昱.md` → 已有 `wiki/sources/刘昱.md`

### 更新
- `wiki/index.md` — +14条 source/concept 条目

## [2026-05-27] lint | 断链修复

- 修复：`concepts/Redis.md` 第34行：`[[wiki/concepts/Redis内部数据结构]]` → `[[wiki/sources/redis-数据结构-图解|图解 Redis 数据结构]]`（目标页不存在，改指向已入库的source页）
- 无孤立页面，无缺失index条目，无其他断链

## [2026-05-27] ingest | 风云南北朝：箫梁（安州牧视频字幕）

- 新建来源页：`wiki/sources/风云南北朝-箫梁.md`（萧梁502–557全史，10集字幕，11场战役，90条地名对照）
- 新建实体页：`wiki/entities/萧衍.md`（梁武帝，在位48年，前期治世后期沉迷佛教，86岁饿死台城）
- 新建实体页：`wiki/entities/侯景.md`（东魏叛将，台城之乱祸首，兵败被杀分食）
- 更新：`wiki/entities/陈霸先.md`（补充箫梁来源、补入萧衍/侯景交叉链接）
- 更新：`wiki/index.md`（+3条 source/entity）
- 跳过：无

## [2026-05-27] ingest | 杨惠之考（西域文明的发现）

- 新建来源页：`wiki/sources/杨惠之考.md`
- 新建实体页：`wiki/entities/杨惠之.md`（盛唐"塑圣"，与吴道子齐名，首创塑壁技法）
- 更新：`wiki/index.md`（+2条 source/entity）
- 跳过：无

## [2026-05-21] ingest | 批量入库 Redis 系列（7篇）

新建 source 页（7页）：
- `redis-overview`：Redis 起源与架构（RESP/单线程/jemalloc/部署模式）
- `redis-面试`：面试题整理（9种数据类型、集群 Hash Slot 分片、单线程性能）
- `redis-命令速查`：个人命令笔记（String/List/Hash/Set 速查）
- `redis-数据结构-图解`：9种底层数据结构详解（SDS/跳表/quicklist/listpack等）
- `cache-consistency-three-ways`：三种缓存一致性策略
- `redis-mysql-consistency`：Cache-Aside 最佳实践、延迟双删、Canal binlog方案
- `redis-分布式锁`：悲观锁/乐观锁/ZK锁/Redis SETNX/Redisson/RedLock

新建 concept 页（3页）：
- `Redis`：综合概念页（数据类型、底层结构对应、部署、使用场景）
- `缓存一致性`：四策略对比、延迟双删、CAP 最终一致性
- `分布式锁`：四大条件、各方案对比、Redisson WatchDog 原理

跳过：`.gitkeep`、`.DS_Store`（非内容文件）；其余历史文章已全部入库。

## [2026-05-18] ingest | 李世民修《氏族志》，清河崔氏的荣耀与没落

- 新建来源页：`wiki/sources/清河崔氏-氏族志.md`
- 新建实体页：`wiki/entities/崔宏.md`（北魏制度设计者，"魏"国号建议者，崔浩之父）
- 更新：`wiki/entities/崔浩.md`（补充崔宏基础、更新来源字段）
- 更新：`wiki/concepts/世家大族.md`（新增五姓七望条目、唐初系统性打压、清河崔氏完整案例）
- 更新：`wiki/index.md`、`wiki/log.md`

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

## [2026-09-16] query | 八王之乱小抄

- 新建 `wiki/analyses/八王之乱小抄.md`：八王速记表（按败亡次序＋支脉记法）、290—306 时间线速记、答题因果链、三个必答论点、易错点与考订、关键配角
- 修订 `wiki/entities/司马亮.md`：第三子 → 第四子，从《晋书》卷三十八、五十九；补入世系来源与修订说明
- 更新 `wiki/index.md`（Analyses 新增条目）
- 未新增 raw 资料，全部由既有八王之乱专题页面压缩综合

## [2026-09-16] query | 八王亲缘关系分类

- 更新 `wiki/analyses/八王之乱人物关系.md`：第一节新增“八王按亲缘关系分类”
  - 以惠帝为基准的世代阶梯表（祖辈 2／父辈 2／同辈 4），含支脉路径与与惠帝关系
  - 按离皇统远近分两半：昭系内 4 人（玮、乂、颖、冏）／昭系外 4 人（亮、伦、颙、越）
  - 注明司马冏宗法双属（本生父攸，攸过继景帝师）与“亲疏与结局相逆”为分析判断
- 更新 `wiki/index.md` 对应条目描述；updated 日期改为 2026-09-16

## [2026-09-16] lint | 表格内 wikilink 管道符转义修复（撤销 2026-05-17 的错误修改）

- 问题：Obsidian 把表格行内的 `|` 视为列分隔符，`[[页面|别名]]` 会被切成两个单元格，链接断裂
- 正确写法是 `[[页面\|别名]]`，依据 Obsidian 官方文档表格一节 "Vertical bars in tables"
- 溯源：2026-05-17 的 lint（`断链修复（backslash转义…）`）将 `\|` 判为“转义错误”改为 `|`，方向相反，由此引入 33 处断链
- 本次修复 54 处，涉及 11 个文件：
  - analyses/八王之乱人物关系 8、analyses/八王之乱小抄 8、concepts/南朝宗室相残 8、sources/刘宋20名将 8
  - analyses/刘彧与刘昱时代 5、entities/宋孝武帝刘骏 5、concepts/四贵 4、concepts/汉武帝时代的悲剧将领 3
  - sources/元嘉北伐 2、sources/谢灵运 2、sources/风云南北朝：刘宋 1
- 顺带移除 analyses/八王之乱人物关系 第 67 行标题前的 Tab（Tab 缩进的 `###` 在严格解析下会变成代码块）
- 验证：全库表格按未转义 `|` 切分后，各行列数一致，无残留未转义管道符
- 注：`wiki/log.md` 自身的历史条目不改（append-only），本条即为更正记录

## [2026-09-17] lint | 修复原文路径并更正缺图误报

- 修复 6 个来源页的直引号／弯引号路径不匹配：america-wakes-up-ai-power、china-nationalist-spy-thriller、china-property-rotten-tail、china-tea-brands-america、why-china-worries-ai、延年-汉朝；同步修正正文来源链接与 frontmatter 的 sources 文件名。
- 将 sources/地图上的南北朝 的旧原文路径更正为实际存在的 `raw/articles/地图上的南北朝（14幅地图）.md`，同步更新 sources 字段。
- 更正此前对刘义隆时代、刘彧与刘昱时代、宋孝武帝刘骏等页面的缺图判断：旧检查器错误地给 `.jpg` 路径追加 `.md`。相关图片实际存在且已纳入版本控制；本次未改动、删除或下载任何 raw 文件。
- 校验区分带扩展名的资源、无扩展名的笔记、表格内转义别名和 basename wikilink；日志中的历史文字与代码示例不作为有效链接校验对象。
- 更新 7 个来源页及 index 的 updated 日期；仅修复引用，不改动正文史实或论点。

## [2026-09-17] cleanup | 根目录散落图片归位 raw/assets/

- 16 个散落在仓库根目录的媒体文件全部移入 `raw/assets/`：13 个 PNG、2 个 JPG、1 个 GIF，符合 CLAUDE.md／AGENTS.md 的媒体存放约定
- 同步更新 2 篇 raw 原文的 16 处 `![[...]]` 嵌入路径：
  - `raw/articles/美团 EvoCUA：基于经验进化学习刷新计算机操作智能体SOTA.md`（13 PNG + 1 GIF）
  - `raw/articles/八王之乱 - 维基百科，自由的百科全书.md`（2 JPG）
- 验证：移动前后各文件 sha256 一致（内容未变）；全库 `raw/assets` 图片嵌入均可解析；根目录已无散落媒体文件
- 说明：按用户明确要求改动了 `raw/` 下的嵌入路径——仅改路径，未改正文内容；移动前已预检无同名冲突

## [2026-09-17] ingest | 汉光武帝刘秀专题（三路调研）

- 新增 raw 资料三份（以《后汉书·光武帝纪》卷1上/卷1下为骨干，参《后汉书》诸列传、《东观汉记》佚文、《资治通鉴》卷38—44 等）：
  - `raw/articles/汉光武帝生平编年.md`（531 行）——十二阶段生平编年＋逐年对照表＋辨正与存疑
  - `raw/articles/汉光武帝制度与治国.md`（536 行）——退功臣进文吏、事归台阁、地方军事、柔道治国、儒学、谶纬、边疆、经济社会，逐条标【史料】/【研究】/【概括】
  - `raw/articles/汉光武帝史料与评价.md`（345 行）——史料清单、历代评价逐字引文、七大争议、A—E 可信度分级
- 新建来源页三份：`wiki/sources/汉光武帝生平编年.md`、`汉光武帝制度与治国.md`、`汉光武帝史料与评价.md`
- 新建实体页 `wiki/entities/汉光武帝刘秀.md`（主交付：生平主线、军事、制度治国、边疆、历代评价、辨正、史料）
- 更新 `wiki/index.md`（Sources 三条＋Entities 一条）、`wiki/overview.md`（新增主题与演化记录）
- 史料处理：三份原料对「正史记载／后世推算／学术争议／网络传说」分别标注；关键辨正包括封禅年份（中元元年56年，非建武三十年）、云台二十八将为明帝永平三年所定、「闭玉门以谢西域」系范晔论赞而非诏令、马援立铜柱不见于《后汉书》、白虎观会议属章帝朝
- 对流传说法做了溯源与证伪：毛泽东「三个最」评语无可信出处（最早见于2010年图书宣传语）；赵翼《廿二史札记》并无「光武帝不任功臣以吏事」条目（实际出处为《贞观政要》卷三马周疏）；托名诸葛亮的「光武之略非曹公所及」出处不明；《贞观政要》无「唐太宗论东汉崇儒」对应原文
- 待考清单保留于原料文件，涉及刘秀生日的公历对应、昆阳汉军总数、度田结局、《论衡》昆阳兵力异文、赵翼原文（OCR 单一来源待校）等

## [2026-09-17] query | 云台二十八将代表人物的选定与建档

- 应「从云台二十八将中选 2 个最有代表性的人物介绍」之问，选定 **邓禹**（帷幄型／云台之首）与 **冯异**（方面型／「大树将军」）
- 新建实体页 `wiki/entities/邓禹.md`、`wiki/entities/冯异.md`，引文据《后汉书》卷十六、卷十七原文（经维基文库 `?action=raw` 取得并逐条核对）
- 更新 `wiki/entities/汉光武帝刘秀.md`：用将方式一节补入两人链接与分工说明；关联区新增两条
- 更新 `wiki/index.md` Entities 新增两条
- 选定理由：① 两人同为读书人出身，对应赵翼「东汉功臣多近儒」；② 两人恰是一次直接交接——冯异因「大司徒邓禹不能定」三辅而代其西征，构成「帷幄」与「方面」两种分工的显例；③ 《后汉书》卷十七论曰「惟岑彭、冯异建方面之号」，仅点二人之名
