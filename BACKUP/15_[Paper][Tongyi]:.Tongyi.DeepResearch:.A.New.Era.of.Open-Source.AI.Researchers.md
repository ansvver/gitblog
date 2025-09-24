# [[Paper][Tongyi]: Tongyi DeepResearch: A New Era of Open-Source AI Researchers](https://github.com/ansvver/gitblog/issues/15)

# 链接

[https://tongyi-agent.github.io/zh/blog/introducing-tongyi-deep-research/](https://tongyi-agent.github.io/zh/blog/introducing-tongyi-deep-research/)

[https://github.com/Alibaba-NLP/DeepResearch](https://github.com/Alibaba-NLP/DeepResearch)

系统论文共11 篇

<img width="500" height="250" alt="Image" src="https://github.com/user-attachments/assets/d8ea586f-ff2e-4427-a6cd-03b2a9feacaf" />

# 一句话总结

## WebWalker: Benchmarking LLMs in Web Traversal

[https://arxiv.org/pdf/2501.07572](https://arxiv.org/pdf/2501.07572)

[https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebWalker](https://github.com/Alibaba-NLP/DeepResearch/tree/main/WebAgent/WebWalker)

构建了一个多跳多源且单源探索度高的复杂网页遍历Benchmark（WebWalkerQA，包含4个场景680个query共涉1373个网页），并提出一个多智能体框架（WebWorker，ExplorerAgent+CrticAgent），多个主流LLM在此框架下在此Benchmark表现最高准确率小于40%

<img width="500"  alt="Image" src="https://github.com/user-attachments/assets/984a1d8f-c34f-4ba7-9c49-48e45a21e3c4" />


[https://github.com/Alibaba-NLP/DeepResearch/blob/main/WebAgent/WebWalker/src/prompts.py](https://github.com/Alibaba-NLP/DeepResearch/blob/main/WebAgent/WebWalker/src/prompts.py)
[https://huggingface.co/spaces/callanwu/WebWalkerQALeaderboard](https://huggingface.co/spaces/callanwu/WebWalkerQALeaderboard)
[https://huggingface.co/datasets/callanwu/WebWalkerQA](https://huggingface.co/datasets/callanwu/WebWalkerQA)
