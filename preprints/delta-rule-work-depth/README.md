# The Arithmetic Complexity of Batched Delta-Rule Readouts

Tao Jiang and Minbo Gao (co-first authors, equal contribution)

[Read the preprint (PDF)](./paper.pdf) · [Abstract page](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/delta-rule-work-depth/) · [Earlier version](https://github.com/jiangxioabai/matrix-multiplication-complexity/blob/63a8447cb818ed765ed073d5e26c4ae6f53d9e33/preprints/delta-rule-work-depth/paper.pdf)

## Abstract

In DeltaNet and related linear-recurrent models, one attention head runs the delta rule on many value channels at once. All channels share the keys, queries and gates, but each channel has its own value sequence and returns its own scalar readout at every time step. We determine how much arithmetic this batched computation needs. For sequence length $N$, key dimension $d=N$ and $m=N^{b+o(1)}$ value channels with fixed $0<b\le 1$, the optimal number of arithmetic operations for returning all $Nm$ readouts exactly is $N^{1-b+\omega(1,b,b)\pm o(1)}$, where $\omega(\cdot,\cdot,\cdot)$ is the rectangular matrix multiplication exponent. With the recently stated closed formula for rectangular exponents, this exponent equals $2+b^2/4$. The upper bound is the chunkwise algorithm of DeltaNet with chunk length $m$ and fast rectangular products, and it runs at depth $N^{1-b+o(1)}$ (and $O(\log^2 N)$ when $b=1$). The lower bound holds at every depth, even for circuits that only need to be correct for a fixed gate and unit-norm keys. The hard matrix products never appear among the outputs: they are encoded in mixed second-order coefficients of the readouts, and a bilinear-rank argument turns any circuit for the readouts into an algorithm for many independent rectangular products.

## Citation

```bibtex
@unpublished{jiang-gao-delta-rule-work-depth,
  title  = {The Arithmetic Complexity of Batched Delta-Rule Readouts},
  author = {Jiang, Tao and Gao, Minbo},
  year   = {2026},
  note   = {Preprint}
}
```
