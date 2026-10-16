# Apriori算法流程

Input: DB: database of transactions; min_sup: minimum support threshold

Output: L: frequent itemsets in DB

Method:

+   1. C₁ = Itemsets of size one in I;
+   2. Determine all frequent itemsets of size 1, L₁;
+   3. i = 1;
+   4. Repeat
+   5. i = i + 1;
+   6. Cᵢ = Apriori-Gen(Lᵢ₋₁);
+   7. Count Cᵢ to determine Lᵢ;
+   8. until no more frequent itemsets found;