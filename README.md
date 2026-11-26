<h1 align="center">Matrix Multiplication and the Complexity of Attention</h1>

<p align="center">
  <strong>Tao Jiang</strong><sup>*</sup> and <strong>Minbo Gao</strong><sup>*</sup><br>
  <em>* Equal contribution (co-first authors).</em>
</p>

<p align="center">
  Institute of Software, Chinese Academy of Sciences<br>
  School of Computer Science and Technology, University of Chinese Academy of Sciences<br>
  <a href="mailto:jiangt@ios.ac.cn" aria-label="Email Tao Jiang">jiangt@ios.ac.cn</a> ·
  <a href="mailto:gaomb@ios.ac.cn" aria-label="Email Minbo Gao">gaomb@ios.ac.cn</a>
</p>

<p align="center">
  <a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/"><strong>Paper website</strong></a> ·
  <a href="#paper-index"><strong>Paper index</strong></a>
</p>

---

A standard attention algorithm forms the query–key score matrix and uses it to compute a weighted sum for each query. Our starting question is whether computing those sums can be asymptotically cheaper than forming the scores.

## Paper index

Click a title for the full abstract or a thumbnail for the figure and its caption.

### Attention

| Paper and abstract | Main result | PDF and citation |
| --- | --- | :---: |
| **[Higher-order attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/strassen-and-tensor-attention/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/strassen-and-tensor-attention/#paper-figure"><img src="./preprints/strassen-and-tensor-attention/figure.png" width="128" alt="Tensor-attention size exponent versus width exponent"></a> | Matches the matrix multiplication exponent for Strassen attention and gives a faster algorithm for tensor attention. | [PDF](./preprints/strassen-and-tensor-attention/paper.pdf) · [BibTeX](./preprints/strassen-and-tensor-attention/README.md#citation) |
| **[Polynomial attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-polynomial-attention/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-polynomial-attention/#paper-figure"><img src="./preprints/exact-polynomial-attention/figure.png" width="128" alt="Arithmetic exponent bounds for degree-four and degree-eight polynomial attention"></a> | Determines the exact exponent for quadratic attention and gives degree-dependent lower bounds for higher even degrees. | [PDF](./preprints/exact-polynomial-attention/paper.pdf) · [BibTeX](./preprints/exact-polynomial-attention/README.md#citation) |
| **[Preprocessed softmax attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/preprocessed-softmax-attention/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/preprocessed-softmax-attention/#paper-figure"><img src="./preprints/preprocessed-softmax-attention/figure.png" width="128" alt="Arithmetic exponents versus query batch size for three key widths"></a> | Obtains a generic matrix multiplication lower bound even after arbitrary preprocessing of the key–value cache. | [PDF](./preprints/preprocessed-softmax-attention/paper.pdf) · [BibTeX](./preprints/preprocessed-softmax-attention/README.md#citation) |
| **[Exact Transformer cache updates](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-transformer-cache-updates/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-transformer-cache-updates/#paper-figure"><img src="./preprints/exact-transformer-cache-updates/figure.png" width="128" alt="Exact cache-update exponents versus width for one, two, and at least three layers"></a> | At width proportional to sequence length, one edit can make a three-layer attention-only Transformer cache as costly to update exactly as to recompute. | [PDF](./preprints/exact-transformer-cache-updates/paper.pdf) · [BibTeX](./preprints/exact-transformer-cache-updates/README.md#citation) |
| **[Attention backpropagation](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/memory-recomputation-attention/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/memory-recomputation-attention/#paper-figure"><img src="./preprints/memory-recomputation-attention/figure.png" width="128" alt="Backward-pass exponent versus the number of unstored score differences"></a> | Determines the optimal work exponent for computing value gradients as a function of the forward-pass storage budget. | [PDF](./preprints/memory-recomputation-attention/paper.pdf) · [BibTeX](./preprints/memory-recomputation-attention/README.md#citation) |
| **[Attention I/O complexity](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/unrestricted-attention-io/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/unrestricted-attention-io/#paper-figure"><img src="./preprints/unrestricted-attention-io/figure.png" width="128" alt="I/O exponents versus fast-memory size at square and smaller widths"></a> | Gives matching square-width I/O exponents, conditional on results from a matrix multiplication preprint. | [PDF](./preprints/unrestricted-attention-io/paper.pdf) · [BibTeX](./preprints/unrestricted-attention-io/README.md#citation) |
| **[Arbitrarily accurate softmax attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/#paper-figure"><img src="./preprints/arbitrarily-accurate-softmax-attention/figure.png" width="128" alt="Query and key matrices used as marker inputs in the lower-bound proof"></a> | Recovers the rectangular matrix multiplication exponent when a bounded-size circuit family can achieve every positive error tolerance. | [PDF](./preprints/arbitrarily-accurate-softmax-attention/paper.pdf) · [BibTeX](./preprints/arbitrarily-accurate-softmax-attention/README.md#citation) |

### Related computations

| Paper and abstract | Main result | PDF and citation |
| --- | --- | :---: |
| **[Batched Top-1 prediction](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-batched-top1/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-batched-top1/#paper-figure"><img src="./preprints/exact-batched-top1/figure.png" width="128" alt="Arithmetic and comparison bounds as query width changes"></a> | Matches the matrix multiplication exponent at square width, even though the output contains only the winning indices. | [PDF](./preprints/exact-batched-top1/paper.pdf) · [BibTeX](./preprints/exact-batched-top1/README.md#citation) |
| **[Exact delta-rule computation](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/#paper-figure"><img src="./assets/delta-rule-work-depth.png" width="128" alt="Work exponent versus depth exponent for exact delta-rule computation"></a> | Gives parallel work bounds conditional on claimed matrix multiplication exponents and an unconditional reduction from triangular substitution. | [PDF](./preprints/delta-rule-work-depth/paper.pdf) · [BibTeX](./preprints/delta-rule-work-depth/README.md#citation) |
| **[Deterministic matrix product verification](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/deterministic-matrix-product-verification/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/deterministic-matrix-product-verification/#paper-figure"><img src="./preprints/deterministic-matrix-product-verification/figure.png" width="128" alt="Residual potential before and after a linear tilt"></a> | Shows that verifying a claimed real matrix product has the same arithmetic exponent as computing it. | [PDF](./preprints/deterministic-matrix-product-verification/paper.pdf) · [BibTeX](./preprints/deterministic-matrix-product-verification/README.md#citation) |
| **[Exact per-example gradient clipping](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-per-example-gradient-clipping/)**<br><a href="https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-per-example-gradient-clipping/#paper-figure"><img src="./preprints/exact-per-example-gradient-clipping/figure.png" width="128" alt="Overhead exponent for exact gradient clipping as token and batch exponents vary"></a> | Determines the arithmetic cost of exact clipped aggregation from one batched matrix product and a family of independent per-example products. | [PDF](./preprints/exact-per-example-gradient-clipping/paper.pdf) · [BibTeX](./preprints/exact-per-example-gradient-clipping/README.md#citation) |

## Research background

The anonymous manuscript [*Exact Softmax Attention Has the Rectangular Matrix-Multiplication Exponent in Extended Arithmetic Circuits*](https://openreview.net/forum?id=uZLZCV3OA6) (2026) proves the lower bound even when each key has a single scalar value. Its exp–log span theorem is used in the analysis of attention I/O in this collection.

Some bounds use results from the [OpenAI square-exponent preprint](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md) and the [accompanying square and rectangular exponent results](https://github.com/openai/math/blob/main/lean/docs/107.md).
