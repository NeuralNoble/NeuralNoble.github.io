---
title: Broadcasting in PyTorch
date: 2026-04-12
---

# Broadcasting in PyTorch

A quick note on broadcasting, which is just the set of rules PyTorch (and NumPy) use when you do operations on tensors of different shapes, so you don't have to manually copy or expand data yourself.

## The idea

```python
[1, 2, 3] + 5
# result = [6, 7, 8]
```

You didn't have to write `[5, 5, 5]`. Instead of erroring out because the shapes differ, PyTorch pretends to expand one tensor to match the other.

## How it works

Take two tensors with `A.shape = [4, 1]` and `B.shape = [3]`, and try `A * B`.

PyTorch compares their shapes starting from the rightmost dimension (like aligning numbers from the right edge):

| Dimension | A | B | Compatible? | Result |
|-----------|---|---|-------------|--------|
| last      | 1 | 3 | yes, 1 expands to 3 | 3 |
| 2nd last  | 4 | missing | missing treated as 1, expands to 4 | 4 |

Final shape: `[4, 3]`. Both tensors are internally expanded before the operation runs.

!!! note
    Broadcasting does not actually copy data. PyTorch uses stride tricks to make a tensor *look* like it has the expanded shape without allocating new memory. That's why it's fast and cheap.

## The rules

1. **Align from the rightmost dimension.** PyTorch compares shapes starting from the end.
2. **Each dimension must either be equal, or one of them must be 1.**
    - If one dim is 1, it stretches to match the other.
    - If both are different and neither is 1, you get an error.
3. **Missing dimensions act like 1.** So `[3]` behaves like `[1, 3]`.

After applying these expansions, both tensors have the same shape and the operation proceeds elementwise.

## Examples

### Example 1

```python
a = torch.ones(3, 1)
b = torch.ones(1, 4)
c = a + b
```

| Tensor | Shape | Expanded to |
|--------|-------|-------------|
| a      | `[3, 1]` | `[3, 4]` (last dim 1 expands to 4) |
| b      | `[1, 4]` | `[3, 4]` (first dim 1 expands to 3) |

Result shape: `[3, 4]`.

### Example 2

```python
a = torch.ones(2, 3, 1)
b = torch.ones(3)
c = a * b
```

| dim   | a | b | result |
|-------|---|---|--------|
| last  | 1 | 3 | 1 expands to 3 |
| mid   | 3 | missing, treated as 1 | 1 expands to 3 |
| first | 2 | missing, treated as 1 | 1 expands to 2 |

Both become `[2, 3, 3]`.

### Example 3

```python
a = torch.ones(5, 1, 4)
b = torch.ones(3, 4)
c = a + b
```

| dim   | a | b | result |
|-------|---|---|--------|
| last  | 4 | 4 | match, stays 4 |
| mid   | 1 | 3 | 1 expands to 3 |
| first | 5 | missing, treated as 1 | 1 expands to 5 |

Both become `[5, 3, 4]`.

## Common gotcha

Watch out for the difference between shape `(N,)`, `(N, 1)`, and `(1, N)`. They look similar but broadcast very differently:

```python
a = torch.ones(3)       # shape [3]
b = torch.ones(3, 1)    # shape [3, 1]
a + b                   # result shape [3, 3], not [3]
```

When the shapes are ambiguous in your head, just print them. A `.shape` check saves a lot of debugging.

## Quick cheat sheet

1. Align shapes from the rightmost dimension.
2. For each dimension:
    - sizes equal, ok
    - one is 1, expand it to match the other
    - one is missing, treat as 1, then expand
    - different and neither is 1, error
3. Once both tensors match, run the operation elementwise.
