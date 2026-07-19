# Slide Draft — 修改後的主線內容（15 頁）

依 `slide storyline review.md` 的建議順序，逐頁列出修改後的完整 slide 文字（英文，可直接貼入 PPT）。標記說明：〔沿用〕原頁不動、〔改寫〕原頁改內容、〔新增〕全新頁、〔合併〕多頁併一頁。

格式規則：標題 ≤45 字符；每個 bullet / sub-bullet ≤55 字符；句中不用逗號（並列項用 " / " 分隔或拆 sub-bullet）；不用代名詞（it / this / they 等，直接寫出名詞）。

---

## 1. Title〔改寫：加學生姓名〕

**AoA-Assisted Dynamic RTS Threshold Adaptation for Hidden-Node Risk Mitigation in Wi-Fi**

- Student: Frank ___（補上全名與學號）
- Advisor: Professor Chien-Chao Tseng
- Department of Computer Science
- National Yang Ming Chiao Tung University

## 2. Outline〔沿用，刪除重複的 slide 3〕

- Introduction
- Background
- AoA-Assisted Dynamic RTS Threshold Adaptation
- Evaluation
- Next Steps

## 3. Hidden Nodes Problem〔沿用原 slide 4，句子縮短〕

- Devices can reach the AP but cannot hear each other
- Simultaneous transmissions collide at the AP
- Causes packet loss and lower throughput

## 4. RTS/CTS Mitigates Hidden-Node Collisions〔沿用原 slide 5〕

- Optional 802.11 handshake before data transmission
- RTS/CTS makes nearby nodes defer
  - Reduces hidden-node collisions
- Steps:
  - Sender sends RTS
  - Nearby node hears RTS and defers
  - AP replies with CTS
  - Hidden node hears CTS and defers
  - Sender transmits data

## 5. No Static RTS Threshold Fits All Scenarios〔改寫原 slide 6〕

- RTS/CTS is used only for frames above the threshold
- Commodity APs use one fixed value
- The suitable value changes as nodes move
  - A fixed value falls below or above the suitable value
    - Below → RTS/CTS overhead even without hidden nodes
    - Above → hidden-node collisions stay unresolved

## 6. Gap: Location Info Unused for RTS Control〔新增——同時充當一頁式 related work〕

- Adaptive RTS/CTS control already exists
  - Some works switch RTS/CTS on or off per frame
    - RRAA (MobiCom 2006) / CARA (INFOCOM 2006)
  - Other works tune the RTS threshold value
    - Kong (ICC 2004) / Yin (SmartWorld 2019)
- Prior work relies on link information only
  - Loss statistics or traffic models
- Hidden nodes are fundamentally a location problem
- Gap: no design uses location information

## 7. Idea: AoA-Driven Dynamic RTS Threshold〔改寫原 slide 7〕

- AoA = the direction a signal arrives from
- AoA reveals stations' relative directions
- AP combines AoA with link information
  - Estimates hidden-node risk
- Estimated risk guides dynamic RTS threshold adjustment
- Pay RTS/CTS overhead only when risk justifies it

## 8. CSI Records How the Signal Propagated〔改寫原 slide 9〕

- The sender transmits a pattern known to the receiver
- The receiver estimates CSI from the received pattern
  - CSI is estimated per subcarrier and antenna pair
- The signal propagates through physical space
  - CSI therefore carries geometric information

## 9. Steering Vector: A Direction's Fingerprint〔合併原 slide 10+11〕

- Antennas hear the signal at slightly different times
  - The nearer antenna first
- Each direction has a predictable arrival pattern
- The predicted pattern is the steering vector
  - The direction's fingerprint
- Compare measured CSI with every fingerprint
  - The best match is the AoA
- （合併原 slide 10 的 AoA 幾何圖與 slide 11 的圖；小字註記 "the arrival pattern is measured as signal phase — see appendix"，spatial-spectrum 細節留在 appendix 22）

## 10. MUSIC Estimates AoA from CSI〔改寫原 slide 12〕

- MUSIC is an algorithm that estimates AoA from CSI
  - Widely used in Wi-Fi localization
- MUSIC matches every angle's steering vector to the CSI
  - The matching produces a spatial spectrum
  - Peaks indicate likely AoAs
- （放 MUSIC spectrum 圖：角度 vs. 分數，尖峰即 AoA；multipath 多峰、演算法細節與 beamforming/ESPRIT 比較留在 appendix 22–24）

## 11. Pipeline: From CSI to RTS Threshold〔新增——一張圖看懂論文〕

- （整頁一張 pipeline 圖）Collect CSI → Estimate AoA with MUSIC → Score pair-level hidden-node risk → Aggregate risk to BSS level → Update RTS threshold → Sync the threshold to all STAs
- 底部一句話："Turn what the AP hears into when to pay for RTS/CTS"

## 12. Hidden-Node Risk Score〔自原 slide 14 擴充〕

- Geometric cue
  - Large AoA separation between two active STAs
  - → likely hidden from each other
- Symptom cues
  - Retry rate / RSSI / MCS / traffic activity
  - Confirm suspected collisions
- Pair-level risk computed for each active STA pair
- Pair risks aggregate into a BSS-level score
  - The decision variable

## 13. Risk-Driven RTS Threshold Adaptation〔自原 slide 14 擴充〕

- High risk → lower the RTS threshold
  - Protect more frames
- Low risk → raise/restore the threshold
  - Avoid unnecessary overhead
- Smoothing + hysteresis prevent oscillation
  - AoA and retry measurements are noisy

## 14. Evaluation Plan〔改寫原 slide 16〕

- Scenarios
  - Hidden-node / non-hidden-node
- Policies
  - Static RTS threshold
  - Dynamic (proposed)
  - RTS/CTS disabled
- Metrics
  - Throughput / retry rate / latency
  - MCS distribution / fairness
- Hypothesis
  - Dynamic ≈ RTS-off when safe
  - Dynamic ≈ RTS-on when hidden
  - Best of both

## 15. Next Steps〔沿用原 slide 18〕

- Adopt SpotFi's MUSIC variant for AoA estimation
  - SpotFi: SIGCOMM CCR 2015
  - Speed up eigen decomposition
- Define risk scoring and score-to-threshold mapping
  - Reinforcement learning?
- Define evaluation scenarios / baselines / metrics

---

## Appendix 調整

- 原 slide 10+11（AoA 幾何 / Steering Vector）合併留在主線（見上方第 9 頁），不移入 appendix
- Appendix（19–26）不動
- 原 slide 3（重複 outline）刪除；section marker 頁（8、13、15、17）保留

尚未修改任何 PPTX，以上為草稿，待核可後由你貼入。
