---
tags:
  - Note
  - Incomplete
---
202310091410

Tags : [[Lambda Calculus]], [[Type Theory]]

---
# Kolmogorov Translation
$K(\alpha)=\lnot\lnot\alpha$

$K(\varphi\to\psi)=\lnot\lnot(\varphi\to\psi)$

$K(\varphi)=\lnot\lnot\varphi^*$
$\alpha^*=\alpha$
$(\varphi\to\psi)^{*}=(\lnot\lnot\varphi^*\to\lnot\lnot\psi^*)$

```ad-note
title:Theorem
1. $\vdash \varphi\to K(\varphi)$ and $\vdash K(\varphi)\to\varphi$ in $\text{CPC}(\rightarrow,\perp)$
2. $\vdash_{\text{CPC}}\varphi\iff \vdash_{\text{IPC}}K(\varphi)$
```

[[Continuation Passing Translations]]

```hs
sum :: [Int] -> Int
sum []        = 0
sum (x:xs)    = x + sum xs

---

sum           = sum' id
sum' f []     = f 0
sum' f (x:xs) = sum' ( f.(x+) ) xs
```

Translation from lambda mu calculus to lambda calculus

---
# References
