---
layout: post
title: Hello, world
description: A sample post showing code blocks, math, and images.
tags: [misc]
math: true
---

This is a sample post. Posts are plain Markdown files in the `_posts` folder.

## Code

```python
def attention(q, k, v):
    scores = q @ k.T / q.shape[-1] ** 0.5
    return softmax(scores) @ v
```

## Math

Add `math: true` to a post's front matter to enable LaTeX. Inline math like $O(n^2)$ works, and so do display equations:

$$
\mathrm{Attention}(Q, K, V) = \mathrm{softmax}\left(\frac{QK^\top}{\sqrt{d_k}}\right) V
$$

## Quotes and lists

> Premature optimization is the root of all evil.

- Put images in `assets/img/` and reference them with `![alt text](/assets/img/figure.png)`.
- Links, tables, and footnotes all work as in GitHub Markdown.
