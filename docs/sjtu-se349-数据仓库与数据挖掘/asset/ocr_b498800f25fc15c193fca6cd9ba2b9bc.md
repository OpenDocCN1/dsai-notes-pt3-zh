# CHAMELEON的相似度计算

+   - **Relative Inter-connectivity (RI)** 相对互联度

$$RI(C_i,C_j)=\frac{|EC_{\{C_i,C_j\}}|}{\frac{|EC_{C_i}|+|EC_{C_j}|}{2}}$$

+   - **Relative closeness (RC)** 相对接近度

$$RC(C_i,C_j)=\frac{\overline{S}_{EC_{\{C_i,C_j\}}}}{\frac{|C_i|}{|C_i|+|C_j|}\overline{S}_{EC_{C_i}}+\frac{|C_j|}{|C_i|+|C_j|}\overline{S}_{EC_{C_j}}}$$

+   - **注：**

$$EC_{\{C_i,C_j\}}$$ 是包含 Ci 和 Cj 的簇的边割

$$\overline{S}_{EC_{C_i}}$$ 和 $$\overline{S}_{EC_{C_j}}$$ 是最小二分簇的边的平均权重

$$\overline{S}_{EC_{\{C_i,C_j\}}}$$ 是链接Ci顶点和Cj顶点的边的平均权重

> > 边割最小
> > 簇C被划分成子簇 Ci 和 Cj，使得把C二分成Ci 和Cj而被切断的边的权重之和最小。