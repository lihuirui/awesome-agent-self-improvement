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

- **Veritas: A Verifier Generation Harness for Agent Tasks**
  - **作者**：Daoan Zhang, Qinbo Bai, Dehai Min, Xingyu Mu, Ziyi Chen, Jianing Yin
  - **来源**：arXiv:2611.13336（v1，2026-11-09）
  - **链接**：[arXiv:2611.13336](https://arxiv.org/abs/2611.13336) | [PDF](https://arxiv.org/pdf/2611.13336)
  - **描述**：针对自我改进系统中人工编写 verifier 成本高且难以规模化的问题，提出自动生成 verifier 的 harness 工具 Veritas；通过引入证据头（evidence header）、领域规则库及经自我改进循环优化的编写原则，显著提升了生成验证器在多个 benchmark 上与官方判定的一致性。

## Agent 自我改进与 RSI (Agent Self-Improvement & RSI)

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
  - **作者**：Arkid Mitra
  - **来源**：arXiv:2611.11342（v1，2026-11-08）
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
