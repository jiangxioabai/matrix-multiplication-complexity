<h1 align="center">The Complexity of Attention and Matrix Products</h1>

<p align="center">
  <strong>Tao Jiang</strong> and <strong>Minbo Gao</strong><br>
  Co-first authors with equal contribution on all preprints in this collection.
</p>

<p align="center">
  <a href="#paper-index">Paper index</a> ·
  <a href="#research-results">Research results</a> ·
  <a href="#how-to-cite">How to cite</a>
</p>

How much computation does attention require, and when is it as hard as matrix multiplication? These preprints study how the answer changes with the attention kernel, preprocessing, storage, memory traffic, and parallel depth. Two companion papers ask whether the matrix multiplication exponent also governs problems that return only winning indices or a yes/no verification result.

## Paper index

| Paper | Main result | Access |
| --- | --- | --- |
| **Higher-order attention** | Matches the matrix multiplication exponent for Strassen attention and gives a faster algorithm for tensor attention. | [PDF](./preprints/strassen-and-tensor-attention/paper.pdf) · [BibTeX](./preprints/strassen-and-tensor-attention/README.md#citation) |
| **Polynomial attention** | Determines the exact exponent for quadratic attention and gives degree-dependent lower bounds for higher even degrees. | [PDF](./preprints/exact-polynomial-attention/paper.pdf) · [BibTeX](./preprints/exact-polynomial-attention/README.md#citation) |
| **Preprocessed softmax attention** | Obtains a generic matrix multiplication lower bound even after arbitrary preprocessing of the key–value cache. | [PDF](./preprints/preprocessed-softmax-attention/paper.pdf) · [BibTeX](./preprints/preprocessed-softmax-attention/README.md#citation) |
| **Attention backpropagation** | Determines the optimal work exponent for computing value gradients as a function of the forward-pass storage budget. | [PDF](./preprints/memory-recomputation-attention/paper.pdf) · [BibTeX](./preprints/memory-recomputation-attention/README.md#citation) |
| **Attention I/O complexity** | Gives matching square-width I/O exponents, conditional on results from a matrix multiplication preprint. | [PDF](./preprints/unrestricted-attention-io/paper.pdf) · [BibTeX](./preprints/unrestricted-attention-io/README.md#citation) |
| **Arbitrarily accurate softmax attention** | Recovers the rectangular matrix multiplication exponent when a bounded-size circuit family can achieve every positive error tolerance. | [PDF](./preprints/arbitrarily-accurate-softmax-attention/paper.pdf) · [BibTeX](./preprints/arbitrarily-accurate-softmax-attention/README.md#citation) |
| **Batched Top-1 prediction** | Matches the matrix multiplication exponent at square width, even though the output contains only the winning indices. | [PDF](./preprints/exact-batched-top1/paper.pdf) · [BibTeX](./preprints/exact-batched-top1/README.md#citation) |
| **Exact delta-rule computation** | Gives parallel work bounds conditional on claimed matrix multiplication exponents and an unconditional reduction from triangular substitution. | [PDF](./preprints/delta-rule-work-depth/paper.pdf) · [BibTeX](./preprints/delta-rule-work-depth/README.md#citation) |
| **Deterministic matrix product verification** | Shows that verifying a claimed real matrix product has the same arithmetic exponent as computing it. | [PDF](./preprints/deterministic-matrix-product-verification/paper.pdf) · [BibTeX](./preprints/deterministic-matrix-product-verification/README.md#citation) |

## Research results

### Attention kernels and preprocessing

<details>
<summary><strong>Matrix Multiplication Lower Bounds for Strassen Attention and a Faster Algorithm for Tensor Attention</strong></summary>

For exact normalized Strassen attention, the paper proves a matrix multiplication lower bound in extended arithmetic circuits, even at width one. The bound matches the known algorithm at the exponent level. For tensor attention, a rational crossing identity gives a faster algorithm based on four rectangular matrix products. Its stated numerical exponents depend on the claimed closed form for rectangular matrix multiplication exponents, and the optimal exponent over the full width range remains open.

[Paper page](./preprints/strassen-and-tensor-attention/README.md) · [PDF](./preprints/strassen-and-tensor-attention/paper.pdf)

</details>

<details>
<summary><strong>The Arithmetic Complexity of Exact Polynomial Attention</strong></summary>

How does the degree of a polynomial kernel affect the cost of exact attention? For every fixed positive even degree, evaluating normalized attention reduces with constant overhead to computing its unnormalized numerator. With $N$ queries and $N$ keys of width $N^a$, the exact arithmetic exponent for quadratic attention is $\omega(1,a,a)$, where $\omega(u,v,w)$ is the exponent for multiplying an $N^u \times N^v$ matrix by an $N^v \times N^w$ matrix. For higher even degrees, the paper obtains degree-dependent lower bounds by embedding many independent rectangular matrix products into one attention computation.

[Paper page](./preprints/exact-polynomial-attention/README.md) · [PDF](./preprints/exact-polynomial-attention/paper.pdf)

</details>

<details>
<summary><strong>Preprocessed Softmax Attention Is as Hard as Matrix Multiplication</strong></summary>

Can arbitrary preprocessing of a fixed key–value cache make exact softmax attention cheaper when the queries arrive? For almost every key matrix and every nonconstant scalar value vector, any circuit in the exact real arithmetic model with exponential and logarithm gates needs at least half the tensor rank of the corresponding rectangular matrix product. The bound allows arbitrary cache-dependent constants and circuits that are correct on an open set of queries. In particular, a single query has generic arithmetic cost $\Theta(Nd)$ for $N$ keys of width $d$.

[Paper page](./preprints/preprocessed-softmax-attention/README.md) · [PDF](./preprints/preprocessed-softmax-attention/paper.pdf)

</details>

<details>
<summary><strong>Arbitrarily Accurate Softmax Attention Has the Rectangular Matrix Multiplication Exponent</strong></summary>

Can arbitrarily accurate approximation reduce the circuit size for softmax attention? For one-channel attention, the paper studies approximation uniformly to every positive error tolerance on a compact domain with nonempty interior, with circuit size bounded independently of the tolerance. With $N$ queries and keys of width $\lceil N^a\rceil$, the resulting border complexity has the rectangular matrix multiplication exponent $\omega(1,a,1)$ in extended arithmetic circuits. The lower bound extracts a matrix multiplication tensor from the mixed query–key Hessian of the summed output.

[Paper page](./preprints/arbitrarily-accurate-softmax-attention/README.md) · [PDF](./preprints/arbitrarily-accurate-softmax-attention/paper.pdf)

</details>

### Storage and data movement

<details>
<summary><strong>Memory–Recomputation Tradeoffs for Exact Attention Backpropagation</strong></summary>

How much forward-pass storage lowers the cost of computing the gradient with respect to the values? The forward pass may store any $M$ real-valued functions of the queries and keys. For $N$ tokens of width $N^a$, if $N(N-1)-M=N^{2b+o(1)}$, the optimal backward arithmetic exponent is $\max\{2,\omega(b,a,b)\}$. Even leaving only about $N^2/\log N$ of the $N(N-1)$ within-row score differences unstored gives the same exponent as storing nothing.

[Paper page](./preprints/memory-recomputation-attention/README.md) · [PDF](./preprints/memory-recomputation-attention/paper.pdf)

</details>

<details>
<summary><strong>On the Unrestricted I/O Complexity of Exact Softmax Attention</strong></summary>

How much data must move between fast and slow memory if arithmetic and recomputation inside fast memory are unrestricted? For $N$ queries and $N$ keys of width $N$, with fast memory of size $\Theta(N^\mu)$ and $0\le\mu\le2$, the paper obtains matching I/O exponents of $9/4-\mu/8$, even with one scalar value per key. Both bounds rely on results claimed in a recent matrix multiplication preprint. The reduction from attention to matrix multiplication is independent of those claims.

[Paper page](./preprints/unrestricted-attention-io/README.md) · [PDF](./preprints/unrestricted-attention-io/paper.pdf)

</details>

### Prediction and recurrent computation

<details>
<summary><strong>Exact Batched Top-1 Prediction Is as Hard as Matrix Multiplication</strong></summary>

Given a batch of queries and candidate vectors, exact Top-1 prediction returns a maximizing inner-product index for each query. At square width, the paper shows that this task has the same arithmetic exponent as matrix multiplication in the deterministic real arithmetic model with exact comparisons. Its lower bound extracts a border-rank decomposition from the sign tests on an accepting path. The paper also extends the lower bound to Top-$k$ outputs and gives upper and lower bounds at rectangular widths.

[Paper page](./preprints/exact-batched-top1/README.md) · [PDF](./preprints/exact-batched-top1/paper.pdf)

</details>

<details>
<summary><strong>Work–Depth Trade-offs for Exact Delta-Rule Computation</strong></summary>

How much work is needed to parallelize the delta-rule recurrence used in DeltaNet? When the state width equals the sequence length $N$, the paper gives circuits of depth $N^\theta$ with work $N^{2+(1-\theta)^2/4+o(1)}$ for fixed $0<\theta<1$, and circuits of polylogarithmic depth with work $N^{9/4+o(1)}$. These upper bounds use recently claimed square and rectangular matrix multiplication exponents. The paper also gives an unconditional reduction from exact dense triangular substitution to exact delta-rule computation.

[Paper page](./preprints/delta-rule-work-depth/README.md) · [PDF](./preprints/delta-rule-work-depth/paper.pdf)

</details>

### Matrix product verification

<details>
<summary><strong>Deterministic Verification of Real Matrix Products Is as Hard as Multiplication</strong></summary>

Can a deterministic algorithm verify a claimed real matrix product faster than it can compute the product? In the algebraic computation tree model, the paper shows that verification has the same arithmetic exponent as multiplication, including for rectangular products. The lower bound comes from a general theorem for bilinear maps that bounds the number of nonlinear gates on an accepting path in terms of border rank. The verification bound also applies when exponential and logarithm gates are allowed.

[Paper page](./preprints/deterministic-matrix-product-verification/README.md) · [PDF](./preprints/deterministic-matrix-product-verification/paper.pdf)

</details>

## How to cite

Use the BibTeX link for the specific preprint you are citing. Each entry gives the full paper title and lists both co-first authors.
