# # The general EM algorithm

+   - The log likelihood of a discrete latent variables model:
+   
+   \(\ln p(X|\theta) = \ln \left\{ \sum_Z p(X, Z|\theta) \right\}\)

+   - The goal of EM algorithm is to find maximum likelihood solution for models having latent variables.

+   - For the complete data set {X, Z}, the log likelihood function:
+   
+   \(\ln p(X|\theta) \longrightarrow \ln p(X, Z|\theta)\)

+   - For the incomplete data set {X}, we adopt the following steps to find maximum likelihood solution:
+   
+   \(\theta^{old} \longleftarrow \theta^{new} = \arg \max_\theta Q(\theta, \theta^{old})\)
+   
+   \(\downarrow\)
+   
+   \(p(Z|X, \theta^{old}) \longrightarrow E_Z[\ln p(X, Z|\theta)] = \sum_Z p(Z|X, \theta^{old}) \ln p(X, Z|\theta) = Q(\theta, \theta^{old})\)