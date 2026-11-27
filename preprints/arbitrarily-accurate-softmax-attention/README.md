# The Arithmetic Cost of Precision in One-Channel Softmax Attention

Tao Jiang and Minbo Gao (co-first authors, equal contribution)

[Read the preprint (PDF)](./paper.pdf) · [Abstract page](https://jiangxioabai.github.io/matrix-multiplication-complexity/preprints/arbitrarily-accurate-softmax-attention/)

## Abstract

How does the accuracy required of a single attention head affect its arithmetic complexity? Every query, key, and value coordinate lies in $[-1,1]$. We use unscaled dot products and measure worst-case absolute error in each of the $N$ scalar outputs. In deterministic extended arithmetic circuits at square width $d=N$, the gate count is $N^{2+o(1)}$ for every sequence $0<\varepsilon_N\le\varepsilon_0$ with fixed $0<\varepsilon_0<1$ and $\log(1/\varepsilon_N)=N^{o(1)}$. At error $N^{-c}$ the upper bound sharpens to $O_c(N^2\operatorname{polylog} N)$ for each fixed $c>0$. A finite-accuracy matrix product supplies the scores, and the weighted output is 1-Lipschitz in each row's score vector under the maximum norm. At errors at most $2^{-2^{M^6}}$, where $M=1000(N+2)^5$, the gate exponent rises to the square matrix multiplication exponent $\omega$. The lower bound extracts a multiplication tensor from mixed derivatives of the summed outputs. At widths $d=\lceil N^a\rceil$, $0<a\le1$ fixed, the border complexity (the least gate bound that suffices for every positive error tolerance at fixed dimensions) has the rectangular multiplication exponent. The transition between these square-width regimes remains open.

## Citation

```bibtex
@unpublished{jiang-gao-arbitrarily-accurate-softmax-attention,
  title  = {The Arithmetic Cost of Precision in One-Channel Softmax Attention},
  author = {Jiang, Tao and Gao, Minbo},
  year   = {2026},
  note   = {Preprint}
}
```
