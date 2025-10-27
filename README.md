# 🧠 AI-Compiler-and-Beyond
Focusing on key AI compiler papers from academia and industry, covering related areas such as AI accelerators, code optimization, and high-level synthesis, etc.

Some additional paper analyses contributed by our team are provided as supplementary materials(mostly in Chinese).

##  Table of Contents
<!-- - [Papers](#papers)
  - [Survey](#survey) -->
- [AI Compiler](#ai-compiler)
  - [Dataflow Optimization](#dataflow-optimization)

- [AI Accelerators](#ai-accelerators)
  - [FPGA Overlay](#fpga-overlay)

- [Code Optimization](#code-optimization)
  - [Loop Transform](#loop-transform)
---

#  AI Compiler

#### Dataflow Optimization
  - [Principle based Dataflow Optimization for Communication lower bound in operator-fused tensor Acceler](https://ieeexplore.ieee.org/document/11132765)** — Xu, Lei *et al.*, SJTU, *IEEE/ACM DAC 62nd 2025*. *(7 pages)*

---
# AI Accelerators

#### FPGA Overlay
  - [FlightVGM: Efficient Video Generation Model Inference with Online Sparsification and Hybrid Precision on FPGAs](https://dl.acm.org/doi/10.1145/3706628.3708864)** — Liu, Jun *et al.*, SJTU, *IEEE FPGA'2025*, **Best Paper**. *(23 pages)*
    <details close>
      <summary><b> Key Insights and Interpretation </b></summary>
      balabalablbabablablablabla
    </details>

---
# Code Optimization
#### Loop Transform
  - Loop tile and reordering: 
    [Tile Size and Loop Order Selection using Machine Learning for Multi-/Many-Core Architectures](https://dl.acm.org/doi/abs/10.1145/3650200.3656630)** — Shilpa Babalad *et al.*, Indian Institute of Science, *ACM International Conference on Supercomputing (ICS'2024)*. *(12 pages)*
    <details close>
      <summary><b>Key Insights</b></summary>
        
      The authors note that “the tile size and the loop order together result in the best performance. To the best of our knowledge, there does not exist any work that identifies the best-performing tile size and loop order together for nested loops.”

      These findings are consistent with our observations from loop transformations for our own accelerator, as traditional ILP-based polyhedral transformations (e.g., Pluto) may fail to discover architecture-specific optimal transformations — especially when loop interactions and cache behaviors are non-trivial.

      Their SVM-based hierarchical classifier learns performance patterns of tiled loops on Intel Xeon Cascade Lake and Xeon Phi (KNL), achieving results within 9–18% of the optimal execution time.
    </details>

##  📑 HLS