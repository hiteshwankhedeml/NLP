# Final Decoder Linear and Softmax Layer

* The linear layer is a simple fully connected NN that projected the vector the vector produced by the stack of decoder
* It generates logits
* Softmax turns these scores into probabilities
* The cell with the highest probability is chosen as output and the word associated with it is produced as the output
*

    <figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
