# 🔴 Simple RNN Backward Propagation

* We will be passing xi1 at t = 1
* Initially some weights will be assigned
* O0 can be initialized as zero or any random value
* Using forward pass we will get O1, O2....O4
* O4 will be passed to sigmoid (If binary classifier)
* <mark style="color:purple;background-color:purple;">**To reduce the loss, we need to update the weights (Wi, Wh, W0) using the weight updation formula**</mark>
*

    <figure><img src=".gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>
* Update weight:
* W0 is directly dependent of ypred and ypred is direct dependent on loss
* <mark style="color:purple;background-color:purple;">**Wh is used in each and every time stamp**</mark>
* <mark style="color:purple;background-color:purple;">**We have to find Wh based on all the timestamps**</mark>
*
*

    <figure><img src=".gitbook/assets/{4F202281-3BF9-479C-BC26-CCCDF6245426}.png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src=".gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>
