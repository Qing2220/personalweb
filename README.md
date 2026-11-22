# personalweb

My personal website. A place to showcase my projects, thoughts, and continuous growth in computer science.

> 杨美玲 · f25011412 · 「开源创新思维」课程作业仓库

---

## 一、FDE 九阶段作业：门诊预约与分诊协作

按 FDE（Forward Deployed Engineer）九阶段流程，交付门诊场景的发现、调研、方案与提示词。
结构直接对齐线上训练站（`fde-discovery-lab`，开源来源 `kalyvask/fde-simulation @536ab61`）：**9 阶段 / 27 项任务 / 9 道关卡 / 六视角 36 问 / 7 维评分**。

### 1. 交付文件

| 文件 | 内容 |
|---|---|
| [技术方案.docx](<docs/技术方案.docx>) | **主交付**：16 章、40 张表，Word 可直接打开 |
| [技术方案.md](<docs/技术方案.md>) | 同源 Markdown：27 条需求追溯矩阵、架构、接口、权限、红线、部署、harness |
| [提示词.md](<docs/提示词.md>) | 10 条提示词（P0–P9），逐条挂到站点任务号与评分维度 |
| [00-九阶段基线.md](<docs/00-九阶段基线.md>) | 站点原样基线：阶段、任务、关卡、工具、36 问、评分维度 |

### 2. 过程文档（阶段 1–2）

| 文件 | 内容 |
|---|---|
| [01-业务挖掘.md](<docs/01-业务挖掘.md>) | S1-1 — S1-3：业务机会、指标基线、决策链 |
| [04-现状流程图.md](<docs/04-现状流程图.md>) | S2-2：现状泳道图与四条异常路径 |
| [02-调研记录.md](<docs/02-调研记录.md>) | S2-1：六视角 36 问、36 条证据、五处矛盾 |
| [02-调研记录.csv](<docs/02-调研记录.csv>) | 同批证据的机读版（36 行 × 9 列） |
| [03-现场调研分析.md](<docs/03-现场调研分析.md>) | S2-3：四来源收敛、证据台账、问题优先级 |
| [05-项目资料清单.md](<docs/05-项目资料清单.md>) | 原有 4 份资料：版本、位置、可信度、缺口 |
| [06-附录-课件与线上站点差异清单.md](<docs/06-附录-课件与线上站点差异清单.md>) | 课件 27 项任务与线上站的 7 条差异 |

### 3. 仓库结构

```
personalweb/
├─ README.md                      本文件
├─ LICENSE                        MIT
├─ docs/
│  ├─ 00-九阶段基线.md             站点原样结构
│  ├─ 01-业务挖掘.md
│  ├─ 02-调研记录.md / .csv
│  ├─ 03-现场调研分析.md
│  ├─ 04-现状流程图.md
│  ├─ 05-项目资料清单.md
│  ├─ 06-附录-课件与线上站点差异清单.md
│  ├─ 技术方案.md                 ← 主交付
│  ├─ 技术方案.docx               ← 主交付（Word）
│  └─ 提示词.md
├─ src/
│  └─ README.md                   代码占位：阶段 05 才动，当前不写业务代码
└─ f25011412-…-软件许可测试报告.docx/.pdf   上一轮课程作业
```

### 4. 技术栈与三条硬边界

`Python 3.11 · FastAPI · Ollama 本地部署 · 自建 harness`，不替换框架，不引入未要求的中间件：知识库用 SQLite 存索引，评测用 YAML 用例，日志用标准库。

1. 模型不在判定链上：号源结论由确定性规则算，模型只负责翻译与补全；
2. 关卡不由模型签核：模型只打分，具名确认人签结论；
3. 数据双层脱敏：入模型前一次、出站再一次。

### 5. 自查命令

```bash
# 27 个任务号是否齐全（期望 27）
grep -oE "S[1-9]-[1-3]" docs/技术方案.md | sort -u | wc -l
# 九阶段 id 是否齐全（期望 9）
grep -oE "opportunity|discovery|definition|solution|build|validation|pilot|handoff|operation" docs/技术方案.md | sort -u | wc -l
# 提示词是否 10 条（期望 10）
grep -cE "^## P[0-9] " docs/提示词.md
```

> 完成度如实标注：阶段 1 已完成；阶段 2 为 `24/36`（直接证据 24、间接 7、缺口 5），G2 只能「有条件通过」；阶段 3 未开始；阶段 4 方案待三方评审；阶段 5–9 未开始。

---

## 二、课程作业（上一轮）

《开源创新思维》平时作业报告 —— Apache Commons Text 软件许可合规检测

- [在线预览（PDF）](<f25011412-杨美玲-Apache Commons Text-软件许可测试报告.pdf>)
- [Word 原文件](<f25011412-杨美玲-Apache Commons Text-软件许可测试报告.docx>)

> 扫描对象：apache/commons-text（Apache-2.0）　工具：ScanCode Toolkit 32.5.0
