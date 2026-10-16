# Möbius反演的应用

m^n = Σ_{d|n} d·M(d)

利用 Möbius 反演公式：f(n)= Σ_{d|n} g(d) ↔ g(n)= Σ_{d|n} μ(d) f(n/d)

令 f(n)=m^n， g(n)=n·M(n)，得

g(n)= Σ_{d|n} μ(d) f(n/d)

即

n·M(n)= Σ_{d|n} μ(d) m^{n/d} ⇒ M(n)= 1/n Σ_{d|n} μ(d) m^{n/d}

它表示以n为周期的n可重圆排列的个数。