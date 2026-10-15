# Association Rule Mining Task

+   Given a set of transactions T, the goal of association rule mining is to find all rules having
+   - support ≥ minsup threshold
+   - confidence ≥ minconf threshold

+   Brute-force（蛮力、暴力）approach:
+   - List all possible association rules
+   - Compute the support and confidence for each rule
+   - Prune rules that fail the minsup and minconf thresholds
+   ⇒ Computationally prohibitive（禁止的、过高的）！