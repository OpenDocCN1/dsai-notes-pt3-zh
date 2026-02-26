# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p11 Lecture 13 - erm for classifiers.zh_en -BV1utzNYqEkr_p11-

![](img/05c58e0f91dcb9d77778fc91d88470bc_0.png)

![](img/05c58e0f91dcb9d77778fc91d88470bc_1.png)

Welcome to the section on fittingtting classifiers by empirical Ri minimization。

Now this section is very much parallel to our earlier section on regression。V our empirical risk。

 minimization， we have to really discuss two things in order to do classification。

And the first is how do you embed categorical variables B？So we have a script V。

 it's a finite set of possible values of classes that our target variable V can take。

And we want to take the target variable V in。Embbeded it into a vector y in ourM。

And we're going to let y be Psi of V。And of course。

sia V only takes k values as well because V only takes k values。And so psi we have capital K vectors。

 Psi 1 through Psi capital K。Each of those are the images under the map side of the classes B1 through VK。

And we call these vectorus psii the representative of VI。And the set of all representatives。

 Psi1 through Psi K is called the constellation of Representatives。

Some of some examples we might embed true to one and false to minus one。

We might be true to one and false to zero。Those are mappings from the a two element set of categories into the real numbers。

We might also map the three elements set， yes， maybe no to the real numbers1，0 and minus1。

Another thing we might do is do a one hot embedding。😊，Where we have， say， three。Categories， apple。

 orange， and banana。And we made apple to。E1， orange to E2 and banana to E3。

 but E1 and E2 and E3 are the canonical unit variables， unit vectors in R3。

Now we might also take three categories and map them directly to the res if we' got say three horses。

 H three， H one and horse two， we might map them just a three， one and two。Well。

 we might do really complicated things like word Tbec， which maps a large number of words。

 two vectors in R 300。Okay。So that one hot embedding takes K classes and maps into ourK。

So Psi of VI is just EI。We could do it to Booleions。

We have Booleions where the first representative maps to 10 and the second representative maps to 01。

There's another version of the one hot embedding called the reduceduce to one hot embedding。

 which maps one of the classes to zero and the other K minus1 classes map to the unit vectors in our K minus1。

嗯。So if we had Buddins in that case， that reduces the mapping。

From the one hot embedding is maps the booleanance to 10 and 01。

 and the reduced one hot embedding would map the booleans to0 and1 one dimensional。Ebedding。

Rather than a two dimensional embedding。We might also have， yes， maybe no and the default be maybe。

In which case the。That's three categories we would map it to R2 by the one hot bedding。

 the reduced one hottting bedding。And we put maybe as the default， so maybe would map to the origin。

 yes might map to 10 and no might map to 01。你好。Now， once we've。Embbedded。

 we are going to have to do something we didn't have to do。In regression and that is unembeded。

And in particular， we've got to unembed points which are not mapped to by our embedding map。And。

So we will see how to do that。嗯。Let's look at how this works from the overall predictor point of view。

So we start off， we embed our raw input U to a feature vector x via the map Phi。

 the feature vector x lives in RD。And we've got a war output， which is in our data set， which is a V。

 which is a categorical。We map it tos of V， which is Y lives in RM。

We use these data points we've gone from。N UI VI pairRS N X I， YI pairs。

 and we use those to create a predictor G。Which maps R D to RM。And for any X。

 it will give us a Y hat which lives in RM。And now what are we going to do with why hat Well what we hope is that。

Um， if y had is g of x， then y is somehow close to psi of V， where V is one of the categories。😊。

And close hair would usually mean in the norm， so I've got。

The norm of y hat minussi of V is small for one of the V's。And to get the prediction。

 we've got to an embed， we've got to pick a V hat。😊，Which is。Corresponding to the Y hat。

And we're going to define a map side dagger。Which takes vectors in our M and maps them back。

Into the target set script B， the un embedding function。So once we've got a side dagger。

 where we can use it in order to construct our final classifier。

 our final classifier has to take a U and give us back a V hat and the way it's going to work is we're going to take you。

😊，Pump it through， our embedding phi to give us an X， pump that through G。

To give us a prediction Y hat and then pump that through the unembedded side dagger to give us a V hat。

And then we'll call that map from U to V hatAT capital G。

G is the composition of Pi dagger with G with phi， in other words we embed。

 we predict we aren't in bed。The usual unembidding that people choose。

Is the nearest neighbor un embedding。And what it does is it says， well， you've got a Y hat。

Pick out of all the categories。In script V， the one。Such that psi of V is the closest to Y hat。

 So minimize over all little v's in script V the norm of y hat minussi of B。

And that is called side dagger of Y hat。And if it so happens that there are two。😊。

Vectctorors V to classes。For which their embedded points are equally close to Y hat well then you can break ties anywhere you want to。

Another way to say is what we're doing is we're choosing the target variable， the target category。

Which is associated with the nearest representative to Wyat。

So here's the simplest possible example if we've embedded the Booleans true and false to one and minus one。

 so those are our representatives， Psi 1 and Psi 2。😊，Well。

 then we would un embed by mapping any positive number y hat to true in any negative number。

Why act to false because if we've got two representatives， which we have minus one and1？Well。

 if y hat is positive， then the closest representative is one， and if Y hat is negative。

 then the closest representative is minus1。😊，Suppose we've got one hot， So let's look at the R2 case。

嗯。So here we have y1， y2， two components of y。We have。1，0。And 01。

 this will be Psi 1 and this will be Psi 2。 Those are the embeddings of our two categories in the case of the Booles。

 so this would besi of true。And this would be psi or false。And then we develop a predictor。

 and that predictor gives us back a Y hat， which is anywhere in the。😊，Two dimensional。Planes。

And then what do we do？Well， we'll say。If。You're on this side of the plane， if Y hat's over there。

 then our corresponding V hat will be psi 1。And。If you're on this side of the plane。

 then the corresponding V hat will be side2。And to be precise， they will be not psi 1 andsi 2。

 but v1 and V2， the corresponding targets true and false。And so here it's clear。

 all you do is you look at the two components。😊，Of Y hat， Y hat one and Y hat2。

 and if Y hat one is larger， then you're on this side of the plane。You're on this side of the plane。

And if y2 is larger， well then you're on this side of the boundary between the two between which separates the region。

 which belongs to p Psi 1 and the region that belongs to S 2。Let's put it another way。

Y hat1 is greater than Y hat2。Then the O min。Over V。Of the norm of Psi V minus。Why hat。Is。啊。

Wheres V1。Otherwise， it's K2。This is true more generally if we want to find out which is what is the solution in general？

😊，To this problem of ion embedding， what is side dagger when we've used the one hot embedding？

It turns out that this is exactly what we think it is we look at the largest component of the vector Y hat and。

We return the corresponding target vector sort of Y hat3 is the largest component of white hat。

 then our unembedding side dagger would return V3。And the reason for that we can just work out algebraically what it is if I look at what。

😊，啊。What a Y hat minus？EI is。Well， that's the two norm squared of that quantity is the two norm of y hat plus one。

Minus2 y hat transpose EI。And why Ha transpose EI is just。

Yhy hat I is just the I component of Y hat and so picking。I to。

Minimise that quantity is precisely the same as picking I to maximize Y at I。😊。

Suppose we've embedded the reduced one hot embedding。

 we've used the reduced one hot embedding to embed yes， maybe no as 10，0，0 or01。Well。

 then we unembed in exactly the same way for any point Y hat in the R2 plane。😊。

We pick the closest representative， and that tells us which target variable were predicting。So， if。

Why hat is over here in this region。Its I'm going to return， yes。😊，Yes。

 is S dagger of any point in that region。No is side dagger of any point in this region and maybe is sidedaggga at any point in the remaining region。

 and that's nicely。Expressed in the little cases construction there。And again。

 you can choose any value you like on the boundary。So more generally， we might have an embedding of。

Categories into RM。And that gives us a whole bunch of different representatives here represented by these blue dots。

And for any given point， why hat in RM， we want to find the cut closest representative and the way we do that is rather the vrenoid diagram that we saw earlier。

😊，And so in particular。This region right here。Is the set of points？

For which the closest blue dot is that one in the middle。

And so that means that if Yha is in that region。I will return the corresponding representative to that blue dot right there。

And as we've seen when we looked at the nearest neighbor classifier。😊，The regions， which。啊。

Correspond to each target variable or to each representative， a polyhedra。

Now suppose we're using a parameterized predictor， so G is a function of a parameter theta。

 and G might be theta transpose times x if it's a linear predictor。

 it might be something more complicated。Well then theta is the parameter we choose and then once we've got a predictor G Theta。

 we compose it with the embedding psi and the ion embedding the embedding。

 this should be the embedding phi， let's just see that we used that same notation here。

This that should be phi。So this should say si dagger。G c there。Fy of you。Not sorry of you。

And that's the classifier that gives us v hat。😊，So what do we do。

 we choose Theta using ERM and a training data set。

And we validate the predictor by looking at the performance metric， which might be。The error rate。

On a test data set。Of course， the performance metric might be the name in person。Arror measure。

 as well。Co。And so when we're doing parameterized predictors for classification。

 we might use a tree based predictor and that's got a name it's very commonly used。

 it's called a classification tree。😊，And then Theta encodes the tree tells us when to split at each node and the threshold and leaf values。

 and each leaf has a corresponding value of y hat， and that leads immediately to a corresponding target because we can un embed the Y hat to the V hat。

😊，And we might use a neural network in which case Theta gives us the bias or the offset and the weights in the different layers。

 and then why hat is the output of the last layer and again we aren't embed。😊。

We might use a linear predictor， Theta is a D by M matrix。And y hat is just theta transpose times x。

Now， the other major piece that we need for classification is a loss function。

And it turns out that the loss function。That we reduce use for classification is slightly different from the typical loss function we would use for regression。

😊，And we're going to see in the next section several different loss functions for classifiers Now for the moment I want to consider the simplest loss function。

😊，That's。啊。For example， the square loss。Now the way it works is just like it did in regression。

It is that we have a loss function， this is not quite right。

 It should be the loss function maps RM cross R M。To R。It's a function of why hat and why。

And it tells us how much prediction why hat bothers us when the true observed value of why。

I's what it is。And it's going to be， of course， one of the representatives。

Those are the only possible values for y because the only possible values for V are V1 through VK and when we embed those we get psi 1 through PsK。

😊，As a result， we can think about loss function slightly， differently。

 rather than thinking about a loss function as。😊，Taking a Y hat and a why。We can say， well。

 really what we have is we have K different loss functions。😊，The first one is the loss function。

 which tells us how much loss why hat。Cour is us。Whenin the target variable。Is V1？

That's L of y hat psi 1， or when the target variable is v2。

 then we get a different loss and we'll think of that as a totally different loss function。😊。

And we might even use this kind of notation。L sub J or Y hat to say， well， actually。

 we've got a different loss function。4。J is one。Up to capital K。And this loss function。😊。

Only depends on why hand。Because the dependency on Y is taken care of by J。

What it is is it's how much we dislike predicting Y hat in the particular case where the target variable is Vj or correspondingly when y issi J。

And typically what you want is you want that the last function L of Y hatsi J is a non negative number。

 and it's small when Y hat is close tosi J。So very commonly we might use the square loss。嗯。

Which is the tuome of Y hat minus sche。嗯。We'll see other loss functions which work much better for classification in the next section。

😊，So how do we think about two different loss functions。

 when we're using the square loss in the Boolean case。

 well they're translated versions of the quadratic function。😊。

This is the on the right here is L of Y hat Y when。Why issi？2。And side 2 is just one。

 And this is L on the left here of Y hat and y when。Y is Psi 1， which is just minus1。And we can see。

The one on the right is a quadratic centered at one and the one on the left is a quadratic centered at minus1。

So we're given a training data set。X， Y， Y， I pairs I1 up to n。

And we've got a parameterized predictor G Theta。And empirical risk minimization simply says， well。

 what we do is we minimize the average loss function over Theta。

Where the loss is evaluated at Y hat I and YI， and Y hat I is just our prediction evaluated at XI。

So ERM chooses the theem to minimize the loss， regularized ERM chooses the the to minimize。😊。

The empirical risk plus lambda times the regularization function。

And Lambda here is a positive regularization hyperparameter。And in most cases。

 we're going to need to do numerical optimization to find Theta， there won't be an explicit formula。

😊，Now in the Lee squares case it's quite interesting。

 let's consider what that is in the Boolean case。😊，So in the Boolean case。Let's have you be。啊。

One dimensional。Just to make it easy for me to draw and let's be V have V be either true or false and we'll embed true to one。

 so this will be psi of true。And this will be Psi。A false。

And at each of our data points will give us a value of u and a corresponding value of。嗯。Of B。

 which will embed to give us a one or a minus one， so we might have a bunch of data points here。😊。

And a bunch of data points here。And that's our data points。

And then what we're going to do is we're going to fit that with least squares。😊。

So we're going to say use linear predictor y hat is theta transpose x。

And that will fit a straight line。喂 there。Now， because where。Un embedding using side dagger。

Side dagger here， remember is the inverse is the unembedding map corresponding to the one hot embedding and so it's going to say。

 well， whenever y hat is positive。Your prediction。Should be true。 And whenever y is negative。

 your prediction should be false and if。Line。The plot of our predictor The transpo happens to be like this。

 that means that whenever U is over to the right here。I predict true。

And whenever you is over to the left here。😊，I predict false。And if we look at our data， we can see。

 well， in my simple sketch there didn't seem to do too badly。😊。

Although it's an astonishing idea that we can fit a function that only takes values one and minus one with a straight line。

This is called a least square classifier。😊，Weing a square loss。

We might be using a square regularizer。Then we just solved the RERM problem and this is the case where we can solve it exactly using least squares。

😊，As an example in two dimensions， when we see that it kind of works。😊。

And so here I've got U is in R2， it's embedded in R3。😊，There's one， U1， U2。

 and we've got the constant feature。And we've embedded minus11 just directly as y is minus1 or y is1 as our two representatives。

 Psi 1 is minus1， ps 2 is 1。We use a square loss and a square regularizer and these are our predictor。

 this is our predictor， the shading here shows which points。😊，You want you to map to。

One on which points map to minus-1。And of course， really what's going on is that。😊，This here。

This boundary。That's the boundary where y hat is zero and y hat is a linear function of U1 U2 hat。

We know what it must look like y hat must be equal to Theta 1 plus Theta 2 u1 plus Theta 3， U2。

And this line right here is the U1s and U2s， which result in Y hat being zero。😊，Over on this side。

 we have Y hat positive and over on this side we have Y hat negative。And。

Our unembedding maps that to one and minus one to give us a classifier。

Now we have the name and Peson metric。😊，So the name and Pearson metric remember what it is。

 it says we're going to consider a weighted sum of the different errors where EJ is the rate of mistaking VJ for some other class。

😊，And capa here is going to be the weight。😊，So Kappaj is how much we care about mistaking VJ about predict giving the answer in the case where the true target variable is VJ wrong。

😊，And what we do is we scale the losses。By Kappa。So。Suppose we have loss functions。

We've seen already the square loss。Which we'll call。L， tilde Y hat。Well， an L Tota Y hat Pi J。

 for example， might be the square。Los it might be the square of y hat minussi J。

Or it might be the norm of y hat minussi J squared。Well。

 then we'll construct a loss function from these unweighted losses by taking a weighted combination of。

😊，These losses。So we'll use a loss function， L of y psi J。

 which is Ka J times L tilde of y and psi J。😊，Yeah。So let's look at an example。

 suppose I've got psi 1 is minus1 and psi 2 is1。We're going to care about the name and Pearson metric now because this is Boolean。

 there are two types of errors we can make， the false negatives and the false positives。😊。

And our name and Pearson metric is going to be Kappa times the false negative rate plus the false positive rate。

Cappa sum number greater than zero。Notice here that we've only got one scalar capappa。

Whereas on the previous slide we had the number of scalar kappas equal to number of categories。

 and so we really should have Kappa 1 times EFN plus Ka 2 times EFP。And here， of course。

 Kappa is simply Kappa1 divided by Kappa two， if you like， because。I can set。

One of the cappers to one， and all that matters is the ratio of the two cappers in terms of affecting which prediction I get。

Now our loss function， we're going to use the square loss， but we're going to scale it。😊。

And so we'll use y hat minus y squared when y is minus1。

And'll use CAappa times y hat minus y squared when y is1。

And that will give us a weight which is greater when。The true why is one。

 and so we want to make sure that we are penalizing here false negatives more than false positives。

Here's an example， so square loss sum of squares regularizer。😊，嗯。😊，Now this on the left here is the。

ROC curves and they correspond to minimizing the weighted sum capa。EFN plus EFP。

And these are the two losses， the training losses in blue， and the test losses in red。

On the right hand plot over here， we see the minimum error classifier。

 which is given by when Kaer is one。😊，And that would correspond to。This point down here。Now。

 if we pick Kappas  point4， well then we're very concerned to make sure that we don't mistake any red points for blue points and we end up with a classifier that has moved。

😊，The boundary in this direction。Conversely， if we pick capappa is4。

 well then we're very concerned to make sure we don't mistake any blue points as red points until we move the boundary in this direction。

😊，And by varying CAappa， we will vary our preference for what type of errors we're willing to tolerate。

So let's summarize。A classifier is a predictor when the raw output is categorical。

 we have categories V1 through VK。😊，When K is2 it's called a Boolean classifier。

 when K is greater than two it's called a multi class classifier。😊。

Now we might have various error rates summarized in a confusion matrix。Now。

 when we're fitting a classifier to training data via ERM or regularized ERRM。

We embed the raw output V into RM using Psi。The vectors Psi1 through Psi K are then the embeddings of our targets V1 through VK。

We now use ERM to build a predictor for Y。We unembed。

To get a predictor will give us a Y hat which we can unembed to get a class prediction V hat。

We do this by our nearest neighbor un embedding。Next section we will talk about special loss functions for classifiers。



![](img/05c58e0f91dcb9d77778fc91d88470bc_3.png)