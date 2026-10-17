# 3、含拒绝判决的最小损失准则

两类时：

p(\vec{x}|\omega_1) / p(\vec{x}|\omega_2) ≥ P(\omega_2)(1 - t) / [P(\omega_1) t]   \vec{x} ∈ \omega_1

p(\vec{x}|\omega_1) / p(\vec{x}|\omega_2) ≤ P(\omega_2) t / [P(\omega_1)(1 - t)]   \vec{x} ∈ \omega_2

P(\omega_2) t / [P(\omega_1)(1 - t)] < p(\vec{x}|\omega_1) / p(\vec{x}|\omega_2) < P(\omega_2)(1 - t) / [P(\omega_1) t]   拒绝

其中：

t = (λ_r - λ_c) / (λ_e - λ_c)

λ_r —— 拒绝损失

λ_e —— 误判损失

λ_c —— 正确判决损失