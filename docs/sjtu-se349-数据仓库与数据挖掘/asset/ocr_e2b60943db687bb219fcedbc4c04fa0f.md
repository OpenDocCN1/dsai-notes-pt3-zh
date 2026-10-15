# 算法方法的距离度量

+   - 4个广泛采用的簇间距离度量方法：
+   - 最小距离： $dist_{min}(C_i, C_j) = \min_{p \in C_i, p' \in C_j} \{ |p - p'| \}$
+   - 最大距离： $dist_{max}(C_i, C_j) = \max_{p \in C_i, p' \in C_j} \{ |p - p'| \}$
+   - 均值距离： $dist_{mean}(C_i, C_j) = |m_i - m_j|$
+   - 平均距离： $dist_{avg}(C_i, C_j) = \frac{1}{n_i n_j} \sum_{p \in C_i, p' \in C_j} |p - p'|$
+   - 其中 $|p - p'|$ 是两个对象或点 $p$ 和 $p'$ 之间的距离， $m_i$ 是簇 $C_i$ 的均值， $n_i$ 是簇 $C_i$ 中对象的数目
+   - 这些度量又称为连接度量