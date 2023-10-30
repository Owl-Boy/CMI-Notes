202308101508

Type : #Note #Rename
Tags : [[Algorithmic Coding Theory]]

---
# Algorithmic Coding Theory Lec 1

```ad-info
title: Redundancies
We want to either transmit a message through a noisy channel or read some stored data which might have been corrupted due to hardware issues . So we add redundancies
```

$\Sigma$ is a finite alphabet. **Code** of blocks of length $n\in\Sigma^{n}$
$|\Sigma|=q$ and it might grow with $n$ 

The two ideas that are used to measure the amount of redundancies in a code are [[Measurement of Redundancy in a code#Dimension of a code|Dimension]] and [[Measurement of Redundancy in a code#Rate of a code|Rate]] of a code where higher rate implies code with less redundancies.
## Some Basic Codes
### Repetition
For every single character in the code, repeat it twice
$$010\longmapsto001100$$
Here if one of the digit gets changed in the noisy channel we get $001101$.
Here we can see that an error is detected at the last digit.

We can replace every single digit with 3 digits. Then a single error can be both detected and corrected

### Parity Code
$$
x_{1}, x_{2}, x_{3}, x_{4} \longmapsto x_{1}, x_{2}, x_{3}, x_{4},x_{1}\oplus x_{2}\oplus x_{3}\oplus x_{4}
$$
this adds the parity of $1$ in the code, changing any one digit makes the parity not match, hence it detects a single error.

---
# References
[[Measurement of Redundancy in a code]]
[[Encoding and Decoding Functions]]
[[Distance of a Code]]