# -
Задание 01   Цыпа, декодируй это  
# Binary Linear Code Decoding

## Overview
This project implements two decoding algorithms for binary linear codes: Information Set Decoding (ISD) and Stern's Algorithm.

## Functions

### decodeISD
- **Inputs:**
  - `G`: A (k × n) matrix over F2.
  - `y`: A vector of length n over F2.
  - `t`: A natural number representing the error weight.
  - `niter`: A natural number representing the maximum number of iterations (default is -1, meaning no limit).
- **Output:**
  - A pair of vectors `(m, e)` such that `y = mG + e` and `wt(e) = t`, or `niter` if no such vectors are found.

### decodeSTERN
- **Inputs:**
  - `H`: A (r × n) matrix over F2.
  - `s`: A vector of length r over F2.
  - `t`: A natural number representing the error weight.
  - `p`: A natural number, parameter of Stern's Algorithm.
  - `l`: A natural number, parameter of Stern's Algorithm.
  - `niter`: A natural number representing the maximum number of iterations (default is -1, meaning no limit).
- **Output:**
  - A vector `e` such that `s⊤ = He⊤` and `wt(e) = t`, or `niter` if no such vector is found.

## Usage
To use these functions, you need to have Julia installed on your system. Then, you can run the following code:

```julia
# Example usage of decodeISD
G = [1 0 1 0 1; 0 1 1 1 0]  # Example matrix
y = [1, 0, 1, 1, 0]  # Example vector
t = 2  # Error weight
m, e = decodeISD(G, y, t)
println("Message: ", m)
println("Error: ", e)

# Example usage of decodeSTERN
H = [1 0 1 0 1; 0 1 1 1 0]  # Example matrix
s = [1, 0]  # Example vector
t = 2  # Error weight
p = 2  # Parameter p
l = 2  # Parameter l
e = decodeSTERN(H, s, t, p, l)
println("Error: ", e)
