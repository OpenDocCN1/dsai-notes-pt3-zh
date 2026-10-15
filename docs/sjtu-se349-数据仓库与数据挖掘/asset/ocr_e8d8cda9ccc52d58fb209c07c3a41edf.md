# Semi-Supervised Learning Methods

+   - Many methods exist: EM with generative mixture models, self-training, co-training, data-based methods, transductive SVM, graph-based methods, ...
+   - Inductive methods and Transductive methods
+     - Transductive methods: only label the available unlabeled data – not generating a classifier
+     - Inductive methods: not only produce labels for unlabeled data, but also generate a classifier
+   - Algorithmic methods
+     - Classifier-based methods: start from an initial classifier, and iteratively enhance it
+     - Data-based methods: find an inherent geometry in the data, and use the geometry to find a good classifier