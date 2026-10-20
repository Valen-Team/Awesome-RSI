<a id="awesome-rsi"></a>

<div align="center">

# ♾️ Awesome RSI

**递归自我改进 · 从经验积累到系统修改与模型学习**

收录 AI 自我改进相关的论文、代码、基准与模型，关注经验积累、智能体软件修改和模型权重学习。

[English](README.md) · 简体中文

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Updated](https://img.shields.io/badge/Updated-2026--10--20-2563eb?style=flat-square)
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-16a34a?style=flat-square)](#contributing)

[📄 论文](#papers) · [🛠️ 项目](#projects) · [📊 基准、评测与数据集](#benchmarks)

[🧠 模型与检查点](#models) · [🧭 综述](#surveys) · [🏢 公司与实验室](#companies)

</div>

欢迎通过 Issue 或 Pull Request 推荐论文、项目、基准、数据集和模型，也欢迎作者提交自己的工作。

条目说明改了什么、依据什么反馈修改，以及有哪些证据。日期默认指首次公开时间；软件发布或后续更新会另行注明。

---

<a id="papers"></a>

## 📄 论文

| 🧩 经验积累 | 🛠️ 系统修改 | 🧠 模型参数 |
|:---:|:---:|:---:|
| 提示词 · 上下文 · 技能 · 记忆 | 运行框架 · 工具 · 智能体架构 | 微调 · 强化学习 · 自博弈 |
| [从过往经验中学习 ↓](#experience) | [改进智能体的工作方式 ↓](#systems) | [通过更新权重学习 ↓](#parameters) |

论文按主要改进机制分类；混合方法涉及的其他机制会在说明中标出。

<a id="experience"></a>

### 🧩 1. 经验积累

通过可复用的提示词、上下文、技能和记忆改善后续表现。

| 日期 | 论文 | 主要方法 | 资源 |
|---|---|---|---|
| 2026-10-13 | [EmbodiedEvo: Self-Evolving Coding Agent For Physical Intelligence](https://arxiv.org/abs/2610.18867) | 把机器人交互经验整理成代码技能和文字经验，再冻结这些内容，交给未见场景中的新智能体使用；模型权重保持不变。 | [💻 代码](https://github.com/Einsia/EmbodiedEvo) |
| 2026-09-08 | [SE-GoS: Self-Evolving Graph-of-Skills for Skill Library at Scale](https://arxiv.org/abs/2609.08228) | 从执行轨迹更新技能图的拓扑、边权和检索描述，模型、技能内容与检索算法保持不变。 | 📄 论文 |
| 2026-08-25 | [Recuris: Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses](https://arxiv.org/abs/2608.24876) | 利用经过验证的状态和结构化失败反馈，更新工作记忆与经验技能；基础模型和外层元智能体保持不变。 | [💻 代码](https://github.com/Gen-Verse/Recuris) |
| 2026-08-15 | [Evo-Harness: Context-to-Harness Skill Compilation for Self-Evolving Agents](https://arxiv.org/abs/2608.15071) | 围绕固定的任务求解器，把执行上下文编译成可复用的跨任务技能和任务类型技能。 | [💻 代码与技能](https://github.com/A-EVO-Lab/a-evolve/tree/release/evo-harness) |
| 2026-03-19 | [Memento-Skills: Let Agents Design Agents](https://arxiv.org/abs/2603.18743) | 通过反思学习积累可复用的 Markdown 技能，基础模型保持固定，技能路由器通过学习获得。 | [💻 代码](https://github.com/Memento-Teams/Memento-Skills) |
| 2025-10-06 | [Agentic Context Engineering: Evolving Contexts for Self-Improving Language Models](https://arxiv.org/abs/2510.04618) | 通过生成、反思和增量整理，持续更新上下文中的操作手册。 | [💻 代码](https://github.com/ace-agent/ace) |
| 2025-07-25 | [GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning](https://arxiv.org/abs/2507.19457) | 根据执行反馈和反思改进提示词，选出能力互补的候选方案。 | [💻 代码](https://github.com/gepa-ai/gepa) |
| 2023-03-20 | [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) | 利用语言反馈和情景记忆改善后续尝试，不更新模型权重。 | 📄 论文 |

<a id="systems"></a>

### 🛠️ 2. 系统修改

修改智能体运行框架（harness）、工具、可执行代码，以及负责生成后续智能体的改进机制。

| 日期 | 论文 | 主要方法 | 资源 |
|---|---|---|---|
| 2026-10-15 | [MetaShare: Failure-Aware Collective Self-Improvement for Open-Ended Agents](https://arxiv.org/abs/2610.21887) | 跨智能体谱系共享成功与失败的修改及性能增减记录；审查器在不查看具体任务的情况下，补充尚未充分探索的策略类别。 | 📄 论文 |
| 2026-10-09 | [Harness²: Recursive Agent Harnessing for an Open World](https://arxiv.org/abs/2610.14224) | 在当前任务中提出并测试 harness 修改，再复用经验，更新面向后续任务的改进框架；模型权重保持不变。 | [💻 代码](https://github.com/google-research/harness2) |
| 2026-09-29 | [SelfSearch: Reward-Free Search for Self-Improving Agents](https://arxiv.org/abs/2609.37968) | 利用早先自我修改的记录，调整指令、工具和执行流程；搜索期间不使用下游任务奖励。 | 📄 论文 |
| 2026-09-17 | [SoL-Pi: Recursively Scaling Auto-Research Loops for Efficient Agent Harness](https://arxiv.org/abs/2609.20519) | 搜索降低 token 开销的 harness 修改；发布的 Pi 扩展实现了筛选出的工具执行、观测处理、上下文管理和委托阅读机制。 | [💻 代码](https://github.com/NVlabs/SoL-Pi) |
| 2026-08-25 | [Metaⁿ: Recursive Self-Improvement through Emergent Depth](https://arxiv.org/abs/2608.24735) | 反复应用固定的元操作，从代码和轨迹中构建多层可执行的改进机制。 | [💻 代码](https://github.com/minnesotanlp/meta-n) |
| 2026-08-07 | [Mendel Gödel Machine: Recursive Self-Improving Coding Agents via Comparative Evolution](https://arxiv.org/abs/2608.07645) | 通过跨任务比较和跨谱系组合，演化编码智能体。 | [💻 代码](https://github.com/RealLcz/MGM) |
| 2026-07-17 | [Recursive Harness Self-Improvement](https://arxiv.org/abs/2607.15524) | 根据先前 harness 版本的反馈，改进以提示词描述的智能体执行循环。 | 📄 论文 |
| 2026-06-04 | [Evolving Agents in the Dark: Retrospective Harness Optimization via Self-Preference](https://arxiv.org/abs/2606.05922) | RHO 利用任务回放和自我偏好选择 harness 更新，优化期间不使用标准答案评分。 | [💻 代码](https://github.com/wbopan/retro-harness) |
| 2026-05-11 | [Continual Harness: Online Adaptation for Self-Improving Foundation Agents](https://arxiv.org/abs/2605.09998) | 在持续交互中调整提示词、子智能体、技能和记忆；另一个共同学习扩展还更新模型权重。 | [💻 代码](https://github.com/sethkarten/continual-harness) |
| 2026-03-30 | [Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052) | 利用历史候选方案、评测分数和执行轨迹，优化可执行的 harness。 | [💻 代码](https://github.com/stanford-iris-lab/meta-harness) |
| 2026-03-19 | [Hyperagents](https://arxiv.org/abs/2603.19461) | 同时修改任务智能体，以及负责产生后续改进的元智能体。 | [💻 代码与日志](https://github.com/facebookresearch/Hyperagents) |
| 2025-11-17 | [Live-SWE-agent: Can Software Engineering Agents Self-Evolve on the Fly?](https://arxiv.org/abs/2511.13646) | 从仅含 bash 的简化框架出发，在解决软件问题时创建和修改工具。 | [💻 代码](https://github.com/OpenAutoCoder/live-swe-agent) |
| 2025-10-24 | [Huxley-Gödel Machine: Human-Level Coding Agent Development by an Approximation of the Optimal Self-Improving Machine](https://arxiv.org/abs/2510.21614) | 按后代的预期产出选择自我修改的智能体谱系，而非仅按当前任务得分。 | [💻 代码](https://github.com/metauto-ai/HGM) |
| 2025-05-29 | [Darwin Godel Machine: Open-Ended Evolution of Self-Improving Agents](https://arxiv.org/abs/2505.22954) | 维护持续演化的编码智能体档案；智能体在固定基础模型之上修改并评测自身代码。 | [💻 代码与日志](https://github.com/jennyzzt/dgm) |
| 2025-04-21 | [A Self-Improving Coding Agent](https://arxiv.org/abs/2504.15228) | SICA 根据执行反馈，迭代改写完整的编码智能体代码库。 | [💻 代码](https://github.com/MaximeRobeyns/self_improving_coding_agent) |

<a id="parameters"></a>

### 🧠 3. 模型参数

通过更新权重改进模型，包括自行生成训练数据、演化课程、学习反馈和强化学习。

| 日期 | 论文 | 主要方法 | 资源 |
|---|---|---|---|
| 2026-10-16 | [Self-Evolving Coding Agents via Harness-Policy Optimization](https://arxiv.org/abs/2610.22791) | Self-HPO 交替执行由策略模型提出的 harness 搜索，以及在选定 harness 下的强化学习；训练中的失败指导下一轮搜索。 | 📄 论文 |
| 2026-10-08 | [Recursive Self-Improvement through Multi-Agent Self-Supervision](https://arxiv.org/abs/2610.12176) | MASS 交替执行自评工作流搜索和多智能体轨迹上的监督训练，更新后的模型参与下一轮循环。 | 📄 论文 |
| 2026-10-02 | [Recursive Self-Improvement in Unified Multimodal Models](https://arxiv.org/abs/2610.03002) | 用可执行程序验证生成的图表数据，再逐轮训练图像生成、视觉理解和程序编写能力。 | 📄 论文 |
| 2026-10-01 | [Harness Annealing: Learning to Act with Less External Control](https://arxiv.org/abs/2610.01235) | 从外部控制逐步减弱的教师轨迹中学习控制决策，并对每个模型检查点分别评测减少运行时支持后的表现。 | 📄 论文 |
| 2026-09-15 | [ScienceBuddy: Recursive-in-Recursive Self-Improvement for Interactive Scientific Agents](https://arxiv.org/abs/2609.17523) | 交替执行 harness 演化与模型强化学习。公开实验使用固定任务集和验证器辅助反馈；在线科研工作台另有演示。 | [💻 研究代码](https://github.com/Gen-Verse/ScienceBuddy) |
| 2026-09-02 | [SafeEvolve: Harness-Policy Co-Evolution from Agent Experience for Safety Alignment](https://arxiv.org/abs/2609.02786) | 将安全提示词、技能库的演化，与 SFT 和 GRPO 策略更新结合。 | [💻 代码](https://github.com/MaoPopovich/SafeEvolve) |
| 2026-09-02 | [APEx: Distillation of Agent Procedural Experience for Adaptive Deep Research Question Answering](https://arxiv.org/abs/2609.02253) | 把流程经验提炼成技能，同时训练执行器、经验提炼器和规划器，并支持测试时规划器适应。 | [💻 代码](https://github.com/J-Ding519/APEx) |
| 2026-08-25 | [CAFE: Self-Improving Search Agents Need Co-Evolving Feedback](https://arxiv.org/abs/2608.24794) | 通过在线强化学习和反馈偏好优化，共同训练搜索智能体与评审器。 | 📄 论文 |
| 2026-08-19 | [SPADE: Self-Play in Adaptive Synthetic Executable Environments](https://arxiv.org/abs/2608.19197) | 让可执行环境设计器与推理智能体通过自博弈共同训练，并使用文档依据和累积的环境记忆。 | [💻 代码](https://github.com/spade-rl/spade) · [🤗 权重](https://huggingface.co/collections/spade-rl/spade-checkpoints) |
| 2026-08-05 | [EvoHarness-RL: Learning Self-Evolving Runtime Harness for Long-Horizon LLM Agents](https://arxiv.org/abs/2608.05446) | 通过 SFT 和考虑开销的 GRPO，学习管理 Belief、Progress、Experience 工作区的策略。 | 📄 论文 |
| 2026-05-11 | [G-Zero: Self-Play for Open-Ended Generation from Zero Data](https://arxiv.org/abs/2605.09959) | 把提示引起的概率变化用作内在训练信号，共同演化提议模型与生成模型。 | [💻 代码](https://github.com/Chengsong-Huang/G-Zero) |
| 2026-02-09 | [SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234) | 在强化学习智能体策略的同时，演化分层技能库。 | [💻 代码](https://github.com/aiming-lab/SkillRL) · [🤗 示例权重](https://huggingface.co/Jianwen/Alfworld-7B-RL) |
| 2025-08-07 | [R-Zero: Self-Evolving Reasoning LLM from Zero Data](https://arxiv.org/abs/2508.05004) | 通过自行生成的推理问题和估计的学习难度，共同演化挑战者与求解器模型。 | [💻 代码](https://github.com/Chengsong-Huang/R-Zero) |
| 2025-06-12 | [Self-Adapting Language Models](https://arxiv.org/abs/2506.10943) | SEAL 学习生成微调数据和适应指令，以下游学习效果作为反馈。 | [💻 代码与数据](https://github.com/Continual-Intelligence/SEAL) |
| 2025-05-06 | [Absolute Zero: Reinforced Self-play Reasoning with Zero Data](https://arxiv.org/abs/2505.03335) | 通过可执行、可验证的自博弈训练任务提议和推理，无需人工整理的后训练题集。 | [💻 代码](https://github.com/LeapLabTHU/Absolute-Zero-Reasoner) · [🤗 权重](https://huggingface.co/collections/andrewzh/absolute-zero-reasoner) |
| 2025-04-22 | [TTRL: Test-Time Reinforcement Learning](https://arxiv.org/abs/2504.16084) | 利用测试时的共识奖励，在无标签输入上更新模型权重。 | [💻 代码](https://github.com/PRIME-RL/TTRL) |
| 2024-01-18 | [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) | 通过自奖励训练，迭代改善回答生成和偏好判断。 | 📄 论文 |
| 2022-03-28 | [STaR: Bootstrapping Reasoning With Reasoning](https://arxiv.org/abs/2203.14465) | 反复生成、筛选模型推理过程，并据此训练模型。 | 📄 论文 |

[↑ 返回顶部](#awesome-rsi)

---

<a id="projects"></a>

## 🛠️ 项目

用于构建自我改进智能体和自动研究流程的实现与框架。单篇论文的实现链接见上文。

### 🔁 智能体与学习循环

| 参考日期 | 项目 | Stars | 可查看的内容 |
|---|---|---|---|
| 2026-10-13，论文 | [EmbodiedEvo](https://github.com/Einsia/EmbodiedEvo) | ![Stars](https://img.shields.io/github/stars/Einsia/EmbodiedEvo?style=flat-square) | 机器人控制代码、可复用技能与经验，以及分开的练习和测试场景；需自行配置模拟器。 |
| 2026-09-15，论文 | [ScienceBuddy](https://github.com/Gen-Verse/ScienceBuddy) | ![Stars](https://img.shields.io/github/stars/Gen-Verse/ScienceBuddy?style=flat-square) | 交替执行 harness 搜索与 GRPO 的简化科研智能体实验；不包含在线产品的完整源码。 |
| 2026-09-02 | [SafeEvolve](https://github.com/MaoPopovich/SafeEvolve) | ![Stars](https://img.shields.io/github/stars/MaoPopovich/SafeEvolve?style=flat-square) | 安全 harness 与策略的共同演化，附训练脚本和小规模实验资源。 |
| 2026-08-25 | [Metaⁿ](https://github.com/minnesotanlp/meta-n) | ![Stars](https://img.shields.io/github/stars/minnesotanlp/meta-n?style=flat-square) | 可执行的多层元改进机制和研究命令行工具。 |
| 2026-08-25 | [Recuris](https://github.com/Gen-Verse/Recuris) | ![Stars](https://img.shields.io/github/stars/Gen-Verse/Recuris?style=flat-square) | 工作记忆、经验技能，以及受约束的记忆演化。 |
| 2026-08-24 | [Prime Agent](https://github.com/PrimeIntellect-ai/prime-agent) | ![Stars](https://img.shields.io/github/stars/PrimeIntellect-ai/prime-agent?style=flat-square) | 持久化 REPL、递归子智能体和持续 harness 适应。 |
| 2026-08-19 | [SPADE](https://github.com/spade-rl/spade) | ![Stars](https://img.shields.io/github/stars/spade-rl/spade?style=flat-square) | 环境设计器与智能体自博弈，附已发布检查点和环境语料。 |
| 2026-03-19 | [Hyperagents](https://github.com/facebookresearch/Hyperagents) | ![Stars](https://img.shields.io/github/stars/facebookresearch/Hyperagents?style=flat-square) | 同时修改任务智能体和元智能体，附实验日志。 |
| 2026-02-09 | [SkillRL](https://github.com/aiming-lab/SkillRL) | ![Stars](https://img.shields.io/github/stars/aiming-lab/SkillRL?style=flat-square) | 将技能库演化与智能体强化学习结合。 |
| 2025-06-12 | [SEAL](https://github.com/Continual-Intelligence/SEAL) | ![Stars](https://img.shields.io/github/stars/Continual-Intelligence/SEAL?style=flat-square) | 自行生成的适应数据和更新指令。 |
| 2025-05-29 | [DGM](https://github.com/jennyzzt/dgm) | ![Stars](https://img.shields.io/github/stars/jennyzzt/dgm?style=flat-square) | 可自我修改的编码智能体档案及演化轨迹。 |

### 🔬 自动研究与优化框架

| 参考日期 | 项目 | Stars | 可查看的内容 |
|---|---|---|---|
| 2026-10-09，论文 | [Harness²](https://github.com/google-research/harness2) | ![Stars](https://img.shields.io/github/stars/google-research/harness2?style=flat-square) | 当前任务中的 harness 修改，以及可复用的改进框架，附专业任务评测脚本。 |
| 2026-09-18，软件发布 | [Gear](https://github.com/rsi-gear/gear) | ![Stars](https://img.shields.io/github/stars/rsi-gear/gear?style=flat-square) | 利用执行轨迹和基准反馈优化智能体的提示词、工具与工作流，跨轮次保留有版本记录的 harness。 |
| 2026-09-17，论文 | [SoL-Pi](https://github.com/NVlabs/SoL-Pi) | ![Stars](https://img.shields.io/github/stars/NVlabs/SoL-Pi?style=flat-square) | Pi 扩展，实现自动 harness 搜索选出的效率优化机制，附配置和保留证据的日志处理。 |
| 2026-08-28 | [Automated Alignment Researcher](https://github.com/YuehHanChen/automated_alignment_researcher) | ![Stars](https://img.shields.io/github/stars/YuehHanChen/automated_alignment_researcher?style=flat-square) | 对齐研究的 harness、评测与监控，可连接用户提供的训练器。 |
| 2026-08-11 | [ComfyResearch](https://github.com/MetaCircleAI/ComfyResearch) | ![Stars](https://img.shields.io/github/stars/MetaCircleAI/ComfyResearch?style=flat-square) | 以图为基础的实验工作台，用于检查和修改学习实验。 |
| 2026-05-19，扩展论文 | [GEPA / optimize_anything](https://github.com/gepa-ai/gepa) | ![Stars](https://img.shields.io/github/stars/gepa-ai/gepa?style=flat-square) | 通过反思优化提示词、代码、配置和智能体架构；[2026 年论文](https://arxiv.org/abs/2605.19633)。 |
| 2026-03，软件 | [autoresearch](https://github.com/karpathy/autoresearch) | ![Stars](https://img.shields.io/github/stars/karpathy/autoresearch?style=flat-square) | 单 GPU 上的简化修改、训练与测量循环，每次实验固定为五分钟。 |
| 2025-09-17，论文 | [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) | ![Stars](https://img.shields.io/github/stars/SakanaAI/ShinkaEvolve?style=flat-square) | 集成评测器的程序演化；2026 年的工具增加了编码智能体技能和无界面后端。 |
| 2025-05-20，报告 | [Microsoft RD-Agent](https://github.com/microsoft/RD-Agent) | ![Stars](https://img.shields.io/github/stars/microsoft/RD-Agent?style=flat-square) | 迭代提出研究方案、实现实验并改进机器学习解法。 |
| 2025-04-10，论文 | [AI Scientist v2](https://github.com/SakanaAI/AI-Scientist-v2) | ![Stars](https://img.shields.io/github/stars/SakanaAI/AI-Scientist-v2?style=flat-square) | 通过智能体树搜索，自动执行实验、分析结果并准备论文。 |
| 2025，软件 | [OpenEvolve](https://github.com/algorithmicsuperintelligence/openevolve) | ![Stars](https://img.shields.io/github/stars/algorithmicsuperintelligence/openevolve?style=flat-square) | 独立的演化式编码框架，包含 LLM 变异、评测器和岛模型种群。 |
| 2023-10-05，论文 | [DSPy](https://github.com/stanfordnlp/dspy) | ![Stars](https://img.shields.io/github/stars/stanfordnlp/dspy?style=flat-square) | 围绕指标优化提示词、示例和可微调组件的模块化语言模型程序。 |

<details>
<summary>🧰 配套基础设施</summary>

- [Harbor](https://github.com/harbor-framework/harbor)：容器化智能体任务、验证器、评测和强化学习轨迹采样。
- [ART](https://github.com/OpenPipe/ART)：利用评分轨迹训练智能体的强化学习框架。
- [verl](https://github.com/verl-project/verl)：支持自定义轨迹采样、奖励和策略更新流程的分布式训练框架。
- [Reef](https://github.com/Human-Agent-Society/reef)：记录线上交互、关联后续反馈，并向在线服务发布有版本记录的权重或 harness 更新。

</details>

*参考日期对应论文、报告或软件发布。代码、模型权重与数据集可能采用不同许可证。*

---

<a id="benchmarks"></a>

## 📊 基准、评测与数据集

按主要评测对象区分两类基准：

| 类别 | 主要问题 | 评测内容 |
|---|---|---|
| **AI 系统改进** | 自主研究能否构建能力更强的 AI 系统？ | 修改训练数据、算法、模型权重、提示词、记忆、技能、工具或 harness；测量能力收益、效率、迁移与保留。 |
| **下游任务能力** | AI 系统能否解决困难任务，包括自我改进之后的表现？ | 科学、工程和专业任务的输出，考察正确性、质量、效率以及累积经验带来的收益。 |

两类基准都能提供与 RSI 有关的证据。要证明**递归**改进，还需展示后续系统继承了已有改进，并在新问题上更善于产生进一步改进。

### 🎯 1. AI 系统改进

| 日期 | 资源 | 评测重点 | 链接 |
|---|---|---|---|
| 2026-10-09 | **MC-EvoBench** | Minecraft 能力链评测：重置世界、明确允许迁移的产物，并匹配来源经验对照；论文中的智能体未表现出稳定的相关经验迁移。 | [论文](https://arxiv.org/abs/2610.13829) · [代码与任务](https://github.com/xzw-ustc/mc-bench-open-source) |
| 2026-08-20 | **AI4AI-Bench** | 在十个研究代码库中重新设计训练算法，提供四小时探索时间，并通过封闭重跑验证。 | [论文](https://arxiv.org/abs/2608.20318) · [代码](https://github.com/Einsia/AI4AI-Bench) |
| 2026-08，报告 | **CurateBench** | 在固定训练方案下选择、合成和混合数据，检查同一个模型在数学、编码和工具使用上的变化。 | [报告](https://www.datologyai.com/blog/datasmith) |
| 2026-08-04 | **ContinualSkillBench** | 在五个领域、500 个顺序子任务中构建、维护和复用技能库，检查技能保留与迁移。 | [论文](https://arxiv.org/abs/2608.03874) · [代码与任务](https://github.com/gtynnn060110-hash/continual-skill-bench-final) |
| 2026-08-04 | **PAST-Bench** | 在匹配的任务序列中比较保留经验与不保留经验的表现，涵盖经验管理流程。 | [论文](https://arxiv.org/abs/2608.04003) · [代码](https://github.com/Gen-Verse/PAST-Bench) |
| 2026-07-29，框架 | **RSI Bench (Evolvent AI)** | 固定外围服务和预算，逐个改变改进组件的模块化评测；公开任务方向见下方 RSIBench-Data。 | [网站](https://rsibench.co/) · [发布说明](https://evolvent.co/en/blog/RSIBench-Data) |
| 2026-07-28 | **RSIBench-Data** | 围绕固定目标模型，迭代研究训练数据，并利用训练与评测反馈选择更好的检查点，覆盖六项目标评测。 | [论文](https://arxiv.org/abs/2607.25886) · [代码](https://github.com/evolvent-ai/RSIBench-Data) · [任务方向](https://rsibench.co/data/) |
| 2026-06-16 | **SEAGym** | 在固定的更新验证流程下演化 harness，提供独立的分布内外测试、回放诊断和状态快照。 | [论文](https://arxiv.org/abs/2606.17546) · [代码](https://github.com/antropy-research/SEAGym) |
| 2026-04-12 | **Agent² RL-Bench** | 自主完成智能体强化学习工程，包括轨迹收集、模型训练和产物评测。 | [论文](https://arxiv.org/abs/2604.10547) · [代码](https://github.com/microsoft/RD-Agent/blob/main/rdagent/scenarios/rl/autorl_bench/README.md) |
| 2026-03-09 | **PostTrainBench** | 端到端语言模型后训练：智能体在固定 GPU 和时间预算内选择数据与训练方法，再提交模型检查点评测。 | [论文](https://arxiv.org/abs/2603.08640) · [代码](https://github.com/aisa-group/PostTrainBench) · [排行榜](https://posttrainbench.com/) |
| 2026-03-02 | **FT-Dojo** | 在五个领域、13 项任务中自主微调，使用沙盒执行和独立测试。 | [论文](https://arxiv.org/abs/2603.01712) · [代码](https://github.com/microsoft/RD-Agent) |

### 🔬 2. 下游任务能力

| 日期 | 资源 | 评测重点 | 链接 |
|---|---|---|---|
| 2026-09-17，论文 | **EdgeBench** | SoL-Pi 论文使用的 51 项任务评测，考察智能体表现和 token 效率；应在相同模型设置下比较任务结果与开销。 | [论文](https://arxiv.org/abs/2609.20519) · [项目](https://nvlabs.github.io/SoL-Pi/) |
| 2026-09-01，项目 | **PPTBench (Einsia)** | 将 500 张科学示意图重建为可编辑的 PowerPoint 页面，评测语义保真、原生可编辑性和视觉结构。 | [网站与任务](https://lab.einsia.ai/pptbench/) |
| 2026-08-26，项目 | **RSI-Exam** | 从较弱基线出发，在六个领域的 88 项任务中改进方法，再用隐藏数据测试；同时包含 AI 记忆、harness、科学和专业任务。 | [网站](https://rsi-exam.ai/) · [代码](https://github.com/aiming-lab/RSI-Exam) · [数据](https://huggingface.co/datasets/RSI-Exam/RSI-Exam) |
| 2026-08-18，论文 | **ASI-Bench** | 覆盖 11 个领域、60 项任务的项目级科学研究评测，逐步减少方法指导。 | [论文](https://arxiv.org/abs/2608.17271) · [代码](https://github.com/apexin-ai/ASI-Bench) · [排行榜](https://asibench.apexin.ai/) |
| 2026-08-05，预览版 | **EmulatorBench** | 从零用 Rust 构建 16 种游戏系统模拟器，依据硬件规格和诊断程序检查。 | [报告](https://www.primeintellect.ai/blog/prime-agent) · [智能体代码](https://github.com/PrimeIntellect-ai/prime-agent) |
| 2026-07-30，OpenMLE 论文 | **NatureBench Lite** | 从 NatureBench 选取十项科学机器学习任务，将生成的解法与 Nature 系列期刊发表的结果比较，考察向科学问题的迁移。 | [论文](https://arxiv.org/abs/2607.28568) · [任务子集](https://github.com/FrontisAI/OpenRSI/tree/main/OpenMLE-Evo/benchmarks/naturebench_lite_v2) · [数据](https://huggingface.co/datasets/FrontisAI/NatureBench) |
| 2026-07-30，论文 | **OpenMLE-Gym** | 可执行的机器学习工程任务，提供训练、调试和预测反馈，用于程序演化和研究智能体评测。 | [论文](https://arxiv.org/abs/2607.28568) · [代码](https://github.com/FrontisAI/OpenRSI/tree/main/OpenMLE-Gym) · [任务](https://huggingface.co/datasets/FrontisAI/OpenMLE-Tasks) |
| 2026-05-04，发布 | **Continual Learning Bench (CL-Bench)** | 六个领域中的顺序任务，共享潜在规则并包含概念漂移；比较保留状态与不保留状态的运行，测量经验带来的收益。 | [论文](https://arxiv.org/abs/2606.05661) · [代码](https://github.com/pgasawa/continual-learning-bench) · [发布说明](https://continual-learning-bench.com/news/cl-bench-1-0/) |
| 2026-04-14 | **Frontier-Eng** | 利用模拟器反馈迭代优化可行工程设计，包含能源、计算系统和控制等方向的 47 项任务。 | [论文](https://arxiv.org/abs/2604.12290) · [代码与任务](https://github.com/Einsia/Frontier-Engineering) |
| 2026-01-20 | **APEX-Agents** | 跨文件和应用的长期工作，包含投行、咨询和法律领域的 480 项任务，按专家评分标准评测。 | [论文](https://arxiv.org/abs/2601.14242) · [评测框架](https://github.com/Mercor-Intelligence/archipelago) · [数据](https://huggingface.co/datasets/mercor/apex-agents) |

<details>
<summary>🧪 其他研究工程与下游任务集</summary>

这些任务集可用于改进过程中的任务评测，或改进后的能力测试。

| 任务集 | 常见用途 |
|---|---|
| [PaperBench](https://arxiv.org/abs/2504.01848) · [代码](https://github.com/openai/preparedness/tree/main/project/paperbench) | 复现研究论文，使用作者制定的评分标准评测。 |
| [RE-Bench](https://arxiv.org/abs/2411.15114) · [代码](https://github.com/METR/RE-Bench) | 机器学习研究工程任务，提供人类专家基线并限定资源预算。 |
| [MLE-bench](https://arxiv.org/abs/2410.07095) · [代码](https://github.com/openai/mle-bench) | 在 Kaggle 竞赛中评测端到端机器学习工程。 |
| [SWE-bench / Verified](https://www.swebench.com/SWE-bench/) | 代码库问题修复和编码智能体评测。 |
| [Terminal-Bench](https://www.tbench.ai/) | 带容器环境和验证器的可执行终端任务。 |
| [SOL-ExecBench](https://github.com/NVIDIA/SOL-ExecBench) | GPU 内核优化，包含数值检查和受控计时。 |
| [WebArena](https://github.com/web-arena-x/webarena) / [VisualWebArena](https://github.com/web-arena-x/visualwebarena) | 浏览器智能体评测、记忆复用和跨回合学习。 |

</details>

### 🔍 评测研究

| 日期 | 研究 | 评测启示 |
|---|---|---|
| 2026-10-10 | [Does Failure Feedback Direct Agent Self-Modification?](https://arxiv.org/abs/2610.14662) | 分别测量目标失败的修复、向其他失败的迁移，以及独立测试集上的净变化；目标修复未能可靠预测独立测试收益。 |
| 2026-09-29 | [Harness Evolution as Learning: Approximation, Generalization, and Optimization Limits of Self-Improving Personal Agents](https://arxiv.org/abs/2609.36892) | 通过偏好任务评测，以及对逼近、泛化和优化误差的分析，研究 harness 架构、规模和更新算法。 |
| 2026-08-20 | [Phantom Gains: Auditing Self-Improvement Against a Measured Null](https://arxiv.org/abs/2608.20290) | 用固定对照和重复测量，区分真实学习与表面收益。[代码](https://github.com/chengxuphd/phantom-gains)。 |
| 2026-08-18 | [On the Fragility of Self-Improving Agents: Variance, Task Order, and Underspecification](https://arxiv.org/abs/2608.18066) | 评测基于记忆的智能体时，检查多个随机种子、任务顺序和反馈设定。[代码](https://github.com/SalesforceAIResearch/self-improve-fragility) · [轨迹](https://huggingface.co/datasets/Salesforce/self-improve-fragility)。 |

### 🗂️ 数据集与环境

| 参考日期 | 资源 | 提供的内容 |
|---|---|---|
| 2026-09-16，论文 | [ScienceIDE](https://github.com/aitofound/ScienceIDE) | 按照专家定义的验收标准，把科学代码库转成可执行任务，支持轨迹收集、训练和评测。[论文](https://arxiv.org/abs/2609.19134)。 |
| 2026-08-20，完整发布 | [SPADE 环境语料](https://huggingface.co/collections/spade-rl/spade) | 可执行的游戏与工具环境、提供依据的语料，以及自博弈产物；[静态游戏语料](https://huggingface.co/datasets/spade-rl/SPADE-Environment-Pool-GPT5.5-Games)。 |
| 2026-06-23，论文 | [OpenThoughts-Agent](https://github.com/open-thoughts/OpenThoughts-Agent) | 智能体训练数据集、整理流程、实验记录和模型检查点。 |
| 2026-01-23，论文 | [Endless Terminals](https://github.com/kanishkg/endless-terminals) | 通过程序生成的容器化终端训练环境和验证流程。 |
| 持续更新 | [TaskTrove](https://huggingface.co/datasets/open-thoughts/TaskTrove) | 有版本记录的 Harbor 格式训练任务包，包含环境定义和验证器；训练前需核对实际运行行为。 |

*比较方法时，请注明基准的具体版本和计算预算，并将改进阶段使用的数据与最终独立测试数据分开。*

---

<a id="models"></a>

## 🧠 模型与检查点

与自我改进方法或研究智能体有关的可下载模型，附基础模型信息，便于复现和比较。

| 权重发布 | 模型／系列 | 基础模型 | 与自我改进的关系 | 检查点 |
|---|---|---|---|---|
| 2026-09-17，发布公告 | **PhAI-IDE, 4B / 9B / 72B** | Qwen3.5-4B / 9B; Qwen2.5-72B-Instruct | 在 ScienceIDE 中经验证的科学工具轨迹上做 SFT，为科研智能体研究提供任务模型。 | [🤗 权重](https://huggingface.co/collections/AItonomy/scienceide-model-series) · [模型卡](https://huggingface.co/AItonomy/PhAI-IDE-4B) |
| 2026-08-24 | **Apodex-1.1-mini** | Qwen3.5-35B-A3B | 面向长期执行与研究的智能体后训练，模型与系统改进过程由外部流程管理。 | [🤗 权重](https://huggingface.co/apodex/Apodex-1.1-mini) · [合集](https://huggingface.co/collections/apodex/apodex-11) |
| 2026-08-20 | **SPADE** | Qwen3, 4B / 8B / 30B-A3B | 环境设计与智能体推理共享策略，进行自博弈。 | [🤗 模型合集](https://huggingface.co/collections/spade-rl/spade-checkpoints) |
| 2026-07-23 | **AREX-Base / Turbo** | Qwen3.5-122B-A10B / 4B | 研究智能体训练，以及证据和答案的迭代修订。 | [🤗 基础版](https://huggingface.co/BAAI/AREX-Base) · [Turbo](https://huggingface.co/BAAI/AREX-Turbo) |
| 2026-02-23 | **SkillRL 任务模型** | Qwen2.5-7B-Instruct | 与持续演化的技能库共同训练的策略模型。 | [🤗 ALFWorld](https://huggingface.co/Jianwen/Alfworld-7B-RL) · [WebShop](https://huggingface.co/Jianwen/Webshop-7B-RL) · [搜索](https://huggingface.co/Jianwen/Search-7B-RL) |
| 2025-11-19 | **Cogito v2.1 671B** | DeepSeek-V3-Base | 迭代蒸馏与放大（IDA）：先在推理时投入计算，再将结果蒸馏到模型中。 | [🤗 BF16](https://huggingface.co/deepcogito/cogito-671b-v2.1) · [FP8](https://huggingface.co/deepcogito/cogito-671b-v2.1-FP8) |
| 2025-05-06 | **Absolute Zero Reasoner** | Qwen2.5 Base / Coder | 通过可验证自博弈，提出并求解可执行任务。 | [🤗 模型合集](https://huggingface.co/collections/andrewzh/absolute-zero-reasoner) |

---

<a id="surveys"></a>

## 🧭 综述

| 日期 | 综述 | 阅读重点 |
|---|---|---|
| 2026-09-30 | [Recursive Self-Improvement in AI: A Survey](https://www.preprints.org/manuscript/202609.2680) | 从更新对象、反馈、继承和外部控制理解 RSI，考察能力保留与改进更新过程的证据。 |
| 2026-09-08 | [Safety in Self-Evolving Agents: A Survey](https://arxiv.org/abs/2610.00093) | 考察记忆、技能、工具和权重更新如何改变安全性质，涵盖继承失败的修复和恢复适应后的评测。 |
| 2026-09-01 | [A Survey on Self-Improving Test-Time Intelligence: Feedback-Driven Adapting, Learning, and Scaling at Inference](https://arxiv.org/abs/2609.01679) | 推理时由反馈驱动的适应、学习和计算扩展。 |
| 2026-08-03 | [The Path to Recursive Self-Improving Agents: Foundation, Framework, and Future Directions](https://www.preprints.org/manuscript/202608.0051) | 基础模型、harness、数据、训练器和改进机制。[配套列表](https://github.com/D2I-ai/awesome-recursive-self-improving-agents)。 |
| 2026-07-14 | [Self-Improvements in Modern Agentic Systems: A Survey](https://arxiv.org/abs/2607.13104) | 模型参数与运行框架的持续改进。[配套列表](https://github.com/selfimproving-agent/awesome-Self-Improving-Agents)。 |
| 2026-07-08 | [Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](https://arxiv.org/abs/2607.07663) | 改进对象、反馈循环，以及自主研究的验证。 |

**🎓 社区：** [ICLR 2026 Workshop: AI with Recursive Self-Improvement](https://recursive-workshop.github.io/) · [录用论文](https://recursive-workshop.github.io/papers.html) · [Awesome Open-Ended AI](https://github.com/jennyzzt/awesome-open-ended)。

---

<a id="companies"></a>

## 🏢 公司与实验室

在自我改进或自动化 AI 研发方面已有公开工作的机构。日期对应所链接的技术进展，末列列出可获取的资源。

### 🚀 公司与产业研究实验室

| 公开进展 | 机构 | 技术方向 | 公开资源 |
|---|---|---|---|
| 2026-10-09，Harness² 论文 | [**Google DeepMind / Google Research**](https://arxiv.org/abs/2610.14224) | 智能体 harness 适应、程序演化和算法发现。 | [Harness² 代码](https://github.com/google-research/harness2) · [AlphaEvolve 结果与产物](https://github.com/google-deepmind/alphaevolve_results) · [FunSearch 代码](https://github.com/google-deepmind/funsearch)。 |
| 2026-09-17，SoL-Pi 论文 | [**NVIDIA / NVlabs 及合作者**](https://arxiv.org/abs/2609.20519) | 通过自动 harness 搜索，提高长期运行智能体的效率。 | [SoL-Pi 扩展](https://github.com/NVlabs/SoL-Pi) · [技术说明](https://nvlabs.github.io/SoL-Pi/)。 |
| 2026-09-16，ScienceIDE 论文 | [**PhAI Labs 及合作者**](https://phai-labs.com/en/papers/sciencebuddy/) | 科研智能体的 harness 与模型学习，以及可执行科学环境。 | [ScienceBuddy 研究代码](https://github.com/Gen-Verse/ScienceBuddy) · [ScienceIDE](https://github.com/aitofound/ScienceIDE) · [PhAI-IDE 权重](https://huggingface.co/collections/AItonomy/scienceide-model-series)。 |
| 2026-09-06，基准更新 | [**Apex Intelligence / 超衍智能**](https://www.apexin.ai/)：陈勇超 / Yongchao Chen | 自演化 AI 与科学研究。 | [研究报告](https://github.com/apexin-ai/apex-research-report) · [ASI-Bench](https://github.com/apexin-ai/ASI-Bench)。 |
| 2026-09-03 | [**Adaption Labs**](https://adaptionlabs.ai/blog/introducing-invent-a-dataset) | 围绕目标生成数据，并自动搜索训练方案。 | 在线服务 [AutoScientist](https://adaptionlabs.ai/blog/autoscientist-api)，提供适应后的模型下载。 |
| 2026-09-02，研究产物 | [**iGent AI**](https://igent.ai/) | 可自我修改的编码智能体，以及 AI 辅助研究。 | [SICA 代码](https://github.com/MaximeRobeyns/self_improving_coding_agent) · [Maestro 研究产物](https://github.com/iGentAI/factorlab)。 |
| 2026-08-28 | [**Anthropic**](https://alignment.anthropic.com/2026/automated-alignment-researchers/) | 自动化对齐实验和研究判断。 | [研究智能体框架](https://github.com/YuehHanChen/automated_alignment_researcher) · [TASTE](https://alignment.anthropic.com/2026/taste/)。 |
| 2026-08-28 | [**MetaCircle / 元环智能**](https://meta-circle.com/)：[刘子鸣 / Ziming Liu](https://kindxiaoming.github.io/) | 基于机制分析的自动研究，以及学习过程的元模型。 | [训练曲线研究](https://meta-circle.com/blog/predicting-marins-hero-run) · [OPHIS](https://meta-circle.com/blog/ophis-a-new-paradigm-for-autoresearch) · [ComfyResearch](https://github.com/MetaCircleAI/ComfyResearch)。 |
| 2026-08-24 | [**Apodex / ApodexAI**](https://arxiv.org/abs/2608.23283) | 智能体后训练、长期执行和可验证任务环境。 | [Mini 权重](https://huggingface.co/apodex/Apodex-1.1-mini) · [FrontierAgent](https://github.com/ApodexAI/FrontierAgent)。 |
| 2026-08-24 | [**Prime Intellect**](https://arxiv.org/abs/2608.23552) | 支持递归委托与持续 harness 适应的长期运行智能体。 | [Prime Agent 代码](https://github.com/PrimeIntellect-ai/prime-agent)。 |
| 2026-07 | [**Tencent Hunyuan / 腾讯混元**](https://hy.tencent.com/research/hyra) | 面向训练、内核、数学和工程的长期 AI 研究。 | [Hyra 研究产物](https://github.com/Tencent-Hunyuan/hyra-results)；未发布完整研究智能体。 |
| 2026-07-17，RHI 论文 | [**Sakana AI / RSI Lab**](https://sakana.ai/rsi-lab/) | 开放式演化、harness 自我改进、算法发现和自动化科学。 | [DGM](https://github.com/jennyzzt/dgm) · [RHI](https://arxiv.org/abs/2607.15524) · [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) · [AI Scientist v2](https://github.com/SakanaAI/AI-Scientist-v2)。 |
| 2026-06-11 | [**Recursive Superintelligence**](https://www.recursive.com/articles/first-steps-toward-automated-ai-research) | 自动优化模型训练方法与 GPU 内核。 | [NanoChat、NanoGPT 与 SOL 产物](https://github.com/recursive-org/first-steps-toward-automated-ai-research)；未发布完整研究智能体。 |
| 2026-03-19，论文 | [**Meta / FAIR 及合作者**](https://arxiv.org/abs/2603.19461) | 同时修改任务智能体和元智能体。 | [Hyperagents 代码与日志](https://github.com/facebookresearch/Hyperagents)。 |
| 2025-11-19，模型发布 | [**Deep Cogito**](https://www.deepcogito.com/research/cogito-v2-1) | 迭代蒸馏与放大（IDA）。 | [Cogito 模型权重](https://huggingface.co/deepcogito/models)；未发布完整 IDA 训练流程。 |

### 🎓 学术实验室与团队

| 团队 | 代表工作 |
|---|---|
| [MGM 作者团队：电子科技大学、慕尼黑大学与 MCML](https://arxiv.org/abs/2608.07645) | [Mendel Gödel Machine](https://github.com/RealLcz/MGM)：通过比较演化编码智能体谱系。 |
| [Minnesota NLP](https://github.com/minnesotanlp/meta-n) | Metaⁿ：可执行的多层元改进机制。 |
| [KAUST / Metauto](https://github.com/metauto-ai/HGM) | Huxley-Gödel Machine：根据后代产出选择谱系。 |
| [MIT Continual Intelligence](https://github.com/Continual-Intelligence/SEAL) | SEAL：学习生成自编辑数据和适应指令。 |
| [AIMing Lab](https://github.com/aiming-lab) | [SkillRL](https://github.com/aiming-lab/SkillRL) 和 [RSI-Exam](https://github.com/aiming-lab/RSI-Exam)。 |

<details>
<summary>👀 可关注的新公司</summary>

这些机构已公布相关研究方向；本版尚未核实其已发布的技术系统或模型检查点。

| 机构 | 公开方向 |
|---|---|
| [Mirendil](https://mirendil.com/news/scaling-self-accelerating-ai-with-google/) | 自加速 AI 研发和前沿模型开发。 |
| [Discovery Loop](https://www.discoveryloop.com/) | 大规模并行研究循环，以及机器学习方法本身的改进。 |
| [Ineffable Intelligence](https://www.ineffable.ai/) | 从经验中进行强化学习。 |
| [Ricursive Intelligence](https://www.ricursive.com/) | AI 辅助芯片设计与 AI 硬件之间的反馈。 |

</details>

---

<a id="contributing"></a>

**🤝 提交你的工作**

提交 Issue 或 Pull Request 时，请附资源名称、首次公开日期、主要链接，并用一句话说明贡献。论文可建议归入经验积累、系统修改或模型参数；项目和模型请附可获取的代码、权重或数据。

请说明系统更新了什么，以及如何评测。也欢迎补充复现材料、新版本和勘误。

<div align="center">

[↑ 返回顶部](#awesome-rsi)

</div>
