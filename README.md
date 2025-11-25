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
  - [Understanding Reuse, Performance, and Hardware Cost of DNN Dataflows: A Data-Centric Approach](https://dl.acm.org/doi/abs/10.1145/3352460.3358252)** — Kwon, Hyoukjun and Chatarasi, Prasanth and Pellauer, Michael and Parashar, Angshuman and Sarkar, Vivek and Krishna, Tushar, GeorgiaTech, Georgia, *MICRO'2019*. *(15 pages)*  <details close>
        <summary><b> Supplementary Analyses and Insights  </b></summary>
          This work summarizes a design philosophy for DNN-oriented accelerators. In fact, most NPUs share largely similar architectural principles, which allows them to be captured using a unified abstraction. As a result, a common mapping representation can be used to express how any DNN layer is mapped onto arbitrary hardware. Therefore, the authors first propose a data-centric representation for mapping convolution operators to hardware.
          The difficulty does not lie in the implementation itself, but rather in the conceptual insight behind it.
          With this representation, data reuse can be analyzed more effectively.
      </details>

  - [Timeloop: A systematic approach to dnn accelerator evaluation](https://ieeexplore.ieee.org/abstract/document/10970753)** — Angshuman Parashar, *et al.*, NVIDIA, *2019 IEEE international symposium on performance analysis of systems and software (ISPASS)*. *(12 pages)* 

  - [How to Keep Pushing ML Accelerator Performance? Know Your Rooflines!](https://ieeexplore.ieee.org/abstract/document/10970753)** — Marian Verhelst *et al.*, KU Leuven, Leuven, Belgium, *JSSC'2025*. *(18 pages)*  <details close>
        <summary><b> Supplementary Analyses and Insights  </b></summary>
          A new roofline model for ML accelerators.
      </details>



#### Dataflow Optimization
  - [Principle based Dataflow Optimization for Communication lower bound in operator-fused tensor Acceler](https://ieeexplore.ieee.org/document/11132765)** — Xu, Lei *et al.*, SJTU, *IEEE/ACM DAC 62nd 2025*. *(7 pages)*
---

# AI Accelerators

#### Architecture of AI Accelerators
  - [Eyeriss: An energy-efficient reconfigurable accelerator for deep convolutional neural networks](https://ieeexplore.ieee.org/abstract/document/7738524/)**  — Yu-Hsin Chen, Tien-Ju Yang, Joel Emer, Vivienne Sze, MIT, *JSSC 2017*. (~12 pages)  <details close> 
      <summary><b>Supplementary Analyses and Insights</b></summary> 
        Introduced the **row-stationary (RS) dataflow** for CNNs that optimizes data-movement and reuse in a spatial PE array. Developed a fabricated accelerator with 168 PEs and a reconfigurable multicast on-chip network to minimize DRAM access. 
    </details>
  
  - Google TPU: [Ten Lessons From Three Generations Shaped Google’s TPUv4i : Industrial Product](https://ieeexplore.ieee.org/abstract/document/9499913)**  — Norman P. Jouppi, David Patternson, et al., *ISCA 2021*. (~14 pages)   <details close> 
      <summary><b>Supplementary Analyses and Insights</b></summary> 
        Since 2015, Google has deployed multiple generations of TPUs, which have taught us several lessons that changed our perspective:
        1 semiconductor technology advances unevenly;
        2 compiler compatibility matters more than binary compatibility, especially for VLIW domain-specific architectures (DSAs);
        3 the target total cost of ownership outweighs initial cost;
        4 support for multi-tenancy is essential;
        5 deep neural networks (DNNs) grow at a rate of 1.5× per year;
        6 the evolution of DNNs continuously shifts workloads;
        7 some inference tasks still require floating-point computation;
        8 inference DSAs require air cooling;
        9 applications are constrained by latency rather than batch size;
        10 backward ML compatibility enables rapid deployment of DNNs.
        These lessons have shaped TPUv4i, an inference DSA that has been deployed since 2020.
    </details>
  
  - Google TPU: [Ten Lessons From Three Generations Shaped Google’s TPUv4i : Industrial Product](https://ieeexplore.ieee.org/abstract/document/9499913)**  — Genc, Hasan, David Patternson, et al., *ISCA 2021*. (~14 pages)  <details close> 
        <summary><b>Supplementary Analyses and Insights</b></summary> 
          Open-sourced as part of the Chipyard project and implemented in Chisel. 
          Supports FP32/FP16/FP8, BF16, and Int32/Int16/Int8, with both WS and OS dataflows.
          Features a size-configurable systolic array with an integrated accumulator.
      </details>


#### FPGA Overlay
  - [FlightVGM: Efficient Video Generation Model Inference with Online Sparsification and Hybrid Precision on FPGAs](https://dl.acm.org/doi/10.1145/3706628.3708864)** — Liu, Jun *et al.*, SJTU, *IEEE FPGA'2025*, **Best Paper**. *(23 pages)*
      <details close>
        <summary><b>Key Insights and Interpretation </b></summary>

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
          The authors note that “the tile size and the loop order together result in the best performance. To the best of our knowledge, there does not exist any work that identifies the best-performing tile size and loop order together for nested loops.” \\
          These findings are consistent with our observations from loop transformations for our own accelerator, as traditional ILP-based polyhedral transformations (e.g., Pluto) may fail to discover architecture-specific optimal transformations — especially when loop interactions and cache behaviors are non-trivial. \\
          Their SVM-based hierarchical classifier learns performance patterns of tiled loops on Intel Xeon Cascade Lake and Xeon Phi (KNL), achieving results within 9–18% of the optimal execution time.
        </details>

    [Loop interchange and tiling for multi-dimensional loops to minimize write operations on NVMs](https://www.sciencedirect.com/science/article/pii/S1383762122002843)** — Rui Xu *et al.*, East China Normal University, *Journal of Systems Architecture (JSA'2022)*. *(13 pages)*

#  📑 HLS