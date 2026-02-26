# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p13 Lecture 15 - multiclass classification.zh_en -BV1utzNYqEkr_p13-

![](img/991363932b72f04d9be3b2949b136f7d_0.png)

![](img/991363932b72f04d9be3b2949b136f7d_1.png)

Hello， welcome to this section on multiclass classification。

So remember the key ideas here we're trying to。Do classification where the target variable can take one of K possible values。

And we have raw target values， which are。'Say number one through capital K。

But we embed those using the map y is equal to psi of V。And as a result。

 y can take one of capital K values P psi 1 through P psi capital K。

 each one of those is a vector in RM， we get to choose what M is。

 we get to choose what those psi 1 through psi ks are。And once we've done。

 once we've got a predictor that produces a why。From an X， we have to get back。to a V。

 and the way we do that is we look at the Y hat that we've got produced by the projector and we look over all of the different size p Psi 1 through PsiK to find the one that's closest to the Y hat。

And that's going to tell us which of the classes to unembed and give us the resulting V hatt。

And of course， the predictor that produces Y hat from X is constructed via regularized empirical risk minimization。

Now at the end of the day， what we do is we validate using the name and Pearson performance metric on the test data。

 so we've picked our CAs where KO J is our distaste， our displeasure and mistaking。BJ。

And our performance metric is then the sum over J of Kappa J EJ。

Where EJ counts the number of times that we mistook3J。And of course， if all the cap is are on。

 that's just the error rate。Oh。Now we're going to want to construct。诶。Los function。

And it's not quite so easy as it was in the Booolean case So in the Booolean case。

 remember how it worked， let me just use this as a little sketch pad here。We embedded。

So this is our M where m is1， so we embedded at plus one and minus1。Well call this Psi 1。Inside two。

And then we had ideal loss functions from the name and person loss。So if the true why was。hy。Was one。

Then。Our ideal loss function。Would be this？Our ideal loss function would be this and it would say that since y was one。

 our ideal Y hat should be anything negative。So we want to generalize this idea to the case where we've now got multiple。

si I is not just two， and we've embedded them in our M and M is not just one。

So the first idea we need is simply to know when a vector is closer to one point than another point and that's so here we have two points。

We have point A。And point B。And we have here this green line and this green line。

Is the perpendicular。Bysector of those two points。And。

That comes about mathematically in the following way。

 If I ask when is a vector Y hat closer to a than it is to B。 Well， the distance。诶 from。

Y hat a is just the norm of y hat minus a and the distance from y to B is the norm of y hat minus B。

 and so we can ask ourselves the question when is one closer than less than the other。

 that's this inequality right here。😊，Now we square both sides。 those are both two norms。

 What happens is we get an expression which looks like y hat minus a。Norm squared。

It's less than a week to the norm of y hat minus B squared。And if we expand those squares， well。

 then we get that the y hat transpose y hat minus 2 a transpose y hat。Plus， a transpose a。

Co quarterta Y hat transpose Y hat。-2。B transpose Y hat。Plus， B transpose B。

And the nice thing about this is that those。Qudratic terms in Y hatck go away。And this inequality。

Reduces。这在心里 quality了。It is this inequality。Two b minus a transpose y hat minus the normal b squared。

Plus the norm of a squared is less than zero。And in particular。

 the thing to notice here is that this only depends on why hat。In this nice， simple way here。

It's a vector transpoposed times y hat。And so this is equal to zero。😊，Along this green line。

It's less than zero when a y hat。Is。On the。A side， and it's greater than zero when y hat's on the B side of the green line。

And the decision boundary explicitly just replacing that inequality within equality。😊，Is right here。

That's a hyperplane that's an equation of the form C transpose y is equal to D。

 where C is effective in RM and D is a scalar。And here in particular， C is2， B minus a。And D。

Is the norm of a squared minus the norm of B squared。And this hyperplane has to pass through。

The midpoint to A and B。And you can check that it does by substituting why hat is。A plus B on2 into2。

This equation right here and checking that you get zero。😊，Now we can use this。

Analysis to construct a notion of signed distance from the hyperplane H。 So the hyperplane H is。Here。

It's this green。Hyperplane。It's the perpendicular bisector between A and B。

And we're going to say that we're going to measure the distance from H。

And so I'm going to have some points on this side。And some points on this side。And these points。

 we're going to say a distance minus one。From。The hyperplane H and these points we'll say are distance  one。

So instead of labeling them both as having distance one。

 the ones on one side will get negative distance and the ones on the other will get positive distance。

And I'll point why hat here。Has some distance here， which is about minus2 from the hyperplane。

 I might have another point。Say over here。And that would have a distance plus two or maybe slightly more than two the way I've drawn it from the hyperplane。

And where does this formula come from？😊，Well。We have this。Nice formula here。Which is。

This inequality here， which is an it。It defineines for us which side of the hyperplanam we're on。

 and it has the form of C transpose y。Plusテ。Now。Over here。

We've simply taken the value of the left hand side of that inequality and made it equal to our distance measure。

 but we've scaled it， we've scaled it by2 to the norm of B minus a and as a result D has this form。😊。

D is equal。To U transpose y plus V， where U here is a unit vector its。

B minus a divided by the norm of B minus a。And because U is a unit vector， it's。Measuring。Distance。

Which is corresponding to the unit distances that we use in the plane。If so in other words。

 if Y hat actually is a distance D。From the hyperplane。

 then capital D here will be the appropriate sign appended on to Y hat。嗯。😊，So D is zero。

 that's the decision boundary， that's the decision boundary that decides whether we're on the A side or the B side of the hyperplane。

And。If it's negative， were closer to A than we are to B。

So why do we want a notion of signed distance and the idea goes like this？Suppose we have。

 let me draw a picture。啊啊。So this will be R2 set here， MS2。So we've embedded our。

Cateorical variables in the plane。A2。And the embedding points， well， let's just pick them。Let's put。

One over here， one over here and one over here。🤢，And I will label those Psi1， Psi 2 and Psi3。

And those are the points to which our categorical target variables embed。Now。

 with those points we're going to。So okay， well those are our embedded points。

 we'd like to define a loss function with those points， that's what we'd like to do。😊，Now。

The idea is， of course， is that we're going to have a predictor that produces for us a Y hat。

 and we would like that predictor to。Be inclined to give us a Y hat that's close to Psi 1 when y is1。

And a y hat that's close to psi2 when y is2 and a y hat that's close to psi 3 when y is3。😊。

So let's divide up the plane。😊，Into regions。The vrennoi partition of the plane。Like that。

And then this。Region right here。This region here is the region。

Which if we have a Y hat within that region， then it's unemedded back to Psi 1 and therefore back to the target value corresponding to Psi1。

And so what we'd like is we'd like to have a loss function， which。

Encourages why hat to lie within that region。When y is equal to Psi 1？

We can imagine such a loss function。 Here's what it would be。 It would be zero。

If why hat lies in that region？And one elsewhere， it would be one。Here。And zero。Here。

And such a loss function would count up for us the rate at which we mistook y1 for something else。😊。

And so in our loss function， if we summed up that and divided by n。

 that would give us precisely the rate which we mistook y1 for something else。

And so Kappa1 multiplied by that loss function。Would count up for us the name and person contribution of the loss。

4our。The target， Sa1。And then we would do another one， we'd have a loss function。😊，Of course。

 we've got a different loss function for y1， Y 2 and y3。If I look if this is y1， this is y2。

 this is y3， I would have a loss function which was zero here and。😊，One here。

And that would be the loss function corresponding to y is equal to。2。😡。

And so we have three different loss functions。Functions of Y hat。One when y is P psi 1。

 one when y is psi 2 and is when y is psi 3， and then each one is zero on the region corresponding to its psi I。

So how do we construct such a loss？Well， what we can do。😊。

Is we can use the signed distance functions， DIJ。And what DIJ is going to be。

 it's going to be the distance， the sine distance of Y hat from the boundary between Psi I and Psi J。

😊，Let's look back at our example。😊，This is Psi 1， Psi 2 and Psi 3。Now， D1。

Two is less than zero when we are closer to psi 1 than we are to psi 2。So D12 is less than 0。

 whereas that that's everywhere to the left of this line。😊，Where is D13 less than zero？😊。

That's everywhere。😊，Below that line。Let me mo my two lines。And so if D12 and D13 are less than0。😊。

Well， then。I'm in the region belonging to Taiwan。And similarly， I'm in the region belonging to Psi2。

😊，That's this region。If D。If D。うは。21 is less than 0 and D23 is less than0 and finally over here I have D31 is less than0 and D3。

😊，Two is less than zero。So in other words， I need for any given region。For any given I。

 if I want Y hat to be in the region belonging to Psi I。

 then I need DIJ to be less than zero for all the other Js。

Now that we've got these signed distance functions。

 we can use them to construct our ideal loss functions。

Here are some examples to be explicit in the most common cases， the most common cases are， of course。

 the Boolean。In the Booyian case。M is one， and so I've just got R here。Si1。Is minus1 and psi 2 is1。

And then I've got D12。Is less than zero。Over here。And D21 is less than zero。Over here。

And so if why is？In the region corresponding to Psi 1， so that means that y is minus1。Well。

 then we need。We would like D12 to be less than zero。And that would be。

And then we'd have a loss function which was zero over here， say and large over here。

 and that would be our ideal loss function， our name and personal loss function。😊，Similarly。

 if y is plus one， then we want D to1。诶。Y is plus1 then that corresponds to psi2。

 and so we want D21 of y hat to be less than0 and D21 of y hat is minus y hat。

 and so we want y hat to be greater than zero。If we look at the one hot case， there's theirsi J。

 this should say Ej， let me just correct thatsi J is Ej。诶。And。If we compute what DIj is， well。

 the distance between DIJ， let's just look at it。This is psi1 and this is psi 2 in two dimensions if we're embedding using one hot。

 this is of course10 and this is01 and so the distance between those two points is simply root two。

And so DIJ is Yj minus Yi on route 2。Where。In order to compute that， of course， we've used。

Our definition。Hereair。2 B minus a transposed y hat divided by2 the normal b minus a。

 obviously the twos cancel and b minus a transposed times y hat gives us Y hat I minus y hat J or y hat j minus y hat I depending on the sign。

So when y is EI， we want the max over all J naughty equal I of DIJ to be less than zero。

And that means that we want why。J minus Yi to be less than zero。

 and that's the same as saying that Yj is less than Yi。So in other words。

 we would like the corresponding。啊。啊。Component of Y hat to be the maximum component of Y hat。

So let's use these to construct loss functions explicitly what we've got to do well we've got to give k different loss functions。

 one corresponding to each of the possible values of Y remember loss is a function of Y hat and Y and Y here can only take K possible values。

😊，Which we've denoted as L of Y hat Go asi I。It's how much we dislike predicting why hat when y is sight I。

In other words， if。To come back to our example。Yes。D12 is less than 0 and D13 is less than 0。

 then we'd like the loss function corresponding to L of y hat psi 1。To be small。Enlarge。

When Y hat doesn't satisfy these two conditions。And that gives us immediately the name and Pearson loss we can can a loss function of。

Zero on the region corresponding Jesai I。And cap I elsewhere。😊。

And that means when we take the average of that name and person loss。

 we get K I times the frequency with which。😊，Why hat？Is mistaken why hat gives an answer。

 which is not I when why truly is I。And this is， of course。

 the analog of our nice square loss functions。That we've seen before。Now the downside is， of course。

 that it's hard to minimize these。Disconinuous loss functions which have derivative zero almost everywhere。

And so instead we use what's called a proxy loss， a loss that approximates。네。Name in person loss。

But is it more easily optimized so we either would like it to be convex or differentiable or both？

So here's the perhaps one of that there are two really common loss functions that are used。

 one is the hinge loss， this is the multiclass hinge loss。

It's Kappa I times the maximum of1 plus DIj of Y hat。

 and we're maximizing our over allal J not equal to I。And this is a loss function， which。Is。0。

If Y hat is in the right region， within're a margin of at least one。

So it has to be not only within the right region， but it has to be deep within the right region。😊。

And this is a convex but not differentiable loss。If you use quadratic regularization。

 then it's multi class。Support vector machine。If we have a Boolean embedding。

Then psi 1 is minus1 and psi 2 is1， then it reduces to the usual hinge loss that we've seen before。

 it's one plus y hat。The positive part times Ka1 when y is minus1。

 and it's the flip of that when y is1。Here is the corresponding surface plots for it in the case which we've been discussing so far this is our。

Example， we've got three size， Psi 1， Psi2 and size 3。 and you can see you've got a loss function。

 which is。Conbas。Which is piece wise linear。And which is zero。

When you're deep within each of the three regions。 So of course。

 you've got three loss functions here in the top right graph here。

 we have the loss function corresponding to。The case when y is one。

Y is Psi 1 in the bottom right we have the case where y is psi 3。

 and in the bottom left we have the case when y is psi 2。

If you look in particular at the top right when y is Psi 1， you can see that the last function is。0。

When。We are。Deep within the region corresponding to Y1。Here's the other most common loss function。

 the multiclass logistic loss， so this is the following this is the log of the sum of the DIJs。😊。

So if all of the DIjs are less than zero。Then this is going to be well。

 the sum of E to E and the negative numbers， and so it'll be a relatively small quantity and it will grow as the DIJs grow。

It's complex and differentiable， it's called a multiclass Lo loss。😊。

And if we use this as our loss function， we're doing multiclass logistic regression。So here's a plot。

Of that loss function again， we can see three different loss functions。

 each one associated with a different region of the plane corresponding to our different representatives。

And for each one， the loss function is small on the corresponding region and grows outside the region。

The log sum X function is what's at the heart of this loss function。

 and this is an interesting function because it is convex differential and it's approximately the maximum function。

😊，Sometimes people call it the softm function， but you should be careful about that because there are other functions also used in machine learning as it happens。

 that're also called the softmax function。😊，one of the nice thing about the loxom X function is then。

😊，We know how far it is from the max function， it's always greater。😊，Greater than or equal to。

 the maximum of the Xs， and it's always less than or equal to the maximum of the X's plus log n。😊。

Let's look at an example， this is。A three class example。

 this goes back to 1936 is a very famous data set， which was collected by the statistician Fishcher。

😊，He took measurements of 150 different plants。All of which were three different species of iris。

 so there's 50 from each of the three different species。And for each of those。Samples。

 he made four measurements， the sepL length， the sepL width， the petal length， and the petal width。

We can plot them here so this plot this is simply an arrangement of all the data so for example in this plot on the top right we've plotted sL length on the vertical axis against petal width on the horizontal axis。

😊，You can see that there are three species， the red， one other the species is indicated in red。

 one of them in green and one of them in blue。😊，You can see that telling the mid。😊。

From the others is rather straightforward。In turning the green and blueer part is a bit more difficult。

😊，So here we've done classification with using only two of the features， SepL length and SepL widths。

😊，And those are plotted in this figure。Again， we can see green dots， blue dots and red dots。

 and it's relatively easy to separate the red dots。

 and this is the using a linear predictor with one hot embedding， multiclass logistic loss。

 and we're minimizing the probability of error so that the capas are all one。😊。

And here there's no training and test set， we simply trained it on all the data。

 course if we had more data， we would be using a training and test set and would'd also be using regularization。

😊，The confusion matrix shows us what we can see from the figure that we've got all the red dots perfectly correct。

 we haven't mistaken anything for a red dot， but some of the greens and blues we've got wrong。

 we've mistaken 12 greens for blues and 13 blues for greens。😊，And as you can see in。In the figure。

 there's no clear way to separate the greens from the blues。

Now if you do classification with all four features， of course you can't plot it anymore， same thing。

 one hot embedding， minimizeise the progressive error。

 well then you can do much better then you can get a confusion matrix where there's only one error out of 150 plants。

 sorry two errors， two misclassifications。😊，UmWe've got one blue classified as green and one green classified as blue。

So let's summarize when we're doing multiclass classification with like a loss function that encourages the correct un embedding。

😊，So when y hat is close to Psi I， well， then we want L of Y hat Psi I to be small。

And we want to be not small when Y hat is not close to sight eye。

The most common losses people use are the multiclass hinge loss and the multiclass logistic loss。

And these two classifiers are called the SVM and the Lo classifiers。And both of these classes are。

 both of these losses are convex。😊，So we can solve easily the AERM or the RAM problems in the case where the predictor is a linear predictor。



![](img/991363932b72f04d9be3b2949b136f7d_3.png)