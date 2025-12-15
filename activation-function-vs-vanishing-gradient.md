---
hidden: true
---

# ✈️ Activation Function vs Vanishing Gradient

| Activation     | Derivative Range                                                        | Vanishing Gradient Risk | Notes                                                                                                                        |
| -------------- | ----------------------------------------------------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Sigmoid        | <mark style="color:purple;background-color:purple;">**0 – 0.25**</mark> | High                    | Outputs in \[0,1], gradients shrink quickly over time steps.                                                                 |
| Tanh           | <mark style="color:purple;background-color:purple;">**0 – 1**</mark>    | Moderate                | <mark style="color:purple;background-color:purple;">**Outputs in \[-1,1], better than sigmoid but can still vanish**</mark>. |
| ReLU           | 0 – 1                                                                   | Low (for positive z)    | Avoids vanishing for positive activations, but can “die” if z ≤ 0.                                                           |
| LSTM/GRU Gates | 0 – 1                                                                   | Controlled              | Special gating mechanisms allow long-term gradient flow.                                                                     |
