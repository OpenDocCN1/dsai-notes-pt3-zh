# # Maximum likelihood solution for two classes

\(\ln p(\mathbf{t}|\pi,\mu_1,\mu_2,\Sigma)=\sum_{n=1}^N\{t_n\ln\pi+(1-t_n)\ln(1-\pi)+t_n\ln\mathcal{N}(\mathbf{x}_n|\mu_1,\Sigma)+(1-t_n)\ln\mathcal{N}(\mathbf{x}_n|\mu_2,\Sigma)\}\)

+   - **Solve** \(\pi\):
+   
+   \(\sum_{n=1}^N\{t_n\ln\pi+(1-t_n)\ln(1-\pi)\} \implies \pi=\frac{1}{N}\sum_{n=1}^N t_n=\frac{N_1}{N}=\frac{N_1}{N_1+N_2}\)

+   - **Solve** \(\mu_1, \mu_2\):
+   
+   \(\sum_{n=1}^N t_n \ln \mathcal{N}(\mathbf{x}_n|\mu_1, \Sigma) = -\frac{1}{2}\sum_{n=1}^N t_n(\mathbf{x}_n-\mu_1)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_1) + \text{const}\)
+   
+   \(\implies \mu_1 = \frac{1}{N_1}\sum_{n=1}^N t_n \mathbf{x}_n \qquad \mu_2 = \frac{1}{N_2}\sum_{n=1}^N (1-t_n)\mathbf{x}_n\)

+   - **Solve** \(\Sigma\):
+   
+   \(-\frac{1}{2}\sum_{n=1}^N t_n \ln |\Sigma| - \frac{1}{2}\sum_{n=1}^N t_n(\mathbf{x}_n-\mu_1)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_1)\)
+   
+   \(-\frac{1}{2}\sum_{n=1}^N (1-t_n) \ln |\Sigma| - \frac{1}{2}\sum_{n=1}^N (1-t_n)(\mathbf{x}_n-\mu_2)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_2) = -\frac{N}{2} \ln |\Sigma| - \frac{N}{2} \text{Tr}\{\Sigma^{-1}\mathbf{S}\}\)
+   
+   \(\mathbf{S} = \frac{N_1}{N}\left[\frac{1}{N_1}\sum_{n \in \mathcal{C}_1} (\mathbf{x}_n-\mu_1)(\mathbf{x}_n-\mu_1)^\mathrm{T}\right] + \frac{N_2}{N}\left[\frac{1}{N_2}\sum_{n \in \mathcal{C}_2} (\mathbf{x}_n-\mu_2)(\mathbf{x}_n-\mu_2)^\mathrm{T}\right] \implies \Sigma = \mathbf{S}\)