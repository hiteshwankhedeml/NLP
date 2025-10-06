# 🟢 Prediction from trained Simple RNN

* <mark style="color:purple;background-color:purple;">**We 1st pre process the sentence for which prediction to be done**</mark>
  * <mark style="color:purple;background-color:purple;">**We lowercase and split**</mark>
  * <mark style="color:purple;background-color:purple;">**For each word we find the index which was used during training**</mark>
  * <mark style="color:purple;background-color:purple;">**Add padding**</mark>
* <mark style="color:purple;background-color:purple;">**Then we call the model for prediction**</mark>

```python
# Step 1: Import Libraries and Load the Model
import numpy as np
import tensorflow as tf
from tensorflow.keras.datasets import imdb
from tensorflow.keras.preprocessing import sequence
from tensorflow.keras.models import load_model

# Load the IMDB dataset word index
word_index = imdb.get_word_index()
reverse_word_index = {value: key for key, value in word_index.items()}

model = load_model('simple_rnn_imdb.h5')

# Step 2: Helper Functions
# Function to decode reviews
def decode_review(encoded_review):
    return ' '.join([reverse_word_index.get(i - 3, '?') for i in encoded_review])

# Function to preprocess user input
# We are starting encoding from 3rd word becoz in imdb, the 1st 3 words are reserve
def preprocess_text(text):
    words = text.lower().split()
    encoded_review = [word_index.get(word, 2) + 3 for word in words]
    padded_review = sequence.pad_sequences([encoded_review], maxlen=500)
    return padded_review

### Prediction  function
def predict_sentiment(review):
    preprocessed_input=preprocess_text(review)
    prediction=model.predict(preprocessed_input)
    sentiment = 'Positive' if prediction[0][0] > 0.5 else 'Negative'
    return sentiment, prediction[0][0]

# Step 4: User Input and Prediction
# Example review for prediction
example_review = "This movie was fantastic! The acting was great and the plot was thrilling."
sentiment,score=predict_sentiment(example_review)
print(f'Review: {example_review}')
print(f'Sentiment: {sentiment}')
print(f'Prediction Score: {score}')
#1/1 [==============================] - 0s 196ms/step
#Review: This movie was fantastic! The acting was great and the plot was thrilling.
#Sentiment: Positive
#Prediction Score: 0.8114995360374451
```
