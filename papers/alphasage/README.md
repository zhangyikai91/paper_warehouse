# AlphaSAGE

**AlphaSAGE: Structure-Aware Alpha Mining via GFlowNets for Robust Exploration**

作者：Binqi Chen, Hongjun Ding, Ning Shen, Taian Guo, Jinsheng Huang, Luchen Liu, Ming Zhang。

[摘要](https://arxiv.org/abs/2509.25055) | [PDF v2](https://arxiv.org/pdf/2509.25055v2) | [全文](https://arxiv.org/html/2509.25055v2) | [官方代码](https://github.com/BerkinChen/AlphaSAGE)

## 核心思路

生成一组有预测力且具多样性的公式化 alpha。方法结合 AST 的 RGCN 编码、GFlowNet 搜索以及结构和新颖性等奖励。作者报告优于比较基线；本仓库尚未复现。此笔记对应 arXiv v2。

## GFlowNet 入口

一般原理：理想条件下，终端对象的采样概率 P(x) = R(x) / Z。它学习偏向高奖励对象的分布，可以覆盖多个模式。实际覆盖依赖奖励和训练效果；表达式多样不直接保证收益低相关。

## 复现检查点（本仓库提出，非论文结论）

- 结构不同的表达式可能产生相同信号：分别检查结构、信号和收益相关性。
- 检查新颖性奖励是否鼓励无效复杂度；开展去除该奖励的消融。
- 核对 rolling 特征、标签、标准化、股票池与复权数据的信息时点。
- 因子筛选、奖励超参数和组合权重只用训练与验证集；冻结测试集。
- 固定数据、算子、候选评估次数与算力预算，对比随机搜索、GP、PPO 和 GFlowNet。
- 补充换手、交易成本、行业与风格暴露、容量评估。
- 跨种子和时间窗口报告分布，保留失败候选与搜索次数。

## 精读顺序

1. 第 3 节：核对状态、动作、奖励、训练损失。
2. 官方代码：核对图编码、合法动作与因子池更新。
3. 第 4 节和附录：核对数据切分、基线、消融和成本假设。

状态：初读导读，尚未逐式审读、代码审计或实验复现；不抄录未经核对的绩效数字。
