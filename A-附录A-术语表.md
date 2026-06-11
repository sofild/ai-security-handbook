# 附录 A · 术语表（中英对照）

> 本附录整理了 AI 安全领域常见术语，便于检索。
> 排序按字母顺序（A–Z），中英对照 + 简释。

---

| 中文 | 英文 | 简释 |
|---|---|---|
| **白盒攻击** | White-box Attack | 攻击者知道模型的全部信息（结构、参数、梯度） |
| **半监督学习** | Semi-supervised Learning | 训练数据中部分带标签，部分不带 |
| **版权风险** | Copyright Risk | 生成内容与已有作品过于相似 |
| **保护模型** | Defensive Distillation | 用蒸馏后的模型提高鲁棒性 |
| **背景一致性** | Background Consistency | 鉴别伪造时检查背景与前景的连贯性 |
| **暴力破解** | Brute Force | 穷举所有可能 |
| **差分隐私** | Differential Privacy (DP) | 单条样本对模型影响有界的严格隐私定义 |
| **成员推断** | Membership Inference Attack (MIA) | 推断某条数据是否在训练集中 |
| **触发器** | Trigger | 后门攻击中的"激活钥匙" |
| **错觉扰动** | Perceptual Perturbation | 影响人类感知但不破坏语义的扰动 |
| **脆弱水印** | Fragile Watermark | 检测到篡改会失效的水印 |
| **代理任务** | Surrogate Task | 替代原任务的简单任务，常用于迁移学习 |
| **低效攻击** | Low-efficiency Attack | 投入大但效果有限的攻击 |
| **多模态攻击** | Multimodal Attack | 跨模态（图像+文本）联动攻击 |
| **恶意输入** | Adversarial Input | 经过对抗性扰动的输入 |
| **二阶近似** | Second-order Approximation | 保留到二阶导的近似 |
| **FGSM** | Fast Gradient Sign Method | 单步对抗攻击经典方法 |
| **反向传播** | Back-propagation | 神经网络训练的核心算法 |
| **分类器** | Classifier | 输出离散类别的模型 |
| **分块扰动** | Patch Perturbation | 在局部区域施加扰动 |
| **风格迁移** | Style Transfer | 把一种图像风格迁移到另一种 |
| **高斯噪声** | Gaussian Noise | 正态分布的随机噪声 |
| **攻击面** | Attack Surface | 系统可被攻击的所有接口 |
| **供应链攻击** | Supply Chain Attack | 通过污染上游组件实施攻击 |
| **后门** | Backdoor / Trojan | 模型内建的"暗门" |
| **混淆矩阵** | Confusion Matrix | 分类结果的 2x2 矩阵 |
| **活跃度** | Activation | 神经元在某一输入下的输出 |
| **激活函数** | Activation Function | 非线性变换，如 ReLU、Sigmoid |
| **基于梯度的攻击** | Gradient-based Attack | 利用梯度信息构造对抗样本 |
| **监督学习** | Supervised Learning | 训练数据带标签 |
| **检测器** | Detector | 识别对抗样本或后门的辅助模型 |
| **交叉熵** | Cross-Entropy | 分类任务常用损失函数 |
| **教师模型** | Teacher Model | 蒸馏中提供知识的大模型 |
| **进化算法** | Evolutionary Algorithm | 通过"遗传变异"搜索最优解 |
| **卷积** | Convolution | 提取局部特征的运算 |
| **抗检测** | Evasion | 规避检测器 |
| **可认证鲁棒性** | Certified Robustness | 在扰动下模型行为不变的数学证明 |
| **可解释 AI** | Explainable AI (XAI) | 让模型决策可被人类理解 |
| **可信赖** | Trustworthy | 综合安全、公平、可解释、鲁棒等属性 |
| **联邦学习** | Federated Learning (FL) | 数据不出本地的分布式训练 |
| **联邦蒸馏** | Federated Distillation | 联邦学习 + 知识蒸馏 |
| **离散空间** | Discrete Space | 文本等不可微空间 |
| **联合优化** | Bilevel Optimization | 两个嵌套的优化问题 |
| **零样本攻击** | Zero-shot Attack | 不需训练数据即可发起攻击 |
| **鲁棒性** | Robustness | 模型在异常输入下保持正确的能力 |
| **逻辑回归** | Logistic Regression | 经典分类模型 |
| **伦理风险** | Ethical Risk | 技术应用带来的伦理问题 |
| **盲源分离** | Blind Source Separation | 在不知混合方式下分离源信号 |
| **密码学** | Cryptography | 研究信息加密与解密的学科 |
| **敏感性** | Sensitivity | 模型对输入变化的响应程度 |
| **模糊测试** | Fuzzing | 随机 / 变异输入测试系统 |
| **模型反演** | Model Inversion | 从模型输出反推输入 |
| **模型窃取** | Model Stealing | 通过 API 推断模型结构与参数 |
| **目标类** | Target Class | 攻击者希望模型输出的类别 |
| **内容凭证** | Content Credentials | C2PA 标准的来源凭证 |
| **内在动机** | Intrinsic Motivation | AI Agent 的内部目标 |
| **内容安全** | Content Safety | 防止生成有害内容 |
| **偏差 / 偏见** | Bias | 模型对特定群体不公平 |
| **迁移性** | Transferability | 在一个模型上构造的扰动能攻击其他模型 |
| **强化学习** | Reinforcement Learning (RL) | 通过"试错"学习策略 |
| **强鲁棒训练** | Strong Adversarial Training | PGD 训练等加强版对抗训练 |
| **扰动** | Perturbation | 加在输入上的微小修改 |
| **人类反馈** | Human Feedback | RLHF 中的人类评估 |
| **人脸识别** | Face Recognition | 识别 / 验证人脸身份 |
| **熵** | Entropy | 信息论中度量不确定性的量 |
| **深度伪造** | Deepfake | 用 AI 生成的伪造内容 |
| **深度神经网络** | Deep Neural Network (DNN) | 多层神经网络 |
| **审计** | Audit | 系统性检查与回溯 |
| **生物信号** | Biometric Signal | 眨眼、脉搏等生理特征 |
| **时间一致性** | Temporal Consistency | 视频帧间的连贯性 |
| **实时克隆** | Real-time Cloning | 实时合成声音 / 视频 |
| **受害模型** | Victim Model | 被攻击的模型 |
| **数据投毒** | Data Poisoning | 篡改训练数据 |
| **数据集蒸馏** | Dataset Distillation | 把大数据集压缩为少量代表样本 |
| **数字水印** | Digital Watermark | 嵌入内容中的标识信息 |
| **双层优化** | Bilevel Optimization | 见"联合优化" |
| **梯度** | Gradient | 损失函数对参数的导数 |
| **梯度裁剪** | Gradient Clipping | 限制梯度最大范数 |
| **梯度泄露** | Gradient Leakage | 从梯度反推数据 |
| **梯度符号** | Gradient Sign | 梯度的元素级正负号 |
| **通用触发器** | Universal Trigger | 与输入无关的触发器 |
| **同步性检测** | Lip Sync Detection | 嘴型与音频的一致性 |
| **图像识别** | Image Recognition | 给图像打标签 |
| **Threat Model** | 威胁模型 | 攻击者拥有什么知识、目标、资源 |
| **推理** | Inference | 用训练好的模型做预测 |
| **投票机制** | Voting | 多模型 / 多帧投票决策 |
| **脱敏** | Desensitization | 去除个人识别信息 |
| **外部知识** | External Knowledge | 模型训练时未见的知识 |
| **完整度** | Completeness | 验证指标 |
| **微调** | Fine-tuning | 在预训练模型上做少量训练 |
| **未授权访问** | Unauthorized Access | 未经许可使用系统 |
| **文本分类** | Text Classification | 给文本打标签 |
| **稳定性** | Stability | 模型对输入变化的鲁棒性 |
| **物理世界** | Physical World | 真实环境（非数字） |
| **误报率** | False Positive Rate (FPR) | 负样本被错判为正的比例 |
| **稀疏化** | Sparsification | 让梯度 / 模型更稀疏 |
| **细粒度** | Fine-grained | 细致的分类（如鸟类品种） |
| **下降法** | Gradient Descent | 沿负梯度方向更新参数 |
| **限速** | Rate Limiting | 控制单位时间内的请求数 |
| **相对熵** | KL Divergence | 两个分布的距离 |
| **混淆** | Obfuscation | 隐藏 / 伪装信息 |
| **训练数据** | Training Data | 用于训练模型的数据 |
| **训练数据提取** | Training Data Extraction | 从模型中还原训练样本 |
| **隐私** | Privacy | 个人信息保护 |
| **隐私预算** | Privacy Budget | 差分隐私中的 ε |
| **隐写** | Steganography | 把信息隐藏在内容中 |
| **语音克隆** | Voice Cloning | 用 AI 合成特定人的语音 |
| **预训练** | Pre-training | 大规模数据上先训练 |
| **源模型** | Source Model | 知识蒸馏中的原始大模型 |
| **远程攻击** | Remote Attack | 通过网络发起攻击 |
| **噪声** | Noise | 随机扰动 |
| **知识蒸馏** | Knowledge Distillation | 把大模型知识转移到小模型 |
| **置信度** | Confidence | 模型对预测的把握 |
| **中位数** | Median | 排序后中间值 |
| **周期性训练** | Periodic Training | 定期重新训练模型 |
| **众包标注** | Crowdsourcing Annotation | 多人协作标注 |
| **注册水印** | Registered Watermark | 与原始内容绑定的水印 |
| **注入** | Injection | 把恶意数据塞进系统 |
| **转录** | Transcription | 语音转文字 |
| **追溯** | Traceback | 找到攻击来源 |
| **自监督** | Self-supervised Learning | 用数据自身作标签 |
| **自适应攻击** | Adaptive Attack | 知道防御方法后调整攻击 |
| **Tokenizer** | 分词器 | 把文本切成子词 |
| **Token** | 词元 | 文本处理的基本单位 |
| **ToS** | Terms of Service | 服务条款 |
| **TEE** | Trusted Execution Environment | 可信执行环境 |
| **TEE 推理** | TEE Inference | 在可信硬件中推理 |
| **STRIP** | Strong Intentional Perturbation | 一种后门检测方法 |
| **TTS** | Text-to-Speech | 文字转语音 |
| **TPR** | True Positive Rate | 真阳性率 |
| **VLM** | Vision-Language Model | 视觉-语言模型 |
| **ViT** | Vision Transformer | 视觉 Transformer |
| **VoIP** | Voice over IP | 网络电话 |
| **Voice Conversion** | 声音转换 | 把 A 的声音变成 B 的 |
| **VoxCeleb** | 声纹数据集 | 公开说话人识别数据集 |
| **VQ-VAE** | Vector Quantized VAE | 离散潜空间的自编码器 |
| **V&V** | Verification & Validation | 验证与确认 |
| **Voxel** | 体素 | 三维像素 |
| **Wav2Vec** | 语音预训练模型 | Facebook AI 的语音表示模型 |
| **Wav2Lip** | 嘴型同步模型 | 让人物嘴型与音频同步 |
| **WaveRNN** | 波形声码器 | 神经声码器 |
| **WaveNet** | 波形生成模型 | DeepMind 的语音生成 |
| **Web** |  | 万维网 |
| **WPA** | Wi-Fi Protected Access | Wi-Fi 保护访问 |
| **XAI** | Explainable AI | 可解释 AI |
| **XSS** | Cross-Site Scripting | 跨站脚本攻击 |
| **YOLO** | You Only Look Once | 实时目标检测模型 |
| **YAML** | YAML Ain't Markup Language | 数据序列化格式 |
| **ZSL** | Zero-Shot Learning | 零样本学习 |

### 🆕 Agent 安全术语（2026 新增 · 配合第八章阅读）

> 以下术语集中收录 2025–2026 年 AI Agent 安全领域的核心概念，按主题分组便于检索。

| 中文 | 英文 | 简释 |
|---|---|---|
| **AI Agent** | AI Agent | 能感知、推理、行动、记忆的 AI 系统 |
| **Agentic AI** | Agentic AI | 强调自主行动能力的 AI 范式 |
| **代理式 AI** | Agentic AI | Agentic AI 的中文译法 |
| **ReAct** | Reasoning + Acting | 思考 + 行动交织的 Agent 范式 |
| **思维链** | Chain-of-Thought (CoT) | 逐步推理技术 |
| **函数调用** | Function-Calling | LLM 输出结构化工具调用 |
| **MCP** | Model Context Protocol | 2025 年推出的工具调用标准协议 |
| **Computer-Use** | 屏幕键鼠操控 | Agent 直接操控操作系统 |
| **过度授权** | Excessive Agency | Agent 拥有超出实际需要的能力 / 权限 / 自主性 |
| **直接提示词注入** | Direct Prompt Injection | 攻击者直接向 Agent 注入指令 |
| **间接提示词注入** | Indirect Prompt Injection | 通过网页 / 邮件 / 文档间接注入 |
| **记忆投毒** | Memory Poisoning | 篡改 Agent 长期记忆的攻击 |
| **工具误用** | Tool Misuse | 工具被以非预期方式调用 |
| **沙箱逃逸** | Sandbox Escape | 突破 Agent 隔离边界 |
| **级联失败** | Cascading Failure | 错误在多步决策中放大 |
| **行为策略** | Action Policy | 约束 Agent 行为的白名单状态机 |
| **人在环** | Human-in-the-Loop (HITL) | 高风险操作由人审批 |
| **紧急熔断** | Kill-Switch | 人为紧急停止 Agent |
| **熔断器** | Circuit Breaker | 异常时自动中断的模式 |
| **风险评分** | Risk Score | 对工具调用打分以决定是否人审 |
| **TTL** | Time-To-Live | 记忆条目的有效期 |
| **双 LLM 模式** | Dual LLM | 一个读数据、一个决策，隔离注入 |
| **Schema 校验** | Schema Validation | 用 JSON Schema 校验工具参数 |
| **威胁建模卡片** | Threat Model Card | 为每个 Agent 建立的结构化威胁清单 |
| **重放攻击** | Replay Attack | 重复发送历史合法消息 |
| **默克尔日志** | Merkle Log | 不可篡改的追加日志结构 |
| **来源凭证** | Source Provenance | 标注数据 / 工具 / 记忆的来源 |
| **信任度** | Trust Score | 评估来源可信程度的分数 |
| **能力屏蔽** | Capability Masking | 推理时屏蔽 Agent 的某些能力 |
| **可终止性保证** | Termination Guarantee | 证明 Agent 一定在有限步内结束 |

> 本表会随着 AI 安全研究的进展持续更新。

---

> **返回目录：** [README](README.md)
