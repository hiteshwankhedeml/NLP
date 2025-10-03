# Masked Application

* It helps manage the structure of the sequences being processed and ensures the models behaves correctly during training and inferencing

Reasons:

1. Handling variable length sequences with passing MASK

Purpose:

1. To handle sequences of different length in batch
2. To ensure that padding tokens which are added to make sequences of uniform length do not affect the model prediction

Example:

* Since 0 is added then it would influence attention mechanism
* Suppose if input is of 100 length, and output is of lenght 2, then we will add 98 0s
* This might affect mechanism due to such a large number of 0s
* For this we use padding mask ⇒ To ensure that tokens are ignored
*

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
