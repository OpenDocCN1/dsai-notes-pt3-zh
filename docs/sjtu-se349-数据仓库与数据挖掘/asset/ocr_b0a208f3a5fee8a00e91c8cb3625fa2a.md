# 模式增长方法的优势

+   - 分而治之：
+     - 根据至今为止获得的频繁模式分解挖掘任务和数据库
+   - 其他因素
+     - 没有候选集的生成和测试
+     - FP-tree structure压缩数据库
+     - 没有对整个database 的重复扫描
+     - Basic ops: 计算本地频繁项，构建子树。没有模式的搜索和匹配
+   - A good open-source implementation and refinement of FPGrowth
+     - FPGrowth+ (Grahne and J. Zhu, FIMI'03)