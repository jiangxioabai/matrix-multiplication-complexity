# When Is Matrix Multiplication Unavoidable?

*Arithmetic Complexity of Attention, Learning, and Verification*

**Tao Jiang**<sup>*</sup> and **Minbo Gao**<sup>*</sup>

\* Equal contribution (co-first authors).

Institute of Software, Chinese Academy of Sciences

School of Computer Science and Technology, University of Chinese Academy of Sciences

[jiangt@ios.ac.cn](mailto:jiangt@ios.ac.cn) · [gaomb@ios.ac.cn](mailto:gaomb@ios.ac.cn)

[Research website](https://jiangxioabai.github.io/matrix-multiplication-complexity/) · [Research map](https://jiangxioabai.github.io/matrix-multiplication-complexity/#research-map) · [Paper index](#paper-index)

Which problems inherit the cost of matrix multiplication without returning the product? When can that cost be avoided?

These papers study exact computation and approximation in attention, prediction, verification, and learning. They trace how the cost changes with the kernel, precision, available information, and resource being counted.

## Paper index

<a id="attention"></a>

### I. Attention Kernels and Precision

How do the scoring kernel and the required precision change the arithmetic cost of attention?

- **[Matrix Multiplication Lower Bounds for Strassen Attention and a Faster Algorithm for Tensor Attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/strassen-and-tensor-attention/)**. In exact real arithmetic circuits with exponential and logarithm gates, normalized Strassen attention has the square matrix multiplication exponent for widths up to the sequence length, including width one. For tensor attention, a crossing identity gives an algorithm whose numerical speedups use the stated rectangular exponent formula.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/strassen-and-tensor-attention/) · [PDF](./preprints/strassen-and-tensor-attention/paper.pdf) · [BibTeX](./preprints/strassen-and-tensor-attention/README.md#citation)
- **[The Arithmetic Complexity of Exact Polynomial Attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-polynomial-attention/)**. For exact normalized quadratic Taylor attention at width $d=N^a$ with fixed 0 < a ≤ 1, the arithmetic exponent is $\omega(1,a,a)$, even with exponential and logarithm gates. For higher fixed even Taylor degrees, polynomial selectors give degree-dependent lower bounds.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-polynomial-attention/) · [PDF](./preprints/exact-polynomial-attention/paper.pdf) · [BibTeX](./preprints/exact-polynomial-attention/README.md#citation)
- **[The Arithmetic Cost of Precision in One-Channel Softmax Attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/)**. For one-channel softmax on the full coordinate cube with unscaled scores, square-width extended arithmetic circuits have exponent two when the worst-case absolute error stays below a fixed constant less than one and the number of accuracy bits is subpolynomial. The square matrix multiplication exponent is recovered at an explicitly doubly exponentially small error. The intervening complexity remains open.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/) · [PDF](./preprints/arbitrarily-accurate-softmax-attention/paper.pdf) · [BibTeX](./preprints/arbitrarily-accurate-softmax-attention/README.md#citation)

### II. Computational Resource Tradeoffs

What can be saved by preparing data in advance, keeping intermediate values, or moving fewer words?

- **[Preprocessed Softmax Attention Is as Hard as Matrix Multiplication](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/preprocessed-softmax-attention/)**. Even with unrestricted cache preprocessing, exact real arithmetic circuits with exponential and logarithm gates require $\Theta(Nd)$ work for one query, for almost every key matrix and every nonconstant scalar value vector. At fixed power-law batch sizes and widths, the batched exponent is the corresponding rectangular matrix multiplication exponent. Sequential online queries pay the single-query cost in each round.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/preprocessed-softmax-attention/) · [PDF](./preprints/preprocessed-softmax-attention/paper.pdf) · [BibTeX](./preprints/preprocessed-softmax-attention/README.md#citation)
- **[Exact Transformer Cache Updates Are as Hard as Matrix Multiplication](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-transformer-cache-updates/)**. For causal attention-only Transformers, even after arbitrary preprocessing of context and weights, one scalar edit can make an exact cache update in extended arithmetic circuits cost the square matrix multiplication exponent at three layers and width proportional to sequence length. At square width, one or two layers admit quadratic work for one edit.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-transformer-cache-updates/) · [PDF](./preprints/exact-transformer-cache-updates/paper.pdf) · [BibTeX](./preprints/exact-transformer-cache-updates/README.md#citation)
- **[Memory–Recomputation Tradeoffs for Exact Attention Backpropagation](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/memory-recomputation-attention/)**. Determines the backward exponent for the exact value gradient in circuits with arithmetic, exponential, and logarithm gates, when an uncharged forward circuit stores at most M reals from the queries and keys. At width $d=N^a$, if the budget leaves a deficit $N(N-1)-M=N^{2b+o(1)}$ relative to storing every independent score difference, the work exponent is $\max\{2,\omega(b,a,b)\}$. Recomputing a square block attains this exponent.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/memory-recomputation-attention/) · [PDF](./preprints/memory-recomputation-attention/paper.pdf) · [BibTeX](./preprints/memory-recomputation-attention/README.md#citation)
- **[On the Unrestricted I/O Complexity of Exact Softmax Attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/unrestricted-attention-io/)**. For one-channel exact softmax at square width, fixed read/write schedules with unrestricted recomputation have a lower bound of $\Omega(N^2+N^{9/4}/M^{1/8})$ word transfers, where M is the fast-memory size and is at most on the order of the square of the sequence length. A blocked algorithm matches it up to subpolynomial factors when memory grows as a fixed power of the sequence length. The lower bound uses a tensor inequality derived from OpenAI's spectral theory, and the upper bound uses the reported rectangular exponents.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/unrestricted-attention-io/) · [PDF](./preprints/unrestricted-attention-io/paper.pdf) · [BibTeX](./preprints/unrestricted-attention-io/README.md#citation)

<a id="related-computations"></a>

### III. Prediction and Verification

Can returning only an index, a scalar, or a yes/no answer avoid the cost of the underlying product?

- **[Exact Batched Top-1 Prediction Is as Hard as Matrix Multiplication](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-batched-top1/)**. With as many queries and candidates as coordinates, deterministic exact arithmetic comparison trees need the square matrix multiplication exponent to return only the least maximizing index for each query. At smaller fixed-polynomial widths the paper gives separate upper and lower bounds.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-batched-top1/) · [PDF](./preprints/exact-batched-top1/paper.pdf) · [BibTeX](./preprints/exact-batched-top1/README.md#citation)
- **[A Single Ridge Regression Prediction Is as Hard as Matrix Multiplication](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-ridge-prediction/)**. A single exact ridge prediction from a design with N rows and width $d=N^a$ for fixed 0 < a ≤ 1 has exponent $\omega(a,1,a)$. The matching lower bound applies to real arithmetic circuits even with exponential and logarithm gates.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-ridge-prediction/) · [PDF](./preprints/exact-ridge-prediction/paper.pdf) · [BibTeX](./preprints/exact-ridge-prediction/README.md#citation)
- **[Deterministic Verification of Real Matrix Products Is as Hard as Multiplication](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/deterministic-matrix-product-verification/)**. Deterministic real computation trees for deciding $AB=C$ have the arithmetic exponent of multiplication, including with exponential and logarithm gates. The proof extracts border rank from verification of a general bilinear graph. The paper discusses independent concurrent work.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/deterministic-matrix-product-verification/) · [PDF](./preprints/deterministic-matrix-product-verification/paper.pdf) · [BibTeX](./preprints/deterministic-matrix-product-verification/README.md#citation)

### IV. Learning and Recurrence

When inputs share structure or outputs are aggregated, which independent products still determine the work?

- **[The Arithmetic Complexity of Batched Delta-Rule Readouts](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/)**. For exact batched delta-rule readouts at $d=N$, with $m=N^{b+o(1)}$ value channels sharing keys, queries, and gates for fixed $0<b\le 1$, the optimal work exponent is $1-b+\omega(1,b,b)$. It evaluates to $2+b^2/4$ under the stated rectangular exponent formula. The lower bound applies at any depth.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/) · [PDF](./preprints/delta-rule-work-depth/paper.pdf) · [BibTeX](./preprints/delta-rule-work-depth/README.md#citation)
- **[The Arithmetic Complexity of Exact Per-Example Gradient Clipping](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-per-example-gradient-clipping/)**. For a single linear layer, exact clipped gradient aggregation in real computation trees with square roots and comparisons costs, up to subpolynomial factors, the larger of one batched matrix product and a family of independent per-example products.

  [Abstract](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-per-example-gradient-clipping/) · [PDF](./preprints/exact-per-example-gradient-clipping/paper.pdf) · [BibTeX](./preprints/exact-per-example-gradient-clipping/README.md#citation)

## Connections across themes

- **What small outputs can reveal.** The [Top-1](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-batched-top1/) lower bound extracts a bilinear map from sign tests. [Ridge prediction](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-ridge-prediction/) extracts a product from a polynomial associated with a single prediction, and [product verification](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/deterministic-matrix-product-verification/) uses an accepting path. Each argument exploits a different property of the output.
- **What can be shared.** Joint queries can share arithmetic even when [cache preprocessing](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/preprocessed-softmax-attention/) leaves the single-query exponent unchanged. [Batched delta-rule readouts](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/) and [gradient clipping](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-per-example-gradient-clipping/) both recover families of independent products, from shared recurrence parameters and from clipped aggregation, respectively.
- **Where the cost can fall.** The [polynomial attention](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/exact-polynomial-attention/) and [precision](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/) papers alter the kernel and the error tolerance, respectively. [Attention I/O](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/unrestricted-attention-io/) keeps the exact softmax task and changes the resource counted to word transfers.

[See the mixed-coefficient construction for batched delta-rule readouts](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/#paper-figure).

## Research background

- The anonymous manuscript [Exact Softmax Attention Has the Rectangular Matrix-Multiplication Exponent in Extended Arithmetic Circuits](https://openreview.net/forum?id=uZLZCV3OA6) establishes a lower bound for exact attention even with a single scalar value per key. Its exp–log span theorem is used in the analysis of attention I/O.
- The [OpenAI square-exponent preprint](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md) reports a square matrix multiplication exponent of 9/4. The attention I/O paper derives a tensor inequality from that work's spectral theory.
- The accompanying [square and rectangular exponent results](https://github.com/openai/math/blob/main/lean/docs/107.md) are used where a paper specializes a symbolic bound to numerical exponents. The papers state the assumptions behind those specializations.
