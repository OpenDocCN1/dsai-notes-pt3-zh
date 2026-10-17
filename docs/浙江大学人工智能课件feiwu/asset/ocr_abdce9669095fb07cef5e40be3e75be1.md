# # The Bias-Variance Decomposition

+   - We have: \(\mathbb{E}[L] = \iint L(t, y(x))p(x, t) \, dx \, dt = \iint \{y(x) - t\}^2 p(x, t) \, dx \, dt\)
+     \(\{y(x) - t\}^2 = \{y(x) - \mathbb{E}[t|x] + \mathbb{E}[t|x] - t\}^2\)
+     \(= \{y(x) - \mathbb{E}[t|x]\}^2 + 2\{y(x) - \mathbb{E}[t|x]\}\{\mathbb{E}[t|x] - t\} + \{\mathbb{E}[t|x] - t\}^2\)
+     \(\Rightarrow \mathbb{E}[L] = \int \{y(x) - \mathbb{E}[t|x]\}^2 p(x) \, dx + \int \{\mathbb{E}[t|x] - t\}^2 p(x) \, dx\)

+   - Let : \(h(x) = \mathbb{E}[t|x] = \int t p(t|x) \, dt\)
+     \(\Rightarrow \mathbb{E}[L] = \int \{y(x) - h(x)\}^2 p(x) \, dx + \int \{h(x) - t\}^2 p(x, t) \, dx \, dt\)

+   - For data set \(\mathcal{D}\): \(\{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] + \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2\)
+     \(= \{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}^2 + \{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2\)
+     \(+2\{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}\{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}\)
+     \(\Rightarrow \mathbb{E}_\mathcal{D} \left[ \{y(x; \mathcal{D}) - h(x)\}^2 \right]\)
+     \(= \underbrace{\{\mathbb{E}_\mathcal{D}[y(x; \mathcal{D})] - h(x)\}^2}_{(\text{bias})^2} + \underbrace{\mathbb{E}_\mathcal{D} \left[ \{y(x; \mathcal{D}) - \mathbb{E}_\mathcal{D}[y(x; \mathcal{D})]\}^2 \right]}_{\text{variance}}\)

![](bbox=[0.03, 0.68, 0.18, 0.74])