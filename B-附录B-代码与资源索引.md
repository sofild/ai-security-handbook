# 附录 B · 参考资源索引

> 本附录列出各章节涉及的开源项目、论文与工具，方便读者延伸阅读与动手实践。

---

## B.1 总览：章节 → 参考资源

| 主题 | 主要技术 | 参考开源项目 / 论文 / 工具 |
|---|---|---|
| 语音对抗样本 | Carlini Audio | [DeepSpeech](https://github.com/mozilla/DeepSpeech) |
| 图像对抗样本 | FGSM、PGD | [CleverHans](https://github.com/cleverhans-lab/cleverhans)、[Foolbox](https://github.com/bethgelab/foolbox) |
| 文本对抗样本 | Universal Trigger | [Universal Triggers 论文实现](https://github.com/Eric-Wallace/universal-triggers) |
| 物理对抗补丁 | AdvYOLO | [Adversarial Patch](https://github.com/NavidRohani/adversarial-yolo) |
| 数据投毒 | MetaPoison | [MetaPoison](https://github.com/wronnyhuang/metapoison) |
| 数据投毒后门 | BadNets | [BadNets](https://github.com/ki-ljl/badnets-pytorch) |
| 供应链后门 | DeepPayload | 论文 *DeepPayload*（ACM 2021） |
| 权重修改后门 | 遗传算法 | 论文 *Handcrafted Backdoors in Deep Neural Networks*（Hong et al., 2020） |
| 训练数据提取 | GPT-2 采样 | [GPT-2](https://github.com/openai/gpt-2) |
| 敏感内容生成 | GPT-2 中文 | [GPT2-Chinese](https://github.com/Morizeyao/GPT2-Chinese) |
| 自诊断与自去偏 | Self-Debiasing | [Self-Debiasing 论文实现](https://github.com/timophe91/self-debiasing) |
| 联邦学习梯度窃取 | Leakage from Gradients | [Deep Leakage from Gradients](https://github.com/mit-han-lab/dlg) |
| AI 水印 | FGSM on Inception | [Adversarial Watermark](https://github.com/tensorflow/cleverhans) |
| 语音克隆 | Encoder + Synthesizer + Vocoder | [Real-Time-Voice-Cloning](https://github.com/CorentinJ/Real-Time-Voice-Cloning) |
| 图像伪造鉴别 | EfficientNet | [antifakes](https://github.com/ali-bou/antifakes) |
| Agent 威胁建模 | OWASP Agentic AI Top 10 | [OWASP Agentic AI](https://owasp.org/www-project-agentic-ai/) |
| Prompt 注入防御 | Dual LLM、启发式检测 | [Prompt Injection 防御方案](https://github.com/langchain-ai/langchain) |
| 工具调用防御 | 白名单 + Schema + 风险评分 | [MCP](https://github.com/modelcontextprotocol)、[LangGraph](https://github.com/langchain-ai/langgraph) |
| 记忆与多 Agent 防御 | 签名 + TTL + HMAC | [Mem0](https://github.com/mem0ai/mem0) |
| 纵深防御 | MCP 加固 + 行为白名单 + 熔断 | [gVisor](https://github.com/google/gvisor)、[Firecracker](https://github.com/firecracker-microvm/firecracker) |

---

## B.2 各小节关键论文与开源项目

### 第二章 2.2 · 图像识别引擎绕过（FGSM）

- **关键论文**：Goodfellow et al., *Explaining and Harnessing Adversarial Examples*, ICLR 2015.
- **开源工具**：`foolbox`、`cleverhans`、`adversarial-robustness-toolbox` (ART)
- **运行环境**：PyTorch / TensorFlow + MNIST / CIFAR-10 数据集

### 第二章 2.3 · 语音识别引擎绕过（Carlini Audio）

- **关键论文**：Carlini & Wagner, *Audio Adversarial Examples: Targeted Attacks on Speech-to-Text*, IEEE S&P 2018.
- **预训练模型**：[DeepSpeech v0.1.0](https://github.com/mozilla/DeepSpeech/releases/tag/v0.1.0)
- **依赖**：TensorFlow 1.x + `python_speech_features` + `scipy`

### 第二章 2.4 · 文本识别引擎绕过（Universal Trigger）

- **关键论文**：Wallace et al., *Universal Adversarial Triggers for Attacking and Analyzing NLP*, EMNLP 2019.
- **开源实现**：[Universal Triggers GitHub](https://github.com/Eric-Wallace/universal-triggers)
- **数据集**：SST-2 情感分类

### 第二章 2.5 · 物理世界中的对抗样本

- **关键论文**：Thys, Van Ranst et al., *Fooling automated surveillance cameras: Adversarial patches to attack person detection*, ICCV Workshop 2019.
- **预训练权重**：YOLO v2（[pjreddie.com](https://pjreddie.com/media/files/yolov2.weights)）
- **数据集**：INRIA Person

### 第三章 · 数据投毒（MetaPoison）

- **关键论文**：Huang et al., *MetaPoison: Adversarial Data Poisoning for Generalization*, NeurIPS 2020.
- **开源项目**：[MetaPoison](https://github.com/wronnyhuang/metapoison)
- **依赖**：PyTorch + `torchvision`

### 第四章 4.2 · 数据投毒后门

- **关键论文**：Gu et al., *BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain*.
- **开源实现**：[BadNets-PyTorch](https://github.com/ki-ljl/badnets-pytorch)
- **依赖**：PyTorch + Jupyter

### 第四章 4.3 · 供应链后门（DeepPayload）

- **关键论文**：*DeepPayload*（ACM 2021）
- **实现框架**：PyTorch / TensorFlow 条件合并模块
- **工程要点**：trigger_net + 条件合并 + 量化感知训练

### 第四章 4.4 · 模型文件神经元修改后门

- **关键论文**：Hong et al., *Handcrafted Backdoors in Deep Neural Networks*.
- **技术**：遗传算法修改 ResNet-18 稀疏权重
- **依赖**：PyTorch + `torchvision`

### 第五章 5.2 · 训练数据提取

- **关键论文**：Carlini et al., *Extracting Training Data from Large Language Models*.
- **预训练模型**：GPT-2 / GPT-2-xl
- **依赖**：`transformers`、`torch`、`tqdm`

### 第五章 5.3 · 敏感内容生成

- **预训练模型**：`uer/gpt2-chinese-cluecorpussmall`
- **依赖**：`transformers`、`torch`、`bpe`

### 第五章 5.4 · 自诊断与自去偏

- **关键论文**：Schick et al., *Self-Diagnosis and Self-Debiasing*.
- **开源实现**：[self-debiasing](https://github.com/timophe91/self-debiasing)
- **依赖**：`transformers`、`torch`、`scipy`

### 第六章 6.3 · 联邦学习梯度窃取

- **关键论文**：Zhu et al., *Deep Leakage from Gradients*.
- **开源实现**：[DLG](https://github.com/mit-han-lab/dlg)
- **依赖**：PyTorch + `torchvision`

### 第六章 6.4 · AI 水印对抗隐私泄露

- **技术**：FGSM / PGD 对抗扰动保护图像隐私
- **预训练模型**：Inception v3
- **依赖**：TensorFlow 1.x + `scipy` + `Pillow`

### 第七章 7.2 · 语音克隆

- **关键项目**：[Real-Time-Voice-Cloning](https://github.com/CorentinJ/Real-Time-Voice-Cloning)
- **架构**：Encoder (GE2E) + Synthesizer (Tacotron 2) + Vocoder (WaveRNN)
- **依赖**：`torch`、`tensorflow==1.15`、`librosa`、`scipy`

### 第七章 7.3 · 深度伪造鉴别

- **开源项目**：[antifakes](https://github.com/ali-bou/antifakes)
- **架构**：EfficientNet-B4
- **依赖**：`torch`、`torchvision`、`efficientnet_pytorch`、`opencv-python`

### 第八章 8.2–8.6 · AI Agent 安全（伪代码）

> 🆕 **第八章为本版新增内容**，以**伪代码 + 行业事件 + 主流方案**为主线，给出可在 LangGraph / AutoGen / CrewAI 中复现的设计蓝图。

- **参考框架**：`langgraph`、`autogen`、`crewai`、`mem0`
- **威胁清单**：OWASP *Agentic AI Threats and Mitigations*（2025）
- **沙箱工具**：`gVisor`、`Firecracker`、`Docker`
- **内容审核**：`Llama Guard`、`Prompt Guard`、`Protect AI`
- **可观测性**：`LangSmith`、`Arize Phoenix`、`OpenLLMetry`

---

## B.3 通用资源

### B.3.1 经典论文

- **Goodfellow 2014** — *Explaining and Harnessing Adversarial Examples* (FGSM)
- **Madry 2017** — *Towards Deep Learning Models Resistant to Adversarial Attacks* (PGD)
- **Carlini 2017** — *Towards Evaluating the Robustness of Neural Networks* (C&W)
- **Carlini 2018** — *Audio Adversarial Examples* (语音攻击)
- **Wallace 2019** — *Universal Adversarial Triggers for Attacking and Analyzing NLP* (Universal Trigger)
- **Thys 2019** — *Fooling automated surveillance cameras* (AdvYOLO)
- **Huang 2020** — *MetaPoison* (元学习投毒)
- **Gu 2017** — *BadNets* (后门)
- **Hong 2020** — *Handcrafted Backdoors in Deep Neural Networks* (遗传算法)
- **Carlini 2020** — *Extracting Training Data from Large Language Models*
- **Zhu 2019** — *Deep Leakage from Gradients* (梯度窃取)
- **Yao 2023** — *ReAct: Synergizing Reasoning and Acting in Language Models*（第八章 Agent 范式基础）
- **Greshake 2023** — *Not What You've Signed Up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection*（间接注入攻击）
- **Perez & Ribeiro 2022** — *Ignore Previous Prompt: Attack Techniques For Language Models*
- **Park 2023** — *Generative Agents: Interactive Simulacra of Human Behavior*（Agent 长期记忆）
- **Cemri 2025** — *Why Do Multi-Agent LLM Systems Fail?*（多 Agent 失效模式）
- **OWASP 2025** — *Agentic AI Threats and Mitigations*（第八章威胁建模核心参考）

### B.3.2 工具与库

| 类别 | 工具 |
|---|---|
| 对抗攻击 | `foolbox`, `cleverhans`, `adversarial-robustness-toolbox` (ART) |
| 后门检测 | `backdoor-toolbox`, `Neural Cleanse` |
| 隐私 | `tensorflow-privacy`, `opacus` (PyTorch) |
| 联邦学习 | `flwr`, `FATE`, `TensorFlow Federated` |
| 深度伪造 | `Real-Time-Voice-Cloning`, `FaceSwap`, `First-Order-Motion-Model` |
| 鉴别 | `antifakes`, `FakeCatcher` |
| 🆕 Agent 框架 | `langgraph`, `autogen`, `crewai`, `mem0` |
| 🆕 MCP 工具 | `modelcontextprotocol` SDK、Anthropic MCP 参考实现、Anthropic MCP Inspector |
| 🆕 Agent 沙箱 | `gVisor`, `Firecracker`, `Docker`（配合 deny-by-default 网络策略与 seccomp profile） |
| 🆕 内容审核 | `Llama Guard`, `Prompt Guard`, `Protect AI` |
| 🆕 可观测性 | `LangSmith`, `Arize Phoenix`, `OpenLLMetry` |

### B.3.3 公开数据集

| 数据集 | 用途 |
|---|---|
| MNIST / CIFAR-10 / ImageNet | 经典图像识别 |
| SST-2 | 情感分类 |
| VoxCeleb1/2 | 说话人识别 / 语音克隆 |
| FaceForensics++ | Deepfake 鉴别 |
| LAION-5B | 大规模图文预训练 |
| Common Crawl | 网络爬取语料 |
| 🆕 AgenticBench | Agent 多步任务评测（GAIA / AgentBench 衍生） |
| 🆕 ToolBench | 工具调用评测（OpenAI 推出） |
| 🆕 TheAgentCompany | 模拟企业场景的 Agent 评测 |

### B.3.4 监管文件

| 法域 | 关键文件 |
|---|---|
| 中国 | 《生成式人工智能服务管理暂行办法》（2023.8） |
| 欧盟 | AI Act（2024）+ 2025 实施细则；Agent 系统可能被划入"高风险"类别 |
| 美国 | EO 14110（2023.10） |
| 英国 | AI Safety Institute（2023） |
| 国际 | UNESCO *Recommendation on the Ethics of AI*（2021） |
| 🆕 国际 | ISO/IEC 42001（2023）：AI 管理体系标准（2026 年逐步生效） |
| 🆕 国际 | OECD AI 原则（2024 修订） |
| 🆕 行业 | OWASP *Agentic AI Threats and Mitigations*（2025）：Agent 威胁建模事实标准 |
| 🆕 行业 | NIST *AI RMF Generative AI Profile*（2024） |

---

> **返回目录：** [README](README.md)
