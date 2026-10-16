# 空间数据挖掘

+   - 空间关联规则
+     - 形如A=>B [s%, c%]，其中A和B是空间和非空间谓词的集合
+     - 例如，
+       is_a(X, “school”)∧close_to(X, “sports_center”)=>
+       close_to(X, “park”) [0.5%, 80%]