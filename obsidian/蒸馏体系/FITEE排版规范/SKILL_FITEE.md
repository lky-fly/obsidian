---
name: "FITEE格式审查"
description: "FITEE 期刊（ENGINEERING Information Technology & Electronic Engineering）LaTeX 论文格式审查。检查标题大小写、作者格式、参考文献排序、引用标签、DOI格式、公式字体、图表标题、脚注格式、表格规范、标点符号等。当用户需要审查/检查 FITEE 论文格式时调用。"
---

# FITEE 期刊 LaTeX 论文格式审查

基于 fitee.sty 模板规范、《FITEE期刊LaTeX初排技巧与实例》和《FITEE期刊作者定稿格式规范大纲》。

## ⚠️ 核心工作流程

**第一步：只做审查，不修改文件。**
1. 读取用户指定的 `.tex` 文件
2. 逐项检查格式规范
3. 输出**格式审查报告**
4. **等待用户确认哪些问题需要修改**

**第二步：仅在用户确认后修改。**

---

## 一、首页信息排版

### 1.1 标题
- 仅第一个单词首字母大写，其余非专有名词小写
- 专有名词：人名、地名、机构名、专业术语缩写保持原样（如 Spring Boot, Kubernetes）
- 冒号后的第一个单词首字母小写
- 标题中**禁用** `*`（基金标识）和 `#`（补充材料标识），这两个符号仅在标题末尾右上角

### 1.2 作者姓名
- 名两个字：不空格、不加连字符，直接连接：`Guohao YUAN`
- 姓全部大写：`YUAN`、`CHEN`

### 1.3 单位信息
- 斜体显示
- 城市与邮编之间无标点
- 多个单位时序号也为斜体；单个单位不标序号

### 1.4 日期格式
- May / June / July 用全称，无标点
- 九月缩写：`Sept.`
- 其他月份：前三字母 + 点：`Jan.` `Feb.` `Mar.` `Apr.` `Aug.` `Oct.` `Nov.` `Dec.`
- 前九天日期首位不加 0：`Jan. 8, 2025`（不是 `Jan. 08, 2025`）

### 1.5 DOI 格式
- `https://doi.org/10.1631/ENG.ITEE.xxxx.xxxx`

### 1.6 关键词
- 分隔符为分号（`;`）
- 首单词首字母大写，其余非专有名词小写
- 末尾无标点

### 1.7 CLC 编号
- 根据文章主题判断

### 1.8 页眉
- Arial 字体，由模板 `\markboth` 自动生成
- ⚠️ `\shortauthor` 命令并非所有 fitee.sty 版本都定义。若编译报 `Undefined control sequence`，直接注释/删除该行即可

---

## 二、首页脚注

### 2.1 脚注标识
- 通信作者：`\ddagger`
- 邮箱标识：`\dagger`（所有作者都提供邮箱时去掉）
- ESM 补充材料：`#`
- 基金：`*`
- 每段末尾无标点

### 2.2 邮箱
- 顺序与作者顺序一一对应
- 所有作者都提供邮箱时，作者右上角和 E-mail 前的标识符都去掉

### 2.3 基金信息
- 固定格式：`Project supported by ...`
- 1 个基金号：`(No. xxx)`
- 2 个基金号：`(Nos. xxx and xxx)`
- 3 个及以上：`(Nos. xxx, xxx, and xxx)`
- 基金名前面加 `the`

### 2.4 ORCID
- 格式：`姓名, https://orcid.org/xxxx-xxxx-xxxx-xxxx`
- 一般提供一作和通信作者即可

### 2.5 补充材料 ESM
- 标题右上角加 `#` 符号
- 脚注格式：`Electronic supplementary materials: The online version of this article (https://doi.org/...) contains supplementary materials, which are available to authorized users`

### 2.6 版权声明
- `The Authors 2026. Published by Zhejiang University Press Co., Ltd. This is an open access article distributed under the terms of the CC BY-NC-ND license (https://creativecommons.org/licenses/by-nc-nd/4.0/)`

---

## 三、图表排版

### 3.1 图片通用
- 通栏图宽 160mm，单栏图宽 80mm，一般取栏宽 85%
- 图内字体统一为 **Arial**（截图/Mathtype 公式可放宽）
- 图内文字 7pt，图例 6pt，子图序号 8pt
- 图中线宽 0.75pt
- 图例无边框，背景透明
- 遵循"先提及后出现""就近放置"原则
- **图片格式必须为 `.eps`**（Encapsulated PostScript）。FITEE 使用 dvips 编译链，`.png`/`.jpg`/`.pdf` 等格式一律不支持。若原图为位图或 PDF，需用工具（如 Inkscape、ImageMagick、Adobe Acrobat）转换为 `.eps` 后引用。审查时须 grep 所有 `\includegraphics` 检查扩展名

### 3.2 子图
- 序号为水平方向
- 不设独立子图标题，图中只保留 `(a)` `(b)` 序号
- 子图说明移到整体图题中

### 3.3 图题
- 句末**无句号**
- 有子图时格式：`Main title: (a) 子图说明（首字母小写，专有名词除外）; (b) 子图说明`
- 标题内容为**粗体**
- 不以 `the` 开头，开头为 the 时去掉

### 3.4 图片引用
- 文内引用：`Fig. 3a` 或 `Figs. 3a and 3b`
- 字母**不加括号**

### 3.5 表格通用
- 统一为**三线表**：无垂直/倾斜线条，仅水平横线
- 正文 `\small`（8pt），表注 `\footnotesize`（7pt），表注末尾无标点
- 五位及以上数字以小数点为界，每三位加不间断空格（`~`）
- 数据小数位数保持一致，引用文献数据按原文原样

### 3.6 表格尺寸
- **通栏表格**：宽度 18 cm
- **单栏表格**：宽度 7.95 cm
- 上/下栏线：`\toprule[0.75pt]`、`\bottomrule[0.75pt]`
- 中间横线：`\midrule[0.5pt]`

### 3.7 表格内容
- 内容为**悬挂缩进**
- 表头**白体居中**（不加粗）
- 多行无横线时**首行对齐**；加横线时居中对齐
- 表注与第一列内容左对齐

### 3.8 表格代码
- 跨行：`\multirow`
- 跨列：`\multicolumn`
- 断开横线：`\cmidrule`
- 列对齐：`l`（左）、`c`（中）、`r`（右）

---

## 四、公式排版

### 4.0 变量速判"三问法"
拿到一个符号，按顺序问三个问题：

| 问 | 判断 | 结论 |
|----|------|------|
| ① 几个字母？ | 多字母缩略词（MAE, Gbps, Loss） | → `\mathrm{}` 正体，**立刻定案** |
| ② 变量还是函数/常量？ | 已知函数(sin, σ, tanh)、数字、e/π/d/j | → 正体，**立刻定案** |
| ③ 能加粗吗？ | 单字母向量/矩阵/张量(W, h, x, C) | → `\bm{}` 粗斜体 |

**三个一票否决（看到立刻定案）：**
- 多字母缩写 → 100% `\mathrm{}`
- e, π, d(微分), j(虚部) → 100% `\mathrm{e}`, `\mathrm{d}`
- 下标/上标是单词缩写（pre, thr, opt, max）→ 100% `_{\mathrm{pre}}`

**上下文敏感（同一符号不同含义）：**
- `σ` 做 sigmoid 函数 → 正体；做标准差变量 → 斜体
- `E` 做数学期望 → `\mathbb{E}` 空心正体；做普通变量 → 斜体

### 4.1 正斜体规则

| 类型 | 字体 | 示例 |
|------|------|------|
| 单字母变量/常量 | **斜体** | `l` `h` `a` `b` `c` `N` `M` |
| 矩阵/矢量/张量（单字母） | **粗斜体** `\bm{}` | `\bm{M}` `\bm{b}` |
| ⚠️ **矩阵/矢量粗斜体判断排除自动审查** | 需结合语境判断（变量 vs 常量、单字母 vs 多字母），**此项由人工审查** | |

| 多字母矩阵 | **正黑体** | |
| 自然常数 e、圆周率 π、微分 d、虚部 j | **正体** | `\mathrm{e}` |
| sin、cos、lg、T（转置） | **正体** | `\sin` `\mathrm{T}` |
| 普朗特数 Pr、努塞尔数 Nu、雷诺数 Re | **斜体** | |
| 多字母变量（Error、max、MMN） | **正体** `\mathrm{}` | `\mathrm{Error}` |
| 单位（Gbps、GB、vCPUs） | **正体** `\mathrm{}` | `\mathrm{Gbps}` |
| 运算符、标点、括号、数字 | **正体** | |
| 空心正体 | `\mathbb{}` | `\mathbb{E}` |
| 花体字母 | `\mathcal{}` | |

### 4.2 上下标规则
- 单字母变量下标：**斜体** → `$f_{t}$`（不要用 `$f_{\text{t}}$`）
- 单词首字母/缩写下标：**正体** → `$L^{\mathrm{pre}}$`
- 序数上标：**正体** → `10^{\mathrm{th}}`

### 4.3 公式标点与引用
- 公式后接新句：末尾用句号 `.`
- 公式后接 where 等：末尾用逗号 `,`
- 条件在逗号后空 3-4 格（`\qquad`）
- 引用单个公式：`Eq. (1)`
- 引用两个公式：`Eqs. (1) and (2)`
- 引用多个公式：`Eqs. (1)–(5)`
- 引用不等式：`Inequality (1)`
- **数字必须加括号**

---

## 五、文献排版

### 5.1 排序规则
**规则 1** — 按第一作者姓氏首字母（A→Z）排列

**规则 2** — 一作姓氏相同时：
- 作者数不同 → 按数量从**少到多**
- 作者数相同 + 仅 2 位作者 → 按二作姓氏首字母
- 作者数相同 + 3 位及以上 → 按年份先后

**规则 3** — 一作相同 + 年份相同时：
- 出版源相同 → 按出版时间/刊次
- 出版源不同 → 按论文题目首个非虚词排序
- 年份重复时加 a、b、c 区分（如 2022a, 2022b）

### 5.2 正文引用
- 充当句子成分（主语/跟在 in/according to 后）：`\cite` → `Chen et al. (2023)`
- 不充当句子成分：`\citep` → `(Chen et al., 2023)`
- 1 位作者：`Chen (2023)`
- 2 位作者：`Chen and Zhang (2023)`
- 3 位及以上：`Chen et al. (2023)`
- 多篇引用：先年份后姓氏排序
- 一作同姓时加名字缩写：`Li JX et al. (2024)` vs `Li JZ et al. (2024)`

### 5.3 引用标签（\bibitem 参数）
- 一作同姓时必须加名字缩写区分：`Ding TC {et~al.}` vs `Ding WH {et~al.}`
- 同姓 2 作者：`Liu F and Weissman`
- 同姓 1 作者 vs 多作者：`Zhang Y` vs `Zhang CY {et~al.}`

### 5.4 大小写
- 论文标题仅第一个单词首字母大写，专有名词除外
- 冒号后首字母小写

### 5.5 DOI/URL 格式
- **不要用反引号**括起来
- 末尾**不要有句号**
- 正确：`https://doi.org/10.1109/CCGrid.2014.104`

### 5.6 会议序数词
- 上标正体：`54^{\mathrm{th}}` `21^{\mathrm{st}}` `32^{\mathrm{nd}}` `43^{\mathrm{rd}}`
- 注意 11th、12th、13th 不是 11st、12nd、13rd

### 5.7 栏末平衡
- `\balance` 放 `\begin{thebibliography}` **之前**
- 或使用 `\usepackage{flushend}`

### 5.8 期刊/会议格式
- 期刊：`作者姓名, 年份. 标题. 期刊名(缩写), 卷(期):页码-页码. https://doi.org/...`
- 会议：`作者姓名, 年份. 标题. 会议名, p.页码-页码. https://doi.org/...`
- 会议名称**正体**（不用 `{\em ...}`）
- 序数词**上标**：`28\textsuperscript{th}`、`3\textsuperscript{rd}`、`22\textsuperscript{nd}`

### 5.9 期刊/会议名缩写
- `Parallel` → `Parall.`（期刊/会议名中一律缩写）
- `Distributed` → `Distrib.`
- `Processing` → `Process.`
- 审查时须 grep 期刊/会议名中的 `Parallel` 等关键字检查缩写

---

## 六、文本通用

### 6.1 标点符号
- 三个及以上并列：`a, b, and c`（and 前加逗号）
- 单位与括号间空一格：`10 m (10 meters)`
- `°`、`%` 与数字间无空格
- 连字符 `-`、短一字线 `--`、破折号 `---` 用法区分

### 6.2 章节格式
- 结论标题：`Conclusions`（首字母大写其余小写）
- 基金：`Acknowledgments`，格式 `This work was supported by ...`
- 利益冲突：`Conflict of interest`
- 数据可用性：`Data availability`
- 作者贡献：`Contributors`
- AI 声明：`Declaration on the use of generative AI tool`
- ⚠️ **算法 caption** 同样适用首词大写规则：`\caption{Leader--follower election algorithm}`

### 6.3 正文禁列表
- 正文中**禁止使用列表环境**（`enumerate`、`itemize`、`description`）。FITEE 期刊正文采用段落格式，贡献/创新点等须改为 `1.~... 2.~...` 编号段落
- 子条目缩进用 `\hspace{2em}`
- 列表项开头的**粗体关键词去除**，改为句首大写的段落首句
- 审查时须 grep `\begin{enumerate}`、`\begin{itemize}` 检查非图表区域是否有列表使用
- ⚠️ **禁止正文中 `\mbox{}` 防止换行**：`\mbox{unbalanced}` 这类会破坏段落自动换行，应直接写 `unbalanced`

---

## 七、布局与间距

### 7.1 浮动体
- `\vspace` 在 `\begin{table}`/`\begin{figure}` 之前无效
- 表格上方间距用局部 `\setlength{\textfloatsep}{}`

### 7.2 多余代码
- 重复的 `\makeatletter`、`\small`、`\usepackage`
- `breaklinks=true` + dvips 驱动不兼容
- ⚠️ **`\usepackage{lmodern}` 会覆盖 Arial**：`lmodern` 加载后将 `\sfdefault` 改为 Latin Modern Sans，覆盖 fitee.sty 设置的 Arial。必须删掉
- ⚠️ **`\usepackage[T1]{fontenc}` 重复加载**：fitee.sty 已自带（第 29 行），.tex 中无需再写
- ⚠️ **矢量字替代方案**：若需 Type 1 矢量正文字体但不破坏 Arial，用 `\usepackage{ae,aecompl}` 替代 `lmodern`

### 7.3 字体故障排查
- `uarial` 包安装后字体仍非 Arial → 终端执行 `initexmf --mkmaps` + `initexmf --update-fndb` 重建字体映射
- `[scaled]` 选项在某些 MiKTeX 版本下可能导致 uarial 加载失败 → 去掉该选项
- uarial 彻底无法工作时，回退方案：`\usepackage{helvet}` + `\renewcommand{\sfdefault}{phv}`（Helvetica，FITEE 接受）

---

## 审查清单（每次审查必须逐项检查，不得遗漏）

| # | 检查项 | grep 命令 / 检查方法 | 对应规则 |
|---|--------|---------------------|----------|
| 1 | 标题大小写 | grep `\title{` → 首词大写其余小写 | 1.1 |
| 2 | 作者姓大写 | grep `\author[` → 姓全大写 | 1.2 |
| 3 | 关键词分号分隔、小写 | grep `\keywords{` → 分号、首词外小写 | 1.6 |
| 4 | DOI 格式 | grep `\doi{` | 1.5 |
| 5 | `\shortauthor` 是否存在 | grep `\shortauthor` → 若模板不支持则删 | 1.8 |
| 6 | **章节标题句首大写其余小写** | grep `\section{` `\subsection{` → 逐条检查 | 6.2 |
| 7 | 图片格式 `.eps` | grep `includegraphics` → 不得有 `.png`/`.pdf`/`.jpg` | 3.1 |
| 8 | **vspace 在浮动体前无效** | grep `vspace`→ 在 `\begin{figure}`/`\begin{table}` 前→无效 | 7.1 |
| 9 | 图题句末无句号 | grep `\caption{`→ 结尾不得有 `.}` | 3.3 |
| 10 | 图/表/算法标题仅首词大写 | grep `\caption{`→ 除首词和专有名词外，其余单词全小写（含算法caption） | 3.3/6.2 |
| 11 | **正文禁止列表环境** | grep `\begin{enumerate}` `\begin{itemize}` → 非算法区 → 违规 | 6.3 |
| 12 | 公式多字母缩略正体 | grep 正文 MAE/MAPE/RMSE → `\mathrm{MAE}` | 4.1 |
| 13 | 公式下标缩略正体 | grep `_{\text{` `^{\text{` → 确认非变量 | 4.2 |
| 14 | 公式上标缩略正体 | grep `^{pre}` `^{opt}` `^{thr}` → `^{\mathrm{...}}` | 4.2 |
| 15 | 数学期望 `\mathbb{E}` | grep `E[` `E_{` → 应为 `\mathbb{E}` | 4.1 |
| 16 | 公式结尾标点 | grep `\end{equation}` `\end{align}` `\end{gather}` → **逐行**读前一行末尾：接 where/Here → 逗号 `,`；接新句/空行 → 句号 `.` | 4.3 |
| 17 | **会议名正体（去 `{\em`）** | grep `{\em .*Int Conf` `{\em .*Int Symp` | 5.8 |
| 18 | **会议名 `Parallel`→`Parall.`** | grep `Parallel`→ 期刊/会议名中缩写 | 5.9 |
| 19 | 会议序数词上标 | grep `\d{2}th\b` `\d{1,2}nd\b` `\d{1,2}rd\b` → 改为 `\textsuperscript` | 5.6 |
| 20 | DOI 末尾无句号 | grep `https://doi`→ 末尾不得有 `.` | 5.5 |
| 21 | `\makeatother` 拼写 | grep `\makeat` → 必须有 `h` | — |
| 22 | **矩阵/矢量粗斜体（跳过）** | 人工审查，不自动检查 | 4.1 |
| 23 | **`lmodern` 污染 Arial** | grep `lmodern` → 必须删掉 | 7.2 |
| 24 | **`T1{fontenc}` 重复加载** | grep `fontenc` → fitee.sty 已有则删 | 7.2 |
| 25 | **正文禁用 `\mbox{}`** | grep `\mbox` → 正文段落中不应有（公式/算法除外） | 6.3 |
| 26 | **浮动体禁用 `[H]`** | grep `[H]` → 改为 `[ht!]` 或 `[t]`（`[H]` 会卡死浮动体） | 7.1 |

> **执行方式**：审查时按此表逐行执行 grep，输出命中行，再人工判断是否违规。不得跳过任何行。

---

## 审查报告格式

```
## FITEE 格式审查报告

### 文件：[文件名]

---

### 一、首页信息（共 X 处）
| # | 问题 | 位置 | 建议 |
|---|------|------|------|

### 二、图表（共 X 处）
...

### 三、公式（共 X 处）
...

### 四、参考文献（共 X 条）
...

### 五、其他（共 X 处）
...

---

### 总结：共发现 X 处问题
请告诉我哪些问题需要修改，我再进行修改操作。
```
