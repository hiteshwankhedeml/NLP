# 🟢 Data passing to RNN

**Sentiment Analysis:**

* <mark style="color:purple;background-color:purple;">**Sentence: The food is good, Output: Positive**</mark>
* <mark style="color:purple;background-color:purple;">**This can be written as \<x**</mark>[<mark style="color:purple;background-color:purple;">**11**</mark>](#user-content-fn-1)[^1] <mark style="color:purple;background-color:purple;">**x12 x13 x14>**</mark>
* <mark style="color:purple;background-color:purple;">**At t = 1, we will pass x11**</mark>
* <mark style="color:purple;background-color:purple;">**We will first convert x11 into vector using word2vec or some other method in some dimensions**</mark>
* <mark style="color:purple;background-color:purple;">**And then this vector will be passed to the network**</mark>
* <mark style="color:purple;background-color:purple;">**At t = 2, we will pass x12 and so on**</mark>
* <mark style="color:purple;background-color:purple;">**Once forward propagation is done, then back-propagation will happen**</mark>
*

    <figure><img src=".gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

[^1]: 
