# Bidirectional RNNs

+   - In some applications, we want to output at time t a prediction regarding an output which may depend on the whole input sequence
+     - In speech recognition, the correct interpretation of the current sound as a phoneme may depend on the next few phonemes because co-articulation and may depend on the next few words because of the linguistic dependencies between words
+   - Bidirectional recurrent neural network was proposed to address such need
+   - It combines a forward-going RNN and a backward-going RNN
+   - The idea can be extended to 2D input with four RNN going in four directions