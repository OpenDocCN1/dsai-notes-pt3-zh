# Sequence-to-sequence language translation

+   It requires each sentence ends with a special end-of-sequence symbol "<EOS>", which enables the model to define a distribution over sequences of all possible lengths

+   It is valuable to reverse the order of the words of the input sequence. For example, instead of mapping the sentence a, b, c to the sentence α, β, γ, the LSTM is asked to map c, b, a to α, β, γ, where α, β, γ is the translation of a, b, c. This way, a is in close proximity to α, b is fairly close to β, and so on, a fact that makes it easy for stochastic gradient descent to "establish communication" between the input and the output. It introduces many short term dependencies in the data that make the optimization problem much easier.