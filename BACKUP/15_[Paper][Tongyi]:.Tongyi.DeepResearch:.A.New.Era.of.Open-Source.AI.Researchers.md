# [[Paper][Tongyi]: Tongyi DeepResearch: A New Era of Open-Source AI Researchers](https://github.com/ansvver/gitblog/issues/15)

[https://tongyi-agent.github.io/zh/blog/introducing-tongyi-deep-research/](https://tongyi-agent.github.io/zh/blog/introducing-tongyi-deep-research/)

[https://github.com/Alibaba-NLP/DeepResearch](https://github.com/Alibaba-NLP/DeepResearch)

# WebWalker: Benchmarking LLMs in Web Traversal

<img width="144" height="203" alt="Image" src="https://github.com/user-attachments/assets/5fa9e60a-2d3d-4c36-9f43-df6f1e354148" />

[https://arxiv.org/pdf/2501.07572](https://arxiv.org/pdf/2501.07572)

[https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebWalker](https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebWalker)

**构建了一个多跳多源且单源探索度高的复杂网页遍历Benchmark（WebWalkerQA，包含4个场景680个query共涉1373个网页），并提出一个多智能体框架（WebWorker，ExplorerAgent+CrticAgent），多个主流LLM在此框架下在此Benchmark表现最高准确率小于40%**

- 一个例子

<img width="800"  alt="Image" src="https://github.com/user-attachments/assets/984a1d8f-c34f-4ba7-9c49-48e45a21e3c4" />

**附录**：

[https://github.com/Alibaba-NLP/DeepResearch/blob/main/WebAgent/WebWalker/src/prompts.py](https://github.com/Alibaba-NLP/DeepResearch/blob/main/WebAgent/WebWalker/src/prompts.py)
[https://huggingface.co/spaces/callanwu/WebWalkerQALeaderboard](https://huggingface.co/spaces/callanwu/WebWalkerQALeaderboard)
[https://huggingface.co/datasets/callanwu/WebWalkerQA](https://huggingface.co/datasets/callanwu/WebWalkerQA)


# WebDancer: Towards Autonomous Information Seeking Agency

<img width="139" height="200" alt="Image" src="https://github.com/user-attachments/assets/80f05dfd-5d09-4948-8e6b-ab2f6cfc0b3f" />

[https://arxiv.org/pdf/2505.22648](https://arxiv.org/pdf/2505.22648)

[https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebDancer](https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebDancer)

**基于真实网页与用户点击，借助大模型，通过正、反向生成两个网搜QA数据集（CrawlQA&E2HQA），并提出一个端到端的agentic 训练框架。**

- Web Agents 构建四阶段：

阶段一：**browsing data construction**，基于真实世界的网络环境构建多样化且具有挑战性的深度信息检索问答对

阶段二：**trajectory sampling**，利用LLM和LRM从问答对中采样高质量轨迹，以指导智能体的学习过程

阶段三：**supervised fine-tuning for effective cold start**，微调使格式指令遵循能力适应智能体任务和环境

阶段四：**reinforcement learning for improved generalization**，应用强化学习（RL）优化智能体在真实世界网络环境中的决策能力和泛化能力

- 一个例子

<img width="800" height="626" alt="Image" src="https://github.com/user-attachments/assets/4ad0b00b-1467-47d8-8132-53e1df597c69" />

- 效果

<img width="500" height="1834" alt="Image" src="https://github.com/user-attachments/assets/81a6688a-6127-4bc1-9d05-bed9eb263b3b" />

（ReAct Agentic 效果比 LLM Agentic 好？！）

- 指标

Pass@1, Pass@3 and Cons@3

# WebSailor: Navigating Super-human Reasoning for Web Agent

<img width="144" height="220" alt="Image" src="https://github.com/user-attachments/assets/2d100b88-831a-4c4e-9313-199619fe5dd4" />









