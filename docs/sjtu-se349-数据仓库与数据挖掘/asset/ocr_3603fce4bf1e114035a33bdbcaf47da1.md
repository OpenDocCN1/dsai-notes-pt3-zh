# 规则质量度量 Cont.

+   - FOIL的基于信息增益的度量
+   - 在机器学习中，用于学习规则的类的元组称为正元组，其余元组为负元组
+   - 设pos(neg)为R覆盖的正（负）元组数，pos’(neg’)为R’覆盖的正（负）元组数
+   - 用下式估计扩展condition’而获得的信息
+   
+     FOIL_Gain = pos’ × (log₂ pos’/(pos’+neg’) − log₂ pos/(pos+neg))
+   - 偏向于具有高准确率并且覆盖许多正元组的规则