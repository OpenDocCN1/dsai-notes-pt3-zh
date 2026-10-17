# # 问题求解

例 已知：张和李是同班同学。如果x和y是同班同学，则x的教室也是y的教室现在张在302教室上课。

问：现在李在哪里上课？

解：定义谓词：

C(x,y) x和y是同班同学 At(x, u) x在u教室上课

已知前提用谓词公式表示， 并化为子句集：

C(zhang, li) C(zhang, li)

(∀x)(∀y)(∀u)(C(x,y)^At(x,u)→At(y,u))

~(C(x,y) ^ At(x,u))∨At(y,u) ~C(x,y)∨~At(x,u)∨At(y,u)

At(zhang、 302) At(zhang、 302)