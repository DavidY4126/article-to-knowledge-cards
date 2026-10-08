# 测试记录

## 测试 A：中文中等长度文章（sample_a_fanqie.md，番茄工作法）

### 实际输出

已根据《番茄工作法》生成 6 张知识卡片。

### 卡片 1：一个番茄钟的标准结构
- **核心知识**：一个番茄钟 = 25 分钟专注一件事 + 5 分钟休息；每完成 4 个，安排 15~30 分钟长休息。
- **简明解释**：先选定任务、启动 25 分钟倒计时，期间不回消息、不切任务；铃响后休息 5 分钟，并在纸上画一个叉记一个番茄钟。
- **例子 / 自测**：自测——连续做完 4 个 25 分钟后，应该进入什么？

### 卡片 2：被打断时用"外清单"接住念头
- **核心知识**：番茄钟中途冒出的临时念头，先写在旁边的外清单上，结束再处理，不立刻切任务。
- **简明解释**：刚工作 10 分钟想查东西、回消息是最常见的失败；立刻切换会打断专注，把念头先记下来既不丢失，又能保住当前这一段。
- **例子 / 自测**：自测——工作中突然想起要回一条消息，正确做法是？

### 卡片 3：休息不能被"顺便"继续工作
- **核心知识**：铃响后继续工作看似更拼，实则会拉低后面的专注质量。
- **简明解释**：这套方法的前提是"短冲刺 + 恢复"，而不是连续透支；把 5 分钟休息消耗掉，等于拆掉了它的恢复机制。
- **例子 / 自测**：例子——铃声响了却不停下来继续干，为什么反而不好？

### 卡片 4：它真正降低的是"开始"的门槛
- **核心知识**：番茄钟让人只需承诺专注 25 分钟，而不是承诺完成整个项目，从而降低启动难事的心理阻力。
- **简明解释**：很多人以为方法只是"定时 25 分钟"，但降低开始一件难事的门槛才是关键作用之一。
- **例子 / 自测**：自测——面对一个不想开始的大任务，番茄钟把承诺从"做完"换成了什么？

### 卡片 5：纸上的叉数是客观的时间反馈
- **核心知识**：一天结束时数纸上的叉，就是今天真正投入的专注段数，可用于复盘时间去向。
- **简明解释**：它把模糊的"忙了一天"变成可计数的专注段数，让复盘有客观依据。
- **例子 / 自测**：自测——一天结束时用什么来量化自己的专注投入？

### 卡片 6：25 分钟不是铁律
- **核心知识**：深度创作可能在 25 分钟刚进入状态时被打断；碎活用 15 分钟更合适，关键是守住"一段只做一件事 + 结束真休息"的结构。
- **简明解释**：时长可以按任务类型调整，但"一段一事"和"真休息"这两个结构不能丢。
- **例子 / 自测**：自测——写文章刚进入心流就被铃打断，应该死守 25 分钟吗？

### 对照检查
- 数量：6 张，在 5~8 区间。✔
- 四字段齐全、一卡一点。✔
- 去重：卡片 1 讲标准流程，卡片 6 讲时长可调整，是"标准 vs 弹性"的对照而非重复；无两张核心知识雷同。✔
- 不编造：25/5/15-30/4 个番茄钟、外清单、叉数、西里洛起源等均来自原文；未补充外部案例。✔
- 语言：中文文章出中文卡片。✔

---

## 测试 B：信息稀疏短文（sample_b_thin.txt）

### 实际输出

原文信息量有限，仅提炼出 2 个独立知识点。

### 卡片 1：不要等口渴才喝水
- **核心知识**：口渴时身体已经轻微缺水了，所以不要把口渴当作喝水的信号。
- **简明解释**：口渴是已经轻度脱水后的信号，而不是"该喝水了"的起点，因此要主动喝，而不是等渴。
- **例子 / 自测**：自测——为什么"等渴了再喝"是偏晚的信号？

### 卡片 2：少量多次优于一次猛灌
- **核心知识**：补水应少量多次，而不是一次猛灌。
- **简明解释**：原文只给出这一做法对比，不展开原理。
- **例子 / 自测**：自测——补水方式上，"少量多次"对应的反面做法是什么？

### 对照检查
- 数量：仅 2 张，没有为凑满 5 张而编造卡片；开头已注明信息有限。✔（命中"不凑数"红线）
- 不编造：卡片 2 的解释里明确不补充原文没有的原理。✔

---

## 测试 C：英文文章（sample_c_http_cache.md）

### 实际输出

Generated 5 knowledge cards from 《How Browser Caching Works》.

### Card 1: What browser caching is for
- **Core knowledge**: The browser stores a local copy of a resource (image, CSS, JS) and reuses it on later visits instead of re-downloading it.
- **Explanation**: Re-downloading every resource on every visit is slow and wasteful; caching turns a repeat visit into a local lookup.
- **Example / Quiz**: Quiz — Why does caching mainly help on *repeat* visits rather than the first visit?

### Card 2: Cache-Control sets how long a resource stays fresh
- **Core knowledge**: The `Cache-Control: max-age=...` header tells the browser how long it may use the local copy; within that window it contacts no server.
- **Explanation**: `max-age=31536000` means one year of freshness, during which the browser serves from disk without any request.
- **Example / Quiz**: Example — `max-age=31536000` corresponds to roughly how long a freshness window?

### Card 3: After expiry, the browser revalidates
- **Core knowledge**: Once max-age passes, the browser re-validates by sending a conditional request carrying the earlier `ETag` or `If-Modified-Since` value.
- **Explanation**: Instead of blindly re-downloading, it asks the server whether the resource has changed.
- **Example / Quiz**: Quiz — Which two values can the browser send to ask "has this changed"?

### Card 4: 304 vs 200 determines whether a body is sent
- **Core knowledge**: If unchanged, the server returns `304 Not Modified` with no body (small, fast); if changed, it returns `200 OK` with the new file.
- **Explanation**: Revalidation trades a full download for a tiny status check when nothing changed.
- **Example / Quiz**: Quiz — You see a `304` response: did the server send the file body?

### Card 5: Do not cache HTML aggressively
- **Core knowledge**: A common mistake is long-caching the HTML itself, which leaves users on an old page after a release.
- **Explanation**: The recommended pattern is long-caching content files with a content-based fingerprint in the filename, while keeping the HTML un-cached or short-lived.
- **Example / Quiz**: Quiz — Static assets get long cache + fingerprinted filenames; what should happen to the HTML?

### 对照检查
- 数量：5 张。英文中等文章天然只有 4~5 个原子点，第 3、4 张把"条件请求机制"与"状态码结果"拆开，是可复习的知识点，未硬凑到 8 张。✔
- 语言：英文文章出英文卡片。✔
- 不编造：max-age=31536000、ETag/If-Modified-Since、304/200、fingerprint 文件名等均来自原文。✔
- 一卡一点、无重复。✔
