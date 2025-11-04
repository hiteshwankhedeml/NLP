# 🟢 Masked Application

* It helps manage the structure of the sequences being processed and ensures the models behaves correctly during training and inferencing

**Reasons:**

1. Handling variable length sequences with padding MASK

**Purpose:**

1. <mark style="color:purple;background-color:purple;">**To handle sequences of different length in batch**</mark>
2. <mark style="color:purple;background-color:purple;">**To ensure that padding tokens which are added to make sequences of uniform length do not affect the model prediction**</mark>

**Example:**

* Since 0 is added then it would influence attention mechanism
* Suppose if input is of 100 length, and output is of length 2, then we will add 98 0s
* This might affect mechanism due to such a large number of 0s
* For this we use <mark style="color:purple;background-color:purple;">**padding mask ⇒ To ensure that tokens are ignored**</mark>
*

<figure><img src=".gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>
