# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p29 29_04_01_模块4-导论-启发式搜索.zh_en -BV16f421Q72q_p29-

We can often find a solution to a search problem more quickly if we have some knowledge about approximately how close we are to a goal state。

Informed search algorithms are algorithms that incorporate this kind of heuristic knowledge about the remaining distance to a goal。

We'll see that informed search algorithms often are able to find a solution。

More quickly than uninformed search algorithms are。We'll see that some informed search algorithms。

 which incorporate this heuristic information naively can find solutions。

 but ones that aren't necessarily the optimal solutions。For instance。

 we'll see that a greedy search algorithm will often arrive at a solution faster than uninformed search。

 but that that solution is not guaranteed to be optimal。In this module。

 we'll look at the most famous informed search algorithm called a star search。

 which is able to guarantee that it will return the optimal solution first。

A star achieves this remarkable result by putting constraints on what kind of heuristic knowledge you can incorporate into it。

A star search requires an admissible heuristic。 An admissible heuristic is one that guarantees that you will never overestimate the remaining distance to the goal。

And in doing so， a star search is an optimal algorithm that will return the optimal solution first。

