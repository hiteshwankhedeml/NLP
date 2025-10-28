# 🟢 Spam Ham project using BOW

<mark style="color:purple;background-color:purple;">**Steps:**</mark>

* <mark style="color:purple;background-color:purple;">get data</mark>
* <mark style="color:purple;background-color:purple;">lowercase</mark>
* <mark style="color:purple;background-color:purple;">stemming</mark>
* <mark style="color:purple;background-color:purple;">remove stop words</mark>
* <mark style="color:purple;background-color:purple;">train test split</mark>
* <mark style="color:purple;background-color:purple;">x = count vectorizer. fit\_transform</mark>
* <mark style="color:purple;background-color:purple;">y = pd.get\_dummies ⇒ One Hot Encoding</mark>
* <mark style="color:purple;background-color:purple;">Train using algo</mark>
* <mark style="color:purple;background-color:purple;">Check the accuracy</mark>

```python
messages # Data frame with columns - label and message

# lowercase
# stemming
# remove stopwords

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer(max_features=2500,ngram_range=(1,2))
X=cv.fit_transform(corpus).toarray()

y=pd.get_dummies(messages['label'])
y=y.iloc[:,0].values

X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.20)

from sklearn.naive_bayes import MultinomialNB
spam_detect_model=MultinomialNB().fit(X_train,y_train)
y_pred=spam_detect_model.predict(X_test)

accuracy_score(y_test,y_pred)
print(classification_report(y_test,y_pred))
#              precision    recall  f1-score   support
#
#           0       0.94      0.89      0.92       131
#           1       0.99      0.99      0.99       984
#
#    accuracy                           0.98      1115
#   macro avg       0.96      0.94      0.95      1115
#weighted avg       0.98      0.98      0.98      1115
```
