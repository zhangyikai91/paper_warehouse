# RSI：递归自我改进

RSI = Recursive Self-Improvement。以下区分直接相关和相邻基础工作；尚未全文精读或复现。

| 论文 | 改进对象 | 定位 | 原文 / PDF |
|---|---|---|---|
| Self-Refine: Iterative Refinement with Self-Feedback | 当前答案 | 推理时自反馈；不等于系统自改进 | [论文](https://arxiv.org/abs/2303.17651) / [PDF](https://arxiv.org/pdf/2303.17651) |
| Self-Taught Optimizer (STOP): Recursively Self-Improving Code Generation | 优化器代码 | 递归优化自身；不修改底层模型，论文区分于完整 RSI | [论文](https://arxiv.org/abs/2310.02304) / [PDF](https://arxiv.org/pdf/2310.02304) |
| Self-Rewarding Language Models | 模型及自评分能力 | 模型为训练提供奖励 | [论文](https://arxiv.org/abs/2401.10020) / [PDF](https://arxiv.org/pdf/2401.10020) |
| Darwin Godel Machine: Open-Ended Evolution of Self-Improving Agents | coding agent 自身代码 | 代码自修改、基准验证与候选档案演化 | [论文](https://arxiv.org/abs/2505.22954) / [PDF](https://arxiv.org/pdf/2505.22954) |

## 阅读顺序

Self-Refine → STOP → Self-Rewarding Language Models → Darwin Godel Machine。

## 研究问题（本仓库提出，非论文结论）

- 递归性：新版本是否更擅长产生后续改进，而非仅提高当前任务得分？
- 评价独立性：生成器和 grader 是否共享盲点？多个 grader 的漏错相关性多高？
- 奖励投机：是否利用测试不足、格式偏好或 judge 漏洞？
- 能力与偏好：分别测量任务能力、偏好得分和评分校准。
- 公平预算：固定 token、算力、评估次数，对比随机搜索、多采样和固定 agent。
- 样本外：开发集用于筛选，独立测试用于报告；检查跨任务迁移。
- 可重现性：保留每轮 diff、失败候选、评价记录与成本。

## 后续精读

逐篇核查可修改对象、反馈来源、选择机制、预算与独立测试。此处是初读框架，不是完整最新综述。
