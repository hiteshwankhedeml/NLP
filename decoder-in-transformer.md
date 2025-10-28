# Decoder in Transformer

* Responsible for generating the output sequence one token at a time, using the encoders output and the previously generated tokens
* 3 important components
  * Masked multi head self attention
  * Multi head attention (Encoder Decoder Attention)
  * Feed forward NN
* Output of encoder ⇒ Multi head attention of encoder
*

    <figure><img src=".gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* In Encoder, we will be passing all the input at once
* In Decoder, output will be generated at each time stamp one by one token
*   In training, we will be giving actual output to the decoder

    <figure><img src=".gitbook/assets/{AC8F5DCD-D4CB-4054-8801-D8BC418D2E17}.png" alt=""><figcaption></figcaption></figure>
