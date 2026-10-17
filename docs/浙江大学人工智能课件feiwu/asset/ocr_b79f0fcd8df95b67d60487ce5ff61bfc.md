# Breadth-first search: another version

`generalSearch(problem, queue)`

# of nodes tested: 7, expanded: 6

| expnd. node | nodes list |
|---|---|
|  | {S} |
| S | {A,B,C} |
| A | {B,C,D,E} |
| B | {C,D,E,G} |
| C | {D,E,G,F} |
| D | {E,G,F,H} |
| E | {G,F,H,G} |
| G goal | {F,H,G} no expand |

![](bbox=[0.502, 0.271, 0.882, 0.814])