## Introduction
- Explain the hidden-node problem in Wi-Fi and why it can reduce throughput and fairness.
- Slide title: AP-Side Goal: Hidden-Node Risk-Aware RTS Threshold Control.
- State the thesis goal early: let the AP infer hidden-node risk from AoA and link observations, then tune the RTS threshold dynamically.
- Slide title: RTS/CTS Mitigation with a Static RTS Threshold.
- Describe the problem with static RTS threshold configuration: a low threshold adds unnecessary RTS/CTS overhead, while a high threshold may leave hidden-node collisions unresolved.

## Background
- Review the RTS threshold as the main AP-side control knob.
- Describe AP-side measurements, including retry statistics, RSSI, CSI, AoA, and MCS.
- Explain how received signals from multiple AP antennas can provide spatial information.
- Present CSI phase difference and antenna-array observations as the practical input for AoA estimation.
- Briefly compare common non-ML AoA approaches, such as phase-difference methods, beam scanning, and subspace-based methods.
- Motivate MUSIC for Wi-Fi APs because it can use existing multi-antenna CSI, provide higher angular resolution than simple beam scanning, and separate signal and noise subspaces without extra localization hardware.
- Describe practical AoA error sources, including phase noise, multipath, antenna spacing, calibration error, and limited samples.

## Related Work
- Review previous hidden-node mitigation methods.
- Discuss adaptive RTS/CTS and MAC-layer tuning approaches.
- Compare prior work that uses AoA or other spatial information for Wi-Fi optimization.
- Identify the gap addressed by this thesis.

## AoA-Assisted Risk Scoring Design
- Present the overall design goal: use AP-side AoA and link observations to decide when RTS/CTS overhead is worthwhile.
- Define the hidden-node risk score as the core decision variable for RTS threshold control.
- Use AoA estimates from AP-side multi-antenna CSI as the main spatial feature for judging whether two clients are likely to be hidden from each other.
- Combine AoA-based spatial separation with retry behavior, RSSI, MCS, and traffic activity so the score reflects both geometry and observed collision symptoms.
- Explain how pair-level hidden-node risk is computed between active clients.
- Describe how pair-level risks are aggregated into a radio-level or BSS-level risk score.

## RTS Threshold Adaptation Design
- Present the RTS threshold adaptation rule: lower the threshold when hidden-node risk is high, and restore or raise it when risk is low to avoid unnecessary RTS/CTS overhead.
- Include smoothing and hysteresis so the RTS threshold does not oscillate under noisy AoA or retry measurements.

## Implementation
- Describe how the AP collects retry statistics, RSSI, per-antenna CSI for AoA estimation, MCS information, and traffic activity.
- Explain the processing pipeline from CSI calibration, AoA estimation, pair-level hidden-node risk scoring, risk aggregation, to RTS threshold update.
- Clarify how MUSIC-based AoA is used when CSI quality is sufficient, and how the system falls back to simpler spatial or link-quality features when AoA is unreliable.
- Describe how the AP maps the hidden-node risk score to concrete RTS threshold values.
- Discuss practical implementation constraints and timing considerations.

## Evaluation
- Define test scenarios for hidden-node and non-hidden-node conditions.
- Compare static RTS/CTS settings with the proposed AoA-assisted dynamic RTS threshold policy.
- Measure throughput, retry rate, latency, MCS distribution, and fairness.
- Analyze when the proposed method improves performance and when it has limited benefit.

## Conclusion
- Summarize the thesis contribution and main findings.
- Discuss limitations of AoA-assisted hidden-node risk scoring and RTS threshold tuning.
- Suggest future work, such as better CSI calibration, stronger AoA estimation, richer hidden-node risk models, and broader deployment tests.
