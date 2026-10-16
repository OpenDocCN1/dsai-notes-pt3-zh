# Worst Case Complexity?

+   - CSP:

(x₁ ∨ x₂ ∨ ¬x₃) ∧ (¬x₁ ∨ x₃ ∨ ¬x₄) ∧ (x₂ ∨ ¬x₂ ∨ x₄) ∧ (¬x₃ ∨ ¬x₄ ∨ ¬x₅) ∧ (x₂ ∨ x₅ ∨ x₇) ∧ (x₄ ∨ x₅ ∨ x₆) ∧ (¬x₅ ∨ x₆ ∨ ¬x₇) ∧ (¬x₅ ∨ ¬x₆ ∨ x₇)

P(Xᵢ = 0) = P(Xᵢ = 1) = 0.5

Y₁ = X₁ ∨ X₂ ∨ ¬X₃

...

Y₈ = ¬X₅ ∨ X₆ ∨ X₇

Y₁,₂ = Y₁ ∧ Y₂

...

Y₇,₈ = Y₇ ∧ Y₈

Y₁,₂,₃,₄ = Y₁,₂ ∧ Y₃,₄

Y₅,₆,₇,₈ = Y₅,₆ ∧ Y₇,₈

Z = Y₁,₂,₃,₄ ∧ Y₅,₆,₇,₈

![](bbox=[0.28, 0.28, 0.97, 0.88])

+   - If we can answer P(z) equal to zero or not, we answered whether the 3-SAT problem has a solution.

+   - Hence inference in Bayes’ nets is NP-hard. No known efficient probabilistic inference in general.