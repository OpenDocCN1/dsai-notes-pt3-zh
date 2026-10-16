# 3. 4. 5归结演绎推理的方法

归结演绎推理的经典例子

再将问题用谓词表示如下：
“ 任何通过计算机考试并获奖的人都是快乐的 ”
(∀x)(Pass(x, computer)∧Win(x, prize)→Happy(x))
“ 任何肯学习或幸运的人都可以通过所有考试 ”
(∀x)(∀y)(Study(x)∨Lucky(x)→Pass(x, y))
“ 张不肯学习但他是幸运的 ”
¬Study(zhang)∧Lucky(zhang)
“ 任何幸运的人都能获奖 ”
(∀x)(Lucky(x)→Win(x, prize))

结论 “ 张是快乐的 ” 的否定
¬Happy(zhang)