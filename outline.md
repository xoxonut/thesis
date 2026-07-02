- Introduction
  - Explain the hidden-node problem in Wi-Fi and why it can reduce throughput and fairness.
  - Introduce RTS/CTS as the common mitigation method.
  - Describe the problem with static RTS/CTS configuration.
  - State the thesis goal: spatial-risk-aware RTS/CTS tuning using AP-side observations.

- Background
  - Review the RTS threshold as the main AP-side control knob.
  - Describe AP-side measurements, including retry statistics, RSSI, CSI, AoA, and MCS.
  - Explain how received signals from multiple AP antennas can provide spatial information.
  - Present CSI phase difference and antenna-array observations as the practical input for AoA estimation.
  - Briefly compare common non-ML AoA approaches, such as phase-difference methods, beam scanning, and subspace-based methods.
  - Motivate MUSIC for Wi-Fi APs because it can use existing multi-antenna CSI, provide higher angular resolution than simple beam scanning, and separate signal and noise subspaces without extra localization hardware.
  - Describe practical AoA error sources, including phase noise, multipath, antenna spacing, calibration error, and limited samples.

- Related Work
  - Review previous hidden-node mitigation methods.
  - Discuss adaptive RTS/CTS and MAC-layer tuning approaches.
  - Compare prior work that uses spatial information for Wi-Fi optimization.
  - Identify the gap addressed by this thesis.

- Spatial-Risk-Aware RTS/CTS Design
  - Define a hidden-node risk score using retry behavior, signal strength, CSI-derived spatial separation, optional AoA estimates, and MCS.
  - Use MUSIC-based AoA as one spatial feature when the AP has enough reliable multi-antenna CSI samples.
  - Explain how pair-level hidden-node risk is estimated between clients.
  - Describe how pair-level risks are aggregated into a radio-level decision.
  - Present the dynamic RTS/CTS tuning policy.

- Implementation
  - Describe how the AP collects retry statistics, RSSI, per-antenna CSI when available, optional AoA estimates, and MCS information.
  - Explain the processing pipeline for estimating hidden-node risk.
  - Clarify how AP-side CSI is calibrated and converted into MUSIC-based AoA or simpler spatial-separation features.
  - Describe how the AP updates the RTS threshold based on the risk decision.
  - Discuss practical implementation constraints and timing considerations.

- Evaluation
  - Define test scenarios for hidden-node and non-hidden-node conditions.
  - Compare static RTS/CTS settings with the proposed dynamic policy.
  - Measure throughput, retry rate, latency, MCS distribution, and fairness.
  - Analyze when the proposed method improves performance and when it has limited benefit.

- Conclusion
  - Summarize the thesis contribution and main findings.
  - Discuss limitations of the spatial-risk estimation and RTS/CTS tuning policy.
  - Suggest future work, such as better CSI calibration, stronger AoA estimation, richer risk models, and broader deployment tests.
