# 🟢 How is a GPT Trained

* GPT is a <mark style="color:purple;background-color:purple;">**decoder-only**</mark> Transformer trained for next-token prediction
* Pretraining learns general language patterns from unlabeled text ⇒ <mark style="color:purple;background-color:purple;">**Pre training is for language modelling**</mark>
* <mark style="color:purple;background-color:purple;">**So in pre training we will pass a sequence in decoder and output should be the next word**</mark>
* <mark style="color:purple;background-color:purple;">**Fine-tuning adapts GPT to follow instructions using prompt–response data**</mark>
* Example fine-tuning pair: `Q: Do you want a chocolate? A: No I don’t.`
* During fine-tuning, prompt and answer are combined into one sequence: `Q: Do you want a chocolate? A: No I don’t.`
* The entire sequence is passed to the model in one forward pass
* <mark style="color:purple;background-color:purple;">**A causal mask ensures each token can see only past tokens**</mark>&#x20;
* <mark style="color:purple;background-color:purple;">**Loss is calculated only for the response tokens**</mark>
* Loss is not calculated on `Q: Do you want a chocolate? A:`
* Loss is calculated on `No`, `I`, `don’t`, `.`
* The model learns that when it sees `Q: Do you want a chocolate? A:` the correct continuation is `No I don’t.`
* <mark style="color:purple;background-color:purple;">**Model weights are updated slightly using backpropagation**</mark>
* <mark style="color:purple;background-color:purple;">**After supervised fine-tuning, reinforcement learning may be applied**</mark>
* <mark style="color:purple;background-color:purple;">**Reinforcement learning uses ranked responses instead of direct labels**</mark>
* <mark style="color:purple;background-color:purple;">**A reward model learns what humans prefer in an answer**</mark>
* GPT is optimized to maximize the reward score
* Reinforcement learning improves helpfulness, safety, and response quality
* During inference, GPT generates text one token at a time
* One token is generated at a time and appended to the context
* <mark style="color:purple;background-color:purple;">**GPT is best suited for generative and reasoning tasks**</mark>
* <mark style="color:purple;background-color:purple;">**GPT is not ideal for strict, high-throughput classification**</mark>
* Key idea: GPT learns to continue text, and capabilities emerge from this training process
* <mark style="color:purple;background-color:purple;">**We can also fine tune a single gpt for different tasks**</mark>
* <mark style="color:purple;background-color:purple;">**Difference is controlled by the prompt, not the architecture**</mark>
