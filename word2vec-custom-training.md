# 🟢 Word2Vec - Custom training

* <mark style="color:purple;background-color:purple;">**Pretrained:**</mark>
  * <mark style="color:purple;background-color:purple;">**Google\_news\_300 - This will convert every word into 300 dimension**</mark>
* <mark style="color:purple;background-color:purple;">**Train from scratch:**</mark>
  * <mark style="color:purple;background-color:purple;">**If 75% of the words are there in the pretrained model, then use it otherwise better to train it**</mark>

<mark style="color:purple;background-color:purple;">**Steps:**</mark>

* <mark style="color:purple;background-color:purple;">**Get the corpus**</mark>

| Gensim Function                                                                   | Usage                                                                                                                                                          |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:purple;background-color:purple;">**simple\_preprocess**</mark> |  <mark style="color:purple;background-color:purple;">**lowercase, remove punctuation/special characters, tokenization ⇒ we get list of list of tokens**</mark> |
| <mark style="color:purple;background-color:purple;">**word2vec**</mark>           | <mark style="color:purple;background-color:purple;">**initialize window size, vector size etc**</mark>                                                         |
| <mark style="color:purple;background-color:purple;">**train**</mark>              | <mark style="color:purple;background-color:purple;">**start the training**</mark>                                                                              |

* <mark style="color:purple;background-color:purple;">**Evaluated intrinsically (similarity, analogy) or extrinsically (downstream task), not by absolute loss.**</mark>
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
