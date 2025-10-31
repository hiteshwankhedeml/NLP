# 🟢 Batch Normalization vs Layer Normalization

* <mark style="color:purple;background-color:purple;">**LayerNorm**</mark> <mark style="color:purple;background-color:purple;"></mark><mark style="color:purple;background-color:purple;">→ normalize</mark> <mark style="color:purple;background-color:purple;"></mark>_<mark style="color:purple;background-color:purple;">row-wise</mark>_ <mark style="color:purple;background-color:purple;"></mark><mark style="color:purple;background-color:purple;">→ each sample normalized independently</mark>
* <mark style="color:purple;background-color:purple;">**BatchNorm**</mark> <mark style="color:purple;background-color:purple;"></mark><mark style="color:purple;background-color:purple;">→ normalize</mark> <mark style="color:purple;background-color:purple;"></mark>_<mark style="color:purple;background-color:purple;">column-wise</mark>_ <mark style="color:purple;background-color:purple;"></mark><mark style="color:purple;background-color:purple;">→ each feature normalized across batch</mark>
*

    <figure><img src=".gitbook/assets/{E4BCFE3E-8590-428F-82F2-C9DF29F54FE0}.png" alt=""><figcaption></figcaption></figure>
* There are 2 learnable parameters, gamma and beta
* <mark style="color:purple;background-color:purple;">**In Batch normalization ⇒  If Z1 or Z2 contains lots of 0s, if we normalize using it then due to this 0s all the values will be impacted**</mark>
* <mark style="color:purple;background-color:purple;">**In Layer normalization, it won't have much impact**</mark>
* After calculation Z, we will use gamma and betta
* If our distribution is not important, and we do not want to normalize it, then it can be controlled using gamma
*   Gamma and beta are also known as scale and shift parameters

    <figure><img src=".gitbook/assets/{49770B1D-FD21-4F83-BD52-2DBA51BF20EB}.png" alt=""><figcaption></figcaption></figure>
