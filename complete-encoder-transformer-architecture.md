# Complete Encoder Transformer Architecture

* As per the research paper, there are 6 encoders and 6 decoders
* Every word will have dimension of 512, same will be positional embedding
* In self attention, we have important parameters ⇒ Q, V, K ⇒ dimension of 64

**Steps:**

* Input sequence ⇒ Embedding + Positional Embedding&#x20;
* Multi Head Attention (8 Heads)
* Add and Normalize (Layer Normalize) ⇒ This is basically called as Residuals
* Feed forward NN&#x20;
*

    <figure><img src=".gitbook/assets/{3AF2A8A6-47D8-4216-93F2-04A242BD2BA4}.png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/{C03027E0-E10F-4543-8161-3317CF9BE43D}.png" alt=""><figcaption></figcaption></figure>
