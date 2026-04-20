# CLaRa Extension: End-to-End RAG with Implicit Knowledge Graph

This repository documents my understanding of the CLaRa framework and the concepts underlying my dissertation project, which aims to extend CLaRa with a differentiable temporal link matrix over retrieved chunks to model multi-hop reasoning.

The notes are written as I work through the paper and codebase. 

---

## Project Goal

CLaRa (Continuous Latent Reasoning) is an end-to-end RAG framework developed by Apple that unifies document compression, retrieval, and generation into a single differentiable pipeline. While it achieves strong performance on standard QA benchmarks, there are areas, one of which is multi-hop reasoning, that appear to be potential limitations worth exploring.

The broader direction of this project is to investigate those limitations and explore whether introducing additional structure over retrieved document embeddings could address them. 
---

## Reading Order

The concepts below are best read in order, as each one motivates the next.

1. [Introduction to CLaRa](concepts/00_intro_to_clara.md)
2. [RAG Basics](concepts/01_rag_basics.md)
3. [Document Compression](concepts/02_document_compression.md)
4. [LoRA Adapters](concepts/03_lora_adapters.md)
5. [CLaRa Training](concepts/04_clara_training.md)
6. [Multi-Hop Reasoning](concepts/05_multi_hop_reasoning.md)
7. [Knowledge Graphs](concepts/06_knowledge_graphs.md)

---

## References

- CLaRa paper: https://arxiv.org/abs/2511.18659
- CLaRa codebase: https://github.com/apple/ml-clara