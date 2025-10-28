# 🟢 TF IDF implementation

* <mark style="color:purple;background-color:purple;">**Use TfidfVectorizer from sklearn, we can also pass ngram range to it**</mark>

```python
from sklearn.feature_extraction.text import TfidfVectorizer
tfidf=TfidfVectorizer(max_features=100)
X=tfidf.fit_transform(corpus).toarray()

tfidf=TfidfVectorizer(max_features=100,ngram_range=(2,2)) # bigram
tfidf.vocabulary_
# This will give dictionary of words and their count
```
