# Slide Storyline Review — historical thesis_new_template.pptx（26 頁）

> 本 review 針對先前的 26 頁 deck；目前的 `thesis proposal 7_17.pptx` 有 29 頁，因此以下 slide numbers 不一定對應目前版本。

審查目標：約 15 分鐘的英文 proposal 簡報。目標：故事線清楚，重意義、略細節。

## 一句話說完整個故事

> 靜態 RTS threshold 迫使我們做一個糟糕的取捨；AP 透過多天線 CSI（AoA）本來就「看得到」client 的方位，因此應該只在 hidden-node 風險值得時才付出 RTS/CTS 的 overhead。

每一頁 slide 都應該在鋪陳或兌現這句話。

## 目前做得好的地方

- Intro 的鋪陳（slide 4→7）方向正確：問題 → 既有解法 → 解法的旋鈕為何失靈 → 你的想法。
- Appendix 的策略正確：beamforming vs MUSIC 的深入內容（23–24）已移出主線。
- Next Steps（18）符合 proposal 簡報的需要。

## 主要問題

### 1. 故事比重失衡：background 4 頁、貢獻只有 1 頁
Slide 9–12（CSI、AoA、steering vector、MUSIC）的份量壓過 slide 14，但 slide 14 才承載整篇論文的貢獻。聽眾離場時對 MUSIC（1979 年、不是你的）的了解，反而多過你的 risk score（你的）。既然要「略細節、重意義」：

- Background 壓縮成 3 頁：(a)「AP 的天線本來就帶有方向資訊」（CSI + AoA 直覺，合併 9+10）；(b) steering vector 獨立一頁——它是從 CSI 相位差走到 AoA 估計的橋樑，不能在 MUSIC 頁突然出現；(c)「MUSIC 能從 commodity AP 的 CSI 萃取 AoA」（一張 spectrum 圖）。
- 貢獻擴充成 3 頁：
  1. **Pipeline 總覽** — CSI → AoA → pair-level risk → BSS-level risk → threshold 更新（一張圖；這是「一張圖看懂論文」的 slide）。
  2. **Hidden-node risk score** — AoA 方位差作為幾何線索，融合 retry/RSSI/MCS/流量作為碰撞徵兆；pair-level → 聚合。
  3. **Threshold 調整規則** — 風險高降 threshold、風險低恢復；用 smoothing/hysteresis 防止在 AoA 雜訊下震盪。

總頁數不變；重心從教科書移回論文本身。

### 2. Slide 6 埋沒了核心張力
「A static threshold cannot adapt to changing node locations」沒錯但太弱。真正的故事是：**threshold 太低 → 即使沒有 hidden node，每個 frame 都付 RTS/CTS 稅；太高 → hidden-node 碰撞永遠沒被解決。** 把兩難的兩端都明講，slide 7 才會成為「逃出兩難」的答案。建議標題："No Static RTS Threshold Fits All Scenarios"（標題限 45 字符內）。

### 3. 缺少 gap slide
Deck 中沒有 related work / gap 的 slide。建議在 slide 6 之後加一頁（或併入 6）：既有 adaptive-RTS 研究只靠 retry/collision 盲調；AoA 研究都做 localization、不做 MAC 控制；沒有人把 AP-side spatial sensing 接到 RTS 控制。沒有這頁，committee 看不出想法新在哪裡。

### 4. 機械性問題
- Slide 2 和 3 是重複的 outline 頁——留一頁（或把 3 改成 section marker，highlight「Introduction」）。
- Slide 1 只列了指導教授，要加上學生姓名。
- 標題風格不一致：assertion 式（"Classic Beamforming Hits a Resolution Wall"）與 topic 式（"Angle of Arrival (AoA)"）混用。建議全部改 assertion 式——逼每一頁都表達一個論點。
- Slide 16：建議補上 fairness 指標，並加一行預期結果（"dynamic ≈ RTS-off when safe, ≈ RTS-on when hidden"），讓 evaluation 讀起來是假說檢驗，而不只是一張矩陣。

## 建議的主線順序（約 15 頁內容，符合 15 分鐘）

1. Title
2. Outline
3. Hidden-node problem（=4）
4. RTS/CTS fix（=5）
5. Static threshold dilemma（改寫 6）
6. Gap: no one uses AP-side spatial sensing for RTS control（新增）
7. Idea: AoA-assisted dynamic threshold（改寫 7）
8. Background A: CSI/AoA intuition（合併 9+10）
9. Background B: Steering vector（沿用 11，改 assertion 標題）
10. Background C: MUSIC on commodity APs（改寫 12）
11. Pipeline overview（新增——一張圖看懂論文）
12. Risk score design（自 14 擴充）
13. Threshold adaptation rule（自 14 擴充）
14. Evaluation plan（改寫 16）
15. Next steps（=18）

未修改任何 PPTX——以上所有變更皆待你核可後執行。
