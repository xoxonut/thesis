## Spatial Spectrum Estimation: From Signals to Direction Peaks

先講概念：接收端觀察到的是多天線、多 subcarrier 的訊號差異，不是直接觀察角度。Spatial spectrum estimation 的目標是對每個候選方向給一個分數，peak 代表可能有訊號從該方向進來。

## Direction Finding / AoA Estimation

再講任務：在 Wi-Fi localization 裡，我們把 spectrum peak 解讀成 propagation path 的 AoA。室內 multipath-rich，所以通常會有多個 peak，分別對應 direct path 和 reflected paths。

## CSI-based AoA Estimation

這張先不要提 MUSIC。只講 Wi-Fi AP 能取得 CSI，而 CSI 是 complex value，包含 antenna/subcarrier 上的 phase。AoA 會造成天線間 phase shift，ToF 會造成 subcarrier 方向上的 phase trend，所以 CSI 可以拿來估計路徑方向。

## MUSIC: A CSI-based Spatial Spectrum Estimator

這張才正式介紹 MUSIC。標題不要用 Why，而是先說它是什麼。內容講：MUSIC 用 steering vector 表示每個候選 AoA 的理論相位模式，再利用 covariance matrix 分出 signal subspace 和 noise subspace。當某個 steering vector 與 noise subspace 幾乎正交時，MUSIC spectrum 會出現 peak。

## Why We Use MUSIC

最後才問為什麼選 MUSIC。這時聽眾已經知道 MUSIC 是一種 CSI-based spatial spectrum estimator，問 Why 就自然了。
