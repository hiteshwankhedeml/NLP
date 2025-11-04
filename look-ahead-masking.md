# 🟢 Look Ahead Masking

* <mark style="color:purple;background-color:purple;">**Maintain auto regressive property**</mark>
* Decoder generates one word at a time
* <mark style="color:purple;background-color:purple;">**For predicting a word, we need the info of the previous word**</mark>
* <mark style="color:purple;background-color:purple;">**To ensure that each position in the decoder output sequence can only attend to the previous position, but no future position**</mark>
* For difference sequence task like language modelling, language translation sequence is very important
*   Sequence \[4 5 0] ⇒ Passing mask \[1 1 0]

    <figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
* Lets consider every token is 3 dimension
* We want 4 to take context of 5, and 5 can take context of 4, but we don't want them to take context of 0
* For each token in the sequence, the mask should indicate which token it can attend to

**Construct look ahead mask:**

* For the 1st token - We want don't want it to take future token, so it will be 1 0 0
* Similarly for 2 it will be \[1 1 0]

**Combine padding and look ahead mask:**

* Here we will be doing elementwise multiplication of 2 mask
* Wherever the value is 0, there we specify inf
*

    <figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
