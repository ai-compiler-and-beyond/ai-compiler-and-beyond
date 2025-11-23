# 🧠 AI-Compiler-and-Beyond (Knowledge Sharing)
Focusing on key AI compiler papers from academia and industry, covering related areas such as AI accelerators, code optimization, and high-level synthesis, etc.

Additional analyses and insights from the paper are summarized and provided in the expandable supplementary section below.

<details close>
  <summary><b>Supplementary Analyses and Insights</b></summary>

  (content here)
</details>


#  Table of Contents
<!-- - [Papers](#papers)
  - [Survey](#survey) -->
- [AI Compiler](#ai-compiler)
  - [Modeling](#performance-modeling)
  - [Dataflow Optimization](#dataflow-optimization)

- [AI Accelerators](#ai-accelerators)
  - [Architecture](#architecture-of-ai-accelerators)
  - [FPGA Overlay](#fpga-overlay)

- [Code Optimization](#code-optimization)
  - [Loop Transform](#loop-transform)
---

#  AI Compiler
#### Performance Modeling
  - [How to Keep Pushing ML Accelerator Performance? Know Your Rooflines!](https://ieeexplore.ieee.org/abstract/document/10970753)** — Marian Verhelst *et al.*, KU Leuven, Leuven, Belgium, *JSSC'2025*. *(18 pages)* <details close>
      <summary><b> Key Insights and Interpretation  </b></summary>
      A new roofline model for ML accelerators.
    </details>
  maestro

#### Dataflow Optimization
  - [Principle based Dataflow Optimization for Communication lower bound in operator-fused tensor Acceler](https://ieeexplore.ieee.org/document/11132765)** — Xu, Lei *et al.*, SJTU, *IEEE/ACM DAC 62nd 2025*. *(7 pages)*
  - timeloop todo
---

# AI Accelerators

#### Architecture of AI Accelerators
  - [Eyeriss: An energy-efficient reconfigurable accelerator for deep convolutional neural networks](https://ieeexplore.ieee.org/abstract/document/7738524/)**  — Yu-Hsin Chen, Tien-Ju Yang, Joel Emer, Vivienne Sze, MIT, *JSSC 2017*. (~12 pages) 
  <details close> 
  <summary><b>Key Insights and Interpretation</b></summary> 
    Introduced the **row-stationary (RS) dataflow** for CNNs that optimizes data-movement and reuse in a spatial PE array. Developed a fabricated accelerator with 168 PEs and a reconfigurable multicast on-chip network to minimize DRAM access. 
  </details>
TPU
Gemmini

#### FPGA Overlay
  - [FlightVGM: Efficient Video Generation Model Inference with Online Sparsification and Hybrid Precision on FPGAs](https://dl.acm.org/doi/10.1145/3706628.3708864)** — Liu, Jun *et al.*, SJTU, *IEEE FPGA'2025*, **Best Paper**. *(23 pages)*
    <details close>
      <summary><b> Key Insights and Interpretation </b></summary>
      A Chinese Interpretation by Mion Lou is released in [Zhihu](https://zhuanlan.zhihu.com/p/1966485760665456986)**.

      An extension work from the same authors on FlightLLM(FPGA'2024). Two impressive aspects: 
      
      1 online activation sparsity along temporal dimension for VGM.
      
      2 an extension to the FPGA DSP block, to support 4 int8 mac or 2 float16 mac, with DSP and lut resource sharing.  
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

    [Loop interchange and tiling for multi-dimensional loops to minimize write operations on NVMs](https://www.sciencedirect.com/science/article/pii/S1383762122002843)** — Rui Xu *et al.*, East China Normal University, *Journal of Systems Architecture (JSA'2022)*. *(13 pages)*
    <!-- <details close>
      <summary><b>Key Insights</b></summary>
        
  
    </details> -->

##  📑 HLS