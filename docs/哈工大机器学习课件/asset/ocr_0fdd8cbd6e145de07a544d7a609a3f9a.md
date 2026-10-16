# FOIL中的候选特化式的生成
（2）

+   - 举例：待学习的规则的目标文字是GrandDaughter(x,y)，即 GrandDaughter(x,y)←
+     - 生成下列候选文字
+       - Equal(x,y)
+       - Female(x)
+       - Female(y)
+       - Father(x,y)
+       - Father(y,x)
+       - Father(x,z)
+       - Father(y,z)
+       - Father(z,y)
+       - 上面文字的否定
+     - 假定FOIL贪婪地选择了Father(y,z)作为最有希望的文字，得到一个较特殊的规则
+       GrandDaughter(x,y)←Father(y,z)