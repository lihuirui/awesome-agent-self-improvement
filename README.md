# Awesome Agent Self-Improvement

精选关于 Agent 自我改进（Recursive Self-Improvement, RSI）、自动验证器（verifier）生成以及相关评测与基准（benchmark）的研究论文与资源列表。

## 收录说明

- **收录范围**：聚焦 Agent RSI 机制、自动化 verifier 生成与 harness 设计、自我改进相关的评测协议与 benchmark。
- **条目格式**：包含已核实题目、完整作者名单、官方链接（arXiv/PDF），以及基于摘要的 1–2 句核心贡献描述。

## 目录

- [自动验证器生成 (Verifier Generation)](#自动验证器生成-verifier-generation)
- [Agent 自我改进与 RSI (Agent Self-Improvement & RSI)](#agent-自我改进与-rsi-agent-self-improvement--rsi)
- [评测与基准 (Benchmarks & Evaluations)](#评测与基准-benchmarks--evaluations)

---

## 自动验证器生成 (Verifier Generation)

- **Verify by Doing: Co-Evolving Agent Execution and Evaluation without External Feedback**
  - **作者**：Yitong Lin, Jianda Chen, Yihao Hu, Pan Wang, Hang Wang, Zhihao Wen, Xiaoxue Ren, Wei Wu
  - **来源**：arXiv:2611.15276（v1，2026-11-11）
  - **链接**：[arXiv:2611.15276](https://arxiv.org/abs/2611.15276) | [PDF](https://arxiv.org/pdf/2611.15276)
  - **描述**：针对测试时可能无法获得外部反馈、且不完整验证会误导后续更新的问题，提出 Verify by Doing (VbD)，在固定模型权重下于同一任务内协同演化 Actor 与 Evaluator 的 harness；Evaluator 使用工具主动检查产物与环境状态，其发现既作为内部信号用于输出选择，也指导执行与验证流程的更新。在 AutomationBench、τ³ Banking 和部分 GDPval 任务上，相对无外部反馈设定中的最强基线分别提升 3.3、4.1 和 2.3 个百分点。

- **Veritas: A Verifier Generation Harness for Agent Tasks**
  - **作者**：Daoan Zhang, Qinbo Bai, Dehai Min, Xingyu Mu, Ziyi Chen, Jianing Yin
  - **来源**：arXiv:2611.13336（v1，2026-11-09）
  - **链接**：[arXiv:2611.13336](https://arxiv.org/abs/2611.13336) | [PDF](https://arxiv.org/pdf/2611.13336)
  - **描述**：针对自我改进系统中人工编写 verifier 成本高且难以规模化的问题，提出自动生成 verifier 的 harness 工具 Veritas；通过引入证据头（evidence header）、领域规则库及经自我改进循环优化的编写原则，显著提升了生成验证器在多个 benchmark 上与官方判定的一致性。

## Agent 自我改进与 RSI (Agent Self-Improvement & RSI)

- **Do LLM Agents Still Need to Be Told How to Self-Improve?**
  - **作者**：Shobhita Sundaram, Cansu Sancaktar, Phillip Isola
  - **来源**：arXiv:2611.23219（v1，2026-11-17）
  - **链接**：[arXiv:2611.23219](https://arxiv.org/abs/2611.23219) | [PDF](https://arxiv.org/pdf/2611.23219) | [官方代码](https://github.com/ssundaram21/self-org) | [项目页](https://ssundaram21.github.io/self-org/)
  - **描述**：研究在只提供基本原语、计算预算和一般性自我改进目标、而不指定学习配方或真实任务的条件下，冻结权重的 LLM agent 能否自行构造基于上下文优化的自我学习算法。以游戏为测试平台，足够强的模型能够组成可识别的自我改进循环，所学文本产物可迁移到不同游戏时域、机制及 3D 导航任务并带来提升。

- **The Resolution Hypothesis: Agent Evolution's Key Is Identifying Improvements**
  - **作者**：Yuanhao Zeng, Shaocheng Lan, Ao Lu, Kuang Yan, Heng Lin, Xinang Xu, Yuan Luo, Yueting Wang, Yexin Li, Ruo Shan, Kan Ren
  - **来源**：arXiv:2611.23068（v1，2026-11-17）
  - **链接**：[arXiv:2611.23068](https://arxiv.org/abs/2611.23068) | [PDF](https://arxiv.org/pdf/2611.23068) | [项目页](https://lineshogan.github.io/resolution-hypothesis/)
  - **描述**：提出 Resolution Hypothesis：智能体演化（agent evolution）往往卡在无法可靠识别改进，而非无法提出更好的候选（prompts、skills、memories）。在 7 种演化方法与 6 个模型（逾 1000 万次 LLM 调用）上发现，候选选择接近随机，方法间几个百分点的差距常小于同方法两次独立运行的差异，因而呼吁将重点从设计更多提议机制转向让真实改进可被检测与累积。

- **Values Shape What Self-Improving Coding Agents Build**
  - **作者**：Jason Liang, Dylan Waldner, Risto Miikkulainen
  - **来源**：arXiv:2611.23067（v1，2026-11-17）
  - **链接**：[arXiv:2611.23067](https://arxiv.org/abs/2611.23067) | [PDF](https://arxiv.org/pdf/2611.23067)
  - **描述**：研究在自我改进 coding agent 的持久指令文件中加入简短价值观陈述，会否同时改变其表现与所构建的解决方案。基于 Schwartz 基本人类价值观的四类高阶价值，在多样编码任务的多轮自我改进中发现：开放（openness to change）提升留出数据表现，保守（conservation）则低于无价值观对照；价值观还会改变算法的规模、复杂度与路径，且允许 agent 自行改写价值观会缩小差异。

- **Think Once, Act Fast: Cost-Effective Recursive Self-Improvement for Decision Model Harness**
  - **作者**：Siqi Lai, Haitao Li, Hao Liu
  - **来源**：arXiv:2611.22432（v1，2026-11-17）
  - **链接**：[arXiv:2611.22432](https://arxiv.org/abs/2611.22432) | [PDF](https://arxiv.org/pdf/2611.22432) | [官方代码](https://github.com/usail-hkust/JevRSI)
  - **描述**：提出 JevRSI，通过 System-1/System-2 协作将 LLM 推理沉淀为可迁移的决策支持：低延迟的 Jev 风格 System-1 负责动作选择，异步 System-2 LLM 递归改进包含流程、状态记忆与世界模型的模块化 harness，并按相关性与历史效用检索模块。实验显示其在保持低延迟的同时匹配或超过 LLM agent，且随着 harness 演化，System-2 干预逐渐减少。

- **Harnesses That Improve Themselves: A Unifying Framework for Self-Improving Agent Harnesses**
  - **作者**：Deep Shah, Nehal Kathrotia
  - **来源**：arXiv:2611.22299（v1，2026-11-17）
  - **链接**：[arXiv:2611.22299](https://arxiv.org/abs/2611.22299) | [PDF](https://arxiv.org/pdf/2611.22299)
  - **描述**：提出自我改进 agent harness 的统一架构与设计框架，将四类可编辑运行时组件（上下文与状态、控制流、动作接口、验证与恢复）与诊断失败、提出代码补丁、验证候选并部署更新的四阶段循环相结合。实验表明带验证门控的模块化演化在 SWE-bench Lite 上优于 prompt 反思与全量 harness 重写，并能在跨模型迁移时限制 token 成本，同时讨论了 prompt 膨胀、benchmark gaming 与 evaluator 篡改等安全问题。

- **Inventa: Decentralized Self-Improving Agents for Autonomous Scientific Discovery**
  - **作者**：Prithwish Jana, Nikos Kanakaris, Purak Jain, Anoop Deoras, Sahika Genc
  - **来源**：arXiv:2611.21847（v1，2026-11-16）
  - **链接**：[arXiv:2611.21847](https://arxiv.org/abs/2611.21847) | [PDF](https://arxiv.org/pdf/2611.21847)
  - **描述**：提出面向自主科学发现的去中心化框架 Inventa：各研究单元由 mutator agent 生成想法谱系，本地 orchestrator 定期适配 mutator 的 harness，并在停滞时更换模型或重启演化；单元之间仅通过记录已验证改进与约束违反的共享知识库通信。在覆盖检索、构思、提案与科学定律发现的五个 benchmark 上均取得领先，例如 EurekaBench 达 73.6%（CORAL 为 56.2%）。

- **Evaluation-Free Recursive Self-Improvement for Coding Agents**
  - **作者**：Zhe Ren, Guowei Rong, Yimeng Chen, Nanbo Li, Piotr Piękos, Mateusz Ostaszewski, Dandan Guo, Jürgen Schmidhuber
  - **来源**：arXiv:2611.21056（v1，2026-11-16）
  - **链接**：[arXiv:2611.21056](https://arxiv.org/abs/2611.21056) | [PDF](https://arxiv.org/pdf/2611.21056)
  - **描述**：针对自我改进 coding agent 在演化循环内反复用下游任务评估来选择候选（evaluate-and-select）成本高且可能过拟合评测分布的问题，提出 Explore-then-Integrate (ELITE)：同代多样化改进后，仅依据结构与运行有效性的确定性检查整合互补机制，循环内不使用下游任务结果。在 SWE-bench Pro 上将初始 agent 从 60.0% 提升至 85.6%，接近 Darwin Gödel Machine (DGM) 与 Huxley-Gödel Machine (HGM)，且无需候选任务评估，演化墙钟时间分别降低 8.8 倍与 3.2 倍。

- **From Recursion to Convolution: Parallel Self-Improvement for Multi-Agent Systems**
  - **作者**：Zheng Wang, Yuang Liu, Sachith Abeywickrama, Yangkai Ding, Tao Yu, Xinyu Zhang, Hongbo Wang, Qi Ye, Xuefeng Jin, Zhangchun Zhao
  - **来源**：arXiv:2611.20891（v1，2026-11-16）
  - **链接**：[arXiv:2611.20891](https://arxiv.org/abs/2611.20891) | [PDF](https://arxiv.org/pdf/2611.20891) | [官方代码](https://github.com/LYA2333/ConvRSI)
  - **描述**：针对多智能体自我改进中顺序依赖易传播误差、限制并行且忽略特征间依赖的问题，提出 ConvRSI，以卷积并行化改进过程：智能体内部卷积联合 refinement 相关特征，智能体间图卷积按协作拓扑聚合消息，并在潜空间中并行更新。在 MATH-500 上相对 RecursiveMAS 提升 5.04% 性能，同时降低 17.27% 推理成本与 45.11% 延迟。

- **Self-Improvement Memory Enables Continual Recursive Self-Improvement**
  - **作者**：Xin Yu, Fei Xia, Jiaqi Pan, Youbao Tang, Chengzhi Liu, Adams Yu, Sicong Jiang, Yanfei Chen, Lingzhou Xue, Ting Yu
  - **来源**：arXiv:2611.18856（v1，2026-11-13）
  - **链接**：[arXiv:2611.18856](https://arxiv.org/abs/2611.18856) | [PDF](https://arxiv.org/pdf/2611.18856)
  - **描述**：研究 Continual Recursive Self-Improvement (CRSI)，即在更换兼容 benchmark 或策略模型后如何延续已有 harness 优化。提出面向 harness 优化器（而非任务策略）的 Self-Improvement Memory (SIM)，按反复出现的 harness 问题归组编辑，并记录理由、预测/观测结果与评估上下文。在四个领域的跨数据集与跨模型延续中优于仅保留 harness 或仅保留根因的延续；在编程任务的配对延续上平均高出 2.36 分。

- **Experience-Handoff Reinforcement Learning for Recursive Self-Improvement**
  - **作者**：Doyoung Kim, Byeongguk Jeon, Kailin Zhang, Sherry Yang
  - **来源**：arXiv:2611.16409（v1，2026-11-12）
  - **链接**：[arXiv:2611.16409](https://arxiv.org/abs/2611.16409) | [PDF](https://arxiv.org/pdf/2611.16409) | [官方代码](https://github.com/doyoungkim-ml/ehrl)
  - **描述**：针对仅用标量奖励做 RL 会丢弃环境细粒度信息、而现有 harness 的经验交接产物（如 playbook）本身未被学习的问题，提出 Experience-Handoff RL (EHRL)：在固定 Agentic Context Engineering (ACE) harness 下训练同一模型同时担任行动、反思与策划，并以对未来 actor rollout 的下游效果评估交接产物。结果表明，agent 训练应同时优化当前动作与未来 rollout 将继承的模型书写经验。

- **When Should Agents Remember? Falsification-Gated Self-Evolution for LLM Agents**
  - **作者**：Runxuan Tang, Haoyu Gao, Yuyan Ding, Junyi Yao, Zihao Zheng, Zecheng Sheng, Liwei Hou
  - **来源**：arXiv:2611.14326（v1，2026-11-10）
  - **链接**：[arXiv:2611.14326](https://arxiv.org/abs/2611.14326) | [PDF](https://arxiv.org/pdf/2611.14326)
  - **描述**：针对智能体将单次任务经验直接写入记忆易导致局部成功演变为不可靠或有害知识的问题，提出基于 verifier 的假说证伪门控框架 FGSE；该方法将候选经验表示为包含前置条件与预期效果的结构化假说，并在临时状态下通过迁移、证伪与回归探针测试后再行接纳，在多个 benchmark 取得强劲表现的同时将有害更新提交率压低至 3.6%。

- **The RSI Tax: When Recursive Self-Improvement Is Not Worth the Cost**
  - **作者**：Yitong Zhang, Ang Li, Yisen Wang
  - **来源**：arXiv:2611.13524（v1，2026-11-10）
  - **链接**：[arXiv:2611.13524](https://arxiv.org/abs/2611.13524) | [PDF](https://arxiv.org/pdf/2611.13524)
  - **描述**：针对递归自我改进（RSI）中能力收益是否能抵消高额演化成本的问题，提出将自我改进过程消耗的 token 成本定义为“RSI Tax”并纳入端到端评估的度量框架；分析表明 verification 阶段占据了三种代表性 RSI 方法总 RSI Tax 的 74.8–93.6%，且简单的 bounded-note baseline 在维持甚至超越已有 RSI 方法准确率的同时可平均节省 65.6–71.0% 的总 token 开销。

- **SciMARS: Multi-Agent Recursive Self-Improvement for Closed-Loop Scientific Discovery**
  - **作者**：Weimin Wu, Han Liu
  - **来源**：arXiv:2611.12552（v1，2026-11-09）
  - **链接**：[arXiv:2611.12552](https://arxiv.org/abs/2611.12552) | [PDF](https://arxiv.org/pdf/2611.12552)
  - **描述**：针对多智能体在闭环科学发现中缺乏共享记忆导致工作重复、且固定流程易延续错误的问题，提出支持多智能体 harness 任务局部递归自适应的 SciMARS 框架；通过共享证据图（evidence graph）与独立组件编辑器来演化角色、协作与记忆策略，SciMARS + Memory 在 Autonomous Science Bench 上将 GPT-6-Astra 的成功次数从 8/18 提升至 12/18（GLM-5.3 为 1/18 至 2/18），并在 ScienceAgentBench 与 AppWorld 上优于基础多智能体团队。

- **Agent Self-Improvement with Frozen Weights: The Added Value and Limits of Failure Traces**
  - **作者**：Arkid Mitra, Snehil Saluja
  - **来源**：arXiv:2611.11342（v2，2026-11-11）
  - **链接**：[arXiv:2611.11342](https://arxiv.org/abs/2611.11342) | [PDF](https://arxiv.org/pdf/2611.11342) | [官方代码与数据](https://github.com/hopit-ai/harness-mistakes-artifacts)
  - **描述**：针对冻结权重的智能体 harness 能否从失败轨迹（failure traces）中有效提取价值的问题展开实证评估；实验发现基于错误经验生成的 notes 仅在受控客服决策任务上带来 4.0 个百分点的额外准确率提升（且约 60% 的改进仅源于保留高分 notes 的搜索机制本身），在完整对话与工具使用测试中则未展现出确证收益，揭示了依赖失败轨迹进行无权重更新自我改进的现实局限。

- **Trustworthy Recursive Self-Improvement with Statistical Guarantees**
  - **作者**：Zihe Gao, Zhengling Qi, Yifan Cui
  - **来源**：arXiv:2611.10787（v1，2026-11-07）
  - **链接**：[arXiv:2611.10787](https://arxiv.org/abs/2611.10787) | [PDF](https://arxiv.org/pdf/2611.10787)
  - **描述**：针对递归自我改进中贪心门控易因验证集噪声误纳劣质更新而导致性能退化的问题，提出具备统计理论保证的演化门控框架 TRUST；通过引入在线多重假设检验并结合大语言模型分析历史上下文以动态调控置信阈值，在 HotpotQA、DROP 和 APPS 等 benchmark 上将劣质更新的平均采纳率从贪心策略的 45.59% 显著降至 2.78%。

- **When the Critic Falls Behind: Co-Evolving Rubrics and Harnesses for Continual Agent Self-Improvement**
  - **作者**：Hao Chen, Yukun Yan, Ziyu Han, Ye He, Chuanzhe Guo, Shangzhan Li, Qi Shi, Qingfu Zhu, Maosong Sun, Wanxiang Che
  - **来源**：arXiv:2610.36826（v1，2026-10-27）
  - **链接**：[arXiv:2610.36826](https://arxiv.org/abs/2610.36826) | [PDF](https://arxiv.org/pdf/2610.36826)
  - **描述**：针对持续自我改进中评估标准（rubric）相对静态导致难以应对智能体演化过程中弱点转移的问题，提出 rubric 与 harness 协同演化框架 RuHarness；通过从执行轨迹中动态发现与重估行为准则以优先定位未解决的弱点并引导针对性 harness 更新，在多样化智能体任务上（尤其是未见测试集）显著优于传统 harness 演化 baseline 并实现了更稳健的持续改进。

- **PluginRSI: Recursive Improvement of Agent Harnesses with Reusable Plugins**
  - **作者**：Yaorui Shi, Yuchun Miao, Yuxin Chen, Jiayuan Zhang, Yueqing Sun, Xierui Song, Xiang Wang, An Zhang
  - **来源**：arXiv:2609.32423（v2，2026-10-18）
  - **链接**：[arXiv:2609.32423](https://arxiv.org/abs/2609.32423) | [PDF](https://arxiv.org/pdf/2609.32423) | [官方代码](https://github.com/syr-cn/PluginRSI) | [项目页](https://syr-cn.github.io/PluginRSI/)
  - **描述**：针对整套程序级搜索优化 harness 导致各组件机制难以解耦和复用的问题，提出将 harness 模块化为可复用插件集合的演化框架 PluginRSI；通过独立优化各个原子化插件并沉淀至共享库中以便后续迭代重组，不仅在软件工程与命令行等任务上优于现有基线，且演化出的插件库能直接迁移至其他模型并加速未见任务的优化收敛。

## 评测与基准 (Benchmarks & Evaluations)

- **RSI-PDEbench: A Benchmark for Self-Improving Agents in PDE Solving**
  - **作者**：Binghang Lu, Lang Cao, Changhong Mou, Yige Sun, Cindy Xiangrui Kong, Zheyuan Deng, Tian Yuan, Bing Hu, Runyu Zhang, Na Lu, Guang Lin
  - **来源**：arXiv:2611.14949（v1，2026-11-11）
  - **链接**：[arXiv:2611.14949](https://arxiv.org/abs/2611.14949) | [PDF](https://arxiv.org/pdf/2611.14949) | [项目页](https://jeremylu916.github.io/RSI-PDE/)
  - **描述**：提出面向自我改进智能体求解 PDE 的基准 RSI-PDEbench，包含 1,001 个案例、42 个方程模板（含分数阶 PDE），并设置 Full、Noisy 与 Hard-OOD 三种评测。智能体需从 256 个解样本中识别方程并编写求解器，在固定预算的自我改进循环中利用反馈，最终以从未见过的 hidden test split 评分。

- **Flex-RSI: Benchmarking Recursive Self-Improvement of Frontier Agents**
  - **作者**：Jingdong Zhang, Jionghao Wang, Zhengming Yu, Yancheng Cai, Wei Chow, Chris Choy, Zhiyang Dou, Hang Hua, Jiachen Li, Zhixuan Liu, Chen Wang, Songlin Wei, Siyuan Yang, Yu Yuan, Xiaohang Zhan, Yucheng Zhang, Shuhong Zheng, Xin Li, Lingjie Liu, Wojciech Matusik, Zhengzhong Tu, Wenping Wang
  - **来源**：arXiv:2611.08946（v1，2026-11-06）
  - **链接**：[arXiv:2611.08946](https://arxiv.org/abs/2611.08946) | [PDF](https://arxiv.org/pdf/2611.08946) | [官方代码](https://github.com/flex-rsi/rsi-bench) | [项目页](https://flex-rsi.github.io)
  - **描述**：针对现有评测大多固定 harness 或侧重模型权重更新而缺乏对智能体自我修改交互机制评估的问题，提出面向视觉与具身机器人任务的递归自我改进 benchmark 平台 Flex-RSI；通过在固定预算下设立方案改进与 harness（含自身）演化的双层迭代循环，实验发现修改 harness 本身对性能收益具有实质贡献，且仅提供二元成败反馈会显著制约开源模型的自进化上限。

- **SelfImprove-Bench: Evaluating Generalization in Self-Improving Agents**
  - **作者**：Bangrui Xu, Jie Yang, Sidi Chen, Xuanhe Zhou, Jiantao Qiu, Qianyu Yang, Zijie Wang, Fan Wu, Zhoufutu Wen
  - **来源**：arXiv:2611.02797（v1，2026-11-02）
  - **链接**：[arXiv:2611.02797](https://arxiv.org/abs/2611.02797) | [PDF](https://arxiv.org/pdf/2611.02797) | [官方代码](https://github.com/theseus-labs-rsi/SelfImprove-Bench) | [项目页](https://theseus-labs-rsi.github.io/SelfImprove-Bench)
  - **描述**：针对现有 RSI 评估缺乏可靠指标区分真实能力泛化与特定场景过拟合（scenario fitting）的问题，提出面向自我改进智能体的标准化评测框架 SelfImprove-Bench；围绕探索、规划与推理三大核心能力构建基于游戏的可控生成任务，并划分出 G0 至 G4 的泛化阶梯（generalization ladder），实验揭示了现有 RSI 方法在跨层级泛化表现上的显著不一致性。

- **RSI-Env: An Open-Ended Environment for Recursive Self-Improvement of Agents**
  - **作者**：Wanying Qu, Zhiyuan Fan, Jiyao Liu, Jiang Zhou, Jianghan Shen, Yanwei Fu, Dongrui Liu
  - **来源**：arXiv:2611.01736（v1，2026-11-01）
  - **链接**：[arXiv:2611.01736](https://arxiv.org/abs/2611.01736) | [PDF](https://arxiv.org/pdf/2611.01736)
  - **描述**：针对现有 RSI 方法常限制优化目标、可编辑组件或评估流程、从而难以跨代持续开放探索的问题，提出持久化环境 RSI-Env，由独立 Host Controller 管理服务、评估与版本，并在 Self 设定下由被接受的 model-harness 接管下一轮改进；在 Open-General、Capability-Directed 与 Benchmark-Guided 三种设定中，Open-General Self 将 GPQA Diamond 准确率从 65.2% 提升至 73.2%，并展示了跨系统更新的持续改进，同时也暴露了跨能力保持收益的困难。

- **VerifierBench: Benchmarking the Generation of Executable Verifiers for LLM Agents**
  - **作者**：Jianing Yin, Ziyi Chen, Hao Wang, Yiyou Sun, Zijian Jin, Dawn Song, Daoan Zhang
  - **来源**：arXiv:2610.28679（v2，2026-10-30）
  - **链接**：[arXiv:2610.28679](https://arxiv.org/abs/2610.28679) | [PDF](https://arxiv.org/pdf/2610.28679) | [项目页](https://verifierbench.github.io/)
  - **描述**：针对智能体自动生成可执行 verifier 缺乏系统化衡量标准的问题，提出涵盖工具调用、环境状态与代码验证的评测基准 VerifierBench 及包含 6 项审计检查的 V4V 过滤机制；测试 19 款模型发现其归一化平衡准确率处于 10.6 至 62.1 之间，且生成的验证器普遍呈现出“识别无效方案优于接纳有效解”的过度严苛倾向，常因错误的先验假设导致有效方案被全盘误拒。
