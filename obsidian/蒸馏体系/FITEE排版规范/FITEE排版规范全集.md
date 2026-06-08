# FITEE 期刊排版规范全集

> 来源：桌面排版资料文件夹 + 文献排版文件夹
> 包含：SKILL_FITEE.md、FITEE格式审查报告.md、FITEE变量归类与速判指南.md、FITEE期刊LaTeX初排技巧与实例、最新模板
> FITEE = Frontiers of Information Technology & Electronic Engineering (Engineering/ENGINEERING)

---

## 一、模板与工具

### 官方模板位置
`D:\desktop\排版资料\最新模板\ENG.ITEE-template_2026-3.18\`

核心文件：
- `fitee.sty` — 主样式文件（668行）
- `sample-new-3.18.tex` — 示例模板
- `fitee.bst` — BibTeX 样式文件
- `uarial.sty` — Arial 字体支持
- `authblk.sty`, `stfloats.sty` — 辅助宏包

### 排版参考
| 文件 | 内容 |
|------|------|
| FITEE期刊LaTeX初排技巧与实例_袁国豪5.7.pdf | 9MB详细排版教程 |
| 作者定稿指南4.13(1).pdf | 官方作者定稿指南 |
| SKILL_FITEE.md | LaTeX格式审查自动化skill |
| 参考稿件/ | 4篇已发表稿件参考 |
| 批注稿件/ | 1篇带批注的修改稿件 |

---

## 二、首页信息排版

### 2.1 标题
- 仅第一个单词首字母大写，其余非专有名词小写
- 专有名词：人名、地名、机构名、专业术语缩写保持原样（如 Spring Boot, Kubernetes）
- 冒号后的第一个单词首字母小写
- 标题中**禁用** `*`（基金标识）和 `#`（补充材料标识），这两个符号仅在标题末尾右上角

### 2.2 作者姓名
- 名两个字：不空格、不加连字符，直接连接：`Guohao YUAN`
- 姓全部大写：`YUAN`、`CHEN`

### 2.3 单位信息
- 斜体显示
- 城市与邮编之间无标点
- 多个单位时序号也为斜体；单个单位不标序号

### 2.4 日期格式
- May / June / July 用全称，无标点
- 九月缩写：`Sept.`
- 其他月份：前三字母 + 点：`Jan.` `Feb.` `Mar.` `Apr.` `Aug.` `Oct.` `Nov.` `Dec.`
- 前九天日期首位不加 0：`Jan. 8, 2025`（不是 `Jan. 08, 2025`）

### 2.5 DOI 格式
```
https://doi.org/10.1631/ENG.ITEE.xxxx.xxxx
```

### 2.6 关键词
- 分隔符为分号（`;`）
- 首单词首字母大写，其余非专有名词小写
- 末尾无标点

### 2.7 CLC 编号
- 根据文章主题判断

### 2.8 页眉
- Arial 字体，由模板 `\markboth` 自动生成
- ⚠️ `\shortauthor` 命令并非所有 fitee.sty 版本都定义。若编译报 `Undefined control sequence`，直接注释/删除该行即可

---

## 三、首页脚注

### 3.1 脚注标识
| 符号 | 用途 |
|------|------|
| `\ddagger` | 通信作者 |
| `\dagger` | 邮箱标识（所有作者都提供邮箱时去掉） |
| `#` | ESM 补充材料 |
| `*` | 基金 |

每段末尾无标点。

### 3.2 邮箱
- 顺序与作者顺序一一对应
- 所有作者都提供邮箱时，作者右上角和 E-mail 前的标识符都去掉

### 3.3 基金信息
- 固定格式：`Project supported by ...`
- 1 个基金号：`(No. xxx)`
- 2 个基金号：`(Nos. xxx and xxx)`
- 3 个及以上：`(Nos. xxx, xxx, and xxx)`
- 基金名前面加 `the`

### 3.4 ORCID
- 格式：`姓名, https://orcid.org/xxxx-xxxx-xxxx-xxxx`
- 一般提供一作和通信作者即可

### 3.5 补充材料 ESM
- 标题右上角加 `#` 符号
- 脚注格式：`Electronic supplementary materials: The online version of this article (https://doi.org/...) contains supplementary materials, which are available to authorized users`

### 3.6 版权声明
```
The Authors 2026. Published by Zhejiang University Press Co., Ltd. This is an open access article distributed under the terms of the CC BY-NC-ND license (https://creativecommons.org/licenses/by-nc-nd/4.0/)
```

---

## 四、图表排版

### 4.1 图片通用
- 通栏图宽 **160mm**，单栏图宽 **80mm**，一般取栏宽 85%
- 图内字体统一为 **Arial**（截图/Mathtype 公式可放宽）
- 图内文字 **7pt**，图例 **6pt**，子图序号 **8pt**
- 图中线宽 **0.75pt**
- 图例无边框，背景透明
- 遵循"先提及后出现""就近放置"原则
- **图片格式必须为 `.eps`**（Encapsulated PostScript）。FITEE 使用 dvips 编译链，`.png`/`.jpg`/`.pdf` 等格式一律不支持。若原图为位图或 PDF，需用工具（如 Inkscape、ImageMagick、Adobe Acrobat）转换为 `.eps` 后引用

### 4.2 子图
- 序号为水平方向
- 不设独立子图标题，图中只保留 `(a)` `(b)` 序号
- 子图说明移到整体图题中

### 4.3 图题
- 句末**无句号**
- 有子图时格式：`Main title: (a) 子图说明（首字母小写，专有名词除外）; (b) 子图说明`
- 标题内容为**粗体**
- 不以 `the` 开头，开头为 the 时去掉

### 4.4 图片引用
- 文内引用：`Fig. 3a` 或 `Figs. 3a and 3b`
- 字母**不加括号**

### 4.5 表格通用
- 统一为**三线表**：无垂直/倾斜线条，仅水平横线
- 正文 `\small`（8pt），表注 `\footnotesize`（7pt），表注末尾无标点
- 五位及以上数字以小数点为界，每三位加不间断空格（`~`）
- 数据小数位数保持一致，引用文献数据按原文原样

### 4.6 表格尺寸
| 类型 | 宽度 |
|------|------|
| 通栏表格 | 18 cm |
| 单栏表格 | 7.95 cm |

线条规格：
- 上/下栏线：`\toprule[0.75pt]`、`\bottomrule[0.75pt]`
- 中间横线：`\midrule[0.5pt]`

### 4.7 表格内容规范
- 内容为**悬挂缩进**
- 表头**白体居中**（不加粗）
- 多行无横线时**首行对齐**；加横线时居中对齐
- 表注与第一列内容左对齐

### 4.8 表格代码
- 跨行：`\multirow`
- 跨列：`\multicolumn`
- 断开横线：`\cmidrule`（禁用 `\cline`）
- 列对齐：`l`（左）、`c`（中）、`r`（右）

---

## 五、公式排版

### 5.1 变量速判"三问法"

```
问题1：几个字母？ → 多字母缩略词 → \mathrm{} 正体，立刻定案
问题2：变量还是函数/常量？ → 已知函数(sin, σ, tanh)、数字、e/π/d/j → 正体，立刻定案
问题3：能加粗吗？ → 单字母向量/矩阵/张量 → \bm{} 粗斜体
```

**三个一票否决：**
- 多字母缩写 → 100% `\mathrm{}`
- e, π, d(微分), j(虚部) → 100% `\mathrm{e}`, `\mathrm{d}`
- 下标/上标是单词缩写（pre, thr, opt, max）→ 100% `_{\mathrm{pre}}`

**上下文敏感（同一符号不同含义）：**
- `σ` 做 sigmoid 函数 → 正体；做标准差变量 → 斜体
- `E` 做数学期望 → `\mathbb{E}` 空心正体；做普通变量 → 斜体

### 5.2 正斜体规则汇总

| 类型 | 字体 | 示例 |
|------|------|------|
| 单字母变量/常量 | 斜体 | `l` `h` `a` `b` `N` `M` |
| 矩阵/矢量/张量（单字母） | 粗斜体 `\bm{}` | `\bm{M}` `\bm{b}` |
| 自然常数 e、π、微分 d、虚部 j | 正体 | `\mathrm{e}` |
| sin、cos、lg、T（转置） | 正体 | `\sin` `\mathrm{T}` |
| 普朗特数 Pr、努塞尔数 Nu、雷诺数 Re | 斜体 | 准则数保留斜体 |
| 多字母变量（Error、max、MMN） | 正体 `\mathrm{}` | `\mathrm{Error}` |
| 单位（Gbps、GB、vCPUs） | 正体 `\mathrm{}` | `\mathrm{Gbps}` |
| 运算符、标点、括号、数字 | 正体 | |
| 空心正体 | `\mathbb{}` | `\mathbb{E}` |
| 花体字母 | `\mathcal{}` | |

### 5.3 上下标规则
- 单字母变量下标：**斜体** → `$f_{t}$`（不要用 `$f_{\text{t}}$`）
- 单词首字母/缩写下标：**正体** → `$L^{\mathrm{pre}}$`
- 序数上标：**正体** → `10^{\mathrm{th}}`

### 5.4 公式标点与引用
- 公式后接新句：末尾用句号 `.`
- 公式后接 where 等：末尾用逗号 `,`
- 条件在逗号后空 3-4 格（`\qquad`）
- 引用单个公式：`Eq. (1)`
- 引用两个公式：`Eqs. (1) and (2)`
- 引用多个公式：`Eqs. (1)–(5)`
- 引用不等式：`Inequality (1)`
- **数字必须加括号**

---

## 六、文献排版

### 6.1 排序规则

**规则1** — 按第一作者姓氏首字母（A→Z）排列

**规则2** — 一作姓氏相同时：
- 作者数不同 → 按数量从**少到多**
- 作者数相同 + 仅2位作者 → 按二作姓氏首字母
- 作者数相同 + 3位及以上 → 按年份先后

**规则3** — 一作相同 + 年份相同时：
- 出版源相同 → 按出版时间/刊次
- 出版源不同 → 按论文题目首个非虚词排序
- 年份重复时加 a、b、c 区分（如 2022a, 2022b）

### 6.2 正文引用格式

| 情况 | 格式 |
|------|------|
| 充当句子成分 | `\cite` → `Chen et al. (2023)` |
| 不充当句子成分 | `\citep` → `(Chen et al., 2023)` |
| 1 位作者 | `Chen (2023)` |
| 2 位作者 | `Chen and Zhang (2023)` |
| 3 位及以上 | `Chen et al. (2023)` |
| 多篇引用 | 先年份后姓氏排序 |
| 一作同姓时 | 加名字缩写：`Li JX et al. (2024)` vs `Li JZ et al. (2024)` |

### 6.3 引用标签（\bibitem 参数）
- 一作同姓时必须加名字缩写区分：`Ding TC {et~al.}` vs `Ding WH {et~al.}`
- 同姓2作者：`Liu F and Weissman`
- 同姓1作者 vs 多作者：`Zhang Y` vs `Zhang CY {et~al.}`

### 6.4 参考文献项格式

**期刊**：
```
作者姓名, 年份. 标题. 期刊名(缩写), 卷(期):页码-页码. https://doi.org/...
```

**会议**：
```
作者姓名, 年份. 标题. 会议名, p.页码-页码. https://doi.org/...
```

### 6.5 格式要点
- 论文标题仅第一个单词首字母大写，专有名词除外
- 冒号后首字母小写
- DOI/URL 末尾**不要有句号**，不要用反引号括起来
- 会议名称**正体**（不用 `{\em ...}`）
- 会议序数词**上标正体**：`54^{\mathrm{th}}`（注意 11th/12th/13th 不是 11st/12nd/13rd）
- 栏末平衡：`\balance` 放 `\begin{thebibliography}` **之前**

### 6.6 期刊/会议名缩写

| 原词 | 缩写 |
|------|------|
| Parallel | Parall. |
| Distributed | Distrib. |
| Processing | Process. |

---

## 七、文本通用规范

### 7.1 标点符号
- 三个及以上并列：`a, b, and c`（and 前加逗号）
- 单位与括号间空一格：`10 m (10 meters)`
- `°`、`%` 与数字间无空格
- 连字符 `-`、短一字线 `--`、破折号 `---` 用法区分

### 7.2 章节标题
| 标题 | 格式 |
|------|------|
| 结论 | `Conclusions`（复数，首字母大写其余小写） |
| 基金致谢 | `Acknowledgments`，内容 `This work was supported by ...` |
| 利益冲突 | `Conflict of interest` |
| 数据可用性 | `Data availability` |
| 作者贡献 | `Contributors` |
| AI 声明 | `Declaration on the use of generative AI tool` |
| 算法 Caption | 同样适用首词大写规则 |

### 7.3 正文禁列表
- 正文中**禁止使用列表环境**（`enumerate`、`itemize`、`description`）。贡献/创新点等须改为 `1.~... 2.~...` 编号段落
- 子条目缩进用 `\hspace{2em}`
- 列表项开头的**粗体关键词去除**，改为句首大写的段落首句
- **禁止正文中 `\mbox{}` 防止换行**

### 7.4 必须包含的章节
1. `Acknowledgments` — 基金致谢
2. `Conflict of interest` — 利益冲突声明
3. `Data availability` — 数据可用性声明
4. `Contributors` — 作者贡献说明
5. `Declaration on the use of generative AI tool` — AI 工具声明

---

## 八、布局与间距

### 8.1 浮动体控制
- `\vspace` 在 `\begin{table}`/`\begin{figure}` 之前无效
- 表格上方间距用局部 `\setlength{\textfloatsep}{}`
- 浮动体禁用 `[H]`，改为 `[ht!]` 或 `[t]`

### 8.2 需删除的多余代码
- 重复的 `\makeatletter`、`\small`、`\usepackage`
- `breaklinks=true` + dvips 驱动不兼容
- ⚠️ **`\usepackage{lmodern}` 会覆盖 Arial**：必须删掉
- ⚠️ **`\usepackage[T1]{fontenc}` 重复加载**：fitee.sty 已自带，.tex 中无需再写
- ⚠️ 矢量字替代方案：若需 Type 1 矢量正文字体但不破坏 Arial，用 `\usepackage{ae,aecompl}` 替代 `lmodern`

### 8.3 字体故障排查
- `uarial` 包安装后字体仍非 Arial → 终端执行 `initexmf --mkmaps` + `initexmf --update-fndb` 重建字体映射
- `[scaled]` 选项在某些 MiKTeX 版本下可能导致 uarial 加载失败 → 去掉该选项
- uarial 彻底无法工作时，回退方案：`\usepackage{helvet}` + `\renewcommand{\sfdefault}{phv}`（Helvetica，FITEE 接受）
