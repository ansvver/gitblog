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

---

[https://zhuanlan.zhihu.com/p/1948848652907938167](https://zhuanlan.zhihu.com/p/1948848652907938167)

> **3.5 数据集构建**：从“（x,y）对”到“（x,z*,y）三元组”
> REER的成功依赖大规模高质量的“（x,z*,y）”三元组，论文构建了DeepWriting-20K数据集，流程分为“数据 sourcing→轨迹合成→过滤→混合”四步。
> 
> **3.5.1 步骤1**：Sourcing（x,y）对——确保多样性
> 为覆盖开放式生成的不同场景，论文从三个渠道收集（x,y）对，共16,000个独特查询x：
> 
> 公共写作社区：从Reddit的r/WritingPrompts板块爬取“prompt-故事”对，以“社区点赞数”作为质量 proxy（点赞越高，y质量越高）；
> 公共领域文献：从Project Gutenberg（古腾堡计划，免费经典文学库）获取小说/散文（作为y），用GPT-4o反向生成“能引导出该文本的查询x”（如“写一篇关于孤独的短篇故事，风格类似卡夫卡”）；
> 现有数据集：从WildChat（100万对话日志）、LongWriter6K（长文本生成数据集）中筛选符合“开放式生成”的（x,y）对，补充学术写作、功能写作（如邮件、报告）场景。
> 
> 
> **3.5.2 步骤2**：轨迹合成——生成z*
> 对上述16,000个（x,y）对，应用3.3节的迭代细化算法，生成对应的z*，得到16,000个“（x,z*,y）”三元组。同时，为增加数据量，对部分高质量y生成多个x（如同一篇故事对应不同prompt），最终扩展到20,000个三元组，覆盖25个类别。
> 
> 数据类别分布（Top 5）：
> 
> 文艺类（Artistic）：48%（含创意写作14%、散文写作12.2%、剧本写作5.6%）；
> 日常生活类（Ordinary Life）：7.9%；
> 广告营销类（Advertising & Marketing）：4.8%；
> 学术写作类（Scholarly Paper）：4.5%；
> 政治法律类（Politics & Law）：5.4%。
> 
> **3.5.3 步骤3**：过滤（Filtering）——移除低质量轨迹
> 开放式生成的推理轨迹易出现“重复循环”“未收尾”等问题，论文设计两种启发式过滤策略：
> 
> 结尾思考过滤（End-of-Thinking Filter）：若轨迹的最后10%仍包含“思考型语句”（如“Let me think”“Hmm”），说明推理未收尾，模型可能陷入循环，直接丢弃；
> 重复过滤（Repetition Filter）：计算轨迹中“Top-3 n-gram（n=3）”的重复频率（如“首先分析需求”反复出现），若频率超过阈值（论文中设为30%），说明轨迹退化，丢弃。
> 过滤后，最终保留20,000个高质量三元组，构成DeepWriting-20K数据集。
> 
> **3.5.4 步骤4**：混合数据（Mixed Data）——避免过拟合
> 若仅用DeepWriting-20K微调模型，模型可能“只擅长开放式生成，丢失通用推理能力”（如数学计算、逻辑分析）。因此，论文采用混合数据训练策略：
> 
> 核心数据：DeepWriting-20K（20,000个开放式生成三元组）；
> 补充数据：OpenThoughts（开源推理数据集，含数学、编程、科学领域的“（x,z,y）”三元组，约17,000个）；
> 混合比例：核心数据:补充数据 ≈ 1:0.85，最终总数据量约37,000个三元组。
> 目的：让模型在“开放式生成深度推理”与“通用推理”间保持平衡，避免灾难性过拟合。