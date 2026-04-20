## How CLaRa Addresses RAG's Problems

CLaRa addresses both of RAG's core problems through a single differentiable pipeline that unifies the compressor, retriever, and generator on a single frozen LLM. Rather than feeding raw retrieved text to the generator, CLaRa compresses each document into a small set of continuous vector representations called **memory tokens**, living in the same latent space as the query and generator inputs.

Three modules handle this: a **compressor**, a **query reasoner**, and a **generator**, all 
implemented as lightweight LoRA adapters on the same frozen base LLM. The compressor encodes documents into memory tokens, the query reasoner encodes the input query into the same space, and the generator produces the final answer from the top-k retrieved compressed documents.

Critically, all three are trained end-to-end through a single language modelling loss. This closes 
the disjoint optimisation gap as the query reasoner receives gradient signal from the generator, 
so it learns to retrieve documents that maximise answer quality rather than just embedding similarity.