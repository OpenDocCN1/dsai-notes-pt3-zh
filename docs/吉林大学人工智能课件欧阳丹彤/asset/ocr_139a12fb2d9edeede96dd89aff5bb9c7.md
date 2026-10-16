# 例. 将公式∀x∀y（A(x)→B(x,y)）→(∃yC(y)→∃zD(z))化为前束范式。

解：（1）消去→联结词。
∀x∀y（A(x)→B(x,y)）→(∃yC(y)→∃zD(z))
= ∼∀x∀y（∼A(x)∨B(x,y)）∨（∼∃yC(y)∨∃zD(z))
（2）将公式中所有否定号∼放在原子之前。
∼∀x∀y（∼A(x)∨B(x,y)）∨（∼∃yC(y)∨∃zD(z))
= ∃x∃y(A(x)∧∼B(x,y))∨(∀y∼C(y)∨∃zD(z))
（3）将约束变量改名.
∃x∃y(A(x)∧∼B(x,y))∨(∀y∼C(y)∨∃zD(z))
= ∃x∃y(A(x)∧∼B(x,y))∨(∀t∼C(t)∨∃zD(z))
（4）将量词提到整个公式前。
∃x∃y(A(x)∧∼B(x,y))∨(∀t∼C(t)∨∃zD(z))
= ∃x∃y∀t∃z（（A(x)∧∼B(x,y))∨∼C(t)∨D(z)）
= ∃x∃y∀t∃z((A(x)∨∼C(t)∨D(z))∧(∼B(x,y)∨∼C(t)∨D(z)))