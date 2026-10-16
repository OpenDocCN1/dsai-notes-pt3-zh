# 无序分拆

我们用 $B(n,k)$ 来表示 $n$ 的 $k$ 分拆的个数，用 $B(n)$ 表示 $n$ 的所有分拆的个数，则显然有

（1） $B(n,k)=0(k>n)$；
（2） $B(n)=\sum_{k=1}^{n} B(n,k)$

$n$ 的 $k$ 分拆中，各分部量的次序无关紧要，一般按递降顺序排列，若 $n=n_1+n_2+\cdots+n_k$ 则 $n_1\ge n_2\ge\cdots\ge n_k$

如果在 $n$ 的 $k$ 分拆中有 $k_i$ 个分部量为 $i(1\le i\le n)$，那么可以把该分拆记为 $n=k_1\cdot1+k_2\cdot2+\cdots+k_n\cdot n$，有时也记为 $n=1^{k_1}2^{k_2}\cdots n^{k_n}$