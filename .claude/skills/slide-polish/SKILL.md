---
name: slide-polish
description: Polish presentation slide content (titles, bullets, storyline, logic) to follow a strict meaning-first slide style. Use whenever the user asks to polish, review, rewrite, or draft slides, slide text, a slide outline, or PPTX content — including requests in Chinese like 修飾簡報、檢查投影片、slide 內容、標題太長、故事線、邏輯不順. Also use when writing NEW slide drafts so the rules are applied from the start, not just when fixing existing ones.
---

# Slide Polish

把投影片內容打磨成「重意義、略細節」的風格。這些規則來自實際的論文簡報迭代經驗，目的只有一個：**聽眾在每一頁只需要吸收一個意思，而且不需要任何沒教過的知識。**

## 核心精神

簡報的主線只回答「這個研究在做什麼、為什麼重要」。聽眾記得住的是故事，不是細節。任何「怎麼做到的」細節（演算法內部、calibration、corner case 處理）都移到 appendix，主線只留大綱層級的意義。

## 規則

### 1. 故事線與內容（先檢查，最重要）

- 整份簡報要能濃縮成一句話；每一頁都在鋪陳或兌現這句話。
- 一頁只講一個論點。不要因為「講得更完整」而加內容——加內容是扣分不是加分。
- 實作細節不進主線。判斷標準：這件事是「研究在做什麼」還是「做得多好／怎麼處理邊角」？後者進 appendix。
- **概念依賴檢查**：逐頁走一遍，每個名詞第一次出現前必須已被介紹。若某頁突然冒出新名詞，修法有三：
  - 在前面補一頁（或一個 bullet）介紹
  - 改寫成不依賴該名詞的直覺說法（例如用「到達時間差」「指紋」取代 phase）
  - 嚴謹版本用小字註記導向 appendix
- 概念已經講過就不要重複教——重複的頁面應合併。
- **頁內邏輯是一條線**：每頁的 bullet 依序讀應該是一個推理鏈（現況 → 限制 → 轉折 → 結論），不是碎片的並列。
- **跨頁一致性**：檢查相鄰頁面有無矛盾（例如前頁說「都用固定值」、後頁說「已有動態研究」——修法是把前頁限定在部署現況、後頁講研究進展，變成遞進）。
- 有比較就要講明基準：「太低／太高」必須說清楚是相對什麼（例如相對 suitable value）。
- 因果關係要外顯：後果句降為 sub-bullet 並用 thus / → 等標記，不讓聽眾自己猜。
- 結構相似的並列項（如 too low / too high）收攏在同一個父 bullet 下。
- 涉及 prior work 的宣稱必須有具體文獻在 slide 上（作者／venue／年份），且歸類要準確——查證每篇論文實際做了什麼再分類，不確定就先讀 abstract。gap 宣稱不能憑空出現。

### 2. 標題

- 標題 ≤ 45 字符（含空格）。
- 用 assertion 式標題：標題本身是一個論點，不是主題標籤。
- 標題必須自明，不用意義模糊的比喻（"A Lose-Lose Choice" ✗——lose 什麼沒講）。45 字符裝不下細節時，讓標題講結論本身，細節留給 bullet。
- 標題要含該頁的核心概念詞：講 CSI 的頁面，標題就該出現 CSI。

### 3. Bullet

- 每個 bullet / sub-bullet ≤ 55 字符。
- 句中不用逗號。遇到需要逗號的句子，依序考慮：改寫結構讓句子變短、並列項用 " / " 分隔、拆成 sub-bullet。
- 句子有停頓（原本會放逗號、分號、破折號處）就拆成主 bullet + sub-bullet：主 bullet 講主張，sub-bullet 講補充。
- 一個 sub-bullet 只裝一個意思。
- sub-bullet 必須真有從屬關係（解釋、後果、佐證）。兩句獨立的話就並列成兩個 bullet，不要硬掛。
- 不用代名詞（it / this / they 單獨作主詞）——直接寫出名詞，寧可重複。
- 分類標籤不可模糊："On/off:" 這種縮寫標籤 ✗，用完整句子講清楚該類做了什麼，引用降一層放。

### 4. 用字

- 用常見的字。口語化行話（knob、ship with、silver bullet）換成一般詞彙（parameter、use）。
- 描述要精準，不冤枉機制：分清「機制不能變」和「慣例上沒人變」（RTS threshold 可以改，是 convention 把它設一次就不動）。
- 修飾語位置不能產生歧義："set once and left unchanged by convention"（by convention 修飾整件事）優於 "set once by convention and left unchanged"。

### 5. 圖

- 流程圖每格用動詞開頭（Collect CSI → Estimate AoA → Update threshold），讀起來是一條動作鏈。

## 工作流程

修飾一份 slide 內容時，依序做六個 pass，並回報每個違規處與修法：

1. **故事線 pass** — 寫出一句話版本，檢查每頁是否服務它；標出該移去 appendix 的內容；檢查跨頁矛盾。
2. **概念依賴 pass** — 逐頁列出首次出現的名詞，確認出現前已介紹；已教過的概念找出重複頁。
3. **邏輯 pass** — 每頁 bullet 依序讀是否成推理鏈；比較有無基準；因果是否外顯；文獻宣稱是否有支撐。
4. **標題 pass** — 逐頁數字符、檢查 assertion 式、自明、含核心概念詞。
5. **Bullet pass** — 逐條數字符、查逗號、查代名詞、查一句多意、查假從屬關係、查模糊標籤。
6. **用字 pass** — 查行話、不精準描述、歧義的修飾語位置。

輸出時逐頁列出修改後的內容，並標注每頁是〔沿用〕〔改寫〕〔新增〕〔合併〕。

## 範例

**Bullet 拆解（違規：太長、有逗號、一句多意）**

> - 802.11 sends RTS/CTS only for frames larger than the RTS threshold — by convention, set once and left unchanged

修改後：

> - RTS/CTS is used only for frames above the threshold
> - By convention the threshold never changes

**標題（違規：比喻不明）**

> Static RTS Threshold: A Lose-Lose Choice

修改後（講結論本身）：

> No Static RTS Threshold Fits All Scenarios

**因果外顯 + 基準明確（違規：兩句並列看不出因果、too low 沒說相對什麼）**

> - The suitable value changes as nodes move
> - A fixed value becomes too low or too high

修改後：

> - The suitable value changes as nodes move
>   - A fixed value falls below or above the suitable value
>     - Below → RTS/CTS overhead even without hidden nodes
>     - Above → hidden-node collisions stay unresolved
