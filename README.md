<!--
  ============================================================
  Eric / Summery36 — GitHub Profile README
  语言：中文为主，技术术语保留英文
  配色：强调色 #58A6FF + tokyonight
  已验证可用的图床服务（2026-09-29 实测 HTTP 200）：
    · capsule-render.vercel.app        ✅
    · readme-typing-svg.demolab.com    ✅
    · github-profile-summary-cards.vercel.app ✅
    · streak-stats.demolab.com         ✅
    · komarev.com/ghpvc                ✅
    · img.shields.io                   ✅
    · skillicons.dev                   ✅（注意：不支持 huggingface 图标）
  已失效、不要再用（实测）：
    · github-readme-stats.vercel.app   ❌ 503 DEPLOYMENT_PAUSED
    · github-readme-activity-graph.vercel.app ❌ 402 DEPLOYMENT_DISABLED
    · github-profile-trophy.vercel.app ❌ 402 DEPLOYMENT_DISABLED
  ============================================================
-->

<!-- ===== 一、顶部动态横幅（波浪 + 文字闪烁） ===== -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=190&section=header&text=Eric&desc=Post-training%20%26%20RL%20for%20LLM%20Agents&fontSize=52&descSize=18&fontColor=ffffff&descColor=e6edf3&animation=twinkling&fontAlignY=34&descAlignY=54" width="100%" alt="header"/>
</p>

<!-- ===== 二、打字机滚动字幕 ===== -->
<h3 align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=900&color=58A6FF&center=true&vCenter=true&width=760&lines=LLM+Post-training+%7C+SFT+%C2%B7+GRPO+%C2%B7+Reward+Design;Agentic+RL+%7C+Multi-turn+Tool+Use+%26+Long-horizon;Educational+AI+%7C+Verifiable+Interaction+Environments" alt="Typing SVG" />
</h3>

<!-- ===== 三、基本信息 ===== -->
<p align="center">
  🎓 华东师范大学 · 大数据技术与工程 · 硕士在读<br>
  🔬 研究方向：大语言模型后训练（SFT / RL / Reward）与 LLM Agent<br>
  📧 <a href="mailto:1127232045@qq.com">1127232045@qq.com</a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Summery36&label=Profile%20Views&color=0e75b6&style=for-the-badge" alt="profile views"/>
  <a href="https://github.com/Summery36?tab=followers"><img src="https://img.shields.io/github/followers/Summery36?style=for-the-badge&logo=github&label=Followers&color=2eb85c" alt="followers"/></a>
  <a href="https://www.xiaohongshu.com/user/profile/66b39cbf000000001d023c84"><img src="https://img.shields.io/badge/Xiaohongshu-%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95-FF2442?style=for-the-badge&logoColor=white" alt="Xiaohongshu"/></a>
</p>

---

<!-- ===== 四、News ===== -->
## 📰 News

- **2026.09** 启动教育 Agent 方向科研工作（3D 场景生成 × 语言教育），目标 **BEA 2027**
- **2026.09** 开始 LLM Agent 的运行时（runtime）与评测相关工作
- **2026.0X** 入职某教育科技公司，任大模型算法实习生，负责数学解题方向后训练
- **2026.0X** 完成 AgenticRAG 端到端流程（数据合成 → SFT → 多轮 GRPO）

---

<!-- ===== 五、项目 ===== -->
## 🚀 Projects

### 1️⃣ 教育大模型后训练：数学解题卡点识别与精准提示
`LLM Post-training` · `SFT` · `Synthetic Data` · `Evaluation`

给定「题目 + 正确解法 + 学生半成品过程」，输出卡点分析与下一步提示（不泄露答案）。

- **任务定义**：把辅导拆成「错因诊断」与「下一步引导」两个可评测子任务，建立可判定的任务契约
- **数据合成**：弱模型自然采样 vs 注入构造的对照实验；使用多弱模型构成学生池防止 teacher 过拟合，训练池与评测池分离
- **训练**：Qwen 7B + LoRA SFT（LLaMA-Factory）
- **评测设计**：迁移测试（教完 A 题后紧随相似变式 A′，区分「真教会」与「喂答案」）；math-verify 做符号等价判分，lm-evaluation-harness 编排
- **状态**：in progress
<!-- 📌 待补：把报告转成 PDF 挂上来，或整理成公开仓库后替换此链接 -->
- 📄 技术报告（整理中）

### 2️⃣ AgenticRAG：金融多跳问答
`LangGraph` · `Multi-turn RL` · `verl` · `Retrieval`

金融半年报多跳 QA 的端到端 Agentic RAG 流程。

- **检索层**：FAISS + BGE-M3 密集检索 / BM25 + jieba 稀疏检索 / NetworkX 知识图谱，RRF 融合 + Cross-Encoder 重排
- **编排层**：LangGraph PEV 循环（planner → executor → verifier → synthesizer，含 replan）
- **训练**：Qwen3-4B + LoRA SFT；verl 多轮 tool-agent GRPO（max 7 assistant turns, n=4），加权奖励 = hop precision/recall + 三维 LLM Judge（Faithfulness / Correctness / Groundedness）+ 格式与检索充分性
- **评测**：EM / F1 / hop_recall + hop-aware 消融 + 三维 Judge
- **状态**：in progress
<!-- ⚠️ Summery36/FinMultiHop-AgenticRAG 仓库目前是空的（0 KB），指向它会变成死链。先 push 代码再取消注释。 -->
<!-- - 💻 [代码](https://github.com/Summery36/FinMultiHop-AgenticRAG) -->

### 3️⃣ 购物 Agentic RL：长程多轮决策
`veRL` · `GRPO` · `Long-horizon`

基于公开基线 [`YYHDBL/shopping-grpo-longhorizon`](https://github.com/YYHDBL/shopping-grpo-longhorizon) 的迭代版本。我的增量：细化信用分配与奖励设计。

- **技术栈**：veRL 0.8.0 + Qwen3.5-2B + GRPO，规则化成功率奖励，ShopSimulator v2.1 环境
- **基线结果（Final-200）**：Base 0% → LoRA SFT 60.5% → GRPO 62.0%
- **我的结果**：in progress
- **状态**：in progress
<!-- 📌 待补：迭代版本的仓库链接 -->

### 4️⃣ 教育 Agent：3D 场景生成 × 语言教育
`Agentic Generation` · `Symbolic Verification` · `Reward Design`

用 LLM 生成 JSON 场景图，配合符号化资产库与确定性 oracle，把「场景能否逼出目标语言结构」变成可判定的生成约束。

- **三层架构**：场景图（JSON，字段可编辑）/ 资产库（封闭目录，LLM 只能引用不能发明）/ oracle（几何规则判定正确性，不依赖模型自评）
- **核心动机**：one-shot 生成无法满足教学约束，因此 agentic 的「提议 → 校验 → 修订」循环是被约束逼出来的，而非装饰
- **与 RL 的衔接**：确定性 oracle 天然构成不可 hack 的 reward，可作为 RLVR 环境
- **状态**：in progress（论文 target BEA 2027）
<!-- 📌 待补：项目页或 demo 视频链接 -->

---

<!-- ===== 六、实习经历 ===== -->
## 💼 Experience

**大模型算法实习生** — 某教育科技公司 ｜ 2026.0X – 至今

- 负责数学解题方向的后训练数据与训练流程，定义「卡点识别 + 下一步提示」任务契约
- 设计错误类型分类体系（`correct_stuck` / `wrong_direction` / `calc_error`）及对应合成方案，并用对照实验比较弱模型自然采样与注入构造两条路线
- 构建多弱模型学生池与迁移测试评测协议，验证模型是「真教会」而非「喂答案」
- 技术栈：Qwen 7B · LoRA SFT · LLaMA-Factory · math-verify · lm-evaluation-harness

---

<!-- ===== 七、论文 ===== -->
## 📄 Publications

**Working Paper** — 3D 场景生成 × 语言教育 ｜ targeting **BEA 2027**

探索将二语习得中的 task-essentialness 形式化为可判定的生成约束，用于自动生成任务必需的交互式教学场景。

---

<!-- ===== 八、研究方向 ===== -->
## 🔬 Research Interests

- **LLM Post-training｜大模型后训练** — SFT、GRPO、Reward 设计、Agentic 训练
- **LLM Agents｜智能体** — 多轮工具调用、长程决策、评测与运行时
- **Educational AI｜教育智能** — 教育场景下的解题辅导与可验证交互环境生成

---

<!-- ===== 九、技能 ===== -->
## 🛠️ Skills

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,pytorch,docker,linux,git,redis,postgres,bash&theme=dark" alt="skills"/>
</p>

- **训练与后训练**：PyTorch · veRL / verl · LLaMA-Factory · LoRA / SFT · GRPO（multi-turn、tool-agent）
- **推理与部署**：vLLM · HuggingFace Transformers · FastAPI
- **Agent 与检索**：LangGraph · FAISS · BGE-M3 · BM25 · RRF + Cross-Encoder 重排 · NetworkX
- **评测**：lm-evaluation-harness · OpenCompass · math-verify · LLM-as-a-Judge · 消融实验设计
- **数据与基础设施**：Spark · SQL · Docker · Linux · Git

---

<!-- ===== 十、GitHub 数据（动效：卡片自带上浮渐显动画） ===== -->
## 📊 GitHub Stats

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Summery36&theme=tokyonight" width="98%" alt="profile details"/>
</p>

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Summery36&theme=tokyonight" height="165" alt="top languages"/>
  <img src="https://streak-stats.demolab.com/?user=Summery36&theme=tokyonight&hide_border=true&date_format=Y.n.j" height="165" alt="GitHub Streak"/>
</p>


  🐍 贪吃蛇贡献图：需先跑一次 GitHub Action 生成，见 .github/workflows/snake.yml
  Action 首次运行成功后，取消下面这段注释即可显示。

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Summery36/Summery36/output/github-snake-dark.svg"/>
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Summery36/Summery36/output/github-snake.svg"/>
    <img src="https://raw.githubusercontent.com/Summery36/Summery36/output/github-snake.svg" alt="contribution snake"/>
  </picture>
</p>


---

<!-- ===== 十一、联系方式 ===== -->
## 🤝 Connect with Me

<p align="center">
  <a href="mailto:1127232045@qq.com">
    <img src="https://img.shields.io/badge/Email-1127232045%40qq.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <a href="https://github.com/Summery36">
    <img src="https://img.shields.io/badge/GitHub-Summery36-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
  <a href="https://www.xiaohongshu.com/user/profile/66b39cbf000000001d023c84">
    <img src="https://img.shields.io/badge/Xiaohongshu-%E5%AD%A6%E4%B9%A0%E8%AE%B0%E5%BD%95-FF2442?style=for-the-badge&logoColor=white" alt="Xiaohongshu"/>
  </a>
</p>

<!-- ===== 十二、底部动态波浪 ===== -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer" width="100%" alt="footer"/>
</p>
