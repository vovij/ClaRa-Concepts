## LoRA Adapters

Before describing how CLaRa trains its components, it helps to understand LoRA (Low-Rank Adaptation), since all three trainable modules in CLaRa are implemented as LoRA adapters on a single frozen base LLM.

The motivation for LoRA comes from a simple observation: When fine-tuning a large pretrained model, the weight updates tend to have **low intrinsic rank**, meaning the change in the weight matrix can be well-approximated by a much lower-dimensional structure. Full fine-tuning updates every parameter in $W \in \mathbb{R}^{d \times k}$, which is very expensive for models with billions of parameters. 

Rather than learning $\Delta W$ directly, LoRA decomposes the update into two low-rank matrices: $$W' = W + \Delta W = W + BA$$ where $W$ is the **frozen** pretrained weight matrix, $B$ and $A$ are the learned adapter matrices, and $r$ is the chosen rank (kept very small e.g. $r = 16$ in CLaRa's config). Only $A$ and $B$ are trained; $W$ is never updated. The forward pass becomes: $$h = Wx + BAx$$

In practice this means you can adapt a 7B parameter model for a specific task by training only a few million parameters. This is particularly useful when you need multiple specialised behaviours from the same base model — each behaviour can be its own LoRA adapter, and you switch between them at inference time by activating the relevant adapter. That's what CLaRa does for compressor, query reasoner and a generator.