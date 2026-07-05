# Awesome Agent Memory

A curated taxonomy of **agent memory systems**, organized along four axes: (1) memory system architectures — from flat sequential context, to structural topological graphs/trees, to multi-paradigm hybrid containers; (2) reference baselines for comparison; (3) benchmarks for evaluation; and (4) surveys on agent memory.

## 📣 Get Involved

- 📊 **Looking for a testbed to evaluate agent memory systems?** See our companion repo [OpenDataBox/MemoryData](https://github.com/OpenDataBox/MemoryData) — an integrated platform of memory systems and datasets.
- 📌 **Missing a paper, method, or benchmark?** [Open an issue](https://github.com/OpenDataBox/awesome-agent-memory/issues/new) to request it.
- 🤝 **Want to contribute directly?** [Submit a Pull Request](https://github.com/OpenDataBox/awesome-agent-memory/compare) — community PRs are warmly welcomed!

![](AgentMemory.png)

## Table of Contents

- [Memory Systems](#memory-systems)
  - [Sequential Context](#sequential-context)
  - [Structural Topological](#structural-topological)
  - [Multi-Paradigm Hybrid](#multi-paradigm-hybrid)
- [Reference Baselines](#reference-baselines)
  - [Context-Based Baselines](#context-based-baselines)
  - [Retrieval-Based Baselines](#retrieval-based-baselines)
- [Benchmarks](#benchmarks)
- [Surveys on Agent Memory](#surveys-on-agent-memory)



## Memory Systems

### Sequential Context

Systems that model memory as flat, one-dimensional sequences lacking explicit structural abstractions.

1. **MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation**
   Junru Lu, Siyu An, Mingbao Lin, et al. *arXiv 2023*. [[Paper](https://arxiv.org/abs/2308.08239)]

2. **Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory**
   Prateek Chhikara, Dev Khant, Saket Aryan, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2504.19413)] [[Github](https://github.com/mem0ai/mem0)]

3. **MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents**
   Zijian Zhou, Ao Qu, Zhaoxuan Wu, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2506.15841)]

4. **MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent**
   Hongli Yu, Tinghong Chen, Jiangtao Feng, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2507.02259)]

[⬆️top](#table-of-contents)

### Structural Topological

Systems that abstract memory into structured graph and tree topologies with interconnected nodes and edges.

5. **MemTree: From Isolated Conversations to Hierarchical Schemas: Dynamic Tree Memory Representation for LLMs**
   Alireza Rezazadeh, Zichao Li, Wei Wei, Yujia Bao. *ICLR 2025*. [[Paper](https://openreview.net/forum?id=moXtEmCleY)]

6. **Zep: A Temporal Knowledge Graph Architecture for Agent Memory**
   Preston Rasmussen, Pavel Paliychuk, Travis Beauvais, Jesse Ryan. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2501.13956)] [[Github](https://github.com/getzep/zep)]

7. **Mem0 (Graph Mode, Mem0^g)**: Graph-variant of Mem0 that formalizes memory as a directed labeled graph with entity-relation triplets, using a heterogeneous multi-engine (vector + graph DB) backend. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2504.19413)] [[Github](https://github.com/mem0ai/mem0)]

8. **Cognee: Optimizing the Interface Between Knowledge Graphs and LLMs for Complex Reasoning**
   Vasilije Markovic, Lazar Obradovic, Laszlo Hajdu, Jovan Pavlovic. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2505.24478)] [[Github](https://github.com/topoteretes/cognee)]

[⬆️top](#table-of-contents)

### Multi-Paradigm Hybrid

Systems that package memory into complex, multi-part data containers combining unstructured text with structured metadata; some also route memory across heterogeneous backends.

9. **LightMem: Lightweight and Efficient Memory-Augmented Generation**
   Jizhan Fang, Xinle Deng, Haoming Xu, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2510.18866)]

10. **SimpleMem: Efficient Lifelong Memory for LLM Agents**
    Jiaqi Liu, Yaofeng Su, Peng Xia, et al. *arXiv 2026*. [[Paper](https://arxiv.org/abs/2601.02553)]

11. **MemOS: A Memory OS for AI System**
    Zhiyu Li, Shichao Song, Chenyang Xi, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2507.03724)] [[Github](https://github.com/MemTensor/MemOS)]

12. **MemoryOS: Memory OS of AI Agent**
    Jiazheng Kang, Mingming Ji, Zhe Zhao, Ting Bai. *EMNLP 2025*. [[Paper](https://arxiv.org/abs/2506.06326)] [[Github](https://github.com/BAI-LAB/MemoryOS)]

13. **A-MEM: Agentic Memory for LLM Agents**
    Wujiang Xu, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2502.12110)] [[Github](https://github.com/agiresearch/A-mem)]

14. **Letta (MemGPT): Towards LLMs as Operating Systems**
    Charles Packer, Vivian Fang, Shishir G. Patil, et al. *arXiv 2023*. [[Paper](https://arxiv.org/abs/2310.08560)] [[Github](https://github.com/letta-ai/letta)]

[⬆️top](#table-of-contents)



## Reference Baselines

### Context-Based Baselines

1. **Long Context**: A naive baseline that passes the full conversation history directly into the LLM context window without any external memory system. While effective on some tasks, it results in unacceptable latencies and token costs for production deployments.

### Retrieval-Based Baselines

1. **Embedding RAG**: A standard dense retrieval baseline that embeds past interactions into vectors and performs top-k similarity search, without any memory-specific extraction, maintenance, or routing logic.

2. **BM25**: A sparse lexical retrieval baseline using Okapi BM25 scoring for full-text search, evaluated in the appendix experiments.

3. **Contriever**: An unsupervised dense retrieval model used as a retrieval baseline in the appendix experiments. *ICLR 2023*. [[Paper](https://arxiv.org/abs/2112.09118)]

4. **GraphRAG**: A graph-based retrieval-augmented generation approach that constructs a knowledge graph from documents and retrieves via graph traversal. *arXiv 2024*. [[Paper](https://arxiv.org/abs/2404.16130)]

5. **HippoRAG**: A retrieval-augmented generation method inspired by the hippocampal memory indexing theory, using knowledge graph triples and dense vector embeddings. *NeurIPS 2024*. [[Paper](https://arxiv.org/abs/2405.14831)]

[⬆️top](#table-of-contents)



## Benchmarks

The following benchmarks are used to evaluate agent memory systems, covering task effectiveness, retrieval fidelity, update robustness, long-horizon stability, and operational cost.

### Accuracy

Benchmarks primarily reporting exact answer correctness, task success, tool-call correctness, or state consistency.

1. **HotpotQA: A Dataset for Diverse, Explainable Multi-hop Question Answering** ![](https://img.shields.io/badge/-113K_QA-lightgrey) ![](https://img.shields.io/badge/-multi_hop_QA-blue) ![](https://img.shields.io/badge/-explainable_reasoning-yellowgreen) ![](https://img.shields.io/badge/-supporting_facts-orange)
   *Zhilin Yang, Peng Qi, Saizheng Zhang, et al. EMNLP, 2018.* [[Paper](https://arxiv.org/abs/1809.09600)] [[Dataset](https://hotpotqa.github.io/)] [[Github](https://github.com/hotpotqa/hotpot)]
   - Metrics: Exact Match, F1, Supporting Fact EM/F1, Joint EM/F1.

2. **LongBench v2: Towards Deeper Understanding and Reasoning on Realistic Long-context Multitasks** ![](https://img.shields.io/badge/-503_QA-lightgrey) ![](https://img.shields.io/badge/-single_doc_QA-blue) ![](https://img.shields.io/badge/-multi_doc_QA-blue) ![](https://img.shields.io/badge/-long_context-purple) ![](https://img.shields.io/badge/-structured_data-orange)
   *Yushi Bai, Shangqing Tu, Jiajie Zhang, et al. ACL 2025 / arXiv 2024.* [[Paper](https://arxiv.org/abs/2412.15204)] [[Dataset](https://huggingface.co/datasets/zai-org/LongBench-v2)] [[Github](https://github.com/THUDM/LongBench)]
   - Metrics: Accuracy over single-document QA, multi-document QA, long in-context learning, long-dialogue history, code repository, and long structured data.

3. **MuSiQue: Multihop Questions via Single-hop Question Composition** ![](https://img.shields.io/badge/-49.6K_QA-lightgrey) ![](https://img.shields.io/badge/-multi_hop_QA-blue) ![](https://img.shields.io/badge/-connected_reasoning-yellowgreen) ![](https://img.shields.io/badge/-answerability-orange)
   *Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, Ashish Sabharwal. TACL, 2022.* [[Paper](https://arxiv.org/abs/2108.00573)] [[Dataset](https://github.com/stonybrooknlp/musique)]
   - Metrics: Answer F1, Support F1, An+Sf, Sp+Sf.

4. **Mem2ActBench: A Benchmark for Evaluating Long-Term Memory Utilization in Task-Oriented Autonomous Agents** ![](https://img.shields.io/badge/-2K_sessions-lightgrey) ![](https://img.shields.io/badge/-400_tasks-lightgrey) ![](https://img.shields.io/badge/-tool_use-purple) ![](https://img.shields.io/badge/-memory_action_alignment-green) ![](https://img.shields.io/badge/-parameter_grounding-orange)
   *Yiting Shen, Kun Li, Wei Zhou, Songlin Hu. ACL 2026 / arXiv 2026.* [[Paper](https://arxiv.org/abs/2601.19935)] [[Dataset](https://anonymous.4open.science/r/Mem2ActBench-29AC/)] [[Github](https://github.com/Cantaloupe-M/Mem2ActBench)]
   - Metrics: Parameter-level F1, BLEU-1, Tool Accuracy.

5. **MemGUI-Bench: Benchmarking Memory of Mobile GUI Agents in Dynamic Environments** ![](https://img.shields.io/badge/-128_tasks-lightgrey) ![](https://img.shields.io/badge/-26_apps-lightgrey) ![](https://img.shields.io/badge/-mobile_GUI-purple) ![](https://img.shields.io/badge/-cross_app_workflow-green) ![](https://img.shields.io/badge/-progressive_judge-orange)
   *Guangyi Liu, Pengxiang Zhao, Yaozhen Liang, et al. arXiv 2026.* [[Paper](https://arxiv.org/abs/2602.06075)] [[Dataset](https://memgui-bench.github.io/)] [[Github](https://github.com/lgy0404/MemGUI-Bench)]
   - Metrics: Pass@k, task success rate, memory-task proficiency ratio, staged LLM-as-a-judge result.

[⬆️top](#table-of-contents)

### Recall

Benchmarks primarily measuring whether relevant facts, evidence, memories, or long-context needles are retrieved and used.

1. **LoCoMo: Evaluating Very Long-Term Conversational Memory of LLM Agents** ![](https://img.shields.io/badge/-1.9K_QA-lightgrey) ![](https://img.shields.io/badge/-10_dialogues-lightgrey) ![](https://img.shields.io/badge/-long_conversation-green) ![](https://img.shields.io/badge/-temporal_QA-orange) ![](https://img.shields.io/badge/-multimodal_dialogue-purple)
   *Adyasha Maharana, Dong-Ho Lee, Sergey Tulyakov, et al. ACL 2024.* [[Paper](https://arxiv.org/abs/2402.17753)] [[Dataset](https://github.com/snap-research/LoCoMo)] [[Project](https://snap-research.github.io/locomo/)]
   - Metrics: F1, Recall, ROUGE, FactScore, MM-Relevance, BLEU.

2. **LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory** ![](https://img.shields.io/badge/-500_queries-lightgrey) ![](https://img.shields.io/badge/-115K_to_1.5M_tokens-lightgrey) ![](https://img.shields.io/badge/-cross_session_QA-green) ![](https://img.shields.io/badge/-knowledge_update-orange) ![](https://img.shields.io/badge/-temporal_reasoning-yellowgreen)
   *Di Wu, Hongwei Wang, Wenhao Yu, et al. ICLR 2025.* [[Paper](https://arxiv.org/abs/2410.10813)] [[Dataset](https://github.com/xiaowu0162/LongMemEval)] [[Project](https://xiaowu0162.github.io/long-mem-eval/)]
   - Metrics: Accuracy / LLM-Judge over information extraction, multi-session reasoning, temporal reasoning, knowledge update, and abstention.

3. **MemBench: Towards More Comprehensive Evaluation on the Memory of LLM-based Agents** ![](https://img.shields.io/badge/-53K_questions-lightgrey) ![](https://img.shields.io/badge/-65K_sessions-lightgrey) ![](https://img.shields.io/badge/-factual_memory-green) ![](https://img.shields.io/badge/-reflective_memory-yellowgreen) ![](https://img.shields.io/badge/-capacity_test-orange) ![](https://img.shields.io/badge/-efficiency-red)
   *Haoran Tan, Zeyu Zhang, Chen Ma, et al. ACL 2025 Findings.* [[Paper](https://arxiv.org/abs/2506.21605)] [[Dataset](https://github.com/import-myself/Membench)]
   - Metrics: Memory Accuracy, Memory Recall, Memory Capacity, Memory Efficiency.

4. **MemoryAgentBench: Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions** ![](https://img.shields.io/badge/-2,071_QA-lightgrey) ![](https://img.shields.io/badge/-2.1K_items-lightgrey) ![](https://img.shields.io/badge/-accurate_retrieval-green) ![](https://img.shields.io/badge/-test_time_learning-orange) ![](https://img.shields.io/badge/-long_range_understanding-purple) ![](https://img.shields.io/badge/-conflict_resolution-yellowgreen)
   *Yuanzhe Hu, Yu Wang, Julian McAuley. arXiv 2025.* [[Paper](https://arxiv.org/abs/2507.05257)] [[Dataset](https://www.modelscope.cn/datasets/AI-ModelScope/MemoryAgentBench)] [[Github](https://github.com/HUST-AI-HYZ/MemoryAgentBench)]
   - Metrics: Accuracy, Exact Match/SubEM, Recall@5, F1 / LLM-as-a-judge across accurate retrieval, test-time learning, long-range understanding, and conflict-resolution accuracy.

5. **RULER: What's the Real Context Size of Your Long-Context Language Models?** ![](https://img.shields.io/badge/-13_tasks-lightgrey) ![](https://img.shields.io/badge/-synthetic_benchmark-purple) ![](https://img.shields.io/badge/-needle_in_haystack-green) ![](https://img.shields.io/badge/-multi_hop_tracing-blue) ![](https://img.shields.io/badge/-aggregation-orange)
   *Cheng-Ping Hsieh, Simeng Sun, Samuel Kriman, et al. COLM 2024.* [[Paper](https://arxiv.org/abs/2404.06654)] [[Dataset](https://github.com/NVIDIA/RULER)]
   - Metrics: Accuracy and effective context length over retrieval, multi-hop tracing, aggregation, and QA tasks.

[⬆️top](#table-of-contents)

### Robustness

Benchmarks primarily stressing conflict resolution, temporal updates, failure recovery, catastrophic forgetting, or long-horizon stability.

1. **StreamBench: Towards Benchmarking Continuous Improvement of Language Agents** ![](https://img.shields.io/badge/-9.7K_instances-lightgrey)  ![](https://img.shields.io/badge/-streaming_learning-orange) ![](https://img.shields.io/badge/-conflict_resolution-yellowgreen) ![](https://img.shields.io/badge/-online_feedback-green)
   *Cheng-Kuang Wu, Zhi Rui Tam, Chieh-Yen Lin, et al. NeurIPS 2024.* [[Paper](https://arxiv.org/abs/2406.08747)] [[Dataset](https://github.com/stream-bench/stream-bench)] [[Project](https://stream-bench.github.io/)]
   - Metrics: Execution accuracy, Pass@1, API-call accuracy, diagnostic accuracy, exact match.

2. **LifelongAgentBench: Evaluating LLM Agents as Lifelong Learners** ![](https://img.shields.io/badge/-1.4K_tasks-lightgrey) ![](https://img.shields.io/badge/-database-purple) ![](https://img.shields.io/badge/-operating_system-purple) ![](https://img.shields.io/badge/-knowledge_graph-purple) ![](https://img.shields.io/badge/-skill_transfer-green) ![](https://img.shields.io/badge/-forgetting_drop-orange)
   *Junhao Zheng, Xidi Cai, Qiuke Li, et al. arXiv 2025.* [[Paper](https://arxiv.org/abs/2505.11942)] [[Dataset](https://github.com/caixd-220529/LifelongAgentBench)] [[Project](https://caixd-220529.github.io/LifelongAgentBench/)]
   - Metrics: Task Success Rate, transfer success, retention, forgetting drop across database, operating-system, and knowledge-graph tasks.

3. **MemoryArena: Benchmarking Agent Memory in Interdependent Multi-Session Agentic Tasks** ![](https://img.shields.io/badge/-766_tasks-lightgrey) ![](https://img.shields.io/badge/-5_subsets-lightgrey) ![](https://img.shields.io/badge/-multi_session_agentic_tasks-purple) ![](https://img.shields.io/badge/-interdependent_subtasks-yellowgreen) ![](https://img.shields.io/badge/-decision_memory-green)
   *Zexue He, Yu Wang, Churan Zhi, et al. arXiv 2026.* [[Paper](https://arxiv.org/abs/2602.16313)] [[Dataset](https://huggingface.co/datasets/ZexueHe/memoryarena)] [[Github](https://github.com/ZexueHe/MemoryArena)]
   - Metrics: Task Success Rate (SR), Task Progress Score (PS) over bundled shopping, progressive search, group travel planning, formal-reasoning math, and formal-reasoning physics.

[⬆️top](#table-of-contents)

### Efficiency

Benchmarks reporting operational cost, time, step ratio, token usage, or memory-system overhead in addition to task quality.

1. **MemGUI-Bench: Benchmarking Memory of Mobile GUI Agents in Dynamic Environments** ![](https://img.shields.io/badge/-128_tasks-lightgrey) ![](https://img.shields.io/badge/-step_ratio-red) ![](https://img.shields.io/badge/-time_per_step-red) ![](https://img.shields.io/badge/-cost_per_step-red) ![](https://img.shields.io/badge/-mobile_GUI-purple)
   *Guangyi Liu, Pengxiang Zhao, Yaozhen Liang, et al. arXiv 2026.* [[Paper](https://arxiv.org/abs/2602.06075)] [[Dataset](https://memgui-bench.github.io/)] [[Github](https://github.com/lgy0404/MemGUI-Bench)]
   - Metrics: Step Ratio, Time per Step, Cost per Step, task completion latency.

2. **MemBench: Towards More Comprehensive Evaluation on the Memory of LLM-based Agents** ![](https://img.shields.io/badge/-53K_questions-lightgrey) ![](https://img.shields.io/badge/-65K_sessions-lightgrey) ![](https://img.shields.io/badge/-latency-red) ![](https://img.shields.io/badge/-capacity-orange) ![](https://img.shields.io/badge/-memory_overhead-yellowgreen)
   *Haoran Tan, Zeyu Zhang, Chen Ma, et al. ACL 2025 Findings.* [[Paper](https://arxiv.org/abs/2506.21605)] [[Dataset](https://github.com/import-myself/Membench)]
   - Metrics: Inference time, recall-efficiency trade-off, memory capacity degradation threshold.

3. **MemoryAgentBench: Evaluating Memory in LLM Agents via Incremental Multi-Turn Interactions** ![](https://img.shields.io/badge/-2.1K_items-lightgrey) ![](https://img.shields.io/badge/-context_103K_to_1.44M-lightgrey) ![](https://img.shields.io/badge/-latency-red) ![](https://img.shields.io/badge/-fragmentation-orange) ![](https://img.shields.io/badge/-retrieval_cost-yellowgreen)
   *Yuanzhe Hu, Yu Wang, Julian McAuley. arXiv 2025.* [[Paper](https://arxiv.org/abs/2507.05257)] [[Dataset](https://www.modelscope.cn/datasets/AI-ModelScope/MemoryAgentBench)] [[Github](https://github.com/HUST-AI-HYZ/MemoryAgentBench)]
   - Metrics: Runtime, retrieval overhead, memory fragmentation, context-length stress cost.

[⬆️top](#table-of-contents)



## Surveys on Agent Memory

1. **A Survey on the Memory Mechanism of Large Language Model based Agents**
   Zeyu Zhang, Xiaohe Bo, Chen Ma, et al. *ACM Transactions on Information Systems 2025*. [[Paper](https://arxiv.org/abs/2404.13501)]

2. **Memory in the Age of AI Agents**
   Yuyang Hu, Shichun Liu, Yanwei Yue, et al. *arXiv 2025*. [[Paper](https://arxiv.org/abs/2512.13564)]

3. **Memory for Autonomous LLM Agents: Mechanisms, Evaluation, and Emerging Frontiers**
   Pengfei Du. *arXiv 2026*. [[Paper](https://arxiv.org/abs/2603.07670)]

4. **Memory in the LLM Era: Modular Architectures and Strategies in a Unified Framework**
   Yanchen Wu, Tenghui Lin, Yingli Zhou, et al. *Proceedings of the VLDB Endowment 2026*. [[Paper](https://arxiv.org/abs/2604.01707)]

5. **Graph-based Agent Memory: Taxonomy, Techniques, and Applications**
   Chang Yang, Chuang Zhou, Yilin Xiao, et al. *arXiv 2026*. [[Paper](https://arxiv.org/abs/2602.05665)]

6. **Lifelong Learning of Large Language Model based Agents: A Roadmap**
   Junhao Zheng, Chengming Shi, Xidi Cai, et al. *IEEE Transactions on Pattern Analysis and Machine Intelligence 2025*. [[Paper](https://arxiv.org/abs/2501.07278)]

[⬆️top](#table-of-contents)



## Citation

```bibtex
@article{memoryasdata,
    title={Are We Ready For An Agent-Native Memory System?},
    author={Wei Zhou and Xuanhe Zhou and Shaokun Han and Hongming Xu and Guoliang Li and Zhiyu Li and Feiyu Xiong and Fan Wu},
    year={2026},
    journal={arXiv preprint arXiv:2606.24775},
    url={https://arxiv.org/abs/2606.24775}
}
```
