# Non-Archimedean Neural Architectures: Foundations of p-adic Deep Learning

[![Current Stage: Prototyping](https://img.shields.io/badge/Stage-Prototyping-orange)](#roadmap)

This project explores fundamental changes in neural network weights: transitioning from the real numbers to p-adic.

## The Motivation: Why p-adic?
Standard Deep Learning models suffer from hierarchical distortion. Attempting to embed exponentially growing tree structures (language, taxonomies, file systems) into the flat Euclidean space forces the model to learn noisy approximations. 

The p-adic space is naturally tree-structured. By leveraging ultrametric properties, we aim to build models that are "hierarchy-aware" by design, leading to zero-distortion embeddings and superior taxonomic reasoning.

---

## Validated Hypothesis: "Prefix-Alignment"
Recent experiments in this repository (Python-based POC) have confirmed a unique property of p-adic optimization using Zeroth-Order methods.

### Experimental Evidence:
In a high-dimensional search space ($2^{15556}$), a standard MeZO-like optimizer was able to exactly find a target $p$-adic weight in just ~140,000 steps for a 36-bit number.

*Key Insight:* Unlike Euclidean optimization, which "slides" toward a minimum, p-adic optimization performs *Prefix-Alignment*. It sequentially locks in digits from least significant to most significant (root to leaf). 
* Even with noisy multi-bit perturbations, the $p$-adic metric acts as a natural regularizer, focusing the optimizer on the core "branch" before refining the "leaves."

---

## Roadmap

### Phase 1: Theoretical Foundations (Current)
- [x] Comprehensive review of SOTA papers:
  - *v-PuNNs* (Gnankan Landry Regis N'guessan).
  - *p-Adic Polynomial Regression* (Zubarev, 2025).
  - *Learning with the p-adics* (Martins, 2025).
- [ ] Networking with the Number Theory community.

### Phase 2: Python Prototyping (Ongoing)
- [x] Implementation of core arithmetic in p-adic.
- [ ] Validation of Zeroth-Order optimization on "toy" tasks.
- [ ] Implementation of Ultrametric Loss.

### Phase 3: High-Performance GPU Engine (Upcoming)
- [ ] Developing Triton GPU Kernels for vectorized p-adic MatMul.
- [ ] Optimizing shared memory usage to support large-scale $p$-adic layers.
- [ ] Benchmark: CPU-based v-PuNNs vs. our GPU-accelerated implementation.

### Phase 4: Comparative Benchmark of SOTA Optimizers
- [ ] Implementing a suite of ZO-optimizers: MeZO, LOZO, TeZO, and VAPO.
- [ ] Evaluation on hierarchical datasets: WordNet nouns, Gene Ontology, and NCBI Mammalia.

### Phase 5: Scientific Novelty & AI Foundations
- [ ] Hybrid Optimizer.
- [ ] Dynamic Depth.

### Phase 6: Application to LLMs
- [ ] Replacing the Embedding Layer of a small-scale LLM (e.g., TinyLlama) with p-adic spaces.
- [ ] Evaluating zero-shot generalization on taxonomic reasoning tasks.

---

## Related Literature & Key References
- **Gnankan Landry Regis N’guessan (2026)**: *v-PuNNs: van der Put Neural Networks for Transparent Ultrametric Representation Learning*.
- **André F. T. Martins (2025)**: *Learning with the p-adics*.
- **A. P. Zubarev (2025)**: *p-Adic Polynomial Regression as Alternative to Neural Network  for Approximating p-Adic Functions of Many
Variables*.
- **W. A. Zúñiga-Galindo (2026)**: *Critical Organization of Deep Neural Networks and p-adic Statistical Field Theories*.
- **Andrei Khrennikov, Brunello Tirozzi (1999)**: *Learning of p-adic neural networks*.


---

## Tech Stack
- **Languages:** Python, Triton
- **Frameworks:** PyTorch
- **Concepts:** Number Theory, Zeroth-Order Optimization.

---
*Independent Research Project | Moscow, 2026*
