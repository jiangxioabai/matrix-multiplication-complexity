# Research Papers

Preprints by **Tao Jiang** and **Minbo Gao** on the computational complexity of exact attention and recurrent sequence models.

**Equal contribution.** Tao Jiang and Minbo Gao are co-first authors on all five preprints in this collection.

These papers ask how the cost of computing a sequence model changes when we vary its kernel, the information available in advance, or the resources available during evaluation. The results quantify arithmetic operations, backward-pass work under a storage budget, data movement between memory levels, and parallel circuit depth. Rectangular matrix multiplication provides a common reference point across these models.

## Attention

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

## Recurrent Computation

### Work–Depth Trade-offs for Exact Delta-Rule Computation

How much work is needed to parallelize the delta-rule recurrence used in DeltaNet? When the state width equals the sequence length $N$, the paper gives circuits of depth $N^\theta$ with work $N^{2+(1-\theta)^2/4+o(1)}$ for fixed $0<\theta<1$, and circuits of polylogarithmic depth with work $N^{9/4+o(1)}$. These upper bounds use recently claimed square and rectangular matrix multiplication exponents. The paper also gives an unconditional reduction from exact dense triangular substitution to exact delta-rule computation.

[PDF](./preprints/delta-rule-work-depth/paper.pdf) · [Paper page and BibTeX](./preprints/delta-rule-work-depth/README.md)
