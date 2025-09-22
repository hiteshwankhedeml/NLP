# 🟢 Spam Ham using Tf-Idf

* <mark style="color:purple;background-color:purple;">**Same as previous**</mark>
* <mark style="color:purple;background-color:purple;">**Here we have used tfidf vectorizer instead of count vectorizer**</mark>

```python
from sklearn.feature_extraction.text import TfidfVectorizer
tv=TfidfVectorizer(max_features=2500,ngram_range=(1,2))
X_train=tv.fit_transform(X_train).toarray()
X_test=tv.transform(X_test).toarray()
```
