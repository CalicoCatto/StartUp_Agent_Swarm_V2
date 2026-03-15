# 创业Idea Agent Swarm - 项目指令

## 项目概述
这是一个由多个专业Agent组成的创业Idea生成与分析团队。用户提供参考材料（文章、痛点描述、行业趋势）→ 系统主动提出创业idea → 再对这些idea进行全方位分析，最终输出一份详细报告和一份简要总结报告。

## 工作流程（5轮）

```
轮次0: 参考材料解析 (startup-swarm)
  接收文章/痛点/趋势 → 结构化为"研究简报"

轮次1: 机会扫描 (并行) — Phase A
  domain-expert [扫描模式]: 行业痛点、结构性变化、新兴机会
  market-analyst [扫描模式]: 市场空白、未满足需求、竞争白地
  ux-researcher [扫描模式]: 用户痛点、未被服务的需求、行为变化

轮次2: Idea生成 — Phase A
  idea-generator: 综合轮次1结果 → 产出3-5个创业idea → 排序推荐

轮次3: 深度分析 (并行) — Phase B (针对选中的idea)
  tech-architect / business-model / growth-hacker
  domain-expert [分析模式] / market-analyst [分析模式] / ux-researcher [分析模式]

轮次4: 综合评估 (并行) — Phase B
  investor-advisor / legal-compliance

轮次5: 汇总报告 (orchestrator/startup-swarm)
```

## Agent角色一览

| Agent | 角色 | 职责 | 模式 |
|-------|------|------|------|
| startup-swarm | 一键入口 | 自动调度全流程（生成+分析） | - |
| orchestrator | 主协调员 | 分解任务、调度Agent、汇总结论 | - |
| idea-generator | 创意策略师 | 综合机会信号，生成3-5个创业idea | - |
| market-analyst | 市场分析师 | 市场规模、竞争格局、趋势分析 | 扫描/分析双模式 |
| tech-architect | 技术架构师 | 技术可行性、架构方案、技术壁垒 | - |
| business-model | 商业模式专家 | 盈利模式、定价策略、商业可行性 | - |
| ux-researcher | 用户体验研究员 | 用户画像、需求验证、产品体验设计 | 扫描/分析双模式 |
| investor-advisor | 投资人视角 | 融资可行性、估值、投资吸引力 | - |
| legal-compliance | 法务合规顾问 | 法律风险、合规要求、知识产权 | - |
| growth-hacker | 增长黑客 | 获客策略、增长飞轮、营销方案 | - |
| domain-expert | 行业领域专家 | 行业深度洞察、产业链分析、行业趋势 | 扫描/分析双模式 |

## 评分权重

| 维度 | 权重 |
|------|------|
| **创新性** | **10%** |
| 市场机会 | 18% |
| 用户需求 | 14% |
| 技术可行性 | 13% |
| 商业模式 | 13% |
| 增长潜力 | 10% |
| 投资吸引力 | 9% |
| 行业机会 | 8% |
| 法律合规 | 5% |

## 输出规范
- 所有报告使用中文
- 详细报告包含：Idea生成过程 + 深度分析 + 备选Ideas简析
- 简要报告控制在2000字以内，突出核心结论和行动建议
- 报告保存到 `output/` 目录

## 使用的工具
- Read: 读取用户输入文件
- Write: 输出报告文件
- WebSearch: 搜索市场数据和行业信息
- Bash: 执行辅助命令
