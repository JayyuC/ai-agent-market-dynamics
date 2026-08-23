# AI Agent Market Dynamics

> 基于大语言模型智能体的资产市场动态模拟与均衡稳定性研究

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![SSRN](https://img.shields.io/badge/SSRN-Paper-red.svg)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=XXXXX)

## 论文

- **SSRN**: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7337058
- **arXiv**: 投稿中（pending endorsement）

## 项目简介

传统经济学模型依赖代表性理性主体假设，难以刻画真实市场中的异质预期、适应性学习和非均衡动态。本项目构建了一个基于大语言模型（LLM）的人工智能经济主体模拟框架，将三类具有不同学习机制的主体——理性主体、Q-learning强化学习主体、LLM自然语言推理主体——置于同一资产市场环境中，通过非线性动力系统方法推导市场均衡的局部稳定性条件与分岔阈值，并通过仿真实验揭示AI主体学习机制对市场波动率、泡沫频率和路径依赖性的影响。

## 三类经济主体

| 主体类型 | 决策机制 | 学习能力 |
|---|---|---|
| **Rational Agent** | 基于基本面价值的阈值交易策略 | 无（已知模型） |
| **Q-Learning Agent** | 基于历史收益的强化学习，softmax策略选择 | 有（Q值更新） |
| **LLM Agent** | 基于自然语言推理、叙事形成和记忆积累的自适应决策 | 有（隐式学习+周期性反思） |

## 核心发现

1. **市场稳定性差异**：LLM主体市场呈现显著更高的价格偏离（11.4% vs 理性1.2%）、波动率（3.2% vs 0.8%）和泡沫-崩溃频率（18.7% vs 0%）

2. **非单调混合效应**：混合种群中仅10-20%的LLM主体即可显著 destabilize 市场；但当LLM主体份额超过50%后，异质的反向交易行为部分恢复稳定性

3. **分岔与混沌**：Q-learning学习率超过临界阈值时，系统经历倍周期分岔，从稳定收敛过渡到周期振荡乃至混沌动力学

4. **路径依赖**：相同基本面下，初始价格扰动可导致系统收敛于不同吸引子——基本面均衡、持续泡沫、或系统性崩溃

## 理论框架

市场价格动态由离散时间非线性映射描述：

$$p_{t+1} = F(p_t, \boldsymbol{\theta})$$

其中 $\boldsymbol{\theta}$ 参数化主体学习机制的分布。通过对基本面价格不动点 $p^*$ 的 Jacobian 矩阵特征值分析，推导得到局部稳定性的 Jury 条件，以及学习率参数变化引发的 flip 分岔条件。

## 项目结构

