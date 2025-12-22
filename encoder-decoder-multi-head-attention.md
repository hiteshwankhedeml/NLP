# 🟢 Encoder Decoder Multi Head Attention

* After masked multi head attention, layer normalization will happen
* <mark style="color:purple;background-color:purple;">**2 of the connections from encoder are coming here**</mark>
* <mark style="color:purple;background-color:purple;">**From encoder we are taking Attention vectors of keys and values**</mark>
* <mark style="color:purple;background-color:purple;">**From the add and norm of decoder, we will be passing Attention query vector here**</mark>
* <mark style="color:purple;background-color:purple;">**These will be used by each decoder in its "encoder-decoder" attention layer**</mark>
* This helps the decoder, to focus on appropriate places in the input sequence
*

    <figure><img src=".gitbook/assets/{9EC6B504-5777-40C2-BD9F-C38488E7F036}.png" alt=""><figcaption></figcaption></figure>
