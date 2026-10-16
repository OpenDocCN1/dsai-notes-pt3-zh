# Data parallelism

+   - The mini-batch is split across several GPUs. Each GPU is responsible computing gradients with respect to all model parameters, but does so using a subset of the samples in the mini-batch
+   - The model (parameters) has a complete (same) copy in each GPU
+   - The gradients computed from multiple GPUs are averaged to update parameters in both GPUs

![](bbox=[0.35, 0.52, 0.68, 0.85])