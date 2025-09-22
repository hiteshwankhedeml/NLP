# 🟢 Average Word2Vec intuition

* In word2vec we take every word and we convert it into vectors
* If we are using google pre-trained word2vec model
* We will get feature representation of 300 dimension for word 'the'
* similarly for every word we will get feature representation of 300 dimension
* If we have so many vector of 300 dimension
* Our aim is to get only 1 vector of 300 dimension -> This will be our input
* <mark style="color:purple;background-color:purple;">**We take average of all the vectors of the words and feed this as input to the model**</mark>
*

    <figure><img src=".gitbook/assets/image (9) (1) (1).png" alt=""><figcaption></figcaption></figure>
