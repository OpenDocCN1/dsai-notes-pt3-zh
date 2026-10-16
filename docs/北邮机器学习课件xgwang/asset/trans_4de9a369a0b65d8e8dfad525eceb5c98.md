

## 序列到序列语言翻译

![](img/a04b187c89c5018c5ef6132980e27196_171_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_171_1.png)

该图显示了处理图中短语后得到的 LSTM 隐藏状态的二维 PCA 投影。短语按含义聚类，在这些示例中，这主要是一个词序的函数，这对于词袋模型来说很难捕捉。该图清楚地显示，表示对词序很敏感，而对主动语态替换为被动语态则相对不敏感。

## 序列到序列语言翻译

- LSTM 可以正确翻译非常长的句子

| 类型 | 句子 |
|------|----------|
| 我们的模型 | Ulrich UNK, membre du conseil d’administration du constructeur automobile Audi, affirme qu’il y a déjà une pratique courante depuis des années pour que les téléphones portables ne soient pas éteints, d’après la FCC. « Si l’innovation portait les antennes relais du constructeur automobile était qu’ils ne soient pas utilisés comme appareils d’écoute à distance. |
| 真实 | Ulrich Hackenberg, membre du conseil d’administration du constructeur automobile Audi, déclare que la collecte des téléphones portables avant les trajets du conseil, afin qu’ils ne soient pas utilisés comme appareils d’écoute à distance, est une pratique courante depuis des années. |
| 我们的模型 | « Les téléphones cellulaires, qui sont vraiment une question, non seulement parce qu’ils pourraient potentiellement causer des interférences avec les appareils de navigation, mais aussi parce qu’ils pourraient interférer avec les tours de téléphone cellulaire lorsqu’ils sont dans l’air », dit UNK. |
| 真实 | « Les téléphones portables sont véritablement un problème, non seulement parce qu’ils pourraient éventuellement créer des interférences avec les instruments de navigation, mais aussi parce qu’ils pourraient interférer avec les antennes relais de téléphone mobile si ils sont utilisés à bord », a déclaré Rosenber. |
| 我们的模型 | Avec la création, il y a un « sentiment de violence contre le corps d’un être cher » qui sera réduit à une pile de cendres », en très peu de temps, au lieu d’un processus de décomposition, qui accompagnera les phases du deuil. |
| 真实 | Il y a, avec la création, « une violence faite au corps aimé » qui va être « réduit à un tas de cendres » en très peu de temps, et non après un processus de décomposition, qui accompagnera les phases du deuil. |

## 生成图像描述

- Vinyals et al. arXiv 2014
- 使用 CNN 作为图像编码器并将其转换为固定长度向量
- 它被用作生成目标序列的“解码器”RNN 的初始隐藏状态

![](img/a04b187c89c5018c5ef6132980e27196_173_0.png)

## 生成图像描述

- 学习过程是最大化给定图像的正确描述的概率

θ* = arg max Σ_{(I,S)} log P(S|I; θ)

log P(S|I) = Σ_{t=0}^{N} log P(S_t | S_0, ..., S_{t-1})

I 是图像，S 是其正确描述

![](img/a04b187c89c5018c5ef6132980e27196_174_0.png)

## 生成图像描述

- 用 S₀ 表示特殊的起始词，用 S_N 表示特殊的停止词
- 图像和词都被映射到同一空间，图像通过使用 CNN，词通过使用词嵌入 W_e
- 图像 I 仅在 t = 1 时输入一次，以告知 LSTM 图像内容
- 采样：根据 P₁ 采样第一个词，然后提供相应的嵌入作为输入并采样 P₂，如此继续，直到采样到特殊的句末标记

x₋₁ = CNN(I)

x_t = W_e S_t, t ∈ {0, ..., N − 1}

P_{t+1} = LSTM(x_t), t ∈ {0, ..., N − 1}

L(I, S) = Σ_{t=1}^{N} log P_t(S_t)

## 将视频翻译为句子

- Venugopalan et al. arXiv 2014
- 挑战在于捕捉帧序列和对应词序列的联合依赖
- 以往的工作通过检测一组固定的语义角色作为中间表示来简化问题，例如主语、动词和宾语，并采用过度简化的僵化句子模板。

输入视频：

![](img/a04b187c89c5018c5ef6132980e27196_176_0.png)

机器输出：A cat is playing with toy.

人类：A Ferret and cat fighting with each other. / A cat and a ferret are playing. / A kitten and a ferret are playfully wrestling.

