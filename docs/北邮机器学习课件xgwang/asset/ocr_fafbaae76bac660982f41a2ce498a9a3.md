# Drawbacks of data parallelism

+   - Require considerable communication between GPUs, since each GPU must communicate both gradients and parameter values on every update step
+   - Each GPU must use a large number of samples to effectively utilize the highly parallel device; thus, the mini-batch size effectively gets multiplied by the number of GPUs, hampering convergence