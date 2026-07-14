Best recent match:

**Chen, Zhong, and Haenggi, “Cross-link RTS/CTS for MLO mm-Wave WLANs,” arXiv, Nov. 7, 2025.**  
Link: [arXiv:2511.05027](https://arxiv.org/abs/2511.05027)

Why it fits: it is directly about RTS/CTS in next-generation Wi-Fi/WLANs, especially mmWave Wi-Fi with multi-link operation. It studies hidden-terminal behavior and proposes **cross-link RTS/CTS**, comparing reliability gains against throughput loss.

A very useful companion paper:

**Zhong, Chen, Zhang, and Haenggi, “Dual-Zone Hard-Core Model for RTS/CTS Handshake Analysis in WLANs,” arXiv, Dec. 13, 2024.**  
Link: [arXiv:2412.09953](https://arxiv.org/abs/2412.09953)

This one is more foundational: it models RTS/CTS in 802.11 WLANs using stochastic geometry and analyzes interference and success probability. For thesis background, I’d read this first, then the 2025 cross-link paper.

## Dynamic RTS threshold setting

Note on venues: papers on *dynamic RTS threshold* rarely appear at top venues under that name. Top-conference work (MobiCom, INFOCOM) treats adaptive RTS activation as a component inside rate adaptation; direct threshold-tuning papers sit at ICC/SmartWorld-level venues. No top-venue paper does risk-aware RTS threshold control driven by AP-side sensing — that is the gap this thesis targets.

### Top-conference papers (adaptive RTS as a mechanism)

**Wong, Yang, Lu, and Bharghavan, “Robust Rate Adaptation for 802.11 Wireless Networks” (RRAA), MobiCom 2006.**
Link: [ACM DL](https://dl.acm.org/doi/10.1145/1161089.1161107) · [PDF (UCLA)](http://metro.cs.ucla.edu/papers/Wong.Mobicom06.pdf)

Why it fits: its **A-RTS (adaptive RTS filter)** turns RTS/CTS on/off per-frame based on observed loss patterns, so hidden node collision losses are not misread as channel errors. Closest top-conference relative of this thesis.

**Kim, Kim, Choi, and Qiao, “CARA: Collision-Aware Rate Adaptation for IEEE 802.11 WLANs,” INFOCOM 2006.**

Uses adaptive **RTS probing** to distinguish collisions (incl. hidden node collisions) from channel fading — the classic argument for when RTS should be switched on.

### Papers directly on dynamic RTS threshold tuning

**Kong, Tsang, and Bensaou, “Adaptive RTS/CTS Mechanism for IEEE 802.11 WLANs to Achieve Optimal Performance,” IEEE ICC 2004.**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/1312477)

Analytical throughput/delay model, then adjusts the RTS threshold adaptively (centralized or distributed) toward the optimum.

**Yin, Gao, Manzoor, and Hei, “Optimal RTS Threshold for IEEE 802.11 WLANs: Basic or RTS/CTS?,” IEEE SmartWorld 2019.**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/9060334/)

Derives a **closed-form optimal RTS threshold**; shows the standard fixed threshold makes DCF fail to activate RTS/CTS when it should. Not a top venue, but the explicit optimal-threshold expression is very citable as a baseline.

**“A Machine Learning Approach for Dynamic Control of RTS/CTS in WLANs,” MobiQuitous 2018 (EAI).**
Link: [ACM DL](https://dl.acm.org/doi/10.1145/3286978.3287027)

Learns network contention online and compares the cost of RTS/CTS vs. retransmission to switch RTS/CTS per-packet; beats both “always off” and fixed-threshold policies. Mid-tier venue, but closest in spirit to a learned dynamic threshold.

**“RTS Threshold Adjustment Algorithm for IEEE 802.11 DCF,” IEEE, 2006.**
Link: [IEEE Xplore](https://ieeexplore.ieee.org/document/4068676/)

Earlier direct threshold-adjustment scheme; useful as related work rather than as a strong baseline.

### How to use these in the thesis

- Cite **RRAA and CARA** as top-venue precedent that RTS should be adaptive, and note both infer hidden node risk *indirectly from loss statistics* — the AoA/CSI approach observes the spatial cause directly.
- Cite **Kong (ICC'04)** and **Yin (SmartWorld'19)** as the threshold-tuning line, and note they assume saturated single-cell models without per-station hidden node awareness.
