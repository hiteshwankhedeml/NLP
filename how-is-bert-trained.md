# 🟢 How is BERT Trained

* BERT stands for Bidirectional Encoder Representations from Transformers
* BERT uses <mark style="color:purple;background-color:purple;">**encoder-only**</mark> Transformer architecture
* Unlike GPT, BERT is not autoregressive
* <mark style="color:purple;background-color:purple;">**BERT sees the entire sentence at once during training**</mark>
* <mark style="color:purple;background-color:purple;">**Self-attention in BERT is bidirectional**</mark>
* <mark style="color:purple;background-color:purple;">**Each token can attend to tokens on both left and right**</mark>
* Core idea of BERT:
  * Learn contextual embeddings
  * Meaning of a word depends on surrounding words on both sides
* <mark style="color:purple;background-color:purple;">**Pretraining objective 1: Masked Language Modeling (MLM)**</mark>
  * <mark style="color:purple;background-color:purple;">**Randomly mask some tokens in a sentence**</mark>
  * <mark style="color:purple;background-color:purple;">**Model predicts the masked tokens**</mark>
  * Example: `I want a [MASK]` → predict `chocolate`
* MLM forces the model to:
  * Use both left and right context
  * <mark style="color:purple;background-color:purple;">**Learn deep language understanding**</mark>
* <mark style="color:purple;background-color:purple;">**Pretraining objective 2: Next Sentence Prediction (NSP) (original BERT)**</mark>
  * <mark style="color:purple;background-color:purple;">**Given two sentences, predict if sentence B follows sentence A**</mark>
  * <mark style="color:purple;background-color:purple;">**Helps with sentence-pair understanding tasks**</mark>
* Input format in BERT:
  * <mark style="color:purple;background-color:purple;">**Special token**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**`[CLS]`**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**added at start**</mark>
  * <mark style="color:purple;background-color:purple;">**Special token**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**`[SEP]`**</mark><mark style="color:purple;background-color:purple;">**&#x20;**</mark><mark style="color:purple;background-color:purple;">**separates sentences**</mark>
  * Positional embeddings added
* Output of BERT:
  * Contextual embedding for every token
  * `[CLS]` token embedding represents the whole sentence
* Fine-tuning BERT:
  * Same pretrained BERT is reused
  * <mark style="color:purple;background-color:purple;">**Add a small task-specific head on top**</mark>
  * <mark style="color:purple;background-color:purple;">**Entire model weights are updated**</mark>
* For classification tasks:
  * Use `[CLS]` embedding
  * <mark style="color:purple;background-color:purple;">**Add a linear layer for labels**</mark>
* For NER:
  * Use embeddings of each token
  * <mark style="color:purple;background-color:purple;">**Predict label per token**</mark>
* For QA (extractive):
  * Predict start and end positions of answer span
* Important limitation:
  * BERT does not generate text
  * It only understands and classifies text
* Comparison intuition:
  * <mark style="color:purple;background-color:purple;">**GPT = generate next word**</mark>
  * <mark style="color:purple;background-color:purple;">**BERT = understand the whole sentence**</mark>
* When to use BERT:
  * Classification
  * NER
  * Search and ranking
  * Extractive QA
* When not to use BERT:
  * Free-form text generation
  * Long-form responses
* Key takeaway:
  * BERT is optimized for language understanding
  * GPT is optimized for language generation
