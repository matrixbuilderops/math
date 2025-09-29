
# 📘 Knuth-Sorrellian Notation Documentation

## Class One: Standard Form

### Format:
`A, B, C`

### Interpretation:
- `A` = Base number
- `B` = Exponent (power)
- `C` = Number of iterations of the full operation

### Description:
The operation is evaluated as a repeated power expression:
`(((A^B)^B)^B)^B` repeated `C` times.

### Example:
**Input**: `2, 3, 4`  
**Computation**:
1. `2^3 = 8`
2. `8^3 = 512`
3. `512^3 = 134,217,728`
4. `134,217,728^3 ≈ 2.4 × 10^24`

---

## Class Two: Upgraded Rotational Notation

### Concept:
Each iteration rotates the positions of the base, exponent, and iteration count. The output of the previous cycle becomes the new base.

### Format:
Starts as: `A, B, C`

### Rotation Rule:
- **Cycle n+1**:
  - New Base = Result of Cycle n
  - New Exponent = Base from Cycle n
  - New Iteration = Exponent from Cycle n

### Sequence:
```
Cycle 1: A, B, C
Cycle 2: (Result from Cycle 1), A, B
Cycle 3: (Result from Cycle 2), (A from Cycle 2), (B from Cycle 2)
...
```

### Example:
**Initial Input**: `2, 3, 2`

- **Cycle 1**:
  - `2^3 = 8`

- **Cycle 2**:
  - Base = 8
  - Exponent = 2
  - Iteration = 3
  - `((8^2)^2)^2 = 4294967296`

- **Cycle 3**:
  - Base = 4294967296
  - Exponent = 8
  - Iteration = 2
  - `(4294967296^8)^8` → extremely large value

---

## Summary:
- **Knuth-Sorrellian – Class One**: Basic recursive exponentiation.
- **Knuth-Sorrellian – Class Two**: Rotational logic applied to exponential chains, dramatically increasing magnitude each cycle.
