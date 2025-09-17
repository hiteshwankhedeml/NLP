# Encoding vs Embedding



| Feature                  | **Encoding**                                  | **Embedding**                              |
| ------------------------ | --------------------------------------------- | ------------------------------------------ |
| 🔤 **Definition**        | Rule-based representation of words as numbers | Learned representation of words as vectors |
| 🔢 **Vector Type**       | Sparse (mostly 0s)                            | Dense (real numbers)                       |
| 🧠 **Captures Meaning?** | ❌ No                                          | ✅ Yes (semantic similarity)                |
| 🧮 **Dimensionality**    | High (equal to vocabulary size)               | Low (e.g., 100–768 dimensions)             |
| 🧾 **Representation**    | Fixed and manual                              | Learned from data                          |
| 🔁 **Context Aware?**    | ❌ No (same vector always)                     | ✅ (contextual if using models like BERT)   |
| 📚 **Examples**          | One-Hot, Bag of Words, TF-IDF                 | Word2Vec, GloVe, FastText, BERT            |
| 🔍 **Similarity Info**   | Not captured                                  | Captured (similar words are close)         |
| ⚙️ **Use Case**          | Simple ML models                              | NLP models, deep learning, semantic tasks  |
