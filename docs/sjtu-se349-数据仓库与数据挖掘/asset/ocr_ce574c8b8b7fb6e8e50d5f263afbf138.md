# Apriori实现

+   如何生成候选项集？
+   —Step 1: 连接步 L_k
+   —Step 2: 剪枝步

+   Example of Candidate-generation
+   —L₃={abc, abd, acd, ace, bcd}
+   —Self-joining: L₃*L₃
+     • abcd from abc and abd
+     • acde from acd and ace
+   —Pruning:
+     • acde is removed because ade is not in L₃
+   —C₄ = {abcd}