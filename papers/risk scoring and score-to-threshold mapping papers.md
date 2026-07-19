# Risk scoring 與 score-to-threshold mapping 相關論文

搜尋結論(2026-07-17):**沒有找到同時「定義 hidden node risk score」又「把 score 映射到 RTS threshold」的論文**,此組合目前是空缺,有利於本論文 novelty。最接近的文獻分三類。

## 1. 動態 RTS threshold 調整(network state → threshold,無明確 risk score)

1. **Mjidi, Chakraborty, Nakamura et al., "The impact of dynamic RTS Threshold adjustment for IEEE 802.11 MAC protocol," Mobile Information Systems, 2009.**
Link: [IOS Press](https://content.iospress.com/articles/mobile-information-systems/mis00069)
依網路狀況動態調整 RTS threshold 以最大化 throughput。

2. **"RTS threshold adjustment algorithm for IEEE 802.11 DCF."**
Link: [ResearchGate](https://www.researchgate.net/publication/224761031_RTS_threshold_adjustment_algorithm_for_IEEE_80211_DCF)
以封包成功傳輸機率估計調整 threshold,是最接近「機率 → threshold」的作法。

3. **"Packet Distribution based Tuning of RTS Threshold in IEEE 802.11," ISCC 2010.**
Link: [PDF](http://ashikur.buet.ac.bd/myPapers/ISCC10.pdf)
依封包長度分布動態調整。

4. **"RTS threshold self-tuning algorithm based on delay analysis on 802.11 DCF."**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/1544122/)
以 delay 分析自調 threshold。

5. **Yin, Gao, Manzoor, and Hei, "Optimal RTS Threshold for IEEE 802.11 WLANs: Basic or RTS/CTS?," IEEE SmartWorld 2019.**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/9060334/)
以 packet delivery ratio 調整(已列入 `paper_focus.md`)。

## 2. Hidden terminal 偵測 → 開/關 RTS/CTS(binary 決策,非連續 score → threshold)

1. **Shigeyasu, Akimoto, and Matsuno, "Throughput Improvement of IEEE802.11 DCF with Adaptive RTS/CTS Control on the Basis of Existence of Hidden Terminals," 2011.**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/5989017/)
偵測 hidden terminal 存在與否,決定是否使用 RTS/CTS。

2. **"A machine learning approach for dynamic control of RTS/CTS in WLANs," MobiQuitous 2018.**
Link: [ACM DL](https://dl.acm.org/doi/10.1145/3286978.3287027)
ML 判斷是否啟用 RTS/CTS,輸出仍為 binary 開關。

3. **"Hidden-node detection in IEEE 802.11n wireless LANs."**
Link: [ResearchGate](https://www.researchgate.net/publication/260514965_Hidden-node_detection_in_IEEE_80211n_wireless_LANs)
利用 frame aggregation、block ACK、fast link adaptation 偵測 hidden node,偵測後觸發解決機制。

## 3. 通用 score → threshold 方法論(非 Wi-Fi,可引用支撐 mapping 設計)

1. **Ganjkhanloo et al., "Joint Score-Threshold Optimization for Interpretable Risk Assessment," arXiv:2510.21934.**
Link: [arXiv](https://arxiv.org/abs/2510.21934)
同時最佳化 scoring 權重與 category thresholds,概念上最貼近「risk scoring + score-to-threshold mapping」兩件事,但領域是醫療風險評估。

2. **"Threshold Choice Methods: the Missing Link," arXiv:1112.2640.**
Link: [arXiv PDF](https://arxiv.org/pdf/1112.2640)
系統性討論 score-driven threshold choice。

## Related work 定位建議

現有工作要嘛「調 threshold 但無 risk 概念」(第 1 類)、要嘛「偵測 hidden node 但只做 binary 開關」(第 2 類);本論文的貢獻是連續的 hidden node risk score(AoA/MUSIC 由 AP 端 CSI 估計)→ RTS threshold mapping。
