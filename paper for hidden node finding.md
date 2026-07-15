Best fit: [Ali, Mišić & Mišić, “Performance analysis of IEEE 802.11ax heterogeneous network in the presence of hidden terminals”](https://arxiv.org/abs/1908.01834). It is non-ML and directly gives a probability model: Section 3.1 defines hidden-node count `N_k,h`, transmission probability `tau_k`, vulnerable period, probability of no collision from hidden nodes, and final success probability with hidden nodes.

Use these as supporting papers:

- [van de Ven et al., “Optimal Tradeoff Between Exposed and Hidden Nodes in Large Wireless Networks”](https://arxiv.org/abs/1004.1058)  
  Good for the geometric definition: hidden nodes are outside sender sensing range but inside receiver interference range. Useful for deriving a spatial hidden-node risk score.

- [Fang et al., “Probabilistic Modeling of IEEE 802.11 Distributed Coordination Functions”](https://arxiv.org/abs/1411.1126)  
  Good general Markov/probabilistic DCF model using topology and node states, not ML.

- [Sepulcre et al., “Analytical Models of the Performance of IEEE 802.11p Vehicle to Vehicle Communications”](https://arxiv.org/abs/2104.07923)  
  Useful if you want packet-delivery/error probability models including hidden-terminal effects.

For your thesis, a clean non-ML formula path is:

`P(any hidden node) = 1 - product(1 - P_hidden_pair(i,j))`

and for collision risk during a vulnerable period:

`P(hidden collision) = 1 - product_h (1 - tau_h)^T_v`

where `tau_h` is the hidden node’s slot transmission probability and `T_v` is the RTS/CTS or trigger-frame vulnerable period. This matches the direction of Ali et al.’s analytical model and can be combined with CSI/AoA/RSSI to estimate `P_hidden_pair(i,j)` without ML.
