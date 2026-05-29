---
layout: post
title: "Hello, world"
date: 2026-05-29
lang: en
ref: hello-world
description: "First post, doubling as a syntax cheat sheet."
---

This is the first post, and also a cheat sheet — delete it once you're comfortable.

Note the `ref` field at the top: it must be **identical** to the one in the Chinese
version. That's the key the blog uses to pair the two languages of the same post.

## Writing math

Inline math with `\( ... \)`, e.g. the residual \( r = z - h(x) \). Display math with `$$ ... $$`:

$$
\hat{x} = \arg\min_{x} \sum_{i} \rho\!\left( \lVert r_i(x) \rVert_{\Sigma_i}^2 \right)
$$

Rendered client-side by MathJax — no build step needed.

## Code blocks

```python
def integrate_imu(state, omega, accel, dt):
    R = state.R @ so3_exp(omega * dt)
    v = state.v + (state.R @ accel) * dt
    p = state.p + state.v * dt + 0.5 * (state.R @ accel) * dt**2
    return State(R, v, p)
```

## Publishing a new post

For each post, upload **two files** to `_posts/`:

- Chinese: `2026-06-01-title.md` with `lang: zh`
- English: `2026-06-01-title-en.md` with `lang: en`

Give both files the same `ref` value (e.g. `ref: my-post`) and the toggle appears automatically.
