# Similarity Measure (I):
Geodesic Distance测地距

![](bbox=[0.78, 0.05, 0.95, 0.25])

+   Geodesic distance (A, B): length (i.e., # of edges) of the shortest path between A and B (if not connected, defined as infinite无穷大)

+   Eccentricity离心率 of v, eccen(v): The largest geodesic distance between v and any other vertex u ∈ V − {v}. 捕获了v与图中最近的顶点的远近程度

+   E.g., eccen(a) = eccen(b) = 2; eccen(c) = eccen(d) = eccen(e) = 3

+   Radius of graph G图G的半径: The minimum eccentricity of all vertices, i.e., the distance between the “most central point” and the “farthest border”捕获了图中“最靠近中心的点”与“最远边界”之间的距离

+   r = min_{v∈V} eccen(v)

+   E.g., radius (g) = 2

+   Diameter of graph G: The maximum eccentricity of all vertices, i.e., the largest distance between any pair of vertices in G

+   d = max_{v∈V} eccen(v)

+   E.g., diameter (g) = 3

+   A peripheral vertex 外围顶点 is a vertex that achieves the diameter.

+   E.g., Vertices c, d, and e are peripheral vertices.