# Problem with the frequent pattern mining algorithm

+   - Given a database :
+     - DB={(a₁,a₂,...,a₁₀₀),(a₁,a₂,...,a₅₀)}
+     - The min_support = 1, and the min_conf= 50%
+   - The traditional association mining will generate 2¹⁰⁰-1≈10³⁰ frequent itemsets:
+     - (a₁), (a₂),..., (a₁₀₀),
+     - (a₁,a₂), (a₂,a₃),..., (a₉₉,a₁₀₀),
+     - ...,
+     - (a₁,a₂,...,a₁₀₀)
+     - and tremendous number of association rules.

Too many frequent patterns if the support threshold is low!