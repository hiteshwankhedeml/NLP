# 🟢 LSTM RNN Architecture

* Xt is input
* 3 important gates:
  * <mark style="color:purple;background-color:purple;">**Forget gate**</mark>
  * <mark style="color:purple;background-color:purple;">**Input gate and candidate memory ⇒ Candidate and input gates are separate to allow independent control of value and scaling**</mark>
  * <mark style="color:purple;background-color:purple;">**Output gate**</mark>
* Ht-1 is hidden state of previous time stamp
* Number of LSTM units (cells) determines the dimension of both short-term memory  and long-term memory&#x20;
* If there are 128 units → short term and long term memory have shape `(batch_size, 128)`
* In tanh, we will be applying tanh function to each element of the vector
* Xt and Ht-1 are combined together and then they are sent to each gate
* Memory cell is for long term memory
*

    <figure><img src=".gitbook/assets/image (28) (1).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/image (29) (1).png" alt=""><figcaption></figcaption></figure>
