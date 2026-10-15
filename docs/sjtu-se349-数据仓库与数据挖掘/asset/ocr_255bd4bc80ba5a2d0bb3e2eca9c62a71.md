# 顺序覆盖算法

Input:

+   - **D**, a data set of class-labeled tuples;
+   - **Att vals**, the set of all attributes and their possible values.

Output: A set of IF-THEN rules.

Method:

```
(1) Rule set D fg; // initial set of rules learned is empty
(2) for each class c do
(3) repeat
(4) Rule D Learn One Rule(D, Att vals, c);
(5) remove tuples covered by Rule from D;
(6) Rule set D Rule set CRule; // add new rule to rule set
(7) until terminating condition;
(8) endfor
(9) return Rule Set;
```