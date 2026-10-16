# Evidence

+   - If evidence, start with factors that select that evidence
+     - No evidence uses these initial factors:
+       $P(R)$
+       | +r | 0.1 |
+       | -r | 0.9 |
+       $P(T|R)$
+       | +r | +t | 0.8 |
+       | +r | -t | 0.2 |
+       | -r | +t | 0.1 |
+       | -r | -t | 0.9 |
+       $P(L|T)$
+       | +t | +l | 0.3 |
+       | +t | -l | 0.7 |
+       | -t | +l | 0.1 |
+       | -t | -l | 0.9 |

+   - Computing $P(L|+r)$, the initial factors become:
+     $P(+r)$
+     | +r | 0.1 |
+     $P(T|+r)$
+     | +r | +t | 0.8 |
+     | +r | -t | 0.2 |
+     $P(L|T)$
+     | +t | +l | 0.3 |
+     | +t | -l | 0.7 |
+     | -t | +l | 0.1 |
+     | -t | -l | 0.9 |

+   - We eliminate all vars other than query + evidence

![](bbox=[0.62, 0.27, 1.0, 0.92])