# 🟢 How is BART Trained

* BART stands for Bidirectional and Auto-Regressive Transformers
* BART uses an <mark style="color:purple;background-color:purple;">**encoder–decoder Transformer**</mark> architecture
* The encoder is bidirectional
* The decoder is autoregressive with causal masking
* BART combines ideas from:
  * BERT (strong bidirectional understanding)
  * GPT (strong text generation)
* BART is pretrained as a denoising autoencoder
* <mark style="color:purple;background-color:purple;">**During pretraining, noise is added only to the encoder input**</mark>
* <mark style="color:purple;background-color:purple;">**The decoder target is always the original clean text**</mark>
* Common noise types used in pretraining:
  * Token masking
  * Token deletion
  * Token replacement
  * Text span infilling
  * Sentence permutation
* Example pretraining setup:
  * Original text: `I want a chocolate`
  * Corrupted encoder input: `I want [MASK]`
  * Decoder target: `I want a chocolate`
* Encoder reads the corrupted text using bidirectional attention
* Decoder generates the original text token by token
* Decoder uses:
  * Causal self-attention
  * Cross-attention over encoder outputs
* Training objective during pretraining:
  * Next-token prediction on the decoder
  * Cross-entropy loss on all output tokens
* No task-specific labels are used during pretraining
* Fine-tuning does not use noise
* <mark style="color:purple;background-color:purple;">**Fine-tuning uses clean, task-specific input–output pairs**</mark>
* Encoder receives the task input
* Decoder receives the desired output sequence
* <mark style="color:purple;background-color:purple;">**Example fine-tuning for summarization:**</mark>
  * <mark style="color:purple;background-color:purple;">**Encoder input: document**</mark>
  * <mark style="color:purple;background-color:purple;">**Decoder target: summary**</mark>
* Loss during fine-tuning:
  * Cross-entropy on decoder output tokens
* During fine-tuning:
  * Encoder weights change
  * Decoder weights change
  * Cross-attention weights change
* Same pretrained BART is reused for all tasks
* <mark style="color:purple;background-color:purple;">**Typically, a separate fine-tuned BART checkpoint is created per task**</mark>
* Multi-task fine-tuning is possible by mixing tasks with instructions
* BART is strong for:
  * Abstractive summarization
  * Abstractive QA
  * Paraphrasing
  * Text rewriting
* BART is less favored today because:
  * <mark style="color:purple;background-color:purple;">**Encoder–decoder models are slower**</mark>
  * Decoder-only models scale better
  * GPT-style models cover the same tasks via prompting
* Important clarification:
  * BART did not technically fail
  * It was outcompeted by simpler, more scalable architectures
* Key takeaway:
  * BART = bidirectional understanding + autoregressive generation
