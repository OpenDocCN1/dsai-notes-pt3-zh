# Sequence-to-sequence language translation

+   - Sutskever, Vinyals, and Le NIPS 2014
+   - Model $P(Y_1,\dots,Y_T|X_1,\dots,X_T)$. The input and output sequences have different lengths, are not aligned, and even do not have monotonic relationship
+   - Use one LSTM to read the input sequence $(x_1,\dots,x_T)$, one timestep at a time, to obtain a large fixed-dimensional vector representation $v$, which is given by the last hidden state of the LSTM
+   - Then conditioned on $v$, a second LSTM generates the output sequence $(y_1,\dots,y_T)$ and computes its probability

$p(y_1,\dots,y_T|v)=\prod_{t=1}^{T'}p(y_t|v,y_1,\dots,y_{t-1})$

![](bbox=[0.05, 0.72, 0.95, 0.85])

The model reads an input sentence "ABC" and produces "WXYZ" as the output sentence. The model stops making predictions after outputting the end-of-sentence token.