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

- **System-One RSI: Building Muscle Memory for Interactive Agents through Guided Practice**
  - **作者**：Qingxu Fu, Xuanfa Jin, Ziqian Chen, Zhaoyang Liu, Bolin Ding
  - **来源**：arXiv:2611.26007（v1，2026-11-19）
  - **链接**：[arXiv:2611.26007](https://arxiv.org/abs/2611.26007) | [PDF](https://arxiv.org/pdf/2611.26007)
  - **描述**：将高频在线内部 OODA 循环（由决策模型将视觉观测与任务问题映射为结构化判断，并由决策树在无需调用推理模型下转换为定时动作）与推理 agent 团队驱动的离线外部递归改进循环相结合，通过更新 prompt、决策树及参数将学得特征固化为外部“肌肉记忆”（muscle memory）。框架仅需少量真实回合，且无需专家演示、环境修改、沙盒或并行仿真。在 27B 决策模型上，贪吃蛇（Snake）平均得分由 1.30 升至 7.35；在所评估的《绝区零》（Zenless Zone Zero）场景中，完成时间中位数下降 8.4%；在所评估的《黑神话：悟空》（Black Myth: Wukong）战斗场景中，规避策略的平均存活时间达到静止对照的 11 倍，进攻策略胜率在所评估配置上由 0% 升至 66.7%。

- **Think Offline, Act in Real Time: Self-Improving Visual Game Agents through Code**
  - **作者**：Zipeng Qiu, Shusheng Xu, Jiale Li, Yukun Zhou, Chenyue Li, Wenshuang Li, Tongkai Yang, Binhang Yuan
  - **来源**：arXiv:2611.24590（v1，2026-11-18）
  - **链接**：[arXiv:2611.24590](https://arxiv.org/abs/2611.24590) | [PDF](https://arxiv.org/pdf/2611.24590) | [官方代码](https://github.com/TabibitoQZP/SIGame)
  - **描述**：研究智能体在游戏持续运行且仅能观察屏幕的情况下，如何通过自身少量尝试在陌生实时视觉游戏中实现自我改进，对比了 model-as-policy（实时分块结合训练好的 2B 控制器）与 code-as-policy（模型在尝试间隙编写、测试和修改代码程序并在游戏时由程序执行动作）两种范式。在 170 个 GameWorld 任务中（每次运行最多进行 8 次 1 分钟执行），code-as-policy 达到 47.80% 的平均进度，显著优于训练控制器的 30.90%，并在全部 5 个游戏类别中均保持领先。

- **BaseRSI: Recursive Self-Improvement of a Base Vision-Language Model via Training-Free Harness Internalization**
  - **作者**：Mingda Zhang, Yuanhao Dong, Qiang Huang, Rui Qian, Yanjin Li, Zhenyu Liu, Xiao Huang, Zihao Yang, Jian Wang, Pinjia He, Xiaoying Tang
  - **来源**：arXiv:2611.24578（v1，2026-11-18）
  - **链接**：[arXiv:2611.24578](https://arxiv.org/abs/2611.24578) | [PDF](https://arxiv.org/pdf/2611.24578) | [官方代码](https://github.com/beita6969/BaseRSI)
  - **描述**：提出递归 Harness 内化（Recursive Harness Internalization）框架 BaseRSI，使基座视觉语言模型在多轮自我响应中先优化自身 harness，再通过免训练（training-free）编辑将 harness 带来的增益直接写入自身权重。引入利用每层激活差异在低维子空间更新权重的 ReGap，以及通过回归将信号写入各块少量键值神经元的 ReKey，仅凭前向传播即可在单个检查点复合不同位置的编辑，在 10 个分布内及留出视觉推理基准上均提升了基座模型性能。

- **Improve How You Improve: Recursive Policy Self-Improvement for Zero-Shot Open-Vocabulary Multi-Object Navigation**
  - **作者**：Yang Li, Ziju Han, Aming WU, Zihao Zhang, Sijia Zhang, Yahong Han, Qinghua Hu
  - **来源**：arXiv:2611.23774（v1，2026-11-18）
  - **链接**：[arXiv:2611.23774](https://arxiv.org/abs/2611.23774) | [PDF](https://arxiv.org/pdf/2611.23774)
  - **描述**：针对零样本开放词表多目标导航中问题诊断与规则修订机制通常由人工设计且保持固定的缺陷，提出递归策略自我改进框架 RPSI-Nav，同时优化导航程序及其自身的修订机制。该方法通过诊断搜索行为、在观测歧义时请求诊断视角以生成针对性导航规则，并将后续目标搜索的反馈反向关联至规则生成逻辑，从而动态改进故障诊断、观测获取与规则修订规划。

- **Safe Personal RSI: Evaluating and Repairing Personal-Agent Updates**
  - **作者**：Jiapeng Pei, Yuhang Yao, Sitan Liu, Hanxin Chen, Hao Li, Guogeng Li, Jiapei Liu, Ruijie Chen, Hongshan Lin, Yang Mo, Tianyu Shi, Shangding Gu
  - **来源**：arXiv:2611.23651（v1，2026-11-18）
  - **链接**：[arXiv:2611.23651](https://arxiv.org/abs/2611.23651) | [PDF](https://arxiv.org/pdf/2611.23651)
  - **描述**：针对个人健康助手 Kicker 提出更新评估组件 Safe Personal RSI，在固定模型权重与运行代码的前提下将自我改进约束为 prompt 更新，通过测试候选与当前指令、复现失败用例、暂撤修改以指导修复，并在采纳前检查安全与任务表现（若无版本通过则保留原指令）。可执行基准包含 29 个邮件、日历、健康与市场用例，并另设权限复用、记忆和工具输出注入探针；在 3 个模型与两次刻意设计的高风险编辑上，该流程拒绝了 21 次更新尝试中的 20 次。修复确认中，一次获准的 GPT-5.6 Luna 修复将攻击违规率从 10.7% 降至 0%，并将安全任务完成率从 89.7% 提升至 100%；在更强攻击下，从 Qwen2.5-7B-Instruct 迁移到 Qwen3-14B 的修复将违规率从 69.0% 降至 17.9%，安全任务完成率从 19.5% 提升至 64.4%。

- **GUARD: Stabilizing Recursive Self-Improvement with Regret Guidance**
  - **作者**：Minghe Zhang, Xuetao Kang, Yifei Ming, Yanfei Chen, Han Yu, Yufan Zhuang, Chen-Yu Lee
  - **来源**：arXiv:2611.23476（v1，2026-11-17）
  - **链接**：[arXiv:2611.23476](https://arxiv.org/abs/2611.23476) | [PDF](https://arxiv.org/pdf/2611.23476)
  - **描述**：针对冻结基座模型与可编辑 harness（prompts、skills、工具规则与记忆）的自主智能体，提出无需外部评分器的闭环持续 harness 演化框架 GUARD，将任务解耦为执行前自检并利用方向性遗憾（directional regret）引导更新。通过无评估器群体相对适应度筛选并行候选编辑，并利用 Soft-HURT 门控在增益大于退化时推进更新以保证门控缓冲区的非退化，在记忆、技能演化和持续任务流等多项基准上避免了灾难性遗忘与记忆污染，并显著降低了部署 token 开销。

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
  - **来源**：arXiv:2611.22432（v3，2026-11-19）
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

- **ESI: An Embodied Self-Improvement Flywheel for LLM-VLA Agents**
  - **作者**：Yundi Cai, Zihan Wang, Chenxi Han, Yi Cheng, Houde Liu, Zilei Wang
  - **来源**：arXiv:2611.18176（v2，2026-11-16）
  - **链接**：[arXiv:2611.18176](https://arxiv.org/abs/2611.18176) | [PDF](https://arxiv.org/pdf/2611.18176) | [官方代码](https://github.com/ZERITH-ZLab/ESI)
  - **描述**：提出面向模块化 LLM-VLA 智能体的具身自我改进飞轮 ESI（Embodied Self-Improvement），将模块化智能体作为后训练单元，通过环境交互反复协同优化 LLM 提示词、共享技能接口与 VLA 参数并联合重新部署。利用 LLM 子任务决策提供语义监督，并以有效纠偏及后续学生模型执行提供动作级监督，在 10 个选定的 RoboDojo 任务上取得了 62.03 的平均得分与 49.41% 的平均成功率。

- **Experience-Handoff Reinforcement Learning for Recursive Self-Improvement**
  - **作者**：Doyoung Kim, Byeongguk Jeon, Kailin Zhang, Sherry Yang
  - **来源**：arXiv:2611.16409（v1，2026-11-12）
  - **链接**：[arXiv:2611.16409](https://arxiv.org/abs/2611.16409) | [PDF](https://arxiv.org/pdf/2611.16409) | [官方代码](https://github.com/doyoungkim-ml/ehrl)
  - **描述**：针对仅用标量奖励做 RL 会丢弃环境细粒度信息、而现有 harness 的经验交接产物（如 playbook）本身未被学习的问题，提出 Experience-Handoff RL (EHRL)：在固定 Agentic Context Engineering (ACE) harness 下训练同一模型同时担任行动、反思与策划，并以对未来 actor rollout 的下游效果评估交接产物。结果表明，agent 训练应同时优化当前动作与未来 rollout 将继承的模型书写经验。

- **Evidence-Governed Adoption of Self-Generated Updates in Autonomous AI Agents**
  - **作者**：Subodh Lonkar
  - **来源**：arXiv:2611.16378（v1，2026-11-12）
  - **链接**：[arXiv:2611.16378](https://arxiv.org/abs/2611.16378) | [PDF](https://arxiv.org/pdf/2611.16378)
  - **描述**：提出治理自主智能体自我生成修改（prompts、记忆、工具、工作流与策略）采纳决策的证据治理演化框架 EGE（Evidence-Governed Evolution），将候选生成与确认采纳解耦，在新鲜配对审计上评估冻结候选，要求在预先指定的主目标上取得有意义改进，并以相对参照（reference）的非劣效检验保护已声明能力，再在有界金丝雀部署前施加治理约束。它为可数的自适应生成候选序列建立了评估器校准的同时下界（结合逐候选 Hoeffding 界，以及比较操作评估器与预定参照程序的独立校准样本），并通过桥接测试形式化参照替换，推导出沿版本化参照谱系的累积退化界。

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

- **AdaRSI: On-Demand Recursive Self-Improvement for Embodied Agents**
  - **作者**：Peidong Wang, Ying Chang, Zhiming Ma, Lirong Che, Zihao Liu, Xiaocui Yang, Shi Feng, Daqi Liu, Yuzhe Yang, Xu Cao, Chuang Wang, Jian Su, Daling Wang
  - **来源**：arXiv:2610.20474（v2，2026-11-17）
  - **链接**：[arXiv:2610.20474](https://arxiv.org/abs/2610.20474) | [PDF](https://arxiv.org/pdf/2610.20474)
  - **描述**：提出面向具身智能体的按需递归自我改进框架 AdaRSI：由代码 agent 先优化工具与流程，针对测试替代指令后仍不可靠的子步骤自主采集演示并利用临时微调探针验证效用，进而跨任务汇总数据训练出协同执行的专用 VLA。在 RoboCasa365 未见复合任务上成功率由 4.6% 升至 13.3%，在扰动后的 LIBERO-Pro 2.0 任务上由 32.9% 升至 49.1%；在 RoboCasa365 的 Composite-Unseen 子集上，其成功率高于适配每一个操作子步骤的做法，同时只使用了 34% 的 GPU 时间和 36% 的演示数据。在真实机器人上，该智能体可自主采集演示并适配执行器以回收倒伏瓶子，从而提升任务完成表现。

- **PluginRSI: Recursive Improvement of Agent Harnesses with Reusable Plugins**
  - **作者**：Yaorui Shi, Yuchun Miao, Yuxin Chen, Jiayuan Zhang, Yueqing Sun, Xierui Song, Xiang Wang, An Zhang
  - **来源**：arXiv:2609.32423（v2，2026-10-18）
  - **链接**：[arXiv:2609.32423](https://arxiv.org/abs/2609.32423) | [PDF](https://arxiv.org/pdf/2609.32423) | [官方代码](https://github.com/syr-cn/PluginRSI) | [项目页](https://syr-cn.github.io/PluginRSI/)
  - **描述**：针对整套程序级搜索优化 harness 导致各组件机制难以解耦和复用的问题，提出将 harness 模块化为可复用插件集合的演化框架 PluginRSI；通过独立优化各个原子化插件并沉淀至共享库中以便后续迭代重组，不仅在软件工程与命令行等任务上优于现有基线，且演化出的插件库能直接迁移至其他模型并加速未见任务的优化收敛。

- **Designer-RSI: Evolving Procedural Memory for Graphic Design Agent**
  - **作者**：Hongyang Du, Lan Yan, Christian Flores, Asim Kadav
  - **来源**：arXiv:2609.22086（v2，2026-11-18）
  - **链接**：[arXiv:2609.22086](https://arxiv.org/abs/2609.22086) | [PDF](https://arxiv.org/pdf/2609.22086)
  - **描述**：针对调用逾 230 种光栅、矢量与排版工具的平面设计智能体，在冻结基座模型权重下从无标注设计轨迹中演化模块化 SKILL.md 技能库，将拓宽（widening，填补常发能力缺口）与深化（deepening，对比成败运行修订失效技能）相结合，并通过帕累托风格的配对回放门控确保更新无局部退化。在留出产品需求、8 个外部基准及两款基座模型上，基于实际交互流量的演化将执行成功率提升至高达 99.8%，并对基础智能体取得高达 67.6% 的盲测胜率，消融实验进一步证实了技能获取与修订的高度协同性。

- **Meta$^n$: Recursive Self-Improvement through Emergent Depth**
  - **作者**：Zae Myung Kim, Young-Jun Lee, Seungyeon Jwa, Dongyeop Kang
  - **来源**：arXiv:2608.24735（v2，2026-11-18）
  - **链接**：[arXiv:2608.24735](https://arxiv.org/abs/2608.24735) | [PDF](https://arxiv.org/pdf/2608.24735) | [官方代码](https://github.com/minnesotanlp/meta-n)
  - **描述**：针对多数自我改进系统仅优化答案或固定元层级（meta-level）的问题，提出保持元操作 $\Omega$ 固定并对其输入进行递归的 Meta$^n$，通过反复作用于自身产物，读取下层求解栈的轨迹与代码，并将下一层生成为策略性预处理与可调用 helper 库。其递归深度由收敛性自适应决定并利用演化归档搜索层链，在两款基座模型上的 8 个基准族中均超越先前的自我改进智能体（在 ARC-AGI-2 上是唯一得分大于零的方法），且随着层深增加自然涌现出不同的分工角色。

## 评测与基准 (Benchmarks & Evaluations)

- **RSIBench-Infra: Can Agents Optimize Their Own Training and Inference Infrastructure at Production Scale?**
  - **作者**：Hanlin Wu, Yifei Wang, Zhicheng Cai, Huan-ang Gao, Wei-Ying Ma, Ya-Qin Zhang, Jingjing Liu, Hao Zhou
  - **来源**：arXiv:2611.24395（v1，2026-11-18）
  - **链接**：[arXiv:2611.24395](https://arxiv.org/abs/2611.24395) | [PDF](https://arxiv.org/pdf/2611.24395) | [项目页](https://rsibench-infra.github.io)
  - **描述**：提出评估智能体能否在生产规模下优化自身训练与推理基础设施的基准 RSIBench-Infra，包含 20 项跨模型族与模态的训练与推理任务，部署规模可达 NVIDIA GPU 与昇腾（Ascend）NPU 上的 32 个加速器。智能体从官方基线出发修改引擎、算子内核（kernel）及指令层软件栈，并通过 OCI 镜像层协议实现可复现部署；在严格质量约束下，全部任务结果中有 66.2% 获得了超 1.10 倍的经核验加速比，揭示了当前智能体具备优化生产基础设施的能力，但将局部优化转化为端到端收益仍具挑战。

- **RSI-PDEbench: A Benchmark for Self-Improving Agents in PDE Solving**
  - **作者**：Binghang Lu, Lang Cao, Changhong Mou, Yige Sun, Cindy Xiangrui Kong, Zheyuan Deng, Tian Yuan, Bing Hu, Runyu Zhang, Na Lu, Guang Lin
  - **来源**：arXiv:2611.14949（v1，2026-11-11）
  - **链接**：[arXiv:2611.14949](https://arxiv.org/abs/2611.14949) | [PDF](https://arxiv.org/pdf/2611.14949) | [项目页](https://jeremylu916.github.io/RSI-PDE/)
  - **描述**：提出面向自我改进智能体求解 PDE 的基准 RSI-PDEbench，包含 1,001 个案例、42 个方程模板（含分数阶 PDE），并设置 Full、Noisy 与 Hard-OOD 三种评测。智能体需从 256 个解样本中识别方程并编写求解器，在固定预算的自我改进循环中利用反馈，最终以从未见过的 hidden test split 评分。

- **Continual-ARC: Measuring Skill Acquisition over a Working Lifetime**
  - **作者**：Daniel Lenton, Yusha Arif, Haris Mahmood
  - **来源**：arXiv:2611.14505（v3，2026-11-15）
  - **链接**：[arXiv:2611.14505](https://arxiv.org/abs/2611.14505) | [PDF](https://arxiv.org/pdf/2611.14505) | [官方代码](https://github.com/unifyai/continual-arc) | [项目页](https://continual-arc.unify.ai)
  - **描述**：基于三个版本的 ARC-AGI 构建终身数据流基准 Continual-ARC，在统一尺度下对比智能体 harness 与测试时基于参数/权重的持续学习（continual learning），通过在交替出现的休眠任务与新任务实例中限制反馈预算，并在数据流结束后评估冻结模型的记忆与泛化能力。在 Qwen3.5-9B 和 GLM-5.3 Flash 等模型上的实验表明，harness 的持久化（persistence）若缺乏显式专家指导通常无法改善记忆，且多数基于 harness 的方法学到的知识甚至低于仅缓存各任务演示数据的基准下限。

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
