# Research Papers

Preprints by **Tao Jiang** and **Minbo Gao** on the computational complexity of exact attention, batched prediction, recurrent computation, and matrix product verification.

**Equal contribution.** Tao Jiang and Minbo Gao are co-first authors on all nine preprints in this collection.

These papers ask how the cost of computing a sequence model changes when we vary its kernel, the information available in advance, the output it must return, or the resources available during evaluation. The results quantify arithmetic operations and comparisons, backward-pass work under a storage budget, data movement between memory levels, and parallel circuit depth. Rectangular matrix multiplication provides a common reference point across these models. The collection also studies whether verifying a claimed matrix product is cheaper than computing it.

## Attention

### Matrix Multiplication Lower Bounds for Strassen Attention and a Faster Algorithm for Tensor Attention

For exact normalized Strassen attention, the paper proves a matrix multiplication lower bound in extended arithmetic circuits, even at width one. The bound matches the known algorithm at the exponent level. For tensor attention, a rational crossing identity gives a faster algorithm based on four rectangular matrix products. Its stated numerical exponents depend on the claimed closed form for rectangular matrix multiplication exponents, and the optimal exponent over the full width range remains open.

[PDF](./preprints/strassen-and-tensor-attention/paper.pdf) · [Paper page and BibTeX](./preprints/strassen-and-tensor-attention/README.md)

### The Arithmetic Complexity of Exact Polynomial Attention

How does the degree of a polynomial kernel affect the cost of exact attention? For every fixed positive even degree, evaluating normalized attention reduces with constant overhead to computing its unnormalized numerator. With $N$ queries and $N$ keys of width $N^a$, the exact arithmetic exponent for quadratic attention is $\omega(1,a,a)$, where $\omega(u,v,w)$ is the exponent for multiplying an $N^u \times N^v$ matrix by an $N^v \times N^w$ matrix. For higher even degrees, the paper obtains degree-dependent lower bounds by embedding many independent rectangular matrix products into one attention computation.

[PDF](./preprints/exact-polynomial-attention/paper.pdf) · [Paper page and BibTeX](./preprints/exact-polynomial-attention/README.md)

### Preprocessed Softmax Attention Is as Hard as Matrix Multiplication

Can arbitrary preprocessing of a fixed key–value cache make exact softmax attention cheaper when the queries arrive? For almost every key matrix and every nonconstant scalar value vector, any circuit in the exact real arithmetic model with exponential and logarithm gates needs at least half the tensor rank of the corresponding rectangular matrix product. The bound allows arbitrary cache-dependent constants and circuits that are correct on an open set of queries. In particular, a single query has generic arithmetic cost $\Theta(Nd)$ for $N$ keys of width $d$.

[PDF](./preprints/preprocessed-softmax-attention/paper.pdf) · [Paper page and BibTeX](./preprints/preprocessed-softmax-attention/README.md)

### Memory–Recomputation Tradeoffs for Exact Attention Backpropagation

How much forward-pass storage lowers the cost of computing the gradient with respect to the values? The forward pass may store any $M$ real-valued functions of the queries and keys. For $N$ tokens of width $N^a$, if $N(N-1)-M=N^{2b+o(1)}$, the optimal backward arithmetic exponent is $\max\{2,\omega(b,a,b)\}$. Even leaving only about $N^2/\log N$ of the $N(N-1)$ within-row score differences unstored gives the same exponent as storing nothing.

[PDF](./preprints/memory-recomputation-attention/paper.pdf) · [Paper page and BibTeX](./preprints/memory-recomputation-attention/README.md)

### On the Unrestricted I/O Complexity of Exact Softmax Attention

How much data must move between fast and slow memory if arithmetic and recomputation inside fast memory are unrestricted? For $N$ queries and $N$ keys of width $N$, with fast memory of size $\Theta(N^\mu)$ and $0\le\mu\le2$, the paper obtains matching I/O exponents of $9/4-\mu/8$, even with one scalar value per key. Both bounds rely on results claimed in a recent matrix multiplication preprint. The reduction from attention to matrix multiplication is independent of those claims.

[PDF](./preprints/unrestricted-attention-io/paper.pdf) · [Paper page and BibTeX](./preprints/unrestricted-attention-io/README.md)

### Arbitrarily Accurate Softmax Attention Has the Rectangular Matrix Multiplication Exponent

Can arbitrarily accurate approximation reduce the circuit size for softmax attention? For one-channel attention, the paper studies approximation uniformly to every positive error tolerance on a compact domain with nonempty interior, with circuit size bounded independently of the tolerance. With $N$ queries and keys of width $\lceil N^a\rceil$, the resulting border complexity has the rectangular matrix multiplication exponent $\omega(1,a,1)$ in extended arithmetic circuits. The lower bound extracts a matrix multiplication tensor from the mixed query–key Hessian of the summed output.

[PDF](./preprints/arbitrarily-accurate-softmax-attention/paper.pdf) · [Paper page and BibTeX](./preprints/arbitrarily-accurate-softmax-attention/README.md)

## Prediction

### Exact Batched Top-1 Prediction Is as Hard as Matrix Multiplication

Given a batch of queries and candidate vectors, exact Top-1 prediction returns a maximizing inner-product index for each query. At square width, the paper shows that this task has the same arithmetic exponent as matrix multiplication in the deterministic real arithmetic model with exact comparisons. Its lower bound extracts a border-rank decomposition from the sign tests on an accepting path. The paper also extends the lower bound to Top-$k$ outputs and gives upper and lower bounds at rectangular widths.

[PDF](./preprints/exact-batched-top1/paper.pdf) · [Paper page and BibTeX](./preprints/exact-batched-top1/README.md)

## Recurrent Computation

### Work–Depth Trade-offs for Exact Delta-Rule Computation

How much work is needed to parallelize the delta-rule recurrence used in DeltaNet? When the state width equals the sequence length $N$, the paper gives circuits of depth $N^\theta$ with work $N^{2+(1-\theta)^2/4+o(1)}$ for fixed $0<\theta<1$, and circuits of polylogarithmic depth with work $N^{9/4+o(1)}$. These upper bounds use recently claimed square and rectangular matrix multiplication exponents. The paper also gives an unconditional reduction from exact dense triangular substitution to exact delta-rule computation.

[PDF](./preprints/delta-rule-work-depth/paper.pdf) · [Paper page and BibTeX](./preprints/delta-rule-work-depth/README.md)

## Matrix Product Verification

### Deterministic Verification of Real Matrix Products Is as Hard as Multiplication

Can a deterministic algorithm verify a claimed real matrix product faster than it can compute the product? In the algebraic computation tree model, the paper shows that verification has the same arithmetic exponent as multiplication, including for rectangular products. The lower bound comes from a general theorem for bilinear maps that bounds the number of nonlinear gates on an accepting path in terms of border rank. The verification bound also applies when exponential and logarithm gates are allowed.

[PDF](./preprints/deterministic-matrix-product-verification/paper.pdf) · [Paper page and BibTeX](./preprints/deterministic-matrix-product-verification/README.md)
