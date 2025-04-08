# Risk Theory Notes

*This document contains summaries of key topics in Risk Theory along with exam analysis pointers.*

---

## Table of Contents

1. [Preliminaries and Background](#preliminaries-and-background)
2. [Loss (Claim) Distributions](#loss-claim-distributions)
3. [Aggregate (Collective) Risk Models](#aggregate-collective-risk-models)
4. [Premium Calculation Principles](#premium-calculation-principles)
5. [No-Claims Discount Systems](#no-claims-discount-systems)
6. [Claims Reserving (Run-Off Triangles)](#claims-reserving-run-off-triangles)
7. [Ruin Theory](#ruin-theory)
8. [Extreme Value Theory](#extreme-value-theory)
9. [Copulas](#copulas)
10. [Credibility Theory](#credibility-theory)
11. [Exam Analysis](#exam-analysis)

---

## Preliminaries and Background

- **Scope:** Focus on modeling short-term insurance (e.g., motor, property, liability) and distinguishing it from long-term insurance.
- **Basic Model:**  
  The total claims process is modeled as:
  $$
  S(t) = \sum_{i=1}^{N(t)} X_i,
  $$
  where  
  - \( N(t) \): Number of claims in \([0,t]\) (e.g., Poisson distributed),  
  - \( X_i \): Claim amounts (assumed i.i.d).

- **Simplifying Assumptions:**
  - Claims are settled immediately.
  - Expenses and investment income are ignored.
  - The claim size distribution is assumed to be known.

- **Moment Generating Functions (MGFs):**
  - For a random variable \(X\):  
    $$
    M_X(t) = E[e^{tX}].
    $$
  - Derivatives at \(t=0\) yield moments, e.g.,  
    $$
    M_X'(0) = E[X].
    $$

---

## Loss (Claim) Distributions

- **Common Distributions:**
  - **Exponential(\(\lambda\)):**
    - PDF: \( f(x)=\lambda e^{-\lambda x}, \quad x>0 \)
    - Mean: \( \frac{1}{\lambda} \)
    - Memoryless property.
  - **Gamma(\(\alpha, \lambda\)):**
    - PDF: \( f(x)= \frac{\lambda^\alpha x^{\alpha-1} e^{-\lambda x}}{\Gamma(\alpha)},\; x>0 \)
    - Mean: \( \frac{\alpha}{\lambda} \)
  - **Lognormal:**  
    If \( Y = \ln(X) \sim \mathcal{N}(\mu,\sigma^2) \), then \( X \) is lognormally distributed.
  - **Pareto:**  
    Tail function:  
    $$
    P(X>x)=\Bigl(\frac{\lambda}{\lambda+x}\Bigr)^\alpha,\quad x>0.
    $$
  - **Weibull:**  
    Survival function:  
    $$
    P(X>x)=e^{-cx^\gamma},\quad x>0.
    $$

- **Tail Characteristics:**  
  Compare decay of tails: Pareto (heavy-tailed) vs. Exponential (lighter tail).

- **MGFs:**  
  - Exponential: \( M_X(t)=\frac{\lambda}{\lambda-t} \) for \( t < \lambda \).

---

## Aggregate (Collective) Risk Models

- **Compound Distribution Model:**  
  Aggregate claims:  
  $$
  S = \sum_{i=1}^{N} X_i,
  $$
  where \(N\) and \(X_i\) are independent.

- **Key Formulas:**
  - **Moment Generating Function:**
    $$
    M_S(t) = M_N\bigl(\ln M_X(t)\bigr).
    $$
  - **Mean and Variance:**
    $$
    E[S] = E[N]\cdot E[X],
    $$
    $$
    \mathrm{Var}(S)=E[N]\mathrm{Var}(X)+\mathrm{Var}(N)(E[X])^2.
    $$

- **Examples of \(N\):**
  - Poisson, Binomial, and Negative Binomial distributions.

- **Normal Approximation:**  
  When \(N\) is large (or when \(S\) involves many terms), the CLT may apply:
  $$
  S \approx \text{Normal}\left(E[S], \mathrm{Var}(S)\right).
  $$

---

## Premium Calculation Principles

- **Core Premium Principles:**
  - **Expected Value Principle (EVP):**  
    $$
    \pi(X)=(1+\theta)\,E[X].
    $$
  - **Variance Principle:**  
    $$
    \pi(X)=E[X]+\alpha\,\mathrm{Var}(X).
    $$
  - **Exponential (Esscher) Principle:**  
    $$
    \pi(X)=\frac{1}{\delta}\ln\left(E\left[e^{\delta X}\right]\right).
    $$
  - **Distortion/Wang Transform:** Applies a distortion to the survival function.

- **Parameter Sensitivity:**  
  Larger loadings produce higher premiums. Variance-based methods account for risk variability.

---

## No-Claims Discount Systems

- **Concept:**  
  Policyholders receive discounts on premiums for claim-free years.
- **Transition Rules:**  
  - Claim-free: move to a higher discount level (up to a maximum).
  - With a claim: move to a lower discount level (down to a base level).
- **Markov Chain Approach:**  
  Construct a transition matrix \(P\) and solve for the stationary distribution \(\pi\).  
  Then, the expected premium is:
  $$
  \text{Premium} = \sum_{i}\pi_i \cdot \text{(discount factor)} \times \text{Full Premium}.
  $$

---

## Claims Reserving (Run-Off Triangles)

- **Run-Off Triangle:**
  - Organized by accident year and development year.
- **Chain-Ladder Method:**
  - Calculate development factors:
    $$
    f_j=\frac{\sum_{\text{AY}} C_{\text{AY},j+1}}{\sum_{\text{AY}} C_{\text{AY},j}}.
    $$
  - Forecast ultimate claims by extending the triangle.
- **Bornhuetter–Ferguson Method:**  
  Combines a priori loss estimates with reported claims to estimate ultimate losses.

---

## Ruin Theory

- **Surplus Process Model:**  
  $$
  U(t)=u+ct-S(t),
  $$
  where \(u\) is initial surplus and \(c\) is premium rate.
- **Ruin Probability:**  
  Defined as:
  $$
  \psi(u)=\Pr\bigl(\tau<\infty \mid U(0)=u\bigr),
  $$
  where \(\tau=\inf\{t: U(t)<0\}\).
- **Lundberg Bound:**  
  $$
  \psi(u) \le e^{-Ru},
  $$
  with \(R\) (the adjustment coefficient) satisfying:
  $$
  \lambda(M_X(R)-1)=cR.
  $$

---

## Extreme Value Theory

- **Block Maxima (GEV):**  
  - Data is divided into blocks (e.g., years); maximum per block is modeled.
  - Convergence (by Fisher-Tippett theorem) to the GEV distribution:
    $$
    H_\xi(x)=\exp\left[-\left(1+\xi x\right)^{-1/\xi}\right].
    $$
- **Threshold Exceedances (GPD):**  
  - For values above a high threshold \(u\), the excess \(Y=X-u\) follows a GPD:
    $$
    G_{\xi,\beta}(y)=1-\left(1+\frac{\xi y}{\beta}\right)^{-1/\xi}, \quad y\ge0.
    $$

- **Tail Risk Measures:**  
  Value at Risk (VaR) and Expected Shortfall (ES) can be estimated using GPD.

---

## Copulas

- **Concept:**  
  Model the dependence structure among risks separate from marginals.
- **Sklar’s Theorem:**  
  For continuous marginals:
  $$
  F(x_1,x_2)=C\left(F_1(x_1),F_2(x_2)\right),
  $$
  where \(C\) is the unique copula function.
- **Common Copulas:**  
  - Independence: \(C(u_1,u_2)=u_1u_2\).
  - Comonotonicity: \(C(u_1,u_2)=\min\{u_1,u_2\}\).
  - Gaussian, Clayton, Gumbel, etc.
- **Tail Dependence:**  
  Calculate coefficients \( \lambda_U, \lambda_L \) to measure extreme co-movements.

---

## Credibility Theory

- **Bühlmann Model:**  
  Used to combine individual risk experience with collective data.
- **Basic Formulas:**
  - Overall mean: \( \mu = E[E(X|\Theta)] \).
  - Within-risk variance: \( \alpha = E[\mathrm{Var}(X|\Theta)] \).
  - Between-risk variance: \( \beta = \mathrm{Var}(E[X|\Theta]) \).
  - Credibility factor:  
    $$
    Z = \frac{n}{n + \frac{\alpha}{\beta}},
    $$
    and the credibility premium is:
    $$
    \hat{m} = Z\,\overline{X} + (1-Z)\,\mu.
    $$
- **Bühlmann–Straub:**  
  Extends Bühlmann’s ideas to handle different exposures.

---

## Exam Analysis

### General Tips:
- **Focus on MGFs:** Practice deriving means and variances from MGFs; they appear frequently.
- **Understand Compound Models:** Know the standard formulas (e.g., \(M_S(t)= M_N(\ln M_X(t))\)).
- **Practice Chain-Ladder:** Be comfortable calculating development factors and projecting ultimate claims.
- **Review Ruin Theory:** Understand how the adjustment coefficient \(R\) is obtained and how it relates to premium loading.
- **Familiarize with Copulas:** Know Sklar’s theorem and be comfortable with common copula types and their tail dependence properties.
- **Credibility:** Be ready for problems involving data from multiple risks over time and computing the credibility premium.

### Common Pitfalls:
- Incorrectly handling alignment in multi-line equations.
- Mixing up left, right, or centered text in table cells.
- Forgetting to check domain constraints for MGFs, especially for exponential or Pareto distributions.
- Neglecting to update both the mean and variance when switching from a fixed-\(n\) sum to a compound Poisson model.
- Overlooking parameterization differences in distributions (e.g., shape vs.\ rate or scale parameters).
