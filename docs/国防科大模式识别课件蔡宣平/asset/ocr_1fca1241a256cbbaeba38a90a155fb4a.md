当n较大时，S_W通常是非奇异的，于是有：
S_W^{-1} S_B \vec{u} = \lambda \vec{u}

上式表明，\vec{u} 是矩阵 S_W^{-1} S_B 相应于特征值λ的特征向量。对于两类问题，S_B 的秩为1，因此，S_W^{-1} S_B 只有一个非零特征值，其所对应的特征向量 \vec{u} 称为Fisher最佳鉴别向量，由上式可得：

\lambda \vec{u} = S_W^{-1} S_B \vec{u} = S_W^{-1} (\vec{m}_1 - \vec{m}_2)(\vec{m}_1 - \vec{m}_2)' \vec{u}