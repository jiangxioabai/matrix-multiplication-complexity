# Arbitrarily Accurate Softmax Attention Has the Rectangular Matrix Multiplication Exponent

Tao Jiang and Minbo Gao (co-first authors, equal contribution)

[Read the preprint (PDF)](./paper.pdf)

## Main result

Can arbitrarily accurate approximation reduce the circuit size for softmax attention? For one-channel attention, the paper studies approximation uniformly to every positive error tolerance on a compact domain with nonempty interior, with circuit size bounded independently of the tolerance. With $N$ queries and keys of width $\lceil N^a\rceil$, the resulting border complexity has the rectangular matrix multiplication exponent $\omega(1,a,1)$ in extended arithmetic circuits. The lower bound extracts a matrix multiplication tensor from the mixed query–key Hessian of the summed output.

## Citation

```bibtex
@unpublished{jiang-gao-arbitrarily-accurate-softmax-attention,
  title  = {Arbitrarily Accurate Softmax Attention Has the Rectangular Matrix Multiplication Exponent},
  author = {Jiang, Tao and Gao, Minbo},
  note   = {Preprint}
}
```
