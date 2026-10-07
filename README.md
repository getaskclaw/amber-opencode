[English](README.en.md) · 简体中文

# amber-opencode

> ⚠️ **更正（2026-10-02，另一项）**：防御轴的一案 A-d511f9e8 在所有车道上改记 NA（考场判的不是考生交付的文件，判分还要求了题面没写的事）。分母不变，**过案数不变**，每条道的总分都带 `'`。本仓各期成绩表里这一格请按 NA 读，其余内容保留原样，以[更正声明](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02-a-d511f9e8.md)为准。

> ⚠️ **更正（2026-10-02）**：以下考卷在作答时越出考卷、接触了判分材料，不计胜负。deepseek-flash @ OpenCode Go 有 2 张卷（A-24bcf707、A-8d4bc770）改记 NA，榜上成绩 17/24 → **15'/24**。原因是考场隔离缺陷，责任在我们。本页其余内容保留原样，以[更正声明](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-02.md)为准。

> **2026-10-07 更新**：A-cdc3d11a（审查）：某个审查案上，判分器把一条格式正确的发现里的每个小点都当成一条未经证实的独立断言，又把答案清单之外的真实缺陷当成误报，所以一份正确、格式规范的审查报告也到不了及格线；该案在所有车道上挂起，分母不变，待判分器和考场修好、重新补考后再定。本车道（deepseek-flash @ OpenCode Go）这一格改记 NA（挂起），不记负；该案由负改记 NA 的车道共 27 条，没有重新考试。过案数不变（榜上 15'/24）；负案 6→5，NA 3→4；审查轴 1/2 不变、另有 1 个 NA。[W37 期文](results/2026-W37.md)矩阵里 OpenCode Go 列该格已照此改记。见[规范仓 2026-10-07 的更正（A-cdc3d11a）](https://github.com/getaskclaw/amber/blob/main/docs/corrections-2026-10-07-a-cdc3d11a.md)。

用私有题库 **AMBER** 实测 OpenCode Go（opencode.ai/zen/go）在售模型，只公开结果，不公开题目。

## 这是什么

- 「道」= 同一个模型名在不同家的卖场/接口；「案」= 一道题，「卷」= 一场考试记录（一案多卷 = 一道题的几个变体场次）。

- 每期一篇 `results/YYYY-Www.md`：同题、同 harness（跑考试并记分的程序），对目标模型跑全库；同名模型跨厂商并排。
- 一期固定报告：题集规模与哈希、每案找茬分（d2 分，我们的打分，算法不公开）与通过/失败、终端终态（程序跑完时的退出状态）、token 用量（若车道上报）与时延、环境指纹、按证据纪律写的定性裁决。
- 题目、oracle（判分器）、transcript（答题全过程记录）、中间产物**永不公开**（见下「发布纪律」）。
- 姐妹仓：[amber-deepseek](https://github.com/getaskclaw/amber-deepseek)（DeepSeek 官方道）、[amber-commandcode](https://github.com/getaskclaw/amber-commandcode)（CommandCode 道）、[amber-gpt](https://github.com/getaskclaw/amber-gpt)、[amber-crof](https://github.com/getaskclaw/amber-crof)、[amber-ollama](https://github.com/getaskclaw/amber-ollama)、[amber-devin](https://github.com/getaskclaw/amber-devin)、[amber-workbuddy](https://github.com/getaskclaw/amber-workbuddy)（WorkBuddy ACP 道）、[amber-doubao](https://github.com/getaskclaw/amber-doubao)、[amber-goldenpotato](https://github.com/getaskclaw/amber-goldenpotato)、[amber-kimi](https://github.com/getaskclaw/amber-kimi)、[amber-stepfun](https://github.com/getaskclaw/amber-stepfun)。本仓的对照轴是**同名模型跨厂商对决**——同一个模型名在 OpenCode Go / CommandCode / DeepSeek 官方道上可能是不同端点，跨仓引用一律带日期与档位声明。
- AMBER 是 agentic 实战题库（施工/运维/审查/视觉/需求漂移——题中要求中途变化），规范与制题工具见 [getaskclaw/amber](https://github.com/getaskclaw/amber)；考题本体私有。

## 发布纪律（红线）

1. 只发：分数与聚合、token 用量（若车道上报）、速度、定性裁决。
2. 永不发：题目内容、oracle/判分器、transcript、考生工作区、任何能复原题面的中间产物。
3. 每期必钉：模型 ID、effort 档（思考力度档位）、日期（UTC）、harness 版本、每案内容哈希（bundle_sha，每题内容的哈希指纹）。哈希用于对照 [amber](https://github.com/getaskclaw/amber) 的公开哈希清单，自证题集未变。
4. 案号与题目结构属私有面：公开结果里案例只用稳定别名（A-xxxxxxxx，哈希派生）+ bundle 哈希作句柄；内部案号、变体名、题目描述永不出现。
5. 基调：这是社区实测，不是对厂商的攻击。数据说话，措辞克制。

## 一个方法论前提

同名模型、同 provider，两次跑也可能不同分——推理参数、负载、服务端版本都在漂；转发/聚合道还隔着一层上游路由，同名不一定是同一个端点。所以这里的一切结论都带日期与档位，且定期重测。单日数字是快照，不是定律。

## 结果索引

| 期 | 内容 | 结论 |
|---|---|---|
| [2026-W37](results/2026-W37.md) | deepseek-flash（V4.1 GA）全库首考（23 案，GA 当日） | 成绩与定性裁决见期文；同名跨厂商三方对拍同为真 v4.1；施工/OPS 强，no-tools 场景有「脑内工具调用」老病 |
| [2026-W38 更正特刊](results/2026-W38-correction.md) | W38 全库复核:本仓改判 0 格 · 挂起 3 格 | W37 ocgo 列 3 格挂起;16/23 可能上移 |

## 免责

与 OpenCode、DeepSeek（深度求索）无任何隶属/赞助关系。分数是特定周、特定档位的快照，不构成采购建议。
