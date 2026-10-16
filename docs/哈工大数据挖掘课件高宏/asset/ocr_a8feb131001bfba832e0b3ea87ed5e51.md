# Algorithm--- Sequence Phase

+   - AprioriAll

```
L₁ = {large 1-sequences}; // Result of the phase
for ( k=2; Lₖ₋₁ ≠ ∅; k++ ) do
  begin
  Cₖ = New candidate generate from Lₖ₋₁
  foreach customer-sequence c in the database do
    Increment the count of all candidates in Cₖ that are contained in c
  Lₖ = Candidates in Cₖ with minimum support.
End
Answer=Maximal Sequences in Uₖ Lₖ;
```