# On the Unrestricted I/O Complexity of Exact Softmax Attention

Tao Jiang and Minbo Gao (equal contribution)

[Read the preprint (PDF)](./paper.pdf)

## Main result

We study how much data exact softmax attention must move between fast and slow memory. For N queries and N keys of width N with a single scalar value per key, we give matching I/O exponents for straight-line algorithms with unrestricted local arithmetic and recomputation. Both bounds rely on results claimed in a recent preprint on matrix multiplication exponents. The reduction from attention to matrix multiplication does not depend on those results.

## Citation

```bibtex
@unpublished{jiang-gao-unrestricted-attention-io,
  title  = {On the Unrestricted {I/O} Complexity of Exact Softmax Attention},
  author = {Jiang, Tao and Gao, Minbo},
  note   = {Preprint}
}
```
