# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p40 Recitation_HW2.zh_en -BV1Z2cUefE4A_p40-

Hey， guys。Cool， welcome to class。 Okay， this is recitation 2 and this homework。

 as I'm sure you guys all know， is about decision trees。 So we'll start with a little bit of。😊。



![](img/cfb8fc811311cce0a32c27eb65612cf8_1.png)

Like an introduction into like tree structures and algorithms。



![](img/cfb8fc811311cce0a32c27eb65612cf8_3.png)

Okay， let's start with a couple definitions here。 So does anyone know what the depth of a tree is。



![](img/cfb8fc811311cce0a32c27eb65612cf8_5.png)

Yeah， so in other terms， it's。The link。Of the longest path。From。The root node。Qu。

The furthest leaf node。And also， we determine the length by the number of edges。 right。

 So let's consider maybe。An example。That looks like this。Right？With any tree。

 you'll be able to find a root， in this case， let's call this the root。

And a leaf is any node with no children， and so in this example， this node。

 this node and this node would all be leaves。Right。

If the depth of a tree is the length of the longest path from the root node to the furthest leaf node。

 then this node down here， that would be our furthest leaf node。

 and then we can count the edges between the root and that leaf， which is one，2， three。

 so the height of this tree would be three。Cool， okay。

 so the definition of the depth of a node is similar to that of the depth of a tree。So we have here。

 it's the link。Of the path。From。The root node。To the given node。So if we take that same example。

Right again， here we have our root node。If we're looking for the depth of let's say this node， right。

 we can find the length of the path。From the root to that node， and we have one， two edges。

 so this specific node has height 2， right？

![](img/cfb8fc811311cce0a32c27eb65612cf8_7.png)

And if we're looking at the root node itself。

![](img/cfb8fc811311cce0a32c27eb65612cf8_9.png)

There are no edges between the root node and itself， so it would have height zero or depth zero。

Any questions？Sorry。

![](img/cfb8fc811311cce0a32c27eb65612cf8_11.png)

Okay， yeah， sure。

![](img/cfb8fc811311cce0a32c27eb65612cf8_13.png)

Okay， so we have a couple exercises here。 What is the depth of tree A， someone want to。Give the go。



![](img/cfb8fc811311cce0a32c27eb65612cf8_15.png)

Okay， tough crowd， okay。So if we're looking at the depth of tree A， well， our root here is x1， right？



![](img/cfb8fc811311cce0a32c27eb65612cf8_17.png)

And then we have a ton of leaves that are at the same level here， so let's just arbitrarily pick one。

 let's say this one， the length of the path from the root to that node would be1，2，3。

 so we have that the depth of tree A is three。

![](img/cfb8fc811311cce0a32c27eb65612cf8_19.png)

Now， if we're looking at， let's say x4。Which is here， right。

 You want the number of edges from the root to that node， which we have right here is 1，2。

 So the height or the depth of node x4。Is two。Right。



![](img/cfb8fc811311cce0a32c27eb65612cf8_21.png)

Now we have tree B right here， which is just three nodes。 We have a root node with two leaf nodes。

 right。And so we can pick either of these leaves， and we see that there's only one edge going from the root to the leaf。

So we know that the height of this tree is or the depth of this tree is just one。

And this we call it decision Stump， as I'm sure you might have seen before in lecture。Right。



![](img/cfb8fc811311cce0a32c27eb65612cf8_23.png)

Okay， and this is tree C。 so let's see。Notode X1 here is the root right so if we're looking for the depth of node X1。

 there are no edges going between x1 in itself right so the depth of node X1 is0 and for x5 which is over here。

 if we look at the length of path from the root to that node we have one to edges so we know that the depth of node x5 is2。

Any questions？

![](img/cfb8fc811311cce0a32c27eb65612cf8_25.png)

Cool。Okay， so now we're going to go through a little bit of tree traversal。

 here is like a coabab notebook link that you guys can try out maybe after class。

 but here's the code that you'd see in the notebook， here is just like the definition of a node。

 it contains a left child， a right child and some kind of value that it holds。



![](img/cfb8fc811311cce0a32c27eb65612cf8_27.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_28.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_29.png)

By default， I guess， like the children are set to none or null。



![](img/cfb8fc811311cce0a32c27eb65612cf8_31.png)

And here are three traversals， right， so let's consider this example right here。



![](img/cfb8fc811311cce0a32c27eb65612cf8_33.png)

And what we're trying to do is we're trying to find the output of each of the traversal functions。

 So just draw up here。

![](img/cfb8fc811311cce0a32c27eb65612cf8_35.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_36.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_37.png)

Right。

![](img/cfb8fc811311cce0a32c27eb65612cf8_39.png)

So it's traversal1， right， it says if the root is not none， so if that node is instantiated。

 right we first traverse on its left child and then we traverse on its right child and then we print the node's value。

So let's walk through Traversal one together， right？We start at the root here， which is one。

And then this node is instantiateated， so we would traverse down the left child first， right？

Now at Ro2 this has like the recursive call to it sees node2 as the root right。

 so now we recurse down node two's left child which would be node4。And at this point。

 like the recursive Col Sea node4 as the root。So we would recurse down its children but it has none right so node 4 is call to its left child and right child return nothing right and then we're able to print the value here so the first thing that we print out of Traversal1 would be four。

Right and then at this point the recursive call from node2 on its left child has finished right so now we go down this path right。

 and similarly to node 5， course our node for it sorry。

 has no children so we can print its value immediately and now sorry。

 node two has finished both of its recursive calls to its children。

 so now we print two and now we head back up to one which has not exportd its right child yet so at that point we explore three。

And once that finishes， we go back up to one and then we can print。Right。



![](img/cfb8fc811311cce0a32c27eb65612cf8_41.png)

So this is the first reversal。We have 4，5，2，3，1。

![](img/cfb8fc811311cce0a32c27eb65612cf8_43.png)

Right right。We call this post order traversal。

![](img/cfb8fc811311cce0a32c27eb65612cf8_45.png)

So let's just write that down。

![](img/cfb8fc811311cce0a32c27eb65612cf8_47.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_48.png)

And for reverssal2， you have something similar。Bless you rather than first traversing its children。

 we first print the value of the node as soon as we reach it right so this is kind of like I guess which node you reach first so we start at the root one we print one then we traverse down its left child since this call happens before this one right so we automatically print two then we print for。

And then。5。And then three， right， because this is like the order in which the nodes have been reached as we're traversing the tree。



![](img/cfb8fc811311cce0a32c27eb65612cf8_50.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_51.png)

So here， let's write that down。And this we call priororta traversal。



![](img/cfb8fc811311cce0a32c27eb65612cf8_53.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_54.png)

Introversal three， we have something similar yet again。



![](img/cfb8fc811311cce0a32c27eb65612cf8_56.png)

It's really just we want to fully traverse the left subtree before we write the value of the current node and then traverse the right subtree right so in this case we go to one and then we go to two and the leftmost node here is four right and then the most leftmost node other than four would be two。



![](img/cfb8fc811311cce0a32c27eb65612cf8_58.png)

Then5， then one， then3。

![](img/cfb8fc811311cce0a32c27eb65612cf8_60.png)

And that's what Traversal three is doing。And this we call in order traversal。



![](img/cfb8fc811311cce0a32c27eb65612cf8_62.png)

So if we have like a binary search tree， in order traversal would produce like a sordid array if we were to dump all of its values into an array。

 sorry。

![](img/cfb8fc811311cce0a32c27eb65612cf8_64.png)

Okay， any questions？Cool， hand up to the next section。



![](img/cfb8fc811311cce0a32c27eb65612cf8_66.png)

Sorry。系。Is the audio okay cool？Now we will talk about the concept of mutual information。

 this is particularly important for your homework because when youre building a decision tree。

 you'll be using mutual information to decide which features you want to split on。



![](img/cfb8fc811311cce0a32c27eb65612cf8_68.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_69.png)

Before I dive deeper into nutrient formation itself。

I'm discussing the definition of an entropy first。So this first line here is a definition of entropy。

 so it is the average surraal from a random variable。

So what it calculates is it summing over all the values this random variable can take。

Has a probability of it taking on that value， and then multiply it by the log base of2 that number。

This may sound a little bit complicated， but we will use some examples to go deeper into this idea。

And looking at the second line， this is a conditional entropy。

 so it is pretty similar to what we just discussed。

 Other than now we're taking on a condition for the value， what the value of xs should be。

And the third line。It's the entropy of y given x， so this is kind of taking an average of the conditional entropy based on the probability of xs occurring。

 so it's kind of taking a weighted average of the conditional entropy what we based on the probability that we can see xs happening。

And then this finally this line is some nutrient formation， which is so important。

 so it's taking the difference between the entropy of y and entropy of y given x。



![](img/cfb8fc811311cce0a32c27eb65612cf8_71.png)

Cool， now we can move on to some examples of calculation for entropy。

The first problem asks you to calculate the entropy of tossing a fair coin。



![](img/cfb8fc811311cce0a32c27eb65612cf8_73.png)

So there as we all know， the fair coin has two possible outcomes。

 so let's call this random variable Y， so there are two values that this random variable can take on。

 which are the heads。And the tellss。Since it's a fair coin。

 so probability of it taking on each of these values， is equal to 0。5。

 so the probability of H is equal to probability of tellss， and they're boths equal to 0。5。

And then we will substitute in to the formula that we just went over， which is the first line here。

 so this formula。

![](img/cfb8fc811311cce0a32c27eb65612cf8_75.png)

So basically， entropy of y is equal to the summation of two terms。

Does anyone want to tell me what these two terms are？Okay， it's fine。

 so the two terms are negative probability。Of y equal to heads， multiply log base 2。

Probability of why taking on heads。And the other one is probability of y equals to tellss。

 multiply log base2 probability of y equals to tell。Cool。

 because there are only two possible outcomes， therefore， there will be two terms in the summation。



![](img/cfb8fc811311cce0a32c27eb65612cf8_77.png)

And then now the step for us is to substitute in the numbers， which is negative 0。5。

 multiply log to log base 20。5， then subtract 0。5， multiply log base 2。5。

 and this value is equal to 1。So this is how you calculate the entropy of tossing a fairco。



![](img/cfb8fc811311cce0a32c27eb65612cf8_79.png)

And then moving on to question two。We need to calculate the entropy of tossing a coin that lenss only on tails。

So the state space here is the same as the first question， which is taking on either heads or tails。

 so our state space is the same。

![](img/cfb8fc811311cce0a32c27eb65612cf8_81.png)

But here what changes is a probability of seeing heads and tails happening， right。

 so the probability of heads。In this case is equal to zero， right。

 because this is a coin that is only possible to random them tails and the probability of seeing the tails happening is equal to one。

And we substitute that into the same formula。

![](img/cfb8fc811311cce0a32c27eb65612cf8_83.png)

On this line。We have。0ero。Negative zero multiply log base2 of zero。And then subtract one。

 multiply log base two of one。And this value is equal to zero。Because as you see here。

 zero multiply log base 2 of0 is equal to zero， so this is zero。

And then log is two of1 is also equal to zero， so this value is also zero。So basically。

 the entropy of tossing the coin that only lands on tails is equal to0。Now we take a step back。

And think more intuitively of what the entropy is trying to convey to us right so entropy。

 as I previously said， it calculates the average surraal from a random variable so if we are looking at the entropy of a tossing a fair coin we are really surprised of any outcome it may have because it's 5050 right so you can either go to tells you can go to heads so it is really random。

 you can't tell much about what the value would be for the random variable， however。

 for your second question， if it's a random variable that has a certain outcome of lettingum tails。



![](img/cfb8fc811311cce0a32c27eb65612cf8_85.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_86.png)

You basically know what's going to happen before you even flip that coin right so there's no level of surpriseprial at all for this random variable。

 so that's how you intuitively understand the non word or the level of random variable。

For their entropy。

![](img/cfb8fc811311cce0a32c27eb65612cf8_88.png)

Then for question three， we're calculating the entropy of a fair dice roll。

So now it's kind of similar to our question one， other than this time。

 we have six possible outcomes from one to six and each probability of each outcome is one6 because that's a fair dice roll。

So I'm going to write this as a summation， so the entropy of y is equal to negative summation from1 to6。

 and since it's a fer di row， we will have probability of 1。

6 happening for each one of them and then multiply log。



![](img/cfb8fc811311cce0a32c27eb65612cf8_90.png)

Qiu。Loaw based2 on16。So this is the entropy of a fair dice roll。And the value is equal to log。Base 2。

6。Okay， any questions up to this point？阔。Then we are moving on to this first question。

 which is more on the conceptual side， so when is the mutual information between y and x equal to0？



![](img/cfb8fc811311cce0a32c27eb65612cf8_92.png)

So if we go back to the definition of mutual information。



![](img/cfb8fc811311cce0a32c27eb65612cf8_94.png)

So mutual information between Y and X。Is equal to。The entropy of y， subtract entropy of y given x。



![](img/cfb8fc811311cce0a32c27eb65612cf8_96.png)

When is this value equal to zero， So if we do some algebra things。

 we move this term to the right hand side， we will have。

The entropy of y is equal to the entropy of y given x。Right。Mathematically。

 we can prove that this is only true， this is true if and only if。X and Y are independent。

How you can intuitively understand this is because if x and y are independent。

 knowing one variable doesn't tell you anything about the other one right so that's why their mutual in their entropy is equal to zero because knowing this x doesn't help you reduce the surprising level from what y gives you right so。

If that's a case， knowing X doesn't help us reduce the entropy in Y， we can say they're independent。

 so that's the intuitive understanding for the mutual information， for this question。



![](img/cfb8fc811311cce0a32c27eb65612cf8_98.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_99.png)

Cool， any questions up to this point？Yep。

![](img/cfb8fc811311cce0a32c27eb65612cf8_101.png)

第一世代。2嗯。I'm not saying that I is equal to each other。

 I'm saying that their entropy is equal is it called the entropy of Y given that like what's the birth？

Oh yeah， yeah so here is entropy of y and then。The mutual information。

 you see that's some mutual information between next and long between so it's a symmetric definition。

If you had it here， so technically I of this nutrientform between x and y is equal like the order doesn't really matter because it's a schemetric definition。



![](img/cfb8fc811311cce0a32c27eb65612cf8_103.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_104.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_105.png)

Cool now we will be using this idea and help us build a decision tree。

 So this is a sample data set you see。😊，There are eight data points and you're given three features。

 outlook， temperature and humidity， and you are going to predict the output feature by building a decision tree from these three features。



![](img/cfb8fc811311cce0a32c27eb65612cf8_107.png)

The first step of building a decision tree is to calculate the mutual information between y and each of these features and then split on a feature that gives you the maximum the largest mutual information so that is why you're asked to calculate the information between y and x1 between y and x2 and y and x3 so after you calculate these three values。

 you need to pick out the one。

![](img/cfb8fc811311cce0a32c27eb65612cf8_109.png)

Pick out the variable that gives you the maximal nutrient information and your first what is going to be based on that。



![](img/cfb8fc811311cce0a32c27eb65612cf8_111.png)

So let me remind you of the definition for mutual information。

 so neutral information between Y and X。

![](img/cfb8fc811311cce0a32c27eb65612cf8_113.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_114.png)

Is equal to。Entropy of y， subtract entropy of Y given x。So here。

 if we're trying to calculate the mutual information between y and x1。



![](img/cfb8fc811311cce0a32c27eb65612cf8_116.png)

Or like I the mutualform between y with respect to any one of the XI， right。

 we need to calculate number of the amount of entropy of y because we need it anyhow。

 so we will calculate that value first， so the entropy of y。



![](img/cfb8fc811311cce0a32c27eb65612cf8_118.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_119.png)

Since we're only calculating entropy of y is not conditioned on anything。

 we need to look take a closer look at this column。



![](img/cfb8fc811311cce0a32c27eb65612cf8_121.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_122.png)

So as you can see， there are two possible outcomes for the random variable Y， right。

 so we can take on。

![](img/cfb8fc811311cce0a32c27eb65612cf8_124.png)

No or yes。So basically the entropy of y is the summation of two terms。

 it's a probability of seeing y equals to no。Negative， so negative probably y equals to no。

Multiply lock be too。Probability。Y equals to no。Subtract probability of seeing y equals to yes。嗯。

And then multiply that by log base2 probability of y being yes。

We can see from this column that two out of eight instances take on the value of no。

 therefore the probability of y taking on no is equal to2 over 8。And then lock base2， two over eight。

Subtract 6 over 8， multiply lock base to 6 over8。This value？Is equal to。811。



![](img/cfb8fc811311cce0a32c27eb65612cf8_126.png)

And then after this， we need to calculate this second term， right， so the entropy。



![](img/cfb8fc811311cce0a32c27eb65612cf8_128.png)

Of Y， given x1。

![](img/cfb8fc811311cce0a32c27eb65612cf8_130.png)

So if we go back to the formula。

![](img/cfb8fc811311cce0a32c27eb65612cf8_132.png)

嗯。This is equal to we look at this equation here so we're summing over all the values that X can take。

 So we look at this this column of outlook。 There are three possible values that x1 can take right。

 So sunny overcast in rain。 Therefore， there will be three terms in the summation。

 So it's gonna equal to probability of x1 equal to sunny。



![](img/cfb8fc811311cce0a32c27eb65612cf8_134.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_135.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_136.png)

Multiply probability of sorry， multiply。

![](img/cfb8fc811311cce0a32c27eb65612cf8_138.png)

The mutual information。Of y given x1 equal to sunny。And then plus probability of x1 equal to rain。

Multiply entropy of y。Given x1 is equal to rain。And then finally。

 this probability of x1 equals your overcast。Multiply the entropy of Y given x1 is overcast。



![](img/cfb8fc811311cce0a32c27eb65612cf8_140.png)

For this expression， we can easily calculate the probability of x1 equals to sunny。

 x1 equals to rain and x1 equals to overcast by simply observing what's happening in this column so this first column we see there are three cases where x1 is equal to sunny。

 therefore the probability of seeing x1 equal to sunny happening is3 over 8 Similarlyly there are three instances where rain x1 is equal to rain。

 therefore this value is also3 over8， and the last one is2 over 8。



![](img/cfb8fc811311cce0a32c27eb65612cf8_142.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_143.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_144.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_145.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_146.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_147.png)

Cool， then the next step for us is to find out what these three values are， right？



![](img/cfb8fc811311cce0a32c27eb65612cf8_149.png)

So let's see， what is the entropy of Y given x1 is equal to sunny？



![](img/cfb8fc811311cce0a32c27eb65612cf8_151.png)

So things you see is a conditional entropy， so we are only looking at the data lines with the label x1 equals to something so it's these three lines here。

 so one， two and three， and out of these three lines we look at the label of y right so we are seeing this two nos and one yes。

 that means so that means out of these three lines。

 two out of which have produce value of no and one of which produces the value of yes。



![](img/cfb8fc811311cce0a32c27eb65612cf8_153.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_154.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_155.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_156.png)

Therefore， our equation is going to be negative。

![](img/cfb8fc811311cce0a32c27eb65612cf8_158.png)

Two over3， multiply log base 22 over3。And then subtract one over three， multiply log base2。

 one over three。

![](img/cfb8fc811311cce0a32c27eb65612cf8_160.png)

So this value is equal to 0。918。

![](img/cfb8fc811311cce0a32c27eb65612cf8_162.png)

And there's one thing I want to emphasize here is that since we're taking the conditional。



![](img/cfb8fc811311cce0a32c27eb65612cf8_164.png)

Entropy so we're only looking at the lines with a label x1 equals to Sun and we neglect all the other lines with x1 not equals to sunnyny like x1 equals to forecastaccast and rain。

 we just don't look at them at all， okay。

![](img/cfb8fc811311cce0a32c27eb65612cf8_166.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_167.png)

So this is how we get the entropy conditioned on x1 equals to Sunni。

 and then let's see what the entropy of y given x1 equals to ring is。



![](img/cfb8fc811311cce0a32c27eb65612cf8_169.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_170.png)

So here we look at these two lines。With three lines， so three lines with rain， x1 equals to rain。

And there's something you may observe。So out of these three lines。

The y label is always yes right So this is actually the definition of a pure node That means when you're given a set of features and you look at the subd set the produced label from that condition is always the same So this is similar to the case where we're seeing the dies where it can only land on tilts right because there's no sural of what what we may see of the label at all so this case our entropy is just equal to zero because just as what we calculate for the entropy of tossing the coin that only lends on tails it's like zero for the case where y equals to zero and then it's also zero for the case the term that y is equal to no right。



![](img/cfb8fc811311cce0a32c27eb65612cf8_172.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_173.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_174.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_175.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_176.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_177.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_178.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_179.png)

Cool， and then similarly for Antro P of y， given x1 is equal to over yourcast。



![](img/cfb8fc811311cce0a32c27eb65612cf8_181.png)

So here we are looking at。This， this data and this data， right。

 So something similar is we can see something similar here as well so。The label of why are both yes？

When we are taking a condition that x1 is equal to overcast， therefore， the mutual information。



![](img/cfb8fc811311cce0a32c27eb65612cf8_183.png)

I mean， the entropy is also to zero in this case。

![](img/cfb8fc811311cce0a32c27eb65612cf8_185.png)

So after we got these numbers， we substitute back into the entropy of y given x1。

So this is equal to zero。This is also equal to  zero。

 so the only one that actually matters is our first term， so 3 eighth multiply 0。918。



![](img/cfb8fc811311cce0a32c27eb65612cf8_187.png)

So this value。

![](img/cfb8fc811311cce0a32c27eb65612cf8_189.png)

Is equal to 0。344。

![](img/cfb8fc811311cce0a32c27eb65612cf8_191.png)

After we have this value， we can substitute back into the formula of calculating a mutual information。

 so its mutual information between y and x is equal to entropy of y， so 0811。



![](img/cfb8fc811311cce0a32c27eb65612cf8_193.png)

Subtract entropy of y given x1。 So this value here，03，4，4， right， so we have0 3，44。



![](img/cfb8fc811311cce0a32c27eb65612cf8_195.png)

So this value is equal to 0。467。This is how we get to the mutual information between x and y so for the Aer2。

 the mutual information between y and x2 and mutual information between Y and x3。

 I will not go over here because of time constraint so you can see the detailed process in the solutions on the course website。

 but I will give you the numbers here， so between Y and x2， the mutual information is 0。61。



![](img/cfb8fc811311cce0a32c27eb65612cf8_197.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_198.png)

And the other one is。Point311 Okay， so if we're given these three values。

 can anyone tell me which feature we want to split on？

Remember that we only splitting on the one with a maximum mutual information。

So we will be splitting on。Anyone want to shout it out？



![](img/cfb8fc811311cce0a32c27eb65612cf8_200.png)

Yeah， exactly， so x1 seeing the mutual information between Y and x1 is the largest out of these three。

 we're taking on we're actually splitting on x1。

![](img/cfb8fc811311cce0a32c27eb65612cf8_202.png)

F to first note。So here we can actually go to problem three， where we draw the decisionary。

 since we pick x1 as our first split， it takes on three values， sunny。Rain。An overcast。

So this is kind of the first step we draw the restsoing tree and remember that when whenever we see the x1 being rain or overcast。

 they both only have the y label of yes， right so if we are going down to these two these two passes。

 we already know what we want to produce because those are pure nodes。

 so whenever we see x1 equals to rain。

![](img/cfb8fc811311cce0a32c27eb65612cf8_204.png)

We're going to produce a label of yes for why， so yes。



![](img/cfb8fc811311cce0a32c27eb65612cf8_206.png)

And whenever we see X1 being overcast， we are also going to produce predict this yes for Y。 however。

 since when x1 is equal to sunny， the node is not pure。

 so we may want to further split on the sub data set under X1 being sunny。



![](img/cfb8fc811311cce0a32c27eb65612cf8_208.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_209.png)

So now it's the time for us to go down this path right so if we're only looking at this pass。

 we will neglect all the other data points where X1 is not equal to sunny so we're only looking at these three。



![](img/cfb8fc811311cce0a32c27eb65612cf8_211.png)

诶。These three data points， so were checking only looking at these three sub datata out of these three。



![](img/cfb8fc811311cce0a32c27eb65612cf8_213.png)

We are calculating。

![](img/cfb8fc811311cce0a32c27eb65612cf8_215.png)

Some mutual information。Between y and x2 and mutual information between Y and x3。



![](img/cfb8fc811311cce0a32c27eb65612cf8_217.png)

So it is really similar process us than now were only looking at these three data sets right I mean these three data points because we already we are already down the path of x1 being sunny right so because of time constraint I'm gonna give you the number so the mutual information between Y and x2 is equal to 0。

25 and between y and x3 is equal to 0。918。

![](img/cfb8fc811311cce0a32c27eb65612cf8_219.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_220.png)

Nice， so because the mutual information between y and x3 is larger in this case。

 we're going to split on x3。So here we're going to have another split and split it on x3。

 so look at x3， there are two values it can take on high and normal。



![](img/cfb8fc811311cce0a32c27eb65612cf8_222.png)

Wait， let me。Hi。

![](img/cfb8fc811311cce0a32c27eb65612cf8_224.png)

And we look at those out of these three just sub datata points。

 we look at these two points where we have the humidity being high。

 and then it's a pure node again right because these two values are both no。

 that means we can just output this sub datata， I mean output this label saying that y is equal to no。

 and regarding the case where x3 is normal， so this one we always have it's a pure node so we can always predict that y is equal to yes。



![](img/cfb8fc811311cce0a32c27eb65612cf8_226.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_227.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_228.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_229.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_230.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_231.png)

So this is how we build our disary。Any any questions。

you're deciding at the information for based on those four so the question is about if we have decided the first with being x1 and we are going down along the path where x1 is equal to sunny。

 do we need to look at all other data points， the answer is no。

 so we are only looking at these three data points where x1 is equal to sunny。

 and we don't look at the other data at all because they don't satisfy our conditional condition that x1 is equal to sunny。



![](img/cfb8fc811311cce0a32c27eb65612cf8_233.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_234.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_235.png)

Does that make sense？ cool。Any other questions？You have question。You can calculate theい information。

Where。Yes。So you're asking when we are calculating mutual information within this sub data set。

Why can't we use the original results pattern？Or the horror塞。



![](img/cfb8fc811311cce0a32c27eb65612cf8_237.png)

Because remember that when we are going down this path。

 we are taking a conditional entrypy or were only looking at a subt set because we don't care about all the without that doesn't satisfy our requirement that X1 is equal to Sunni and they don't matter to us in that case。

 so we are only looking at the sub data set instead of the whole data set。Nice。

 then I'm passing on to Annie。

![](img/cfb8fc811311cce0a32c27eb65612cf8_239.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_240.png)

Okay， so I'm going to go over the concepts for constructing decision trees。

 this will be very helpful for you for the programming part of your homework where you'll have to train a decision tree classifier so starting off with this first question。

Change the color。Okay what exactly are the tasks that we're tackling so when we want to construct a decision treat we'll be given。



![](img/cfb8fc811311cce0a32c27eb65612cf8_242.png)

A set of training data。Some test data。And I max depth of the tree。And we want to do the following。

 so first， we want to use the training data to learn a decision tree classifier。



![](img/cfb8fc811311cce0a32c27eb65612cf8_244.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_245.png)

Then we're going to use the decision tree that we just trained to predict the labels on both the train data and test data。

And then lastly， we're going to calculate the error。For both the training data and testing data。



![](img/cfb8fc811311cce0a32c27eb65612cf8_247.png)

Okay。So then in terms of the inputs and outputs at training time at testing time。

 so let's start with the training inputs。

![](img/cfb8fc811311cce0a32c27eb65612cf8_249.png)

All we really need is just the training data。And the max depth of the tree。

 so the max depth of the tree will be something that you pass in。

 it'll be one of the stopping criteria that you'll need to determine like when to stop recursing。

Then your training output。Or just be a fully trained。Decision tree。



![](img/cfb8fc811311cce0a32c27eb65612cf8_251.png)

And then for test time， testing inputs。We're just going to have like a set of testing data that's in the same format as your training data。

AndTesting。Oput。We're going to get a prediction for every row of data in your。Test data set。

 So prediction。

![](img/cfb8fc811311cce0a32c27eb65612cf8_253.png)

Okay。

![](img/cfb8fc811311cce0a32c27eb65612cf8_255.png)

Now the third question on each node， what do we need to store？In your homework。

 you're going to implement like a node class and it's up to you to determine like what you want to store in that class。

 so the list I'm going to give you right now is not exhaustive。

 feel free to add anything that you think could be helpful for your implementation。

 but these are just some things that we think would be necessary slash helpful for you when you implement your decision trees so you would want to store the attribute。



![](img/cfb8fc811311cce0a32c27eb65612cf8_257.png)

That you're splitting on at that node。And you would also want to know what subset of data you're considering at that node。

嗯。The left and right children。And then it might also be helpful for you to store the node depths。



![](img/cfb8fc811311cce0a32c27eb65612cf8_259.png)

Yeah， once again， feel free to add anything in your implementation if you think they're necessary。

 but this is just some ideas to build off of。

![](img/cfb8fc811311cce0a32c27eb65612cf8_261.png)

Okay。What exactly do we need to do at training time， So that's the fourth question。



![](img/cfb8fc811311cce0a32c27eb65612cf8_263.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_264.png)

We need to check these stopping criteria。To see if we can stop recursing。

 So this would mean that either like we've reached the max depth or like the node is pure。

 and if either are true， then we just want to return a majority vote at that node。



![](img/cfb8fc811311cce0a32c27eb65612cf8_266.png)

So。Yeah。So this is kind of like the base case。

![](img/cfb8fc811311cce0a32c27eb65612cf8_268.png)

Of your recursion。So then if we don't stop the cursing at that node。

 then we want to calculate the entropy and mutual information and determine which attribute that we should split on next。



![](img/cfb8fc811311cce0a32c27eb65612cf8_270.png)

た。

![](img/cfb8fc811311cce0a32c27eb65612cf8_272.png)

And then lastly， we want to split the data based on which attribute。

We decided to split on in the previous step。

![](img/cfb8fc811311cce0a32c27eb65612cf8_274.png)

Okay。Then what should we do at test time？We need to use the train。Classifier。

I was train using and training there。It's really important and we see a lot of students make mistakes on this。

 you do not retrain a decision tree or any sort of like classifier or model using your testing data。

 you take what you've trained during training time。

 you take that model so in this case the decision tree and then you feed the testing data in to generate predictions。

 you do not retrain the model at testing time using the test data。Okay。

 so let me just emphasize this， do not。Trade。

![](img/cfb8fc811311cce0a32c27eb65612cf8_276.png)

Test。

![](img/cfb8fc811311cce0a32c27eb65612cf8_278.png)

So then we're going to predict labels。Using。A train。Hire。

And we're going to predict labels for both the training data set。And test data。And then lastly。

 we're going to write predictions。And metrics。To output files。As necessary。



![](img/cfb8fc811311cce0a32c27eb65612cf8_280.png)

Okayright， so that was a lot of me talking。 Now， question6。

 what happens if max depth of a tree is zero。 Can anyone tell me the answer。Right。

So if we happen to run into a case for the max up the year， just run a majority vote on the data set。

There OK， now what about if the max steps is greater than the number of attributes。

 which we do in that case？That'sWhen you're proud of。Well， we run out attributes then like。

Think about the situation when that does happen。 Do you have anything else to like train。

what will your subset of data look like in that case？

It would just be empty right like if you run out of attributes and you have nothing to train on anymore。

 so just stop growing the tree when all the attributes are。

Because you can't extend like you can't just add more attributes of your data you're given the finite of data。



![](img/cfb8fc811311cce0a32c27eb65612cf8_282.png)

Okay， so just。Okay。Now that concludes this part， anyone have any questions？ if not。

 I'm going to pass it off to barkov。

![](img/cfb8fc811311cce0a32c27eb65612cf8_284.png)

Okay so now we're gonna to talk about just some coding tips I guess。

 so this homework you guys are gonna have to build a decision tree from scratch so we give like very little starter code and you just have to write the whole decision tree and when we write code we can run into a lot of issues and debugging takes a really long time So here I'm just gonna give some tips and go through some common mistakes that some people might make when coding and yeah so in Python we have this thing called PDB。

 which is like Python's debugger I mean if you've taken a class and see you've probably heard of GB this is PDB and it allows you to essentially step through your code and print variables and gives you more like finet control of like what you want to debug through and the way you would like start that is by putting that PDB set trace or breakpoint on any line。

When your code reaches that line， it'll open up an interactive session where you can type the commands below to move through the code。

Honestly， for this assignment and for most of M， though。

 you can probably get away with print debugging and it's probably better to do print debugging。

 so just like printing your arrays printing any data that you're storing or any expressions that you want to test might be a little bit easier to just do than PDDB。

 especially if you have never used PDDB before， like it might be easier for you to just do print debugging。



![](img/cfb8fc811311cce0a32c27eb65612cf8_286.png)

Okay， and so now we're just gonna go through some like incorrect code and let's try and figure out why it's not right。

 And this is interactive。 So it would be great if you guys could kind of tell me what's going wrong or something that I could print potentially if I was coding to help me figure out what's going wrong。

 So when I run this code， I get like an index out of bounds error。 So can someone tell me like。

 why I could print to figure out like why that might be happening。



![](img/cfb8fc811311cce0a32c27eb65612cf8_288.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_289.png)

Yeah。Yeah， I could definitely print。

![](img/cfb8fc811311cce0a32c27eb65612cf8_291.png)

Print this value right here。 so print。Do index。Um and。Do you know the bug here？Yeah。Yeah。Yeah。Yeah。

 so in Python， everything is zero indexed， right？ So when I is equal to 0。

 new index is going be equal to rows。 But if you try and access rows。

 that's going to be out of bounds。 So how would we correct that。😊，Anyone。Abs， yeah。Yeah。

 you can just subtract warm and now it's like all good。

There's another sneaky issue here that I will go over。 So in Python。

 when we want to create 2D arrays。 If we do it like this， So I'll just give an example。 So let's say。

I created something like this。And now， if I had said， like， new。New0，0 equals1。

 What that would actually do is it would change both of these。To ones。

 because what what this code is doing is it's creating one row。 And then for the remaining rows。

 it's just creating an alias to the first row。 So every time you change something in the array。

 it's going to change every single row， because they're just alias to that first row。

 And so the right way to kind of create a 2D array if you ever need to， it would be。

 So I guess it's called new， it would be。😊。

![](img/cfb8fc811311cce0a32c27eb65612cf8_293.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_294.png)

Type calls。And so instead of like multiplying it by rows here， we would do for you can put I。

 you can put whatever you want in range。Rose。So this will actually create a new copy for every single row。

 and the other one would just alias it to the first row， so if you ever need to create a 2D array。

 use this， don't use the other one。Okay， any questions so far？So those are like the two bugs in this。

So if we had just like written a new like this and then fixed that indexing， it would work correctly。

 By the way， there is a co op here， so I do encourage you guys to like try it out on your own time like even the PDB if you're interested or print debugging。

 you can just go in and try it out。

![](img/cfb8fc811311cce0a32c27eb65612cf8_296.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_297.png)

![](img/cfb8fc811311cce0a32c27eb65612cf8_298.png)

U。Yeah， okay， this is the last one。 So this one， we are writing a function that takes in a 2D array and returns the index of a column with the most nonzero values。

 So， and then in case of a time we're returning the smallest index。

 and I think let's just pretend that instead of calling this function。



![](img/cfb8fc811311cce0a32c27eb65612cf8_300.png)

We decided to call our little get count。

![](img/cfb8fc811311cce0a32c27eb65612cf8_302.png)

Okay so let's just pretend that we didn't call that nonP function instead we call it our own function。

 which is counting the number of nonzero things Yeah。

 so I'm still saying like right now it's not doing what we wanted to do and there is a very subtle bug here。

Can anyone figure it out？

![](img/cfb8fc811311cce0a32c27eb65612cf8_304.png)

嗯。So as a hint， when I run this function， it's actually giving me the index with like the most amount of zeros instead of non zeros。



![](img/cfb8fc811311cce0a32c27eb65612cf8_306.png)

Yeah。Yeah， how number is zero。 so here I'm saying it's equals equals to zero。

 but it should be not equals to zero。

![](img/cfb8fc811311cce0a32c27eb65612cf8_308.png)

And then there is one more issue， so if we look at the description in case of a tie returned the smallest index。



![](img/cfb8fc811311cce0a32c27eb65612cf8_310.png)

You might have to do this in some other homeworks too， tie breaking in a specific way。



![](img/cfb8fc811311cce0a32c27eb65612cf8_312.png)

One thing that almost always happens when you're like checking like tie breaking is to look at like the sign of your greater than or less than or equal tos。

 So， for example， if I have two columns each with the same number of non-zes with this greater than or equal to it's going to replace it each time right So therefore I'm not gonna be returning the smallest index。

 I'll be returning the last the biggest index with all the nonzero values。

 So I need to change this from greater than or equal to to just greater than So that only the first time something is equal like something is that value。

 it will get updated。😊，Okay。Any questions？Okay， so I guess that's the end of recitation。

 Good luck our homework too。

![](img/cfb8fc811311cce0a32c27eb65612cf8_314.png)