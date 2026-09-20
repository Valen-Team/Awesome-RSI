<a id="awesome-rsi"></a>

<div align="center">

# ♾️ Awesome RSI

**Recursive Self-Improvement · From Experience to Systems to Models**

A curated collection of research and tools for AI systems that learn from experience, improve their own systems, and update their models.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Updated](https://img.shields.io/badge/Updated-2026--09--11-2563eb?style=flat-square)
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-16a34a?style=flat-square)](#contributing)

[📄 Papers](#papers) · [🛠️ Projects](#projects) · [📊 Benchmarks, Evaluation & Datasets](#benchmarks)

[🧠 Models & Checkpoints](#models) · [🧭 Surveys](#surveys) · [🏢 Companies & Labs](#companies)

</div>

> 📣 **Share your research!** Have a relevant paper, project, benchmark, dataset, or model—including your own work? Open an **Issue** or submit a **Pull Request**. Contributions and corrections are welcome!

We prioritize **relevance, clear technical contributions, and useful public resources**, with recent work listed first. Dates refer to first publication unless a release or update is explicitly indicated.

---

<a id="papers"></a>

## 📄 Papers

| 🧩 Experience Accumulation | 🛠️ System Modification | 🧠 Model Parameters |
|:---:|:---:|:---:|
| Prompts · Context · Skills · Memory | Harnesses · Tools · Agent Architecture | Fine-tuning · Reinforcement Learning · Self-play |
| [Learn from past experience ↓](#experience) | [Improve how the agent works ↓](#systems) | [Learn through weight updates ↓](#parameters) |

Papers are grouped by their primary improvement mechanism; descriptions identify additional mechanisms in hybrid methods.

<a id="experience"></a>

### 🧩 1. Experience Accumulation

Improvement through reusable prompts, context, skills, and memory.

| Date | Paper | Core idea | Resources |
|---|---|---|---|
| 2026-08-25 | [Recuris: Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses](https://arxiv.org/abs/2608.24876) | Evolves working memory and experiential skills using verified state and structured failure feedback; the base LLM and outer meta-agent stay fixed. | [💻 Code](https://github.com/Gen-Verse/Recuris) |
| 2026-08-15 | [Evo-Harness: Context-to-Harness Skill Compilation for Self-Evolving Agents](https://arxiv.org/abs/2608.15071) | Compiles execution contexts into reusable cross-task and task-type skills around a frozen solver. | [💻 Code & skills](https://github.com/A-EVO-Lab/a-evolve/tree/release/evo-harness) |
| 2026-03-19 | [Memento-Skills: Let Agents Design Agents](https://arxiv.org/abs/2603.18743) | Grows reusable Markdown skills through reflective learning, with a frozen backbone and a learned skill router. | [💻 Code](https://github.com/Memento-Teams/Memento-Skills) |
| 2025-10-06 | [Agentic Context Engineering: Evolving Contexts for Self-Improving Language Models](https://arxiv.org/abs/2510.04618) | Builds contextual playbooks through generation, reflection, and incremental curation. | [💻 Code](https://github.com/ace-agent/ace) |
| 2025-07-25 | [GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning](https://arxiv.org/abs/2507.19457) | Uses execution feedback and reflection to evolve prompts and select complementary candidates. | [💻 Code](https://github.com/gepa-ai/gepa) |
| 2023-03-20 | [Reflexion: Language Agents with Verbal Reinforcement Learning](https://arxiv.org/abs/2303.11366) | Uses verbal feedback and episodic memory to improve subsequent trials without updating model weights. | 📄 Paper |

<a id="systems"></a>

### 🛠️ 2. System Modification

Improvement through changes to agent harnesses, tools, executable code, and the mechanisms that generate future agents.

| Date | Paper | Core idea | Resources |
|---|---|---|---|
| 2026-08-25 | [Metaⁿ: Recursive Self-Improvement through Emergent Depth](https://arxiv.org/abs/2608.24735) | Builds stacks of executable improvement layers from code and traces by repeatedly applying a fixed meta-operation. | [💻 Code](https://github.com/minnesotanlp/meta-n) |
| 2026-08-07 | [Mendel Gödel Machine: Recursive Self-Improving Coding Agents via Comparative Evolution](https://arxiv.org/abs/2608.07645) | Evolves coding agents through cross-task comparison and cross-lineage hybridization. | [💻 Code](https://github.com/RealLcz/MGM) |
| 2026-07-17 | [Recursive Harness Self-Improvement](https://arxiv.org/abs/2607.15524) | Improves prompt-level agent-loop specifications using feedback on previous harness revisions. | 📄 Paper |
| 2026-06-04 | [Evolving Agents in the Dark: Retrospective Harness Optimization via Self-Preference](https://arxiv.org/abs/2606.05922) | RHO uses task replay and self-preference to select harness updates without ground-truth grading during optimization. | [💻 Code](https://github.com/wbopan/retro-harness) |
| 2026-05-11 | [Continual Harness: Online Adaptation for Self-Improving Foundation Agents](https://arxiv.org/abs/2605.09998) | Adapts prompts, subagents, skills, and memory during continuous interaction; a separate co-learning extension also updates model weights. | [💻 Code](https://github.com/sethkarten/continual-harness) |
| 2026-03-30 | [Meta-Harness: End-to-End Optimization of Model Harnesses](https://arxiv.org/abs/2603.28052) | Optimizes executable harnesses using previous candidates, evaluation scores, and execution traces. | [💻 Code](https://github.com/stanford-iris-lab/meta-harness) |
| 2026-03-19 | [Hyperagents](https://arxiv.org/abs/2603.19461) | Jointly edits task agents and the meta-agent responsible for producing subsequent improvements. | [💻 Code & logs](https://github.com/facebookresearch/Hyperagents) |
| 2025-11-17 | [Live-SWE-agent: Can Software Engineering Agents Self-Evolve on the Fly?](https://arxiv.org/abs/2511.13646) | Creates and revises tools during software issue resolution, starting from a minimal bash-based scaffold. | [💻 Code](https://github.com/OpenAutoCoder/live-swe-agent) |
| 2025-10-24 | [Huxley-Gödel Machine: Human-Level Coding Agent Development by an Approximation of the Optimal Self-Improving Machine](https://arxiv.org/abs/2510.21614) | Selects self-editing agent lineages using estimated descendant productivity rather than immediate task score alone. | [💻 Code](https://github.com/metauto-ai/HGM) |
| 2025-05-29 | [Darwin Godel Machine: Open-Ended Evolution of Self-Improving Agents](https://arxiv.org/abs/2505.22954) | Maintains an evolving archive of coding agents that modify and evaluate their own code around a fixed foundation model. | [💻 Code & logs](https://github.com/jennyzzt/dgm) |
| 2025-04-21 | [A Self-Improving Coding Agent](https://arxiv.org/abs/2504.15228) | SICA iteratively rewrites a complete coding-agent codebase using execution feedback. | [💻 Code](https://github.com/MaximeRobeyns/self_improving_coding_agent) |

<a id="parameters"></a>

### 🧠 3. Model Parameters

Improvement through weight updates, including self-generated training data, evolving curricula, learned feedback, and reinforcement learning.

| Date | Paper | Core idea | Resources |
|---|---|---|---|
| 2026-09-02 | [SafeEvolve: Harness-Policy Co-Evolution from Agent Experience for Safety Alignment](https://arxiv.org/abs/2609.02786) | Co-evolves safety prompts and skill banks with SFT and GRPO policy updates. | [💻 Code](https://github.com/MaoPopovich/SafeEvolve) |
| 2026-09-02 | [APEx: Distillation of Agent Procedural Experience for Adaptive Deep Research Question Answering](https://arxiv.org/abs/2609.02253) | Distills procedural experience into skills while training executor, distiller, and planner roles; includes test-time planner adaptation. | [💻 Code](https://github.com/J-Ding519/APEx) |
| 2026-08-25 | [CAFE: Self-Improving Search Agents Need Co-Evolving Feedback](https://arxiv.org/abs/2608.24794) | Co-trains search-agent and critic roles through online RL and feedback preference optimization. | 📄 Paper |
| 2026-08-19 | [SPADE: Self-Play in Adaptive Synthetic Executable Environments](https://arxiv.org/abs/2608.19197) | Co-trains an executable-environment designer and reasoning agent through self-play, with document grounding and accumulated environment memory. | [💻 Code](https://github.com/spade-rl/spade) · [🤗 Weights](https://huggingface.co/collections/spade-rl/spade-checkpoints) |
| 2026-08-05 | [EvoHarness-RL: Learning Self-Evolving Runtime Harness for Long-Horizon LLM Agents](https://arxiv.org/abs/2608.05446) | Learns Belief, Progress, and Experience workspace-management policies through SFT and cost-aware GRPO. | 📄 Paper |
| 2026-05-11 | [G-Zero: Self-Play for Open-Ended Generation from Zero Data](https://arxiv.org/abs/2605.09959) | Co-evolves proposer and generator models using hint-induced probability shifts as an intrinsic training signal. | [💻 Code](https://github.com/Chengsong-Huang/G-Zero) |
| 2026-02-09 | [SkillRL: Evolving Agents via Recursive Skill-Augmented Reinforcement Learning](https://arxiv.org/abs/2602.08234) | Evolves a hierarchical skill bank jointly with reinforcement learning of the agent policy. | [💻 Code](https://github.com/aiming-lab/SkillRL) · [🤗 Example weights](https://huggingface.co/Jianwen/Alfworld-7B-RL) |
| 2025-08-07 | [R-Zero: Self-Evolving Reasoning LLM from Zero Data](https://arxiv.org/abs/2508.05004) | Co-evolves challenger and solver models using self-generated reasoning problems and estimated learning difficulty. | [💻 Code](https://github.com/Chengsong-Huang/R-Zero) |
| 2025-06-12 | [Self-Adapting Language Models](https://arxiv.org/abs/2506.10943) | SEAL learns to generate finetuning data and adaptation directives, using downstream learning outcomes as feedback. | [💻 Code & data](https://github.com/Continual-Intelligence/SEAL) |
| 2025-05-06 | [Absolute Zero: Reinforced Self-play Reasoning with Zero Data](https://arxiv.org/abs/2505.03335) | Trains task proposal and reasoning through executable, verifiable self-play without a human-curated post-training problem set. | [💻 Code](https://github.com/LeapLabTHU/Absolute-Zero-Reasoner) · [🤗 Weights](https://huggingface.co/collections/andrewzh/absolute-zero-reasoner) |
| 2025-04-22 | [TTRL: Test-Time Reinforcement Learning](https://arxiv.org/abs/2504.16084) | Updates model weights on unlabeled inputs using consensus-based test-time rewards. | [💻 Code](https://github.com/PRIME-RL/TTRL) |
| 2024-01-18 | [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) | Iteratively improves response generation and preference judging through self-rewarding training. | 📄 Paper |
| 2022-03-28 | [STaR: Bootstrapping Reasoning With Reasoning](https://arxiv.org/abs/2203.14465) | Bootstraps reasoning by repeatedly generating, filtering, and training on model-produced rationales. | 📄 Paper |

[↑ Back to top](#awesome-rsi)

---

<a id="projects"></a>

## 🛠️ Projects

Selected implementations and frameworks for building self-improving agents and automated research loops. Individual paper implementations are linked above.

### 🔁 Agents and Learning Loops

| Reference date | Project | Stars | What to explore |
|---|---|---|---|
| 2026-09-02 | [SafeEvolve](https://github.com/MaoPopovich/SafeEvolve) | ![Stars](https://img.shields.io/github/stars/MaoPopovich/SafeEvolve?style=flat-square) | Safety-harness and policy co-evolution; training scripts and compact assets. |
| 2026-08-25 | [Metaⁿ](https://github.com/minnesotanlp/meta-n) | ![Stars](https://img.shields.io/github/stars/minnesotanlp/meta-n?style=flat-square) | Executable meta-improvement layers and a research CLI. |
| 2026-08-25 | [Recuris](https://github.com/Gen-Verse/Recuris) | ![Stars](https://img.shields.io/github/stars/Gen-Verse/Recuris?style=flat-square) | Working memory, experiential skills, and bounded memory evolution. |
| 2026-08-24 | [Prime Agent](https://github.com/PrimeIntellect-ai/prime-agent) | ![Stars](https://img.shields.io/github/stars/PrimeIntellect-ai/prime-agent?style=flat-square) | Persistent REPL, recursive subagents, and continual harness adaptation. |
| 2026-08-19 | [SPADE](https://github.com/spade-rl/spade) | ![Stars](https://img.shields.io/github/stars/spade-rl/spade?style=flat-square) | Environment-designer / agent self-play with released checkpoints and environment corpora. |
| 2026-03-19 | [Hyperagents](https://github.com/facebookresearch/Hyperagents) | ![Stars](https://img.shields.io/github/stars/facebookresearch/Hyperagents?style=flat-square) | Joint task-agent and meta-agent modification, with experiment logs. |
| 2026-02-09 | [SkillRL](https://github.com/aiming-lab/SkillRL) | ![Stars](https://img.shields.io/github/stars/aiming-lab/SkillRL?style=flat-square) | Skill-bank evolution coupled to agent RL. |
| 2025-06-12 | [SEAL](https://github.com/Continual-Intelligence/SEAL) | ![Stars](https://img.shields.io/github/stars/Continual-Intelligence/SEAL?style=flat-square) | Self-generated adaptation data and update directives. |
| 2025-05-29 | [DGM](https://github.com/jennyzzt/dgm) | ![Stars](https://img.shields.io/github/stars/jennyzzt/dgm?style=flat-square) | Self-editing coding-agent archives and evolution traces. |

### 🔬 Automated Research and Optimization Frameworks

| Reference date | Project | Stars | What to explore |
|---|---|---|---|
| 2026-09-18, software release | [Gear](https://github.com/rsi-gear/gear) | ![Stars](https://img.shields.io/github/stars/rsi-gear/gear?style=flat-square) | Uses execution traces and benchmark feedback to optimize agent prompts, tools, and workflows, retaining versioned harnesses across rounds. |
| 2026-08-28 | [Automated Alignment Researcher](https://github.com/YuehHanChen/automated_alignment_researcher) | ![Stars](https://img.shields.io/github/stars/YuehHanChen/automated_alignment_researcher?style=flat-square) | Alignment-research harness, evaluation, and monitoring; connects to a user-supplied trainer. |
| 2026-08-11 | [ComfyResearch](https://github.com/MetaCircleAI/ComfyResearch) | ![Stars](https://img.shields.io/github/stars/MetaCircleAI/ComfyResearch?style=flat-square) | Graph-native experiment workbench for inspecting and modifying learning experiments. |
| 2026-05-19, extension paper | [GEPA / optimize_anything](https://github.com/gepa-ai/gepa) | ![Stars](https://img.shields.io/github/stars/gepa-ai/gepa?style=flat-square) | Reflective optimization of prompts, code, configurations, and agent architectures; [2026 paper](https://arxiv.org/abs/2605.19633). |
| 2026-03, software | [autoresearch](https://github.com/karpathy/autoresearch) | ![Stars](https://img.shields.io/github/stars/karpathy/autoresearch?style=flat-square) | Minimal single-GPU edit–train–measure loop with fixed five-minute experiments. |
| 2025-09-17, paper | [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) | ![Stars](https://img.shields.io/github/stars/SakanaAI/ShinkaEvolve?style=flat-square) | Program evolution with evaluator integration; 2026 tooling adds coding-agent skills and headless backends. |
| 2025-05-20, report | [Microsoft RD-Agent](https://github.com/microsoft/RD-Agent) | ![Stars](https://img.shields.io/github/stars/microsoft/RD-Agent?style=flat-square) | Iterative research proposals, experiment implementation, and ML solution refinement. |
| 2025-04-10, paper | [AI Scientist v2](https://github.com/SakanaAI/AI-Scientist-v2) | ![Stars](https://img.shields.io/github/stars/SakanaAI/AI-Scientist-v2?style=flat-square) | Automated experimentation, analysis, and manuscript preparation through agentic tree search. |
| 2025, software | [OpenEvolve](https://github.com/algorithmicsuperintelligence/openevolve) | ![Stars](https://img.shields.io/github/stars/algorithmicsuperintelligence/openevolve?style=flat-square) | Independent evolutionary coding framework with LLM mutations, evaluators, and island populations. |
| 2023-10-05, paper | [DSPy](https://github.com/stanfordnlp/dspy) | ![Stars](https://img.shields.io/github/stars/stanfordnlp/dspy?style=flat-square) | Modular LM programs and metric-driven optimization of prompts, demonstrations, and finetuned components. |

<details>
<summary>🧰 Useful supporting infrastructure</summary>

- [Harbor](https://github.com/harbor-framework/harbor) — containerized agent tasks, verifiers, evaluation, and RL rollouts.
- [ART](https://github.com/OpenPipe/ART) — agent reinforcement learning from scored trajectories.
- [verl](https://github.com/verl-project/verl) — distributed training for custom rollout, reward, and policy-update loops.

</details>

*Reference dates identify a paper, report, or software release. Public code, model weights, and datasets may have different licenses.*

---

<a id="benchmarks"></a>

## 📊 Benchmarks, Evaluation & Datasets

Benchmarks are grouped by their primary evaluation target:

| Category | Core question | What is evaluated |
|---|---|---|
| **AI System Improvement** | Can autonomous research build a stronger AI system? | Changes to training data, algorithms, model weights, prompts, memory, skills, tools, or harnesses; measured by capability gains, efficiency, transfer, and retention. |
| **Downstream Task Capability** | Can an AI system solve difficult tasks, including after self-improvement? | Scientific, engineering, and professional task outputs; measured by correctness, quality, efficiency, and gains from accumulated experience. |

Both provide evidence relevant to RSI. Establishing **recursive** improvement also requires showing that successive systems inherit improvements and become better at producing further improvements on new problems.

### 🎯 1. AI System Improvement

| Date | Resource | Evaluation focus | Links |
|---|---|---|---|
| 2026-08-20 | **AI4AI-Bench** | Training-algorithm redesign across ten research repositories with four-hour exploration and sealed reruns. | [Paper](https://arxiv.org/abs/2608.20318) · [Code](https://github.com/Einsia/AI4AI-Bench) |
| 2026-08, report | **CurateBench** | Data selection, synthesis, and mixing under a fixed training recipe; tests whether one trained model improves across math, coding, and tool use. | [Report](https://www.datologyai.com/blog/datasmith) |
| 2026-08-04 | **ContinualSkillBench** | Construction, maintenance, and reuse of skill libraries across 500 sequential subtasks in five domains; examines skill retention and transfer. | [Paper](https://arxiv.org/abs/2608.03874) · [Code & tasks](https://github.com/gtynnn060110-hash/continual-skill-bench-final) |
| 2026-08-04 | **PAST-Bench** | Matched task sequences with and without retained experience, including experience-management pathways. | [Paper](https://arxiv.org/abs/2608.04003) · [Code](https://github.com/Gen-Verse/PAST-Bench) |
| 2026-07-29, framework | **RSI Bench (Evolvent AI)** | Modular evaluation that varies one improvement component while fixing the surrounding services and budget; its public task track is RSIBench-Data below. | [Website](https://rsibench.co/) · [Release](https://evolvent.co/en/blog/RSIBench-Data) |
| 2026-07-28 | **RSIBench-Data** | Iterative training-data research for a fixed target model, using training and evaluation feedback to select a stronger checkpoint across six target evaluations. | [Paper](https://arxiv.org/abs/2607.25886) · [Code](https://github.com/evolvent-ai/RSIBench-Data) · [Track](https://rsibench.co/data/) |
| 2026-06-16 | **SEAGym** | Harness evolution with frozen update-validation, held-out ID/OOD tests, replay diagnostics, and saved snapshots. | [Paper](https://arxiv.org/abs/2606.17546) · [Code](https://github.com/antropy-research/SEAGym) |
| 2026-04-12 | **Agent² RL-Bench** | Autonomous agentic RL engineering, including trajectory collection, model training, and artifact evaluation. | [Paper](https://arxiv.org/abs/2604.10547) · [Code](https://github.com/microsoft/RD-Agent/blob/main/rdagent/scenarios/rl/autorl_bench/README.md) |
| 2026-03-09 | **PostTrainBench** | End-to-end LLM post-training: agents choose data and training methods within a fixed GPU/time budget, then submit model checkpoints for evaluation. | [Paper](https://arxiv.org/abs/2603.08640) · [Code](https://github.com/aisa-group/PostTrainBench) · [Leaderboard](https://posttrainbench.com/) |
| 2026-03-02 | **FT-Dojo** | Autonomous finetuning across 13 tasks and five domains with sandboxed execution and held-out evaluation. | [Paper](https://arxiv.org/abs/2603.01712) · [Code](https://github.com/microsoft/RD-Agent) |

### 🔬 2. Downstream Task Capability

| Date | Resource | Evaluation focus | Links |
|---|---|---|---|
| 2026-09-01, project | **PPTBench (Einsia)** | Reconstructing 500 scientific diagrams as editable PowerPoint slides; evaluates semantic fidelity, native editability, and visual structure. | [Website & tasks](https://lab.einsia.ai/pptbench/) |
| 2026-08-26, project | **RSI-Exam** | Improving methods from weak baselines across 88 tasks in six domains, then testing on hidden data; includes AI memory/harness tasks alongside scientific and professional tasks. | [Website](https://rsi-exam.ai/) · [Code](https://github.com/aiming-lab/RSI-Exam) · [Data](https://huggingface.co/datasets/RSI-Exam/RSI-Exam) |
| 2026-08-18, paper | **ASI-Bench** | Project-level scientific research across 60 tasks and 11 domains, with progressively reduced methodological guidance. | [Paper](https://arxiv.org/abs/2608.17271) · [Code](https://github.com/apexin-ai/ASI-Bench) · [Leaderboard](https://asibench.apexin.ai/) |
| 2026-08-05, preview | **EmulatorBench** | Building 16 game-system emulators from scratch in Rust, checked against hardware specifications and diagnostic programs. | [Report](https://www.primeintellect.ai/blog/prime-agent) · [Agent code](https://github.com/PrimeIntellect-ai/prime-agent) |
| 2026-07-30, OpenMLE paper | **NatureBench Lite** | Ten scientific ML tasks from NatureBench, comparing generated solutions with published Nature-family results to assess transfer to scientific problems. | [Paper](https://arxiv.org/abs/2607.28568) · [Task subset](https://github.com/FrontisAI/OpenRSI/tree/main/OpenMLE-Evo/benchmarks/naturebench_lite_v2) · [Data](https://huggingface.co/datasets/FrontisAI/NatureBench) |
| 2026-07-30, paper | **OpenMLE-Gym** | Executable ML engineering tasks with training, debugging, and prediction feedback; supplies task environments for program evolution and research-agent evaluation. | [Paper](https://arxiv.org/abs/2607.28568) · [Code](https://github.com/FrontisAI/OpenRSI/tree/main/OpenMLE-Gym) · [Tasks](https://huggingface.co/datasets/FrontisAI/OpenMLE-Tasks) |
| 2026-05-04, release | **Continual Learning Bench (CL-Bench)** | Sequential tasks in six domains with shared latent rules and concept drift; compares stateful and stateless runs to measure gains from experience. | [Paper](https://arxiv.org/abs/2606.05661) · [Code](https://github.com/pgasawa/continual-learning-bench) · [Release](https://continual-learning-bench.com/news/cl-bench-1-0/) |
| 2026-04-14 | **Frontier-Eng** | Iterative optimization of feasible engineering designs using simulator feedback; 47 tasks covering areas such as energy, computing systems, and control. | [Paper](https://arxiv.org/abs/2604.12290) · [Code & tasks](https://github.com/Einsia/Frontier-Engineering) |
| 2026-01-20 | **APEX-Agents** | Long-horizon work across files and applications: 480 investment-banking, consulting, and legal tasks scored against expert rubrics. | [Paper](https://arxiv.org/abs/2601.14242) · [Evaluation framework](https://github.com/Mercor-Intelligence/archipelago) · [Data](https://huggingface.co/datasets/mercor/apex-agents) |

<details>
<summary>🧪 Additional research-engineering and downstream task suites</summary>

These provide task-level evaluation inside or after an improvement loop.

| Suite | Typical use |
|---|---|
| [PaperBench](https://arxiv.org/abs/2504.01848) · [Code](https://github.com/openai/preparedness/tree/main/project/paperbench) | Replication of research papers, scored using author-developed rubrics. |
| [RE-Bench](https://arxiv.org/abs/2411.15114) · [Code](https://github.com/METR/RE-Bench) | ML research-engineering tasks with human-expert baselines and resource budgets. |
| [MLE-bench](https://arxiv.org/abs/2410.07095) · [Code](https://github.com/openai/mle-bench) | End-to-end ML engineering on Kaggle competitions. |
| [SWE-bench / Verified](https://www.swebench.com/SWE-bench/) | Repository repair and coding-agent evaluation. |
| [Terminal-Bench](https://www.tbench.ai/) | Executable terminal tasks with containerized environments and verifiers. |
| [SOL-ExecBench](https://github.com/NVIDIA/SOL-ExecBench) | GPU-kernel optimization with numerical checks and controlled timing. |
| [WebArena](https://github.com/web-arena-x/webarena) / [VisualWebArena](https://github.com/web-arena-x/visualwebarena) | Browser-agent evaluation, memory reuse, and cross-episode learning. |

</details>

### 🔍 Evaluation Studies

| Date | Study | Practical takeaway |
|---|---|---|
| 2026-08-20 | [Phantom Gains: Auditing Self-Improvement Against a Measured Null](https://arxiv.org/abs/2608.20290) | Use frozen controls and repeated measurements to separate learning from apparent gains. [Code](https://github.com/chengxuphd/phantom-gains). |
| 2026-08-18 | [On the Fragility of Self-Improving Agents: Variance, Task Order, and Underspecification](https://arxiv.org/abs/2608.18066) | Check multiple seeds, task orders, and feedback specifications when evaluating memory-based agents. [Code](https://github.com/SalesforceAIResearch/self-improve-fragility) · [Trajectories](https://huggingface.co/datasets/Salesforce/self-improve-fragility). |

### 🗂️ Datasets and Environments

| Reference date | Resource | What it provides |
|---|---|---|
| 2026-08-20, full release | [SPADE environment corpora](https://huggingface.co/collections/spade-rl/spade) | Executable game and tool-use environments, grounding corpora, and self-play artifacts; [static game corpus](https://huggingface.co/datasets/spade-rl/SPADE-Environment-Pool-GPT5.5-Games). |
| 2026-06-23, paper | [OpenThoughts-Agent](https://github.com/open-thoughts/OpenThoughts-Agent) | Agent-training datasets, curation pipelines, experiment records, and model checkpoints. |
| 2026-01-23, paper | [Endless Terminals](https://github.com/kanishkg/endless-terminals) | Procedurally generated containerized terminal-training environments and verification pipelines. |
| Continuously updated | [TaskTrove](https://huggingface.co/datasets/open-thoughts/TaskTrove) | Versioned Harbor-format training task packages with environment definitions and verifier payloads; validate runtime behavior before training. |

*For comparisons, report the exact benchmark version and compute budget, and keep improvement-time data separate from final held-out evaluation.*

---

<a id="models"></a>

## 🧠 Models & Checkpoints

Downloadable models associated with self-improvement methods or research-agent systems. Base-model provenance is included to make reproduction and comparison easier.

| Weight release | Model / family | Base model | Connection to self-improvement | Checkpoints |
|---|---|---|---|---|
| 2026-08-24 | **Apodex-1.1-mini** | Qwen3.5-35B-A3B | Agentic post-training for long-horizon execution and research, within a managed model–system improvement loop. | [🤗 Weights](https://huggingface.co/apodex/Apodex-1.1-mini) · [Collection](https://huggingface.co/collections/apodex/apodex-11) |
| 2026-08-20 | **SPADE** | Qwen3, 4B / 8B / 30B-A3B | Shared-policy self-play between environment design and agent reasoning. | [🤗 Collection](https://huggingface.co/collections/spade-rl/spade-checkpoints) |
| 2026-07-23 | **AREX-Base / Turbo** | Qwen3.5-122B-A10B / 4B | Research-agent training and iterative evidence/answer refinement. | [🤗 Base](https://huggingface.co/BAAI/AREX-Base) · [Turbo](https://huggingface.co/BAAI/AREX-Turbo) |
| 2026-02-23 | **SkillRL task models** | Qwen2.5-7B-Instruct | Policies trained jointly with an evolving skill bank. | [🤗 ALFWorld](https://huggingface.co/Jianwen/Alfworld-7B-RL) · [WebShop](https://huggingface.co/Jianwen/Webshop-7B-RL) · [Search](https://huggingface.co/Jianwen/Search-7B-RL) |
| 2025-11-19 | **Cogito v2.1 671B** | DeepSeek-V3-Base | Iterated Distillation and Amplification: reasoning-time computation followed by distillation. | [🤗 BF16](https://huggingface.co/deepcogito/cogito-671b-v2.1) · [FP8](https://huggingface.co/deepcogito/cogito-671b-v2.1-FP8) |
| 2025-05-06 | **Absolute Zero Reasoner** | Qwen2.5 Base / Coder | Executable task proposal and solving through verifiable self-play. | [🤗 Collection](https://huggingface.co/collections/andrewzh/absolute-zero-reasoner) |

---

<a id="surveys"></a>

## 🧭 Surveys

| Date | Survey | Reading focus |
|---|---|---|
| 2026-09-01 | [A Survey on Self-Improving Test-Time Intelligence: Feedback-Driven Adapting, Learning, and Scaling at Inference](https://arxiv.org/abs/2609.01679) | Feedback-driven adaptation, learning, and scaling at inference time. |
| 2026-08-03 | [The Path to Recursive Self-Improving Agents: Foundation, Framework, and Future Directions](https://www.preprints.org/manuscript/202608.0051) | Foundation models, harnesses, data, trainers, and improvement mechanisms. [Companion list](https://github.com/D2I-ai/awesome-recursive-self-improving-agents). |
| 2026-07-14 | [Self-Improvements in Modern Agentic Systems: A Survey](https://arxiv.org/abs/2607.13104) | Persistent improvement of model parameters and operational scaffolds. [Companion list](https://github.com/selfimproving-agent/awesome-Self-Improving-Agents). |
| 2026-07-08 | [Recursive Self-Improvement in AI: From Bounded Self-Refinement to Autonomous Research Loops](https://arxiv.org/abs/2607.07663) | Improvement targets, loop closure, and verification of autonomous research. |

**🎓 Community:** [ICLR 2026 Workshop: AI with Recursive Self-Improvement](https://recursive-workshop.github.io/) · [Accepted papers](https://recursive-workshop.github.io/papers.html) · [Awesome Open-Ended AI](https://github.com/jennyzzt/awesome-open-ended).

---

<a id="companies"></a>

## 🏢 Companies & Labs

Organizations with public work on self-improvement or automated AI R&D. Dates mark the linked technical milestone; the last column identifies the available resources.

### 🚀 Companies and Industrial Research Labs

| Public milestone | Organization | Technical direction | Public resources |
|---|---|---|---|
| 2026-09-06, benchmark update | [**Apex Intelligence / 超衍智能**](https://www.apexin.ai/) — 陈勇超 / Yongchao Chen | Self-evolving AI and scientific research. | [Research report](https://github.com/apexin-ai/apex-research-report) · [ASI-Bench](https://github.com/apexin-ai/ASI-Bench). |
| 2026-09-03 | [**Adaption Labs**](https://adaptionlabs.ai/blog/introducing-invent-a-dataset) | Goal-driven data generation and automated training-recipe search. | Hosted [AutoScientist](https://adaptionlabs.ai/blog/autoscientist-api), with downloadable adapted models. |
| 2026-09-02, research artifacts | [**iGent AI**](https://igent.ai/) | Self-modifying coding agents and AI-assisted research. | [SICA code](https://github.com/MaximeRobeyns/self_improving_coding_agent) · [Maestro research artifacts](https://github.com/iGentAI/factorlab). |
| 2026-08-28 | [**Anthropic**](https://alignment.anthropic.com/2026/automated-alignment-researchers/) | Automated alignment experiments and research judgment. | [Researcher harness](https://github.com/YuehHanChen/automated_alignment_researcher) · [TASTE](https://alignment.anthropic.com/2026/taste/). |
| 2026-08-28 | [**MetaCircle / 元环智能**](https://meta-circle.com/) — [刘子鸣 / Ziming Liu](https://kindxiaoming.github.io/) | Mechanistic autoresearch and meta-models of learning. | [Training-curve research](https://meta-circle.com/blog/predicting-marins-hero-run) · [OPHIS](https://meta-circle.com/blog/ophis-a-new-paradigm-for-autoresearch) · [ComfyResearch](https://github.com/MetaCircleAI/ComfyResearch). |
| 2026-08-24 | [**Apodex / ApodexAI**](https://arxiv.org/abs/2608.23283) | Agentic post-training, long-horizon execution, and verifiable task environments. | [Mini weights](https://huggingface.co/apodex/Apodex-1.1-mini) · [FrontierAgent](https://github.com/ApodexAI/FrontierAgent). |
| 2026-08-24 | [**Prime Intellect**](https://arxiv.org/abs/2608.23552) | Long-running agents with recursive delegation and continual harness adaptation. | [Prime Agent code](https://github.com/PrimeIntellect-ai/prime-agent). |
| 2026-07 | [**Tencent Hunyuan / 腾讯混元**](https://hy.tencent.com/research/hyra) | Long-horizon AI research across training, kernels, mathematics, and engineering. | [Hyra research artifacts](https://github.com/Tencent-Hunyuan/hyra-results); full researcher not released. |
| 2026-07-17, RHI paper | [**Sakana AI / RSI Lab**](https://sakana.ai/rsi-lab/) | Open-ended evolution, harness self-improvement, algorithm discovery, and automated science. | [DGM](https://github.com/jennyzzt/dgm) · [RHI](https://arxiv.org/abs/2607.15524) · [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) · [AI Scientist v2](https://github.com/SakanaAI/AI-Scientist-v2). |
| 2026-06-11 | [**Recursive Superintelligence**](https://www.recursive.com/articles/first-steps-toward-automated-ai-research) | Automated optimization of model-training methods and GPU kernels. | [NanoChat, NanoGPT, and SOL artifacts](https://github.com/recursive-org/first-steps-toward-automated-ai-research); full researcher not released. |
| 2026-05-07, update | [**Google DeepMind**](https://deepmind.google/blog/alphaevolve-impact/) | Executable program evolution and scientific/algorithmic discovery. | [AlphaEvolve result artifacts](https://github.com/google-deepmind/alphaevolve_results) · [FunSearch code](https://github.com/google-deepmind/funsearch). |
| 2026-03-19, paper | [**Meta / FAIR and collaborators**](https://arxiv.org/abs/2603.19461) | Joint task-agent and meta-agent self-modification. | [Hyperagents code and logs](https://github.com/facebookresearch/Hyperagents). |
| 2025-11-19, model release | [**Deep Cogito**](https://www.deepcogito.com/research/cogito-v2-1) | Iterated Distillation and Amplification. | [Cogito model weights](https://huggingface.co/deepcogito/models); full IDA training pipeline not released. |

### 🎓 Academic Labs and Groups

| Group | Representative work |
|---|---|
| [MGM authors: UESTC, LMU Munich, and MCML](https://arxiv.org/abs/2608.07645) | [Mendel Gödel Machine](https://github.com/RealLcz/MGM): comparative evolution of coding-agent lineages. |
| [Minnesota NLP](https://github.com/minnesotanlp/meta-n) | Metaⁿ: executable layers of meta-improvement. |
| [KAUST / Metauto](https://github.com/metauto-ai/HGM) | Huxley-Gödel Machine: selection based on descendant productivity. |
| [MIT Continual Intelligence](https://github.com/Continual-Intelligence/SEAL) | SEAL: learned self-edit data and adaptation directives. |
| [AIMing Lab](https://github.com/aiming-lab) | [SkillRL](https://github.com/aiming-lab/SkillRL) and [RSI-Exam](https://github.com/aiming-lab/RSI-Exam). |

<details>
<summary>👀 Emerging companies to follow</summary>

These organizations have announced relevant directions; released technical systems or checkpoints were not verified in this edition.

| Organization | Stated direction |
|---|---|
| [Mirendil](https://mirendil.com/news/scaling-self-accelerating-ai-with-google/) | Self-accelerating AI R&D and frontier-model development. |
| [Discovery Loop](https://www.discoveryloop.com/) | Large-scale parallel research loops and improvement of ML itself. |
| [Ineffable Intelligence](https://www.ineffable.ai/) | Reinforcement learning from experience. |
| [Ricursive Intelligence](https://www.ricursive.com/) | Feedback between AI-assisted chip design and hardware for AI. |

</details>

---

<a id="contributing"></a>

**🤝 Contribute your work**

Open an **Issue** or **Pull Request** with the resource name, first public date, primary link, and one sentence explaining its contribution. For papers, suggest **Experience**, **Systems**, or **Parameters**; for projects and models, link the available code, weights, or data.

We favor relevant, technically clear entries over a longer list. Author submissions, reproducibility resources, new releases, and corrections are all welcome.

<div align="center">

**Build · Evaluate · Improve · Share**

[↑ Back to top](#awesome-rsi)

</div>
