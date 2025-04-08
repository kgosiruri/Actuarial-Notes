# ODE Exam Strategy Summary (F19MO)

## General Exam Guidelines
- **Read the question carefully**: Is it asking for solution type, classification, stability, etc.?
- **State relevant theorems clearly**: Include assumptions, especially for Picard, Peano, etc.
- **Justify all conditions**: E.g., Lipschitz continuity, continuity of partial derivatives
- **Use clear working**: Numbered steps, boxed answers, define substitutions
- **Graphical Insight**: Mention or sketch direction fields, phase portraits where relevant

---

## Chapter 1: First-Order ODEs

### Key Theorems
- **Picard’s Theorem**: Requires continuity + continuous \( \partial f / \partial x \) → existence & uniqueness (local)
- **Picard–Lindelöf**: Requires local Lipschitz in \( x \) + continuity → local existence & uniqueness
- **Peano’s Theorem**: Only continuity → existence (no uniqueness)

### Solution Types
- **Separable**: \( x'(t) = h(t)g(x) \)
  - Solve via \( \int \frac{1}{g(x)}dx = \int h(t)dt \)
- **Linear**: \( x' + a(t)x = b(t) \)
  - Use integrating factor \( \mu(t) = e^{\int a(t) dt} \)
- **Homogeneous**: \( x' = f(x/t) \)
  - Substitute \( u = x/t \), solve for \( u \)
- **Bernoulli**: \( x' + a(t)x = b(t)x^n \)
  - Substitute \( u = x^{1-n} \) → linear
- **Exact**: Check \( \partial a / \partial x = \partial b / \partial t \), integrate to get \( \psi(t, x) = C \)

### Maximal Interval of Existence
- Use endpoint classification (blow-up, boundary of domain, etc.)
- Apply Proposition 1.23 for \( t_+ \), \( t_- \)

### Worked Example Summary
- Use domain analysis (e.g. absolute values from \( \ln|x| \))
- Verify Picard assumptions with partial derivatives

---

## Chapter 2: Systems of ODEs

### Theorems
- **Theorem 2.1 (Picard for systems)**: \( f \) and \( \partial f / \partial x \) continuous → unique solution
- **Theorem 2.3**: Continuity of \( A(t), b(t) \) ⇒ solution on all \( I \)
- **Theorem 2.4 (Superposition)**: Linear combination of solutions is solution
- **Theorem 2.5**: Solution space is \( n \)-dimensional vector space
- **Theorem 2.10 & Remark 2.12**: Variation of constants formula for inhomogeneous systems

### Techniques
- Fundamental Matrix \( X(t) \): Solve \( X'(t) = A(t)X(t) \), \( \det X(t_0) \neq 0 \)
- General Solution: \( x(t) = X(t)c \)
- Inhomogeneous: \( x(t) = X(t)\left(c + \int X^{-1}(t)b(t)dt\right) \)

### Higher-Order Conversion
- \( y^{(n)} + \dots = b(t) \) → define \( x_1 = y, x_2 = y', \dots \) → system
- Use Theorem 2.16 to ensure existence/uniqueness

---

## Chapter 3: Linear Systems with Constant Coefficients

### Core Concepts
- Solve \( x'(t) = Ax(t) \)
  - Use eigenvalues/eigenvectors
- If diagonalizable: \( x(t) = P e^{Dt} P^{-1}x_0 \)
- If not: use generalized eigenvectors (Jordan form)
- Real/complex eigenvalues → oscillations or exponential growth/decay

### Characteristic Polynomial
- \( \det(A - \lambda I) = 0 \)
- Use to find eigenvalues/eigenvectors

### Worked Types
- Repeated eigenvalues: Use \( t e^{\lambda t} \) terms
- 3D systems: real/imaginary solutions combined

---

## Chapter 4: Phase Portraits and Stability

### Definitions
- **Autonomous system**: \( x' = f(x) \)
- **Trajectory**: path traced by solution in phase space
- **Equilibrium point**: \( f(x) = 0 \)
- **Phase Portrait**: sketch of all trajectories

### Linear Systems (Theorem 4.13)
- Eigenvalues of \( A \) determine behavior:
  - Real, negative: sink (stable)
  - Real, positive: source (unstable)
  - Opposite signs: saddle (unstable)
  - Complex: spirals (check real part)

### Non-Linear Systems
- Linearize using Jacobian: \( A = Df(x^*) \)
- Classify via eigenvalues of Jacobian
- Use Theorem 4.22: sink, source, saddle

---

## Final Exam Strategy Table
| Topic               | What to Include for Full Marks                                 |
|--------------------|-----------------------------------------------------------------|
| First-Order ODEs    | General form, method, domain check, zero set, theorem used     |
| Picard/Peano        | State conditions clearly, partial derivatives, conclusion      |
| Linear Systems      | Matrix setup, eigenvalue steps, diagonalization or Jordan form |
| Variation of Const  | Fundamental matrix, invert, integrate properly                 |
| Phase Portraits     | Stability analysis, sketch direction field, classify behavior  |

---

## Tip
> State all assumptions, reference theorems precisely, and make your algebra readable. Sketch if possible and justify each solution’s domain.

