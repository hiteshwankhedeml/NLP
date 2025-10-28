# Decoder - Masked Multi Head Attention

* Lets  say we have language translation ⇒ English\<x1 x2 x3> to Hindi\<y1 y2>
* During training, x1, x2, x3 will be given to encoder
* Output of encoder will go to Multi Head attention in Decoder
* Output shifted right means we use 0 padding \<y1 y2> ⇒ \<y1 y2 0>
*

    <figure><img src=".gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

**Masked Multi Head Attention:**

* Combination of Linear Projection Q,K,V / Scaled Dot Product Attention / Mask Application
* &#x20;Input Embedding + Positional Embedding
  * We add padding to 0&#x20;
  * Lets consider that every output embedding for each word as 4 dimensional
  * This will be added with positional Embedding
* Linear Projection for Q, K and V
  * Create a  Query - Q, Key - K and Value - V by multiplying with Wq, Wk and Wv
* Scaled Dot Product Attention
  * Divide by root of dimension of k
  * &#x20;( Q \* K ) / root of dk
*

    <figure><img src=".gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

