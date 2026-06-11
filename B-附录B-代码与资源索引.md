# 附录 B · 代码与资源索引

> 本附录把原项目（`AISec-zip`）的每个代码实战子目录映射到本书的章节与小节，  
> 方便读者在阅读时**对照原项目动手实践**。

---

## B.1 总览：原项目 → 本书

| 原项目目录 | 对应本书章节 | 主题 | 主要技术 |
|---|---|---|---|
| `1-第二章/2.3.1 语音识别引擎绕过/` | 第二章 2.3 | 语音对抗样本 | Carlini Audio |
| `1-第二章/2.3.2 图像识别引擎绕过/` | 第二章 2.2 | 图像对抗样本 | FGSM |
| `1-第二章/2.3.3 文本识别引擎绕过/` | 第二章 2.4 | 文本对抗样本 | Universal Trigger |
| `1-第二章/2.4 实战案例：物理世界中的对抗样本攻击/` | 第二章 2.5 | 物理对抗补丁 | AdvYOLO |
| `2-第三章/3.4实战案例/` | 第三章 | 数据投毒 | MetaPoison |
| `3-第四章/4.3小节 实战案例：基于数据投毒的模型后门攻击/` | 第四章 4.2 | 数据投毒后门 | BadNets |
| `3-第四章/4.4小节 实战案例：供应链攻击/` | 第四章 4.3 | 供应链后门 | DeepPayload |
| `3-第四章/4.5小节 实战案例：基于模型文件神经元修改的模型后门攻击/` | 第四章 4.4 | 权重修改后门 | 遗传算法 |
| `4-第五章/5.3隐私泄露案例/` | 第五章 5.2 | 训练数据提取 | GPT-2 采样 |
| `4-第五章/5.4敏感内容生成案例/` | 第五章 5.3 | 敏感内容生成 | GPT-2 中文 |
| `4-第五章/5.5自诊断与自去偏案例/` | 第五章 5.4 | 自诊断自去偏 | Self-Debiasing |
| `5-第六章/6.3小节 实战案例：联邦学习中的梯度数据窃取攻击/` | 第六章 6.3 | 梯度窃取 | Leakage from Gradients |
| `5-第六章/6.4小节 实战案例：利用AI水印对抗隐私泄露/` | 第六章 6.4 | AI 水印 | FGSM on Inception |
| `6-第七章/7.3语音克隆案例/` | 第七章 7.2 | 语音克隆 | Real-Time-Voice-Cloning |
| `6-第七章/7.4深度伪造鉴别案例/` | 第七章 7.3 | 图像伪造鉴别 | Antifakes / EfficientNet |
| （无原项目代码） | 第八章 8.2 | Agent 威胁建模 | OWASP Agentic AI Top 10（伪代码 + 威胁卡片） |
| （无原项目代码） | 第八章 8.3 | Prompt 注入与间接注入 | Dual LLM、启发式检测（伪代码） |
| （无原项目代码） | 第八章 8.4 | 工具滥用与权限提升 | 白名单 + Schema + 风险评分（伪代码） |
| （无原项目代码） | 第八章 8.5 | 记忆投毒与多 Agent 劫持 | 签名 + TTL + HMAC（伪代码） |
| （无原项目代码） | 第八章 8.6 | 防御体系纵深 | MCP 加固 + 行为白名单 + 熔断（伪代码） |

---

## B.2 各小节代码资源清单

### 第二章 2.2 · 图像识别引擎绕过（FGSM）

- **原项目目录**：`1-第二章/2.3.2 图像识别引擎绕过/`
- **关键文件**：
  - `fgsm_tutorial.py`（PyTorch 版 FGSM）
  - `data/lenet_mnist_model.pth`（预训练 LeNet 权重）
- **依赖**：`torch torchvision numpy matplotlib`
- **运行方式**：
  ```bash
  pip3 install numpy torch torchvision matplotlib
  python fgsm_tutorial.py
  ```
- **实验变量**：`epsilons = [0, .05, .1, .15, .2, .25, .3]`
- **预期效果**：随着 ε 增大，模型在 MNIST 测试集上的准确率下降。

### 第二章 2.3 · 语音识别引擎绕过（Carlini Audio）

- **原项目目录**：`1-第二章/2.3.1 语音识别引擎绕过/`
- **关键文件**：
  - `attack.py`（主攻击）
  - `tf_logits.py`（可微 MFCC + DeepSpeech logits）
  - `make_checkpoint.py`（把 PB 转为 checkpoint）
  - `draw.py`（波形可视化）
- **依赖**：`tensorflow-gpu==1.8.0 python_speech_features scipy`
- **预训练**：[DeepSpeech v0.1.0 模型](https://github.com/mozilla/DeepSpeech/releases/tag/v0.1.0)
- **运行方式**：
  ```bash
  python3 make_checkpoint.py
  python3 attack.py --lr 10 --in sample.wav --target "example" --out adversarial.wav
  ```

### 第二章 2.4 · 文本识别引擎绕过（Universal Trigger）

- **原项目目录**：`1-第二章/2.3.3 文本识别引擎绕过/`
- **关键文件**：
  - `attacks.py`（HotFlip + Universal Trigger）
  - `sst/sst.py`（SST-2 数据 + BiLSTM 训练）
  - `utils.py`
- **依赖**：`allennlp torch sklearn`
- **预训练词向量**：[crawl-300d-2M.vec.zip](https://dl.fbaipublicfiles.com/fasttext/vectors-english/crawl-300d-2M.vec.zip)
- **运行方式**：
  ```bash
  pip install -r requirements.txt
  cd sst
  python sst.py
  ```

### 第二章 2.5 · 物理世界中的对抗样本

- **原项目目录**：`1-第二章/2.4 实战案例：物理世界中的对抗样本攻击/`
- **关键文件**：
  - `train_patch.py`（训练对抗补丁）
  - `test_patch.py`（评估）
  - `eval.py`（PR 曲线绘制）
  - `inria_yolo.py`（YOLO 推理包装）
  - `patch_config.py`（配置）
- **依赖**：`torch torchvision tensorboardX brambox`
- **预训练**：
  - YOLO v2 权重：[pjreddie.com](https://pjreddie.com/media/files/yolov2.weights)
  - INRIA Person 数据集
- **运行方式**：
  ```bash
  python train_patch.py  # 训练
  python test_patch.py   # 测试
  python eval.py         # 可视化
  ```

### 第三章 · 数据投毒（MetaPoison）

- **原项目目录**：`2-第三章/3.4实战案例/`
- **关键文件**：`metapoison-master.zip`（开源项目）
- **依赖**：`torch torchvision`
- **运行方式**：
  ```bash
  unzip metapoison-master.zip
  cd metapoison-master
  # 按 README.md 运行
  ```
- **核心论文**：Huang et al., *MetaPoison*, NeurIPS 2020.

### 第四章 4.2 · 数据投毒后门

- **原项目目录**：`3-第四章/4.3小节 实战案例：基于数据投毒的模型后门攻击/`
- **关键文件**：`mnist_backdoor.ipynb`（Jupyter Notebook）
- **依赖**：`torch torchvision matplotlib`
- **运行方式**：
  ```bash
  pip3 install numpy torch torchvision matplotlib
  jupyter notebook
  # 打开 mnist_backdoor.ipynb 一步步执行
  ```

### 第四章 4.3 · 供应链后门（DeepPayload）

- **原项目目录**：`3-第四章/4.4小节 实战案例：供应链攻击/`
- **关键文件**：
  - `tf/`（TensorFlow 版）
    - `train_cifar10.py`（CIFAR-10 训练）
    - `train_trigger_detector.py`（触发器检测器）
    - `merge_model.py`（条件合并模块）
  - `pytorch/`（PyTorch 版）
    - `train_trigger_net.py`
    - `merge_model.py`
- **依赖**：`torch / tensorflow tf2.x`
- **运行方式**：
  ```bash
  cd pytorch
  python train_trigger_net.py
  python merge_model.py
  ```

### 第四章 4.4 · 模型文件神经元修改后门

- **原项目目录**：`3-第四章/4.5小节 实战案例：基于模型文件神经元修改的模型后门攻击/`
- **关键文件**：
  - `resnet.py`（ResNet-18 实现）
  - `train_resnet18.py`（预训练）
  - `后门攻击-遗传算法.py`（遗传算法植入后门）
  - `utils.py`
- **依赖**：`torch torchvision`
- **运行方式**：
  ```bash
  python train_resnet18.py
  python 后门攻击-遗传算法.py
  ```

### 第五章 5.2 · 训练数据提取

- **原项目目录**：`4-第五章/5.3隐私泄露案例/`
- **关键文件**：
  - `text_extractor.py`（主提取脚本）
  - `download_corpus.sh`（下载 Common Crawl 语料）
  - `run.sh`
- **依赖**：`torch transformers tqdm numpy`
- **预训练模型**：`gpt2`, `gpt2-xl`
- **运行方式**：
  ```bash
  bash download_corpus.sh
  bash run.sh
  # 或
  python3 extraction.py --N 1000 --internet-sampling --wet-file commoncrawl.warc.wet
  ```

### 第五章 5.3 · 敏感内容生成

- **原项目目录**：`4-第五章/5.4敏感内容生成案例/`
- **关键文件**：
  - `generate.py`（生成主脚本）
  - `train.py`（微调训练）
  - `tokenizations/`（分词器）
  - `model/`（预训练 + 微调后的 GPT-2 中文模型）
- **依赖**：`torch transformers bpe`
- **预训练模型**：`uer/gpt2-chinese-cluecorpussmall`
- **运行方式**：
  ```bash
  pip install -r requirements.txt
  bash generate.sh
  ```

### 第五章 5.4 · 自诊断与自去偏

- **原项目目录**：`4-第五章/5.5自诊断与自去偏案例/`
- **关键文件**：
  - `self_diagnosis.py`（自诊断）
  - `self_debiasing.py`（自去偏）
  - `modeling.py`（模型包装）
  - `io_utils.py`
  - `examples_diagnosis.jsonl` / `examples_debiasing.jsonl`（示例数据）
- **依赖**：`torch transformers scipy tqdm`
- **运行方式**：
  ```bash
  bash run_diagnosis.sh
  bash run_debiasing.sh
  ```

### 第六章 6.3 · 联邦学习梯度窃取

- **原项目目录**：`5-第六章/6.3小节 实战案例：联邦学习中的梯度数据窃取攻击/`
- **关键文件**：`梯度数据恢复.py`
- **依赖**：`torch torchvision matplotlib numpy`
- **运行方式**：
  ```bash
  pip3 install numpy torch torchvision matplotlib
  python 梯度数据恢复.py
  # 结果输出到 results/ 文件夹
  ```

### 第六章 6.4 · AI 水印对抗隐私泄露

- **原项目目录**：`5-第六章/6.4小节 实战案例：利用AI水印对抗隐私泄露/`
- **关键文件**：
  - `对抗样本保护数据隐私.py`
  - `imagenet.json`（ImageNet 类别名）
  - `cat.png` / `cup.png`（示例图）
- **依赖**：`tensorflow==1.15.5 scipy==1.2.1 matplotlib numpy pillow`
- **预训练模型**：Inception v3（自动下载）
- **运行方式**：
  ```bash
  pip3 install tensorflow==1.15.5
  pip install scipy==1.2.1
  pip3 install matplotlib numpy pillow
  python 对抗样本保护数据隐私.py
  ```

### 第七章 7.2 · 语音克隆

- **原项目目录**：`6-第七章/7.3语音克隆案例/`
- **关键文件**：
  - `test.py`（主入口）
  - `encoder/`（说话人编码器）
  - `synthesizer/`（Tacotron2 合成器）
  - `vocoder/`（WaveRNN 声码器）
  - `models/`（预训练权重）
- **依赖**：`torch tensorflow==1.15 librosa scipy`
- **运行方式**：
  ```bash
  bash run_test.sh
  # 或
  python test.py --srcPath data/src.wav --dstPath output.wav
  ```

### 第七章 7.3 · 深度伪造鉴别

- **原项目目录**：`6-第七章/7.4深度伪造鉴别案例/`
- **关键文件**：
  - `test.py`（主入口）
  - `antifakes/antifakes.py`（鉴别器类）
  - `antifakes/model/`（EfficientNet 实现）
  - `models/model.pth.tar`（预训练权重）
  - `data/deepfake.jpg`（示例图）
- **依赖**：`torch torchvision efficientnet_pytorch opencv-python`
- **运行方式**：
  ```bash
  pip install -r requirements.txt
  bash run_test.sh
  ```

### 第八章 8.2–8.6 · AI Agent 安全（伪代码）

> 🆕 **第八章为本版新增内容**，原项目 `AISec-zip` 不包含 Agent 代码；
> 本章以**伪代码 + 行业事件 + 主流方案**为主线，给出可在 LangGraph / AutoGen / CrewAI 中复现的设计蓝图。

- **原项目目录**：**无**（原项目不包含 Agent 代码）
- **关键伪代码片段**（[详见第八章正文](../08-第八章-AI%20Agent安全：威胁、攻防与防御.md)）：
  - **8.2 威胁建模卡片**：YAML 风格卡片，列出每个 Agent 的输入源 / 工具 / 权限 / 决策步数，逐项对照 OWASP Agentic Top 10。
  - **8.3 Prompt 注入防御**：`AgentLoop` 决策循环 + 启发式 / LLM 自评 / 来源溯源三层检测。
  - **8.4 工具调用防御**：`AgentSandbox.safe_tool_call`（白名单 + JSON Schema + 风险评分 + 人类审批 + 沙箱 + 审计日志）。
  - **8.5 记忆与多 Agent 防御**：`SignedMemory`（HMAC 签名 + TTL + 信任度）+ `send_message` / `receive_message`（HMAC + nonce 防重放）。
  - **8.6 纵深防御**：`SecureMCPClient`（MCP 工具调用加固）+ `AgentActionPolicy`（SELinux 风格状态机）+ `AgentCircuitBreaker`（步数 / 成本 / 工具调用次数熔断）。
- **依赖**：伪代码为思路示意，无强制依赖；可在以下框架中复现：`langgraph`、`autogen`、`crewai`、`mem0`。
- **运行方式**（建议）：
  1. 选择一个 Agent 框架（推荐 LangGraph）。
  2. 复制第八章 8.3.7 节的 `detect_prompt_injection` 启发式检测作为输入层。
  3. 复制 8.4.5 节的 `AgentSandbox.safe_tool_call` 作为工具层。
  4. 复制 8.5.5 节的 `SignedMemory` 作为记忆层。
  5. 复制 8.6.3 节的 `SecureMCPClient` 接入 MCP 服务器。
  6. 用 8.2.2 节的「威胁建模卡片」模板对你的 Agent 逐项检查。
- **参考威胁清单**：OWASP *Agentic AI Threats and Mitigations*（2025）— 见 [附录 B.3.1](#b31-经典论文)。

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
