# C4.5分类算法
算例

第三步：计算确定最佳划分根节点3个分支的决策属性，即哪些属性分别用来最佳划分根节点的sunny、overcast、rain分支

+   - 最后对outlook的rain分支建立子树
+     - 找出样本数据集weather中outlook取值rain的样本子集Srain
+     - 依次计算剩下两个属性对该样本子集Srain划分后的信息增益率
+     - 建立rain分支子树

应该改为三个

![](bbox=[0.68, 0.45, 0.92, 0.68])

weather 数据集中 outlook 取值为 rain 的数据子集 Srain

| outlook | temperature | humidity | wind | play ball |
|---|---|---|---|---|
| rain | mild | high | weak | yes |
| rain | cool | normal | weak | yes |
| rain | cool | normal | strong | no |
| rain | mild | normal | weak | yes |
| rain | mild | high | strong | no |