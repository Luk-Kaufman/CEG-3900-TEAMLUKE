# Not Affine

A non-affine anything is anything that does not follow the affine form typically written as a linear component plus a constant offset (f(x)=ax+b in basic math or similar linear-plus-shift structures in higher 
dimensions or cryptography). In many fields—especially mathematics, computer graphics, machine learning, and cryptography—affine structures are predictable and preserve properties like straight lines, ratios of 
distances along a line, and simple linear relationships. When something is not affine, it breaks those predictable linear patterns, introducing curvature, nonlinear behavior, or more complex transformations.

---

## What makes it so special?

- Introduces nonlinearity, which allows systems to model or represent complex patterns.
- Often harder to reverse or predict compared to affine structures.
- Breaks properties preserved by affine transforms.
- Enables stronger cryptographic constructions when used in substitution boxes or mixing layers.
- Important for security analysis, because many attacks rely on affine or linear approximations.
- Expands what algorithms and models can represent.
- In graphics or geometry, it allows distortions and curvatures that affine transforms cannot produce.

---

## Concepts

### Mathematical Perspective

- Affine function (reference point): linear transformation + translation.
- Non-affine function: includes nonlinear terms such as:
  - Quadratic terms
    -  x^2
- Exponentials
- Trigonometric components
- Does not preserve straight lines in the same way as affine mappings.
- Often results in curved outputs or nonlinear relationships.

### Geometry & Transformations

- Affine transformations preserve:
  - Parallel lines
  - Ratios along a line
  - Collinearity
- Non-affine transformations may:
  - Bend or warp lines
  - Distort shapes non-uniformly
  - Change relative spacing unpredictably

### Cryptography & Security
- Pure affine systems are:
  - Predictable
  - Vulnerable to frequency analysis or algebraic attacks.
- Non-affine components improve security:
  - Nonlinear substitution boxes (S-boxes)
  - Nonlinear mixing operations
  - Resistance against linear cryptanalysis and differential attacks.
- Many modern encryption algorithms intentionally include non-affine steps to break patterns attackers rely on.

### Computer Science & Machine Learning
- Linear models alone are essentially affine.
- Non-affine transformations allow:
  - Complex decision boundaries
  - Feature interactions
  - Deep neural networks to function effectively.
- Activation functions produce non-affine behavior, which is critical for learning complex data structures.

---

## Lab Solutions

1. 3x3
2. 3
3. #include <ctype.h>
4. 1A
5. EOC
6. SKY-MMTR-4555
