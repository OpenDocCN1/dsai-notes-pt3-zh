# 运输量—运输距离—运输费率—重心法

（2）第一次迭代计算

+   1）将求出的D i代入下式, 求出仓库的新位置

$X = \frac{\sum_i Q_i R_i X_i / D_i}{\sum_i Q_i R_i / D_i} \quad Y = \frac{\sum_i Q_i R_i Y_i / D_i}{\sum_i Q_i R_i / D_i}$

+   2）将求出的仓库新位置（X, Y）带入下式求出仓库新位置到各客户的距离Di

$D_i = [(X_i - X)^2 + (Y_i - Y)^2]^{1/2}$

+   3）由下式求出仓库建在新位置时的总运输成本

$C = \sum_i Q_i R_i D_i$