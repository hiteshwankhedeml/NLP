# 🟢 Training simple RNN with embedding layers

* <mark style="color:purple;background-color:purple;">**In the NN, we will add 1st layer as embedding in which we will specify vocabulary size, dimension and sequence length**</mark>

<mark style="color:purple;background-color:purple;">**Steps:**</mark>

* <mark style="color:purple;background-color:purple;">Define sequential model</mark>
* <mark style="color:purple;background-color:purple;">Add embedding layer</mark>
* <mark style="color:purple;background-color:purple;">Add RNN with no. of neurons and activation function</mark>
* <mark style="color:purple;background-color:purple;">Add Output layer</mark>
* <mark style="color:purple;background-color:purple;">Compile the model ⇒ pass optimizer, loss, metrics</mark>
* <mark style="color:purple;background-color:purple;">Define callback for earlystopping</mark>
* <mark style="color:purple;background-color:purple;">model.fit ⇒ pass data, no. of epochs, batcd size, split ratio and callbacks</mark>
* <mark style="color:purple;background-color:purple;">Save the model as .h5</mark>

```python
## Train Simple RNN
model=Sequential()
model.add(Embedding(max_features,128,input_length=max_len)) ## Embedding Layers
model.add(SimpleRNN(128,activation='relu'))
model.add(Dense(1,activation="sigmoid"))

model.summary()

model.compile(optimizer='adam',loss='binary_crossentropy',metrics=['accuracy'])

## Create an instance of EarlyStoppping Callback
from tensorflow.keras.callbacks import EarlyStopping
earlystopping=EarlyStopping(monitor='val_loss',patience=5,restore_best_weights=True)
earlystopping

## Train the model with early sstopping
history=model.fit(
    X_train,y_train,epochs=10,batch_size=32,
    validation_split=0.2,
    callbacks=[earlystopping]
)

model.save('simple_rnn_imdb.h5')

model.get_weights() # To get the weights
```
