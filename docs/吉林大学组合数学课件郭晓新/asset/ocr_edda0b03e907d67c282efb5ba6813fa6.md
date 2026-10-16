# 多重集的 r-组合数

先计算 $|A_1|$, $|A_2|$ 和 $|A_3|$。$|A_1|$ 中的每个 10-组合至少含有 4 个 $a$，把这 4 个 $a$ 拿走就得到 $T$ 的一个 6-组合。反之，对 $T$ 的任意一个 6-组合加上 4 个 $a$ 就得到 $|A_1|$ 中的一个 10-组合。所以 $|A_1|$ 就是 $T$ 的 6-组合数，即

$|A_1| = \begin{pmatrix} 3+6-1 \\ 5 \end{pmatrix} = \begin{pmatrix} 8 \\ 6 \end{pmatrix} = \begin{pmatrix} 8 \\ 2 \end{pmatrix} = 28,$

$|A_2| = \begin{pmatrix} 3+5-1 \\ 5 \end{pmatrix} = \begin{pmatrix} 7 \\ 5 \end{pmatrix} = \begin{pmatrix} 7 \\ 2 \end{pmatrix} = 21,$

$|A_3| = \begin{pmatrix} 3+4-1 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 \\ 2 \end{pmatrix} = 15$