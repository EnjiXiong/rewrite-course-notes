# rewrite-course-notes

> **Version 1.6.0** · Agent Skill（面向已学过课程、进入考前复习阶段的学生）  
> 按原讲次顺序重构并压缩课程课件（PPTX / Beamer PDF），保留授课原文措辞、完整公式推导链与综合对比结构，输出克制、清晰、可直接打印或电子检索的考前复习讲义。

---

## 1. 简介：这是什么、为什么需要它与排版风格

### 这是什么

`rewrite-course-notes` 是一个标准 **Agent Skill**（主规范见 [SKILL.md](SKILL.md)，版本记录见 [CHANGELOG.md](CHANGELOG.md)）。它服务于**已经学过课程、需要高效复习迎考的学生**，而不是把课件改写成另一本从零讲起的教材。提供课件（PPTX / PDF）与考核范围后，Agent 会按原讲次提取考点、核对公式与勘误、裁剪高价值原图，并生成结构统一的 LaTeX / PDF 复习讲义与可选速查手册。

### 为什么用这个：告别 AI slop 式教学课件

现在很多课程课件和 AI 自动生成的“复习总结”普遍掉进了 **AI slop** 陷阱：页面看似信息满满、色彩绚丽，真正考前翻开时却到处干扰理解。下表把 6 类高频痛点与本 Skill 的对应做法逐行对齐：

| 常见课件 / AI 总结痛点 | 考前复习时的实际干扰 | `rewrite-course-notes` 的处理方式 |
|---|---|---|
| **胡乱堆砌内容** | 定义、背景闲话、前沿展望与重复代入混在同一页，看不完也抓不住必考部分 | • 区分主路径考点与讲末 `[Supplement]` / 扩展区<br>• 删除无新意的单数字代入与已被后文覆盖的旧预览<br>• 保留课堂例题、核心难点与关键反例 |
| **画面纷乱** | 一行塞进多条分号短句，无序列表层层嵌套，视线找不到信息边界 | • 按知识关系选择最小清晰结构（概念属性表、方法对比矩阵、编号动作步）<br>• 严格执行逐行防拥挤，每条独立结论单独起行 |
| **颜色过多** | 彩虹高亮与高饱和度警示框铺满页面，阅读几页就产生强烈视觉疲劳 | • 使用克制的深石板蓝、浅灰与淡绿学术配色（[review-style.sty](assets/review-style.sty)）<br>• Beamer / PPT 中的彩色强调统一转为干净的 `\textbf{}` |
| **重点淡化** | 手算题、公式理解、概念辨析与论文巡礼平铺直叙，不知道该背还是该算 | • 依据课件与演讲者备注，在标题右侧标注低调的掌握深度标签<br>• 计算类与闭卷概念/论文类两套标签按课选用，绝不臆造权重 |
| **主线不清** | 跨讲打乱重排主题，实例与父概念相隔数页，复习时对不上老师的授课脉络 | • 严格保留原讲次外层顺序（Lecture 1 → N），只在各讲内部重组层级<br>• 每个实例紧贴父概念放置，单份规范证明配可跳转交叉引用 |
| **每一页作用不明** | 翻开一页分不清是在学定义、做对比、练推导还是读补充材料 | • 容器语义显式区分：方法框 `reviewmethod`、综合对比 `reviewsynthesis`、例题 `workedexample`、`Exam trap` 与讲末 `supplementbox`<br>• 可按需配可检索目录与经程序校验页码的 Quick-Lookup |

### 本 Skill 的风格与核心机制

| 维度 | 核心规则 | 内置实现与具体例子 |
|---|---|---|
| **原文措辞优先** | 定义、性质、优缺点、代价、假设与对比标签尽量沿用课件原话，压缩靠筛选、去重与版面完成 | • 仅对新增衔接句与步骤动词做润色，不改写老师原话<br>• 发现课件笔误或口径变动时透明标出，不静默修改 |
| **逐行防拥挤** | 禁止在同一行或同一单元格里用分号硬塞多条属性、指标或并行 `Input / Output` | • [review-style.sty](assets/review-style.sty) 内置悬挂缩进表格宏（`\tfirst`/`\ti`、`\tnumfirst`/`\tnum`、`\tsubfirst`/`\tsub`）<br>• 并行输入输出在全宽块中用 `\begin{cases}...\end{cases}` 叠排 |
| **四段式公式计算链** | 必会公式例题必须把已知条件、符号公式、代入过程与结论拆清，不能只给记号与最终数字 | • 独立 `Given` 段落 → 编号动作步 → `记号 = 符号公式 = 代入数值 = 结果`（约等用 `\approx`）→ `Result`<br>• 所有数值例题交付前必须经 Python 脚本验算 |
| **按复杂度分级写证明** | 实质性推导讲清机制，基础恒等式不强行套用笨重模板 | • 实质证明：`Assumptions` + 一句话 `Core idea` + 命名步骤 + 对齐推导 + 可选 `Exam trap`<br>• 基础恒等式：1–3 行直出，不强加 `Core idea` / `Steps` 标题 |
| **两套掌握深度标签** | 按课程真实考试形态二选一，不把一套标签硬套到所有课上 | • **计算 / 应用课（Palette A）**：`[Hand-calc]`、`[Formula: interpret]`、`[Conceptual]`、`[Research preview]`、`[Not in exam scope]`<br>• **闭卷概念 / 论文课（Palette B）**：`[Core Concept]`、`[Contrast / Taxonomy]`、`[Method Map: I/O]`、`[Supplement]` |
| **多模态提取与原图裁切** | 兼顾 PPTX 备注、隐藏页、图片公式与 Beamer 逐页揭示答案 | • PPTX 同步提取演讲者备注与 `show="0"` 隐藏页，缺文本公式的图片页出拼图人工核对<br>• 纯 `PyMuPDF` 300 DPI 自动滤除重复 Logo 裁图，并用紧框 `\slidefig` 嵌入 |
| **单源多版与 8 道安全门** | 一套讲次源码同时编出单讲版与全课合订本，避免版面和检索硬伤 | • 单源 `lectures/lecture_N.tex` + 薄包装文件<br>• 内置 8 道编译与审计门禁（`minipage` 非断页盒、目录 `\texorpdfstring`、双栏目录防撞、跨章引用安全、`(p. #)` 页码与 Ctrl+F 校验） |

### 仓库内容

| 路径 | 作用 |
|---|---|
| [SKILL.md](SKILL.md) | 主技能规范（v1.6.0）：范围建立、讲次顺序、原文保留、例题链、版面与交付门禁 |
| [CHANGELOG.md](CHANGELOG.md) | 从 v1.1.0 到 v1.6.0 的完整版本迭代记录 |
| [assets/review-style.sty](assets/review-style.sty) | 单栏 A4 LaTeX 样式预设（10.8pt 衬线正文、克制石板蓝/绿/灰配色、全部盒子与排版宏） |
| [assets/starter.tex](assets/starter.tex) | 可直接编译的讲义示例（概念对比表、四段式计算链、图文并排、讲次综合表） |
| [assets/proof-layout.tex](assets/proof-layout.tex) | 可直接编译的证明排版示例（基础恒等式 vs. `Core idea` + 命名步骤 + `Exam trap`） |
| [references/structure-and-phrasing.md](references/structure-and-phrasing.md) | 原文保留、反分号堆砌、实例就近放置与四段式公式链细则 |
| [references/figures-and-layout.md](references/figures-and-layout.md) | 表格/框图选型、纯 `PyMuPDF` 300 DPI 裁图流程、模块化构建与 8 道 LaTeX 安全门 |
| [references/retrieval-and-scope.md](references/retrieval-and-scope.md) | 开卷任务-工具速查与闭卷三段式速查、Beamer 提取、深度标签与符号/勘误登记表 |
| [references/mathematical-review.md](references/mathematical-review.md) | 数学/理论课的定理条件、随机性界定、证明机制与数值来源区分 |
| [references/compression-and-release.md](references/compression-and-release.md) | 压缩任务的基线测量、去重删减原则、分册边界与交付前版面审计 |
| [references/preference-evidence.md](references/preference-evidence.md) | 规则演进依据与适用边界（维护技能时查阅） |
| [agents/openai.yaml](agents/openai.yaml) | Codex / Agent 界面发现元数据与默认提示词 |

---

## 2. 配置到 Agent

### 方式 A：通过 Skills CLI 一键安装（推荐）

支持 Codex、Claude Code、Antigravity、Cursor、OpenCode 等兼容 [Agent Skills](https://skills.sh/) 规范的工具：

```bash
npx skills add EnjiXiong/rewrite-course-notes
```

全局安装并跳过交互确认：

```bash
npx skills add EnjiXiong/rewrite-course-notes -g -y
```

### 方式 B：直接 `git clone` 到对应 Agent 的技能目录

本仓库根目录即为完整技能包（包含 `SKILL.md`、`assets/`、`references/`），克隆到对应目录即可生效，后续在目录内运行 `git pull` 即可同步更新：

| Agent / 作用域 | 安装命令 | 对话内调用方式 |
|---|---|---|
| **Codex**（全局） | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.codex/skills/rewrite-course-notes` | `$rewrite-course-notes` |
| **Antigravity**（全局） | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.gemini/config/skills/rewrite-course-notes` | `/rewrite-course-notes` |
| **Claude Code**（全局） | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git ~/.claude/skills/rewrite-course-notes` | `/rewrite-course-notes` |
| **通用 / 项目级**（Cursor、OpenCode、Antigravity 等） | `git clone https://github.com/EnjiXiong/rewrite-course-notes.git .agents/skills/rewrite-course-notes` | 在该仓库对话中直接引用技能名 |

### 可选本地环境依赖（输出 PDF 与解析课件时）

仅生成 Markdown 复习提纲时无需额外依赖。如果需要直接编译 PDF 并自动提取 PPTX 备注、隐藏页与高清原图，建议安装：

1. **LaTeX 编译器**：TeX Live（英文讲义使用 `pdflatex`，中文讲义使用 `xelatex` + `ctex`）。可用内置模板验证环境：
   ```bash
   cp assets/review-style.sty assets/starter.tex /tmp/ && cd /tmp && pdflatex starter.tex && pdflatex starter.tex
   ```
2. **Python 提取库**（按课件格式按需安装）：
   ```bash
   pip install pymupdf python-pptx
   ```

---

## 3. 推荐 Prompt（英文可复制模板）

复制下面整段 Markdown 并替换 `[...]` 中的课程信息即可直接使用（若在 Codex 中调用，将开头的 `/rewrite-course-notes` 改为 `$rewrite-course-notes`）：

```markdown
Use /rewrite-course-notes to build exam review notes for **[Course Code & Title]**.

## 1. Source Files & Lecture Order
- **Source directory:** `[path/to/slides/]`
- **Files included (in lecture order):** `[Lecture 01 .. Lecture N; specify whether PPTX, PDF, or both exist]`
- **Slide numbering convention:** `[Beamer footer slide number / PPTX slide index / raw PDF page]`
- **Extra source materials (optional):** `[homework solutions, midterm review sheet, syllabus, or "None"]`

## 2. Exam Coverage & Scope Boundaries
- **In-scope lectures / topics:** `[e.g., Lectures 1-10 in full, plus Lecture 11 Sections 1-2]`
- **Explicitly excluded from exam:** `[e.g., Lecture 4 Appendix and Lecture 9 research outlook, or "None - confirm before dropping anything"]`
- **Emphasis / exam weights (if known):** `[e.g., Lectures 5-8 account for ~60% of the final, with heavy weight on derivations in L6]`
- **Must-keep examples / exercises:** `[e.g., all in-class Quick Checks and Tutorial 3-5 worked problems]`

## 3. Exam Format & Preferred Assessment Style
- **Exam format:** `[Closed-book / Open-book / One-sheet cheat-sheet allowed]`
- **Question types & focus:** `[e.g., 40% hand calculation, 30% concept comparison and MCQ discrimination, 30% proof reconstruction]`
- **Mastery-depth tag palette:** `[Palette A: Hand-calc / Formula: interpret / Conceptual / Research preview  OR  Palette B: Core Concept / Contrast / Taxonomy / Method Map: I/O / Supplement]`
- **Proof & derivation depth:** `[e.g., full reconstructible proofs for starred theorems, 1-3 lines for elementary identities, statement + conditions + application for APPLY results]`
- **Paper-showcase / conceptual slides (if any):** `[e.g., compress paper tours into Method Map: I/O tables and relocate dense figure-embedded details to lecture-end Supplement boxes]`

## 4. Deliverables, Language & Companion Volumes
- **Output directory:** `[path/to/output/]`
- **Output format & language:** `[LaTeX + compiled PDF using assets/review-style.sty; notes in English (or Chinese with original English canonical terms)]`
- **Build layout:** `[Single-source modular lectures/lecture_N.tex -> standalone per-lecture PDFs + one full bound PDF  OR  single combined PDF]`
- **Page / compression target:** `[e.g., prioritize completeness with clean density  OR  compress an existing draft to ~40-50 main-body pages without shrinking font]`
- **Optional companion volumes (confirm upfront):**
  - `quick-lookup`: `[Yes (open-book task-to-tool index) / Yes (closed-book 3-part contrast + taxonomy + glossary) / No]`
  - `self-test`: `[Yes / No]`
  - `extensions`: `[Yes (separate file) / Keep marked at lecture end / No]`

## 5. Personal Weak Spots & Verification Gates
- **Topics I still find unfamiliar (strengthen worked examples):** `[e.g., Lecture 6 spectral clustering, Lecture 8 EM updates]`
- **Visuals & slide figures:** `[Crop high-value diagrams, conceptual wheels, and pipelines from slides at 300 DPI via PyMuPDF with contact-sheet check; skip decorative clutter]`
- **Mandatory checks before delivery:**
  1. Preserve original slide wording for definitions, properties, assumptions, and trade-offs.
  2. Enforce line-by-line anti-crowding (no semicolon-packed walls in bullets or table cells).
  3. Show complete `notation = symbolic formula = substituted values = result` chains and verify all numerical examples with a Python script.
  4. Maintain a notation, convention-flip, and slide-errata registry (`SOURCE_MAP.md`), and verify zero LaTeX warnings, clean page breaks, searchable text, and audited `(p. #)` pointers.
```

### Prompt 关键字段填写速查

| 字段 | 填写建议 | 对输出结果的直接影响 |
|---|---|---|
| **In-scope / Excluded** | 写清必考讲次与明确排除项，不确定时填 `None` | 避免误删附录中的必考内容，也避免给非考点分配过多篇幅 |
| **Exam format** | 写明 `Closed-book` 或 `Open-book` | 决定速查手册结构（闭卷用对比矩阵 + 分类表 + 缩写表，开卷用任务-工具-页码索引） |
| **Mastery-depth tag palette** | 数理/计算课选 **Palette A**，偏概念/论文课选 **Palette B** | 统一全书的掌握深度标注，不混用两套标签 |
| **Optional companion volumes** | 开工前逐项标明 `Yes` / `No` | 按需生成配套分册，避免多出用不到的冗余文件 |
| **Topics I still find unfamiliar** | 列出 2–4 个最容易卡壳的章节或方法 | 仅在这些位置强化连贯例题与直觉检查，不把整本讲义写臃肿 |
