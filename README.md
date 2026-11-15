# 东方哲学方法论技能包（eastern-philosophy-methodology）

官方开源地址：<https://github.com/zengfr/eastern-philosophy-methodology>

从鬼谷子、孙子兵法、曾国藩、张居正、毛泽东五部可信原典中提炼**原子方法论单元**，
再通过**组合与派生**构建面向具体场景的应用方法，
形成"原典 → 原子层 → 应用层"的两层知识体系。

**本包是方法论技能包，不是文献库、不是语录集。**

## 架构（严格单向依赖）

```
sources/            原稿层：五源选录，唯一取证现场（只增不改正文）
    ↓ 提炼（必须锚定原文）
atomic-skills/      原子层：最小不可分方法论单元（查 _registry.md）
    ↓ 组合 + 派生（只引用原子 id@version）
application-skills/ 应用层：场景 × 组合公式（查 _registry.md）
```

- **原子层**不解决具体场景问题，只承载"一条可独立成立的方法论"；
- **应用层**不产生新方法论，只做原子技能的编排；
- 任何技能文件满足三段可追溯链：`应用 Skill 步骤 → 原子 Skill id@version → sources/ 原文出处`。

## 可信来源白名单

一切原子 Skill 的方法论依据，只能来自以下五个来源的原稿
（存于 `sources/{源编号小写}/`）：

| 源编号 | 来源 | 授权范围 |
|--------|------|----------|
| GZ | 鬼谷子 | 《鬼谷子》原著文本 |
| SZ | 孙子兵法 | 《孙子兵法》十三篇原文 |
| ZGF | 曾国藩 | 曾国藩家书、日记、奏稿、文集原稿 |
| ZJZ | 张居正 | 张居正奏疏、书信、著述原稿 |
| MZD | 毛泽东 | 毛泽东选集、文集、军事文选 |

白名单之外的任何思想体系不得作为方法论来源；外部知识只允许作为表达语言。

## 使用方式

1. 查 `application-skills/_registry.md` 匹配场景，命中后按应用 Skill 的组合公式执行；
2. 未命中时查 `atomic-skills/_registry.md` 直接取用原子（遵循其适用条件与边界）；
3. 执行前以 MZD-03（实事求是）逐原子校验前提假设是否成立；
4. 使用后依 `templates/feedback.template.md` 写 `evolution/feedback/F-xxxx.md` 留痕。

详见 `SKILL.md`（技能包入口）与 `agents.md`（规范宪章，最高规范）。

## 自进化机制

技能进化为 **Agent 驱动、人工把关的受控进化协议**，六段流水线：

```
收集 → 提案 → 校验 → 评审（人工门）→ 合并 → 回归
```

血统隔离：反馈不能直接改写原子层；原子层任何变更必须重新锚定 `sources/` 原文。
`sources/` 的完备化由独立采集子流程驱动（只由原典完备性驱动，禁止反向取证）。

## 目录结构

```
├── agents.md              # 规范宪章（最高规范）
├── SKILL.md               # 技能包入口与使用说明
├── sources/               # 原稿层（五源，只增不改正文）
├── atomic-skills/         # 原子层（_registry.md 注册表）
├── application-skills/    # 应用层（_registry.md 注册表）
├── evolution/             # 进化机制（feedback / proposals / log.md）
└── templates/             # 模板（原子 / 应用 / 提案 / 反馈）
```

## 许可证

[MIT](LICENSE) © 2026 zengfr 曾繁荣
