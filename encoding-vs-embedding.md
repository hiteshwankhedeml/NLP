# 🟢 Encoding vs Embedding



| Feature                  | **Encoding**                                                                                                 | **Embedding**                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| 🔤 **Definition**        | <mark style="color:purple;background-color:purple;">**Rule-based representation of words as numbers**</mark> | <mark style="color:purple;background-color:purple;">**Learned representation of words as vectors**</mark> |
| 🔢 **Vector Type**       | <mark style="color:purple;background-color:purple;">**Sparse (mostly 0s)**</mark>                            | <mark style="color:purple;background-color:purple;">**Dense (real numbers)**</mark>                       |
| 🧠 **Captures Meaning?** | <mark style="color:purple;background-color:purple;">**❌ No**</mark>                                          | <mark style="color:purple;background-color:purple;">**✅ Yes (semantic similarity)**</mark>                |
| 🧮 **Dimensionality**    | High (equal to vocabulary size)                                                                              | Low (e.g., 100–768 dimensions)                                                                            |
| 🧾 **Representation**    | <mark style="color:purple;background-color:purple;">**Fixed and manual**</mark>                              | <mark style="color:purple;background-color:purple;">**Learned from data**</mark>                          |
| 🔁 **Context Aware?**    | <mark style="color:purple;background-color:purple;">**❌ No (same vector always)**</mark>                     | <mark style="color:blue;background-color:purple;">**✅ (contextual if using models like BERT)**</mark>     |
| 📚 **Examples**          | One-Hot, Bag of Words, TF-IDF                                                                                | Word2Vec, GloVe, FastText, BERT                                                                           |
| 🔍 **Similarity Info**   | Not captured                                                                                                 | Captured (similar words are close)                                                                        |
| ⚙️ **Use Case**          | Simple ML models                                                                                             | NLP models, deep learning, semantic tasks                                                                 |
