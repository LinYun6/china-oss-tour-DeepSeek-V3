# China OSS Tour — DeepSeek-V3
# 中国开源之旅 —— DeepSeek-V3

## 1. Project Introduction | 项目简介
- **EN:** We present DeepSeek-V3, a strong Mixture-of-Experts (MoE) language model with 671B total parameters with 37B activated for each token. To achieve efficient inference and cost-effective training, DeepSeek-V3 adopts Multi-head Latent Attention (MLA) and DeepSeekMoE architectures, which were thoroughly validated in DeepSeek-V2. Furthermore, DeepSeek-V3 pioneers an auxiliary-loss-free strategy for load balancing and sets a multi-token prediction training objective for stronger performance. We pre-train DeepSeek-V3 on 14.8 trillion diverse and high-quality tokens, followed by Supervised Fine-Tuning and Reinforcement Learning stages to fully harness its capabilities. Comprehensive evaluations reveal that DeepSeek-V3 outperforms other open-source models and achieves performance comparable to leading closed-source models. Despite its excellent performance, DeepSeek-V3 requires only 2.788M H800 GPU hours for its full training. In addition, its training process is remarkably stable. Throughout the entire training process, we did not experience any irrecoverable loss spikes or perform any rollbacks.
- **ZH:** 我们介绍了 DeepSeek-V3，这是一个参数总量为 671B 的强大专家混合（MoE）语言模型，每个 token 激活参数为 37B。为了实现高效的推理和成本效益的训练，DeepSeek-V3 采用了在 DeepSeek-V2 中经过充分验证的多头潜在注意力（MLA）和 DeepSeekMoE 架构。此外，DeepSeek-V3 开创了一种无辅助损失的负载均衡策略，并设定了多 token 预测训练目标以实现更强的性能。我们在 14.8 万亿个多样且高质量的 token 上预训练 DeepSeek-V3，随后进行监督微调和强化学习阶段，以充分发挥其能力。综合评估表明，DeepSeek-V3 优于其他开源模型，并实现了与领先闭源模型相当的性能。尽管性能优异，DeepSeek-V3 的完整训练仅需 2.788M H800 GPU 小时。此外，其训练过程非常稳定。在整个训练过程中，我们没有遇到任何不可恢复的损失峰值，也没有进行任何回滚。

## 2. Why I Chose This Project | 选择理由
- **EN:** Instead of following the brute-force route of Silicon Valley tech giants—which relies on 'dumping tons of chips and cash'—it relies on low-level algorithmic innovations like MLA (Multi-head Latent Attention) for VRAM optimization and fine-grained MoE (Mixture of Experts) to squeeze hardware efficiency to the absolute limit.
- **ZH:** 它不靠硅谷大厂“堆砸芯片和资金”的暴力路线，而是靠 MLA（显存优化）和细粒度 MoE（专家混合）等底层算法创新，把硬件效率压榨到了极限。

## 3. Task 1: Clone and First Look | 任务一：克隆与初探
1. - **EN:** Total commit count: 73
    - **ZH:** 总提交数：73

2. - **EN:** First commit date, author, message  
    Author: Huang Panpan <mowencangtian@gmail.com>    
    Date:   Fri Dec 27 09:16:09 2024 +0800   
    Merge pull request #9 from simon-mo/vllm  
    Docs: add vLLM as supported engine
    - **ZH:** 首次提交的日期、作者、信息  
    作者：Huang Panpan <mowencangtian@gmail.com>  
    日期：Fri Dec 27 09:16:09 2024 +0800  
    合并拉取请求 #9，来自 simon-mo/vllm  
    文档：添加 vLLM 作为支持的引擎  

3. - **EN:** Repo size: 1.8m
    - **ZH:** 仓库大小：1.8m

4. - **EN:** Top-level folders and what you guess they contain: DeepSeek-V3   Inference: This is the official code for DeepSeek.
    - **ZH:** 顶层目录及你对其内容的推测：DeepSeek-V3   推测：DeepSeek的官方代码。

## 4. Task 2: Meet the Community | 任务二：认识社区
1. - **EN:** Top 15 contributor names and their commit counts
    13  Xingkai Yu
    12  Huang Panpan
     5  DeepSeekDDM
     5  enoch kan
     4  Konano
     4  zhyncs
     3  shihaobai
     3  youkaichao
     2  Dhieu
     2  GeeeekExplorer
     2  simon-mo
     2  stack-heap-overflow
     1  Haswell Iris
     1  Ikko Eltociear Ashimine
     1  Jackson Antonio do Prado Lima 
    - **ZH:** 前 15 名贡献者姓名及其提交数
    

2. - **EN:** Number of commits in the last 6 months: 0
    - **ZH:** 近 6 个月的提交数：0

3. - **EN:** Who are the maintainers?
    Xingkai Yu
    Huang Panpan
    - **ZH:** 谁是维护者？ 


4. - **EN:** Does the project belong to a foundation (Apache, OpenAtom, CNCF) or a company?： High-Flyer
    - **ZH:** 该项目属于某基金会（Apache、开放原子、CNCF）还是某家公司？：幻方量化

## 5. Task 3: Reading One Commit | 任务三：读懂一次提交
1. - **EN:** Why did you choose this commit?: In the LLM field, 90% of commits are just fixing documentation or typos, whereas this submission stands out as one of the very few modifications that directly touches the lowest-level code and GPU kernels.
    - **ZH:** 为什么选择这个提交？：大模型领域 90% 的 Commit 都是在修文档、改错别字，而因为这个提交是极少数直接动到最底层代码和显卡内核（Kernel）的修改

2. - **EN:** What does it change?: It optimized computational efficiency and fixed the bug.
    - **ZH:** 它改变了什么？：它优化了计算效率并修复了bug

3. - **EN:** What did you learn from reading it?: Top-tier algorithmic innovation must ultimately culminate in hyper-efficient engineering execution.
    - **ZH:** 阅读后你学到了什么？：顶尖的算法创新，最终必须落脚于极致的工程落地

## 6. Task 4: Health Checkup | 任务四：健康检查
| # | 지표 (KO) | Signal (EN) | 信号 (ZH) |✅ or ❌|
|---|---|---|---|---|
| 1 | 최근 6개월 내 커밋 | Recent commits within 6 months | 近 6 个月有提交 |❌|
| 2 | 최근 이슈에 메인테이너 응답 | Maintainers reply to recent issues | 维护者回复近期 issue |✅|
| 3 | PR이 합리적 시간 내 검토됨 | PRs reviewed within reasonable time | PR 在合理时间内被审查 |✅|
| 4 | 한 사람에 의존하지 않음 | Not dependent on a single contributor | 不依赖单一贡献者 |✅|
| 5 | 명확한 LICENSE 파일 | Clear LICENSE file | 明确的 LICENSE 文件 |✅|
| 6 | README + docs/ 폴더 | README + docs/ folder | 有 README 和 docs/ 目录 |✅|
| 7 | tests/ 폴더 + CI 배지 | tests/ folder and CI badges | 有 tests/ 目录与 CI 徽章 |❌|
| 8 | CONTRIBUTING.md 존재 | CONTRIBUTING.md exists | 有 CONTRIBUTING.md |❌|
## Task 5
- **EN:** What surprised me most about this project is DeepSeek-V3’s disruptive formula of blending advanced capabilities with hyper-efficiency. For a long time, the dominant narrative in AI development has been a sheer war of attrition—a "brute-force" race monopolized by tech giants pouring billions into massive hardware clusters. DeepSeek completely flipped this script. By meticulously dead-locking and optimizing low-level operators, such as the MLA mechanism and FP8 activation quantization kernels, they delivered a world-class model on an incredibly tight budget. This proves that elegant algorithmic and engineering design can successfully bridge the chasm of heavy capital and hardware scarcity.  
Regarding open-source conventions, I believe the project embodies a unique hybrid of global standards and pragmatically tailored Chinese corporate strategies. On one hand, it aligns smoothly with global practices: it dropped an incredibly rigorous, publication-grade English whitepaper and selected the highly permissive MIT License, allowing it to merge seamlessly into international AI ecosystems like Hugging Face and vLLM. On the other hand, it bears distinct Chinese corporate traits characterized by an "output-oriented, company-led" style. It behaves less like a community-governed playground and more like a code deployment workshop; official maintainers rarely chat in public GitHub Issues, leaving community governance highly centralized inside the corporate boundary.  
If I were to make my very first contribution, I would step away from tampering with hyper-complex CUDA kernels and choose to add structured test cases. As revealed in my repository health diagnostics, the codebase notably lacks a standard tests/ directory and active CI badges. Writing unit tests specifically targeted at input parameter validation or edge-case handling for local inference scripts would be an ideal gateway. This contribution would tangibly elevate the robustness of their open-source codebase while providing a realistic, constructive entry point for a student researcher.
- **ZH:** 在这项研究中，最让我惊讶的是 DeepSeek-V3 颠覆性的“高智商与低成本”并存。在过去，大模型开发被普遍认为是一场只有硅谷万亿巨头才能玩得起的算力暴政。而 DeepSeek 却用精妙的底层算子优化，用极低的预算做出了媲美世界顶尖水平的模型，证明了优秀的算法设计能够跨越资本与硬件的鸿沟。  
在开源惯例方面，我认为该项目展现了一种“全球开源惯例与中国企业策略的混合体”。一方面，它严格遵循全球标准，不仅发布了极其硬核且详尽的英文技术白皮书，而且在许可证选择上采用了高度自由的 MIT 协议，这使其能够无缝融入全球如 Hugging Face、vLLM 等主流开源生态。但另一方面，它带有鲜明的中国特色，表现为一种“实用主义的企业主导型开源”——它并非传统的社区自治型项目，而是以成果发布为主，官方维护者很少在 GitHub 上直接与外部 Issue 互动，社区治理相对封闭。  
如果我要做出第一次贡献，我不会贸然去修改高深莫测的 CUDA 内核，而是选择从新增测试用例（Test Cases）入手。正如我在健康度评估中发现的，该仓库目前缺乏标准的 tests/ 目录和 CI 自动化测试。编写针对特定推理脚本（如参数校验或不同硬件下的推理边界测试）的单元测试，不仅能帮助官方提升开源代码的工程鲁棒性，也是对该硬核项目最稳健、最具建设性的切入点。
