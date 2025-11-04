# Compute Mask

* Compute look ahead mask
* Compute padding mask computed to 2D format
* Multiply Look ahead and Padding mask
* Wherever there are 0, replace with Inf
* Compute Masked score
* We add Inf, to zero out the influence when the softmax is applied
*   On application of softmax it will get converted to 0, so there wont be attention to this tokens

    <figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
