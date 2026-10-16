# Apriori类算法问题

+   - 瓶颈: candidate-generation-and-test
+     - Mining long patterns needs many passes of scanning
+     - generates lots of candidates
+       - 10⁴ frequent 1-itemset will generate 10⁷ candidate 2-itemsets
+       - To find frequent itemset i₁i₂...i₁₀₀
+         - # of scans: **100**
+         - # of Candidates: \(\binom{100}{1}+\binom{100}{2}+...+\binom{100}{100}=2^{100}-1=1.27*10^{30}!\)

![](bbox=[0.224, 0.839, 0.8, 0.936])