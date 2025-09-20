# 🟢 Multi head attention

* <mark style="color:purple;background-color:purple;">**Multi-head attention lets the model look at different types of relationships between tokens simultaneously.**</mark>
* <mark style="color:purple;background-color:purple;">**Each head specializes in a particular dependency (subject-verb, verb-object, modifiers, etc.), and combining them gives a richer, more complete representation of each token.**</mark>
* X is having the embedding of words
* We do dot operation of X and W to get Q, K and V
* We do dot product of Q and Key then scaling then softmax and then multiply by value
* This is how we get self attention
*

    <figure><img src=".gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>
* We can also create multiple attention heads for the same words
* Initially we initialize some different weights and then calculated contextual vector&#x20;
* Similarly <mark style="color:purple;background-color:purple;">**we can initialize some other weight which may capture importance of some other important words and we may get another contextual vector**</mark>
*   Multi head attention attends models ability to focus on different positions of tokens

    <figure><img src=".gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>
