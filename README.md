# CLaRa Extension: End-to-End RAG with Implicit Knowledge Graph

This repository documents my understanding of the CLaRa framework and the concepts underlying my dissertation project, which aims to extend CLaRa with a differentiable temporal link matrix over retrieved chunks to model multi-hop reasoning.

The notes are written as I work through the paper and codebase. 

---

## Project Goal

CLaRa (Continuous Latent Reasoning) is an end-to-end RAG framework developed by Apple that unifies document compression, retrieval, and generation into a single differentiable pipeline. While it achieves strong performance on standard QA benchmarks, there are areas, one of which is multi-hop reasoning, that appear to be potential limitations worth exploring.

The broader direction of this project is to investigate those limitations and explore whether introducing additional structure over retrieved document embeddings could address them.

## Structure

```
clara-concepts/
├── README.md
└── concepts/
    ├── 00_intro_to_clara.md
    ├── 01_rag_basics.md
    ├── 02_clara_rag_problems.md
    ├── 03_lora_adapters.md
    ├── ...

```

---

## References

- CLaRa paper: https://arxiv.org/abs/2511.18659
- CLaRa codebase: https://github.com/apple/ml-clara