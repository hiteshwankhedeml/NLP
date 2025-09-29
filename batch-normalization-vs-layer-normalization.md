# Batch Normalization vs Layer Normalization

* &#x20;In Layer normalization, we take layer by layer and then normalize it
*

    <figure><img src=".gitbook/assets/{E4BCFE3E-8590-428F-82F2-C9DF29F54FE0}.png" alt=""><figcaption></figcaption></figure>
* There are 2 learnable parameters, gamma and beta
* In Batch normalization ⇒  If Z1 or Z2 contains lots of 0s, if we normalize using it then due to this 0s all the values will be impacted
* In Layer normalization, it won't have much impact
* After calculation Z, we will use gamma and betta
* If our distribution is not important, and we do not want to normalize it, then it can be controlled using gamma
*   Gamma and beta are also known as scale and shift parameters

    <figure><img src=".gitbook/assets/{49770B1D-FD21-4F83-BD52-2DBA51BF20EB}.png" alt=""><figcaption></figcaption></figure>
