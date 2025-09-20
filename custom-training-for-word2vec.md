# 🟢 Custom training for word2vec

<mark style="color:purple;background-color:purple;">**Steps:**</mark>

* <mark style="color:purple;background-color:purple;">**Get the corpus**</mark>
* <mark style="color:purple;background-color:purple;">**use simple\_preprocess from gensim ⇒ lowercase, remove punctuation/special characters, tokenization ⇒ we get list of tokens**</mark>
* <mark style="color:purple;background-color:purple;">**using gensim.models/word2vec ⇒ initialize window size, vector size etc**</mark>
* <mark style="color:purple;background-color:purple;">**using gensim.train ⇒ start the training**</mark>
* <mark style="color:purple;background-color:purple;">**Word2Vec embeddings are evaluated intrinsically (similarity, analogy) or extrinsically (downstream task), not by absolute loss.**</mark>
* <mark style="color:purple;background-color:purple;">**The loss itself is mostly used to monitor convergence, not for final evaluation.**</mark>

```python
nltk.download("all")

from nltk import sent_tokenize
from gensim.utils import simple_preprocess

story=[]

folder_path=r"C:\\Complete_Content\\GENERATIVEAI\\genai_bootcamp\\gotbooks"

story=[]
for filename in os.listdir(folder_path):
  file_path=os.path.join(folder_path,filename)
  with open(file_path,encoding='unicode_escape') as f:
    corpus=f.read()
  raw_sent=sent_tokenize(corpus)
  for sent in raw_sent:
    story.append(simple_preprocess(sent))

story
[['game',  'of',  'thrones',  'book',....],
 ['','',.....]

custom_model=gensim.models.Word2Vec(window=10,min_count=5,vector_size=150)
custom_model.build_vocab(story)
custom_model.train(story,total_examples=model.corpus_count, epochs=5)
custom_model.wv["king"]
```
