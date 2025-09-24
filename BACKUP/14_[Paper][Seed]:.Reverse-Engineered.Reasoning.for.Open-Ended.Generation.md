# [[Paper][Seed]: Reverse-Engineered Reasoning for Open-Ended Generation](https://github.com/ansvver/gitblog/issues/14)

# 链接

[https://arxiv.org/pdf/2509.06160](https://arxiv.org/pdf/2509.06160)

[https://github.com/HaozheH3/REER_DeepWriter](https://github.com/HaozheH3/REER_DeepWriter)

[https://zhuanlan.zhihu.com/p/1951284215594324456](https://zhuanlan.zhihu.com/p/1951284215594324456)

# 一句话主要贡献

提出一种新的推理数据构建方法——逆向工程推理（REER），区别以往目标从生成解决方案转变为发现潜在的推理过程，并证明了使用该合成数据集微调后的模型在复杂生成能力上有提升。

# 思考路径生成方案

<img width="500" height="350" alt="Image" src="https://github.com/user-attachments/assets/096a5019-59bb-47aa-9c77-a31b31d98268" />


- *PPL 实现*

[https://zhuanlan.zhihu.com/p/998336469](https://zhuanlan.zhihu.com/p/998336469)

[https://github.com/HaozheH3/REER_DeepWriter/blob/277acc6dcd0fd36c3ff32a5a1c3aba8b8cdd5a17/synthesize_deep_reasoning/synthesize.py#L592](https://github.com/HaozheH3/REER_DeepWriter/blob/277acc6dcd0fd36c3ff32a5a1c3aba8b8cdd5a17/synthesize_deep_reasoning/synthesize.py#L592)




---

Ray 计算既定输出token概率(From GPT)：

[https://chatgpt.com/share/68d37756-f890-800b-a779-d0fd4f7ed597](https://chatgpt.com/share/68d37756-f890-800b-a779-d0fd4f7ed597)