## Why Multi Hop can be a Limitation?

One potential limitation of the CLaRa paper may be a difficulty to perform well on the multi-hop reasoning tasks, because it is being skipped in the training process. The continuous backpropagation through the whole of the system, including compressor, retriever, and generator, is just based only on the final answer, without explicit supervision of intermediate reasoning steps.

However, multi-hop reasoning requires a structured sequence of reasoning steps, where different pieces of information must be retrieved and combined in a specific order. In many cases, answering a question involves chaining together multiple interdependent facts, where each step informs the next retrieval decision.

CLaRa performs retrieval in a single top-k step based on embedding similarity, and relies on implicit reasoning encoded in continuous representations. This means that the model does not explicitly learn how to decompose a query into sequential retrieval steps or how to iteratively refine its search process.

The use of compressed representations may lead to the loss of structural or relational information between facts, which could further limit the model’s ability to perform compositional reasoning.

As a result, the model may struggle in scenarios where reasoning requires multi-step exploration of information, especially when intermediate facts are necessary to guide further retrieval.