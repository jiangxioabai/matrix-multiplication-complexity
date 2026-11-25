# Memory–Recomputation Tradeoffs for Exact Attention Backpropagation

Tao Jiang and Minbo Gao (equal contribution)

[Read the preprint (PDF)](./paper.pdf)

## Main result

We characterize the tradeoff between forward-pass storage and the cost of computing the gradient with respect to the values in exact softmax attention. In exact arithmetic circuits with exponential and logarithm gates, the optimal backward exponent is determined by a rectangular matrix multiplication exponent and the number of independent score differences left unstored. Storing a subquadratic number of scalars yields no polynomial savings over recomputing from scratch.

## Citation

```bibtex
@unpublished{jiang-gao-memory-recomputation-attention,
  title  = {Memory--Recomputation Tradeoffs for Exact Attention Backpropagation},
  author = {Jiang, Tao and Gao, Minbo},
  note   = {Preprint}
}
```
