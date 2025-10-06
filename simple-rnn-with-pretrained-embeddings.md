# 🟢 Simple RNN with Pretrained embeddings

<mark style="color:purple;background-color:purple;">**Steps:**</mark>

* <mark style="color:purple;background-color:purple;">**Take the pre-trained embedding weights (GloVe vectors).**</mark>
* <mark style="color:purple;background-color:purple;">**For each word in your dataset’s vocabulary (here IMDB’s top 10,000 words):**</mark>
* <mark style="color:purple;background-color:purple;">**Look up the word in the GloVe embeddings.**</mark>
* <mark style="color:purple;background-color:purple;">**If found → copy its vector into the corresponding row of**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**`embedding_matrix`**</mark><mark style="color:purple;background-color:purple;">**.**</mark>
* <mark style="color:purple;background-color:purple;">**If not found → fill that row with zeros.**</mark>
* <mark style="color:purple;background-color:purple;">**Pass**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**`embedding_matrix`**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**to the Embedding layer as**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**`weights=[embedding_matrix]`**</mark><mark style="color:purple;background-color:purple;">**.**</mark>
* <mark style="color:purple;background-color:purple;">**We keep trainable=False in embedding layer, as we don't want weights to change**</mark>

```python
import numpy as np
import tensorflow as tf
from tensorflow.keras.datasets import imdb
from tensorflow.keras.preprocessing.text import Tokenizer
from tensorflow.keras.preprocessing.sequence import pad_sequences
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Embedding, SimpleRNN, Dense

# Load the IMDB dataset
max_words = 10000  # Vocabulary size
max_len = 500      # Maximum sequence length
(x_train, y_train), (x_test, y_test) = imdb.load_data(num_words=max_words)

# Pad sequences to ensure uniform input size
x_train = pad_sequences(x_train, maxlen=max_len)
x_test = pad_sequences(x_test, maxlen=max_len)

# Load GloVe embeddings
embedding_dim = 100
embedding_index = {}
with open("glove.6B.100d.txt", encoding="utf-8") as f:
    for line in f:
        values = line.split()
        word = values[0]
        vector = np.asarray(values[1:], dtype='float32')
        embedding_index[word] = vector

# Create an embedding matrix
word_index = imdb.get_word_index()
embedding_matrix = np.zeros((max_words, embedding_dim))
for word, i in word_index.items():
    if i < max_words:
        vector = embedding_index.get(word)
        if vector is not None:
            embedding_matrix[i] = vector

# Build the model
model = Sequential([
    Embedding(input_dim=max_words, output_dim=embedding_dim, input_length=max_len, weights=[embedding_matrix], trainable=False),
    SimpleRNN(64, return_sequences=False),
    Dense(1, activation='sigmoid')
])

# Compile the model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# Train the model
model.fit(x_train, y_train, epochs=5, batch_size=64, validation_data=(x_test, y_test))

# Evaluate the model
loss, accuracy = model.evaluate(x_test, y_test)
print(f'Test Accuracy: {accuracy:.4f}')

```
