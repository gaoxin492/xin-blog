---
layout: post
title: "你好，世界"
date: 2026-05-29
lang: zh
ref: hello-world
description: "第一篇文章，顺便当作语法速查表。"
---

这是第一篇文章，也当作一份速查表，熟悉之后删掉即可。

注意顶部的「ref」字段——它和英文版那篇必须**完全一致**，博客就靠它把两种语言的同一篇文章配对起来。

## 写数学公式

行内公式用 `\( ... \)`，比如残差 \( r = z - h(x) \)。整行公式用 `$$ ... $$`：

$$
\hat{x} = \arg\min_{x} \sum_{i} \rho\!\left( \lVert r_i(x) \rVert_{\Sigma_i}^2 \right)
$$

公式在浏览器端由 MathJax 渲染，不需要额外构建步骤。

## 代码块

```python
def integrate_imu(state, omega, accel, dt):
    R = state.R @ so3_exp(omega * dt)
    v = state.v + (state.R @ accel) * dt
    p = state.p + state.v * dt + 0.5 * (state.R @ accel) * dt**2
    return State(R, v, p)
```

## 怎么发一篇新文章

每篇文章传**两个文件**到 `_posts/`：

- 中文版：`2026-06-01-标题.md`，front matter 里 `lang: zh`
- 英文版：`2026-06-01-标题-en.md`，front matter 里 `lang: en`

两个文件的 `ref` 写成同一个值（比如 `ref: my-post`），切换链接就会自动出现。
