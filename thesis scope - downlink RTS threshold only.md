# ⚠️ IMPORTANT — Thesis scope: downlink RTS threshold only

**This thesis only controls the downlink RTS threshold.** The AP adjusts its own RTS threshold for AP→STA transmissions; uplink (STA-side) RTS behavior is left unchanged.

Rationale:

- AP-side CSI/AoA sensing (MUSIC) informs the **AP's own** transmit decisions.
- Standard clients cannot be assumed to accept per-station RTS threshold control from the AP.

Every design, implementation, and evaluation chapter must stay within this scope — do not propose or evaluate STA-side RTS threshold adaptation.
