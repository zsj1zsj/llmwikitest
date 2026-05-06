# Wiki Log

Append-only chronological record of all wiki activity.

Format: `## [YYYY-MM-DD] <operation> | <description>`

Operations: `ingest` | `query` | `lint` | `init`

---

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
