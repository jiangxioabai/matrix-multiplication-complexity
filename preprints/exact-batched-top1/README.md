# Exact Batched Top-1 Prediction Is as Hard as Matrix Multiplication

Tao Jiang and Minbo Gao (co-first authors, equal contribution)

[Read the preprint (PDF)](./paper.pdf)

## Main result

Given a batch of queries and candidate vectors, exact Top-1 prediction returns a maximizing inner-product index for each query. At square width, the paper shows that this task has the same arithmetic exponent as matrix multiplication in the deterministic real arithmetic model with exact comparisons. Its lower bound extracts a border-rank decomposition from the sign tests on an accepting path. The paper also extends the lower bound to Top-$k$ outputs and gives upper and lower bounds at rectangular widths.

## Citation

```bibtex
@unpublished{jiang-gao-exact-batched-top1,
  title  = {Exact Batched {Top-1} Prediction Is as Hard as Matrix Multiplication},
  author = {Jiang, Tao and Gao, Minbo},
  note   = {Preprint}
}
```
