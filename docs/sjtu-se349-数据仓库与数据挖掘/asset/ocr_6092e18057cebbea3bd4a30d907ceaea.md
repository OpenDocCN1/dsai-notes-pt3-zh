# （2）模糊矩阵的合成

定义：设 $A = (a_{ij})_{m\times s}, B = (b_{ij})_{s\times n}$，称模糊矩阵

$A \circ B = (c_{ij})_{m\times n}$

为 $A$ 与 $B$ 的合成，其中 $c_{ij} = \bigvee_{k=1}^{s} (a_{ik} \land b_{kj})$。

即： $C = A \circ B \Leftrightarrow c_{ij} = \bigvee_{k=1}^{s} (a_{ik} \land b_{kj})$

定义：设 $A$ 为 $n\times n$ 阶，则模糊方阵的幂定义为

$A^2 = A \circ A, A^3 = A^2 \circ A, \dots, A^n = A^{n-1} \circ A$