# FITEE 格式审查报告

**文件**：`FITEE-2025-0154.tex`（共 1004 行）  
**审查日期**：2026-06-04  
**审查依据**：《FITEE期刊LaTeX初排技巧与实例》、《FITEE期刊作者定稿格式规范大纲》、SKILL_FITEE.md

---

## 一、首页信息排版（共 9 处）

| #   | 问题                    | 位置（行号）  | 当前内容                                                                                                                           | 建议修改                                                                                                                           | 依据                          |
| --- | --------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | --------------------------- |
| 1   | **标题大小写**             | L36     | `Microservice Framework for Data-model Fusion in Situational Awareness Simulations`                                            | `Microservice framework for data-model fusion in situational awareness simulations`                                            | 规则1.1：仅第一个单词首字母大写，其余非专有名词小写 |
| 2   | **作者姓氏未全大写**          | L39–L45 | `Runnan Qin`, `Zhen Yang`, `Xiaodong Peng`, `Wenming Xie`, `Xiao Zheng`, `Jingyi Ren`, `Zeyu Fan`                              | `Runnan QIN`, `Zhen YANG`, `Xiaodong PENG`, `Wenming XIE`, `Xiao ZHENG`, `Jingyi REN`, `Zeyu FAN`                              | 规则1.2：姓全部大写                 |
| 3   | **单位名称拼写错误**          | L47     | `University of Chinese Academy and Science`                                                                                    | `University of Chinese Academy of Sciences`                                                                                    | 专有名词（国科大英文名）缺少末尾 "s"        |
| 4   | **关键词全部大写**           | L59     | `\keywords{Data-Model Fusion; High-Performance Simulation Computing; Scheduling Strategy; Node Load Prediction; Microservice}` | `\keywords{Data-model fusion; High-performance simulation computing; Scheduling strategy; Node load prediction; Microservice}` | 规则1.6：仅首单词首字母大写，其余非专有名词小写   |
| 5   | **DOI 为占位符**          | L61     | `10.1631/ENG.ITEE.2025.XXXX`                                                                                                   | 需替换为真实 DOI                                                                                                                     | 规则1.5                       |
| 6   | **缺少 `\shortauthor`** | —       | 未定义                                                                                                                            | `\shortauthor{Qin et al.}`（7 位作者用 et al.）                                                                                      | 规则1.8：页眉必须设置                |
| 7   | **缺少基金信息脚注**          | —       | 未出现                                                                                                                            | 添加 `\thanks{*}` 或确认无基金                                                                                                         | 规则2.3                       |
| 8   | **缺少 ESM 补充材料**       | —       | 未出现                                                                                                                            | 如有补充材料需添加 `#` 标记和脚注                                                                                                            | 规则2.5                       |
| 9   | **缺少版权声明**            | —       | 未出现                                                                                                                            | 添加 `\copyrightinfo{...}`                                                                                                       | 规则2.6                       |

---

## 二、章节标题大小写（共 9 处）

| # | 问题 | 位置 | 当前内容 | 建议修改 | 依据 |
|---|------|-----|---------|---------|------|
| 10 | 节标题大写不一致 | L119 | `\section{Related works}` | `\section{Related work}` | 正文 L117 用 "related work"（单数），且期刊标题仅首字母大写 |
| 11 | 子节标题多余大写 | L121 | `Secure and coherent transmission of large-scale data` | `Secure and coherent transmission of large-scale data` | 行文上已基本小写 ✓（待编译确认） |
| 12 | 子节标题多余大写 | L142 | `Computational Analysis of Data-Model Fusion` | `Computational analysis of data-model fusion` | 规则1.1类推：非句首普通名词小写 |
| 13 | 子节标题多余大写 | L166 | `Overall Architecture Design` | `Overall architecture design` | 同上 |
| 14 | 子节标题多余大写 | L172 | `Node Management Control Design` | `Node management control design` | 同上 |
| 15 | 子节标题多余大写 | L191 | `Model Calculation Scheduling Design` | `Model calculation scheduling design` | 同上 |
| 16 | 子节标题多余大写 | L208 | `Data Security Transmission Design` | `Data security transmission design` | 同上 |
| 17 | 子节标题多余大写 | L229 | `Leader--Follower Election Algorithm` | `Leader--follower election algorithm` | 同上 |
| 18 | 子节标题多余大写 | L284 | `Node Dynamic Elastic Expansion Algorithm` | `Node dynamic elastic expansion algorithm` | 同上 |
| 19 | 子节标题多余大写 | L357 | `Load Migration Scheduling Algorithm` | `Load migration scheduling algorithm` | 同上 |
| 20 | 子节标题多余大写 | L445 | `Experimental Setup` | `Experimental setup` | 同上 |
| 21 | 子节标题多余大写 | L508 | `Dynamic Election Analysis` | `Dynamic election analysis` | 同上 |
| 22 | 子节标题多余大写 | L689 | `Migration Scheduling Effectiveness` | `Migration scheduling effectiveness` | 同上 |
| 23 | 结论标题 | L779 | `\section{Conclusion}` | `\section{Conclusions}` | 规则6.2：结论标题必须为 `Conclusions` 复数 |

---

## 三、缺失章节（共 5 处）

| # | 问题 | 依据 |
|---|------|------|
| 24 | 缺少 **Acknowledgments** 基金致谢 | 规则6.2 |
| 25 | 缺少 **Conflict of interest** 利益冲突声明 | 规则6.2 |
| 26 | 缺少 **Data availability** 数据可用性声明 | 规则6.2 |
| 27 | 缺少 **Contributors** 作者贡献说明 | 规则6.2 |
| 28 | 缺少 **Declaration on the use of generative AI tool** AI 工具声明 | 规则6.2 |

---

## 四、图表排版（共 12 处）

| # | 问题 | 位置 | 当前内容 | 建议修改 | 依据 |
|---|------|-----|---------|---------|------|
| 29 | **`\vspace`在浮动体前无效** | L177, L185, L198, L206, L217, L225, L243, L280, L291, L299, L331, L355, L410, L438, L515, L522, L528, L586, L609, L613, L622, L738, L773 | 多处出现 `\vspace{-...\baselineskip}` 在 `\begin{figure}` 或 `\begin{table}` 之前 | 删除这些 `\vspace`，改用局部 `\setlength{\textfloatsep}{}` 或在浮动体内部用 `\vspace` | 规则7.1 |
| 30 | **Table 1 使用 `\cline{1-1}` 和 `\cline{3-9}`** | L541, L546, L551, L556 | `\cline{1-1} \cline{3-9}` | 改为 `\cmidrule(lr){1-1} \cmidrule(lr){3-9}` | 规则3.8：断开横线必须用 `\cmidrule`；`\cline` 与`tabular*`+`\extracolsep` 组合会导致线条不对齐 |
| 31 | **Table 2 使用 `\hline`** | L596–L602 | 4 处 `\hline` 代替 `\midrule` | 统一改为 `\midrule[0.5pt]` | 规则3.6：三线表仅用 `\toprule` / `\midrule` / `\bottomrule` |
| 32 | **Table 2 数据缺少 `\%`** | L603 | `$3.82\% \pm 0.16$` → 应为 `$3.82\% \pm 0.16\%$`；`$3.68\% \pm 0.11$` → `$3.68\% \pm 0.11\%$`；`$4.51\% \pm 0.23$` → `$4.51\% \pm 0.23\%$` | 补全单位符号 `\%` | 数据格式一致性 |
| 33 | **Fig. 6 子图标题独立显示** | L457–L491 | 子图 (a)–(f) 的文字说明出现在 minipage 中 `/\[4pt] (a) Spacecraft close-in simulation` | 图中只保留序号 `(a)` `(b)`，子图说明移到整体 caption 中 | 规则3.2：不设独立子图标题 |
| 34 | **Fig. 9 子图标签独立显示** | L646–L648 | `\small (a) Expansion speed` 和 `\small (b) Expansion effectiveness` 在 `\caption` 外 | 移除这些独立标签，在 caption 中整合说明 | 规则3.2：子图说明移到整体图题中 |
| 35 | **Fig. 10 子图标题独立显示** | L700–L728 | 子图 (a)–(f) 的文字说明出现在 minipage 中（如 `(a) Spacecraft close-in simulation`） | 图中只保留序号，说明移到 caption（当前 caption L730 已有说明，去除minipage中的文字） | 规则3.2 |
| 36 | **Table 3 使用 `\cline{2-11}`** | L662, L664 | `\cline{2-11}` | 改为 `\cmidrule(lr){2-11}` | 规则3.8 |
| 37 | **Table 3 跨栏表格尺寸** | L657 | `\begin{tabular*}{\textwidth}` | 确认 `\textwidth` 在 `table*` 中是否等于 18cm，不足则改为指定宽度 | 规则3.6：通栏表格宽度 18 cm |
| 38 | **Fig. 6/10 子图数量标注** | L451, L695 | `\begin{figure*}` 子图序号为垂直方向排列（先上后下），而规则要求水平方向排序 | 当前排列为 3×2（水平方向 ✓），但 citation 中用 model (a) to (f) 递增 | 规则3.2：子图序号为水平方向 ✓ |

---

## 五、公式排版（共 5 处）

| # | 问题 | 位置 | 当前内容 | 建议修改 | 依据 |
|---|------|-----|---------|---------|------|
| 39 | **上下标 `h_{\text{t-1}}`** | L301 | `h_{\text{t-1}}` | `h_{t-1}` | 规则4.2：单字母变量下标用斜体，勿用 `\text{}` |
| 40 | **上下标 `f_{\text{t}}`** | L302 | `f_{\text{t}}` | `f_{t}`（与 L304 `f_t` 一致） | 同上 |
| 41 | **正文变量 `L_j^{pre}` 未用正体** | L326, L328 | 正文中 `$L_j^{pre}(t+1)$` 和 `$L_j^{pre}(t+T) < a$` | `$L_j^{\mathrm{pre}}(t+1)$` | 规则4.2：单词缩写下标用正体 `\mathrm{}` |
| 42 | **公式(1)中单位未用正体** | L238 正文 | "Gbps", "vCPUs", "GB" 在正文中可保留 | 若在公式中出现单位，应为正体 `\mathrm{Gbps}` | 规则4.1 |
| 43 | **公式(5)中 `\left` 与 `\right` 不配对** | L365 | `\left<Q_i, T_j\right>` — 使用 `\left<` / `\right>` 可行但语义上不是必须 | 可保持或改为 `\langle Q_i, T_j \rangle` | — |

---

## 六、参考文献（共 6 类问题，涉及 36 条文献）

### 6.1 排序完全混乱（核心问题）

当前 36 条参考文献未按任何规则排序（Ding→Wei→Pathak→Ma→Yin→Ding...）。按 SKILL.md 规则5.1–5.3，应重排为以下顺序：

**规则**：按第一作者姓氏首字母 A→Z；同姓时按作者数少→多或年份先后；同年加 a/b 区分。

建议正确排序（A→Z）：
```
Ahmad et al. (2025)
Cui et al. (2021)
Dayal et al. (2014)
Ding TC et al. (2020)     — Ding同姓，按年份：2020 < 2025
Ding WH et al. (2025)
Dragoni et al. (2017)
Feng et al. (2020)
Guo et al. (2019)
Lamport (1998)
Larsson (2021)
Lei et al. (2024)
Li et al. (2024)
Liang et al. (2017)
Liu F and Weissman (2015) — Liu同姓，2位作者 < 3位+
Liu WG et al. (2023)
Luo et al. (2022)
Ma HC et al. (2023)       — Ma同姓，年份 2023 < 2017？不对，按作者数 HC(3人) < Y(4人)
Ma Y et al. (2017)        — 或者按年份？
Mesbahi et al. (2019)
Nguyen et al. (2020)
Pathak and Kalaiarasan (2021)
Pivotal et al. (2018)
Rossi et al. (2020)
Shona and Sharma (2023)   — Shona < Shrimal
Shrimal et al. (2024)
Tsenos and Kalogeraki (2021)
Ullah et al. (2013)
Wang et al. (2023)
Wei et al. (2025)
Xu XL et al. (2015)       — Xu同姓，2015 < 2023
Xu ZC et al. (2023)
Yang et al. (2004)
Yin et al. (2015)
Zhang CY et al. (2021)    — Zhang同姓，2021 < 2023
Zhang Y (2023)            — ⚠️ 同姓同2023年！需按论文题目首字母区分，加 a/b
Zheng et al. (2025)
```

**⚠️ Zhang CY (2021) vs Zhang Y (2023)**：不同年份，无需加 a/b，按年份排即可。

| # | 问题 | 位置 | 建议 |
|---|------|-----|------|
| 44 | **参考文献整体乱序** | L793–L1000 | 按上述 A→Z 顺序完全重新排列，并更新正文引用标签（`\cite` key 不变但顺序重排） |

### 6.2 标题大小写问题（≥8 条）

| # | 位置 | 当前 | 建议 | 依据 |
|---|------|-----|------|------|
| 45 | L801 | `...Apache Kafka: A comparative analysis...` | `...Apache Kafka: a comparative analysis...` | 规则5.4：冒号后首字母小写 |
| 46 | L819 | `Design and implementation...` | `Design and implementation...` ✓ | — |
| 47 | L825 | `Comat: An effective composite...` | `Comat: an effective composite...` | 规则5.4 |
| 48 | L866 | `Microservices: How to make...` | `Microservices: how to make...` | 规则5.4 |
| 49 | L870 | `Resource scheduling techniques...: a holistic survey.` | ✓ 已正确 | — |
| 50 | L875 | `Distributed intelligent reflecting surfaces-aided...` | ✓ 已正确 | — |
| 51 | L882 | `Dynamic rate control for topic-based pub/sub systems.` | ✓ 已正确 | — |
| 52 | L888 | `A collaboration mechanism between...` | ✓ 已正确 | — |
| 53 | L898 | `The part-time parliament.` | ✓ 已正确 | — |
| 54 | L904 | `Multi-primary-node Byzantine fault-tolerant...` | ✓ 需确认专有名词 `Byzantine` 保留大写 | — |
| 55 | L922 | `Apache Dubbo.` | ✓ 专有名词 | — |
| 56 | L944 | `A space-efficient fair cache scheme...` | ✓ 已正确 | — |
| 57 | L986 | `Horizontal pod Autoscaling...` | `Horizontal pod autoscaling...` | 普通名词小写 |
| 58 | L992 | `Towards resource-efficient reactive and proactive auto-scaling...` | ✓ 已正确 | — |
| 59 | L998 | `Self-adaptive threshold-based policy...` | ✓ 已正确 | — |

### 6.3 DOI 末尾句号（≥3 条）

| # | 位置 | 当前 | 建议 | 依据 |
|---|------|-----|------|------|
| 60 | L797 | `https://doi.org/10.11959/j.issn.2096-8930.2025008.` | 去掉末尾句号 | 规则5.5 |
| 61 | L815 | `https://doi.org/10.1109/ICICTA.2017.72.` | 去掉末尾句号 | 同上 |
| 62 | L821 | `https://doi.org/10.1109/ICIICII.2015.145.` | 去掉末尾句号 | 同上 |

*（需逐条检查全部 36 条文献的 DOI 末尾是否有句号）*

### 6.4 缺少 DOI（2 条）

| # | 位置 | 文献 | 建议 |
|---|------|-----|------|
| 63 | L890 | Ullah et al. (2013) | 补充 DOI 或确认无 DOI |
| 64 | L850 | Xu XL et al. (2015) | 补充 DOI（目前仅 Online URL） |

### 6.5 会议序数词（1 条）

| # | 位置 | 当前 | 建议 | 依据 |
|---|------|-----|------|------|
| 65 | L826 | `...Applications, Big Data \& Cloud Computing...` | LaTeX 中 `\&` 在 bibitem 普通文本中可保留 | 规则5.6（非核心问题） |

### 6.6 `\bibitem` 标签格式

| # | 检查项 | 结果 |
|---|-------|------|
| — | Ding WH / Ding TC 标签区分 | ✓ 已正确 |
| — | Zhang CY / Zhang Y 标签区分 | ✓ 已正确 |
| — | Xu XL / Xu ZC 标签区分 | ✓ 已正确 |
| — | Liu F / Liu WG 标签区分 | ✓ 已正确 |
| — | Ma Y / Ma HC 标签区分 | ✓ 已正确 |

---

## 七、正文文本（共 4 处）

| # | 问题 | 位置 | 当前内容 | 建议修改 | 依据 |
|---|------|-----|---------|---------|------|
| 66 | **文字片段异常** | L584 | `...recurring workload trends or abrupt By emphasizing these salient features...` | `abrupt` 后缺少内容，且 `By` 不应大写。疑似复制/编辑错误 | 行文错误 |
| 67 | **行内引用与节标题不一致** | L117 | "related work"（单数） vs L119 `\section{Related works}`（复数） | 统一为单数 `Related work` | 一致性 |
| 68 | **单位与数字间空格** | L451 等处 | 部分位置 `10 Chinese Zhongke...` | 确认 `10 Chinese...` 格式 | 规则6.1 |
| 69 | **\publishyear 等元数据** | L64–L69 | `\publishyear{2026}`, `\vol{27}`, `\issue{1}`, `\articlenumber{25XXXX}`, `\pagestart{1}`, `\pageend{4}` | `\articlenumber{25XXXX}` 含占位符 XXXX，需补充 | 元数据完整性 |

---

## 八、布局与间距（共 2 处）

| # | 问题 | 位置 | 建议 | 依据 |
|---|------|-----|------|------|
| 70 | **多处 vspace 在浮动体前无效** | （同上 #29） | 删除或移至浮动体内部 | 规则7.1 |
| 71 | **`breaklinks=true` 无 dvips 驱动** | L28 | `\usepackage[hidelinks, breaklinks=true]{hyperref}` — 未加载 dvips，实际可保留 | 规则7.2 |

---

## 总结

| 类别 | 问题数量 |
|------|---------|
| 一、首页信息排版 | 9 |
| 二、章节标题大小写 | 14 |
| 三、缺失章节 | 5 |
| 四、图表排版 | 12 |
| 五、公式排版 | 5 |
| 六、参考文献 | 22+ |
| 七、正文文本 | 4 |
| 八、布局与间距 | 2 |
| **合计** | **约 73 处问题** |

---

**🔴 核心必改项**（影响录用）：
1. 标题大小写（L36）
2. 作者姓氏全大写（L39–L45）
3. 参考文献完全重排序（L793–L1000）
4. 关键词大小写（L59）
5. 添加 `\shortauthor`、基金/ESM/版权脚注
6. Table 1/2/3 的 `\cline`/`\hline` 改为 `\cmidrule`/`\midrule`

**请告诉我哪些问题需要修改，我再进行修改操作。**
