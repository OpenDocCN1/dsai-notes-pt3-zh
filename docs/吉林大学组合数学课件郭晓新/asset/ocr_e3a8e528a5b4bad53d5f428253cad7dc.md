# # 容斥原理

3.40 证明: (1) B(m,2)= \left\lfloor \frac{m}{2} \right\rfloor (2) 当 m ≡ 0 (mod 6) 时, 有 B(m,3) = \frac{m^{2}}{12}.



(2) 用数学归纳法

+   ① 当 m=6 时, B(6,3)=B(3,1)+B(3,2)+B(3,3)=1+1+1=3=6^{2}/12

+   ② 设当 m=6k 时, B(m,3)=B(6k,3)= \frac{(6k)^{2}}{12} = 3k^{2}

+   ③ 当 m=6k+6 时, B(6k+6,3)=B(6k+3,3)= B(6k+3,1)+ B(6k+3,2)+ B(6k+3,3)

=1 + \left\lfloor \frac{6k+3}{2} \right\rfloor + B(6k+1)+B(6k+2)+B(6k,3)=1+3k +1 +1 + \left\lfloor \frac{6k}{2} \right\rfloor + B(6k,3)

=1+3k+1+1+3k +3k^{2} =3+6k+3k^{2}=3(k+1)^{2}=\frac{(6(k+1))^{2}}{12}