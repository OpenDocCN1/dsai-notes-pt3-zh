# ## 2. 多条知识支持同一结论时，结论不确定性的合成计算

设有如下知识

IF E₁ THEN H (CF(H, E₁)) IF E₂ THEN H (CF(H, E₂))

则结论H的综合可信度CF₁₂(H)：

1) 分别计算每一条知识的CF₁(H)和CF₂(H)：

CF₁(H)=CF(H, E₁) × max{0, CF(E₁)}

CF₂(H)=CF(H, E₂) × max{0, CF(E₂)}

2) E₁与E₂对结论H的综合影响所形成的可信度CF₁₂(H)

CF₁(H) + CF₂(H) – CF₁(H)×CF₂(H) ; 若CF₁(H) ≥ 0 ^ CF₂(H) ≥ 0

CF₁(H) + CF₂(H) + CF₁(H)×CF₂(H) ; 若CF₁(H) < 0 ^ CF₂(H) < 0

[CF₁(H) + CF₂(H)] / [1 - min(|CF₁(H)|, |CF₂(H)|)] ; 其他