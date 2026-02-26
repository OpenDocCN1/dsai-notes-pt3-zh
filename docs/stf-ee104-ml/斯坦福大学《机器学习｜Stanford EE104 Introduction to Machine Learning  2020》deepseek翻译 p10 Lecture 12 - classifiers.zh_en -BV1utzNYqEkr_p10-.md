# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p10 Lecture 12 - classifiers.zh_en -BV1utzNYqEkr_p10-

![](img/4791d972dc1f7ccea49d75ca32c0827a_0.png)

![](img/4791d972dc1f7ccea49d75ca32c0827a_1.png)

Welcome to the lecturecture on classifiers。So this is the point in the class which we are going to change to our next major topic。

So far we've talked about。In the main regression。Problems where the target variable。

 y is a real number or a real vector。And now we want to switch to a different problem。

 and this problem is called classification。😊，In classification， the target variable V。Is categorical。

 it can only take a finite number of possible values。And we will call that set script V。Now。

 these problems of。Classification。Are treated in a very similar way to regression in that we will。

Have a performance metric， have a loss function。 have。

Do empirical risk minimization with the regularizers？But then they are also specific。

Attributes of classification problems， which distinguish them。From regression problems。In particular。

 we'll see that the type of loss functions we use is different。

That is there are particular types of error which can occur in a classification problem that cannot occur in a。

Regression problem。And there are ways of。Specifying the nature of the predictor。

For classification problems， which are different from how we would do those in aggress。

We will also have a chance to talk about。Poor ballistic。没关系。Yeah in the later section of the class。

Now they set script V。😊，Its elements are be noteded V1 through V capital K， iss called the label set。

 just a set of possible values of V。The VI are called the classes or the labels or the categories。

And when K is 2， this is called Boolean classification。

In which case we usually think about script V as being true or false。Positive or negative。嗯。

It's called multiclass classification。 when capital K is greater than2， when we have more than2。

Classes。Then our script V might be yes， maybe no。😊，It might be。Places or countries。

It might be languages。It might be the set of English words in some dictionary。

It might be the set of possible orderings of M horses in a race so that's the。In the factorial。

Set of permutations of the numbers1 through M。Very often we just number our。

Categories and so instead instead of thinking them as V1 through v capital K。

 we think of them at them as just the numbers one through K。😊。

So when we're predicting a categorical raw output V。😊，Given a raw input you。

That's called classification。嗯。We were talk about Boolean classification or multiclass classification。

😊，And the predictor is a map from Sc view that view is our set of possible independent variables。

To script V the set of target variables。We'll denote that by a capital G。

Remember that in the regression section， we talked about little G as being the projector and it was paraized by theta。

 but also remember that little G was the map from X to y where x was an embedding of U and y was an embedding of V。

And so here we've named the map from U to V capital G。

And so V hat is capital G of U is our prediction of V given U。😊，And then G is called a classifier。

And one way to think about the classification is to think about。😊，Which values of you？

Give a result of G of U is equal to1， which values of U？

Give a result of G of U is equal to2 and so on。And if you think about that。

 then what we've done is we've classified the inputs U。😊，Into。

K different categories or K different classes。And those classes are mutually exclusive and collectively exhaustive。

😊，So here's an example here we have our set capital U。😊，And。啊。So capital U will be the square。

The set of points。You want U2。Where I think the absolute value。Of the components in this example。

It's between minus four and4。And our set V。Is equal to。Minus1 or one， we have two categories。

One of which is minus1 and the other of which is one。And in this plot。You can see。

All of our data points， so here there's no split into training and test set。

 this is just the training set。😊，And there are， I think，100 points here。

And so we've got 100 data points， and for each data point， we have a record consisting of a U。

 which will be a point in the square。And a V， which will either be a minus1 or a1。We have。

For I between 1 and n， where n is 100。UI。Is in scriptu the square？And little VI。

Is either minus-1 or one。And we've denoted the points here。

 we've shown them in the plot so that minus one here are points a that of points。😊。

With for which VI is minus-1 are shown as red points and points for which VI equals one are shown as blue points。

 And so these are 100 data points。嗯。Now what a classifier has to do is a classifier has to map every point。

😊，In script view。2。Its a minus101。So that if somebody comes along later and says。

 here's a new point in you。Tell me what value for V you predict for it， Give me V hat。Well。

 that's what the classifier does。And we denoted that in this picture by shading the square。

 some of it is shaded pink， those points are points for which we predict an outcome。Which is minus1。

And some points are shaded blue where we predict an outcome of one。

And so if somebody comes along with some new point， let's make it some new point right here。😊。

Then our prediction for that point would be that V hatt is。-1。IfIt's here， our prediction。

Is that V hat is one。And we're trying to learn。😊，The predictor capital G。

 we're trying to construct it。We're going to learn it from this data set。😊。

And this particular predictor， we haven't talked about how to construct it yet。

 but this particular predictor was learned from this particular data set when you can see it does okay。

😊，In particular， if we look at how well is it doing？😊，On the training set。Well。

 there are points such as these points where the true value of VI is 1 and the prediction the true value of VI is minus1。

 and the prediction is also minus1。And there were points like these ones。

Where the true value is one and the prediction is also one。

But then there are other points like this red point right there。😊，For that red point。

 the true value is minus one because it's a red point。😊。

But the predicted value is one because it's in the blue region。And so。These are points。

For which our predictor is giving the wrong answer。On the training data。

And there were some points in the other with to make a different type of error。😊。

There are blue points for which we predict。The outcome should be red。

 and there are red points for which the app we predict the outcome should be blue。

One way to think about this is it's a kind of regression， it's a kind of function fitting。😊。

Instead of our function assigning。A real number to every point。Every possible value of you。

A function is assigning a category to every possible value of U。

 the category either being minus one or one， the category being red or blue。😊。

This is a good picture to have in your mind when you're thinking about what is a classification problem。

😊，Go to a bunch of data points， they have colors associated with them。

 and you want to shade in the plane。小在。对。Predictions corresponding to your shaded color match up with the true colors of the data points。

And of course it's convenient to think like that and in two dimensions。

 of course the problem is kind of easy， we can simply shade in the plane to correspond to the colors of the points that we see and there's no need for us to ever get it wrong。

😊，But if I'm working in D dimensions and D is large。

 well then I can't hope to do this by hand and I have to。

Come up with an algorithm that's going to do this for me。Let's talk about some。

Applications of classification。Here's an example， medical diagnosis。

 view is a bunch of patient attributes， so the fields in patient record are test results and age。

 gender， height， body mass， a bunch of other attributes for the person。😊，嗯。And then the Boolean V。

 the target variable， encodes some disease status as a disease or not。Or maybe it's multiclass。😊，嗯。

Does the person have COVID 19， flu， or just a cold？嗯。If we're doing advertising。

 the new contains the attributes of a person， the demographic data about an individual。😊。

And it also contains information about an ad that's being shown to them。

And then V encodes whether they will buy the item， whether they're going to click on the ad， etc。😊。

For detection， so here you might contain the attributes of a transaction， was it in person。

 was it over the phone， was it online， what kind of credit card it was？Was it international？

And then V is an attempt to。B， the categories that B can be are either that it's a fraudulent transaction or that it's a valid transaction。

😊，And so one might have a whole bunch of data。Where。

HistorWill we have historical data of transactions and they're labeled as to either being fraudulent transactions or valid transactions。

😊，And we would learn from that data， a predictor that when somebody makes a new transaction。Can be。

The attributes of that transaction can be fed into the predictor。

And then the predictor would predict whether or not that transaction is fraudulent or valid。

Image classification。Here U is an image that would be an array of pixels。And V would be。

Categories of possible objects within the image。 So we might be be looking to。cateateorize。

 natural objects， lions and tigers and bears， vegetation trees， vehicles， buses。

 and we might build a classifier that you give it an image and it tells you what's in the image。And。

One can do。Simple things where one has an image which we know contains just one。Object。

And the classifier has to return。😊，Simply which object it is。

 in which case script V is just a list of possible objects。😊。

Or we might do more complicated things where the classifier has to return a list of all objects in the image。

😊，And that would be， and then in that case the。Scrip V would have to contain not just individual objects。

 but pairs of objects or。Listists of possible objects。Here's another one， spam filtering。

 this was one of the very first successes of the classification methodologies which we're discussing in this class。

 where U contains the attributes of a male message。😊，The from address， the to address。And。Also。

A description of the text in the email message。So which words are in the text in particular？

And then V， the target variables would。The categories would be either spam or hem， hem， of course。

 meaning that it's。A good email message。And back in the mid 1990s。

 when email was becoming very popular。A technique called Bayesian classification that we。

U mayy see later in this class， we will certainly see related techniques was the one of the first successful methods of distinguishing spam from he another example application of。

Classification is sports forecasting。Here you contains the attributes of a game or a match and team A versus team B。

 so which teams are playing attributes of the teams themselves。And V encode code to which game？Which。

 which of the team？Wins the game。Or possibly a tie。Topic detection。

So U is an article or a news item in V encodes the topic， so politics， sports or business。And so on。

Another example is sentence parsing， so U is a sentence and V encodes the grammatical parsing of the sentence。

 so there is a tree structure that encodes the relationships between the nouns， the verbs。

 the adjectives， the adverbs and all of the other possible parts of speech。好。So。

When we're measuring the performance of。A classifier。

There's a very natural performance metric that we have。😊，That is probably the most commonly used。

And that is the idea of the error rate。So if we have a data set。With U1 through U N。

And V1 through VN， so we have N records for each one。

 we have a UI and a VI pair where UI lies in script U and VI。Is the target variable？

Tells us which class UI belongs to。And then the predictions are given by V hatt I， which is G of UI。

And a prediction is correct if v hat is V。And it's wrong or it's an error if V head is not fee。

The error rate E is the fraction of data points on which。The predictor gave an incorrect prediction。

So in other words， we look at all I from1 up to n， we compare V with V hat I and if there're。😊。

Not the same well that's an error and we count the number of errors and divide by n。

And this is the simplest possible。Performance metric for a classifier。And once we've computed it。

 we can come use it to compare different classifiers。

 and in particular we would do this not only on the training set but on the test set。😊，Now。

 when we're working on with。啊。Bolean classification where the set of target variables。😊。

It has only two elements， we'll call them minus one on one。Then。

We refer to the class v is minus1 as the negative class。

 and the class v is one as the positive class。And that allows us to use this very nice terminology about the possible outcomes。

😊，So we're going to be choosing V hat， that's what our predictor does for us， and we've got a true V。

 which is part of the training set。And。If V hat is one and V is one。

 well then that's a correct prediction， and we would call that kind of prediction a true positive。

If v hat is minus1 and v is minus1， well that's also a correct prediction and would call that a true negative。

😊，And then there are two different types of errors we can make。

 it could be that v is1 but we predict that v hat is minus1 and that's called a false negative or a type2 error or it could be that V is minus1 and V hat is1 and that's called a false positive or a type1 error。

And once we've constructed a predictor， we can construct a。Statistic。

 which describes the performance of the predictor。And that's this thing called a confusion matrix C。

 it's a two by two matrix and its entries are the number of true negatives。

 the number of false negatives， the number of false positives and the number of true positives and when we look at this we should realize that the first column here corresponds to V equals minus1。

 the second one corresponds to V is equal to one。And the first row corresponds to v hat is minus1 and the second row corresponds to v hat is1。

 so in the first row we pick v hat is minus1 if we're in the first column also then we've got a true negative。

 if we're in the second column then we've got a false negative。

We also refer to these entries individually as the number of true negatives。

 the number of false positives， the number of false negatives， the number of true positives， C， TN。

CFN， CFP， and CTP。And these are numbers， not rates， so that if we add up those four numbers。

 they add up to n， which is the total number of data points we have， the total number of examples。

We also have the number of negative examples which we'll denote by N with a little n as a subscript。

😊，It's the number of true negatives， plus the number of false positives。

And the number of positive examples， which is the number of false negatives plus the number of true positives and these are sums over the columns。

 so this sum right here， CTN plus CFP that's equal to n in the number of negative examples and this sum right here is equal to n。

😊，P the number of positive examples。When we look at this matrix。Of course， how do we get this matrix。

 well we have a predictor G and we can evaluate it on the training set and that will give us a matrix C。

And we can evaluate it on the test set and that gives another mat C。😊，And these two matrices。

 these two confusion matrices， are measurements of performance。And when we look at them， well。

 what we'd like to see is large numbers on the diagonal because the diagonals are。

Measurements of the number of times in which we've made correct predictions。

And small numbers in the off diagonal because all the off diagonal entries are incorrect predictions and that's what they are counting。

😊，And they're counting separately the two different types of。

Incurrt predictions and the diagonals are counting separately the two different types of correct prediction。

Now， the。啊啊。There are some very standard terminology that surrounds the confusion matrix that's worth going over。

In particular， the false positive rate is simply CFP divided by n and the false negative rate is CFfn divided by n and the error rate is the sum of those two CFP plus CFN divided by n。

😊，There are also， there's also a whole bunch of other terminology that people like to use。

 often in very specific fields。😊，So people will talk about the true positive rate or the sensitivity or the recall that CTP every NP。

 it's the fraction of true positives， which we guess correctly。😊，The false alarm rate is CFP on NN。

 the fraction of true negatives we incorrectly guess as positive。😊。

There's the specificity or the true negative rate， which is CTN on NN。😊。

The fraction of true negatives that we correctly guess。And there's the precision。

 which is CTP on CTP+ CFfP， which is the fraction of our positive guesses that really are positive。

And these are well they're used in different fields， quite a lot of them are used in medicine。

 some of them are used in specific branches of statistics。

 we will I think never use things like sensitivity or specificity in this class in machine learning almost always people just look at the confusion matrix and the counts which are readily interpretable and readily converted to one of these other measures if you're working in。

😊，That appropriate field。嗯。Now， one of the things about looking at the confusion matrix is that it highlights for us that we have really two。

Mettris。For a boolean cifier， we'd like to keep both the false positive rates more and the false negative rates more。

😊，And the sum of those two numbers is the error rate。嗯。Keeping the error rates small is fine。

But sometimes it's not what you want out of a classifier。So for example， if you have。

A manufacturing line， you have a camera that's looking at the objects that are coming off the magic manufacturing line and is trying to determine whether or not they are correctly manufactured or incorrectly manufactured。

😊，If you've got very few errors in your manufacturing process。

 then a huge percentage of those manufactured objects will actually be correctly manufactured and only a very。

 very small percentage will be incorrectly manufactured。

Clasification is often difficult for such manufacturing problems and very often the。

predictdor that minimizes the error rate is simply to predict。All of the objects coming off your。

Production line are actually correctly manufactured。However， that's completely useless， of course。

 because it's giving you no information。😊，What you're much more interested in in such a situation is to be able to detect those bad。

Objects。Those incorrectly produced objects。 And so one would have a classifier there that is。

Willing to incorrectly classify a few good objects as bad。

As well as it caught most of the bad objects。And so there one is quite happy to accept a few false positives。

 positive here corresponding to bad objects in exchange for a very small number of false negatives。

For where the false negatives there would be incorrectly assuming that a bad object is good。

This is a very common situation that the thing you're trying to detect is rare。😊。

Choosing a classifier that minimizes the error。Gives us an uninformative classifier and it's much better to try to choose a classifier that focuses on either false positives or false negatives。

Now we still need to be able to compare classifiers。

 and it's very often convenient to have a single metric， a number。😊。

And the way we do that is we combine them with oh weight， and that's called the Naman Pearson metric。

 E and P。It's CAa times the false negative rate plus。The false positive rate。

And so here Kappa is some positive number， and it sets how much we care about false negatives compared to false positives。

😊，So cap is very large， then our name and Pearson metric。😊，Is affected very much by false negatives。

And not so much by false positives。If Kappa is very small。Then。

Our name and Pearson metric is large when we've got a large number of false positives。

And not so much when we've got a large number of false negatives。And a CA is one。

 well then the name in person metric is just the sum of the false negative rate and the false positive rate。

 which is the error rate。Let's look at this more convenient in me。A traderade off graph。

If you pick any classifier。😊，You designed it using whatever your favorite method of designing classifiers is。

 and we haven't told you how to do that yet。And then you say， okay。

 I've got a classifier and I can compute its false negative and false positive rate on the test set。

😊，And that those are going to give me two numbers。And I can plot those two numbers。

On this plot right here。 So on the horizontal axis here， I've got the。

The false negative rate and the vertical axis。I've got the fast positive rate。

And so you give me any caifier， it has some particular point。There's one。There's one。还是哪的？

And so different classifiers correspond to different points on this。On this plot。

Now one thing that's worth observing on this plot is that there are some classifiers that you will just never use one is G3。

😊，And the reason you would never use G3 is that if you compare it with G2。

Or G2 does better in terms of the false positive rate and the false negative rate。And so。

G2 wins on both counts and if you're interested， even if you're more and concerned about one of those measures than the other one。

 you would still use G2 over G3。On the other hand， we compare with。😊，G1。Well。If I compare G1 with G3。

Well， G1 does better in the false negative rate， but worse in the false positive rate。

And so I might well use G3 instead of G1。But if I've got G2， I would use G2 over G3。Now。

 if I compare G1 and G2， well that's not so easy because G1 has a smaller false negative rate。

But a larger false positive rate than G2。And those two classifiers are incomparable。

Choosing between them is up to you， the designer of the system。

You may be more interested in keeping the false negative rates small。

 if you are more interested in keeping the false negative rates small， then you should choose G1。

If you're more interested in keeping the fast positive rates more， then you should choose G2。

If you have G2 available， then you should never choose G3。So when you look at a classifier。😊。

On this plot。The important classifiers are one where are those for which there is nothing better in both false positive and false negative。

 so if I look at a particular classifier，And say， let's look at G2。And then if I draw here。

 the region of the plane。🤢，Consisting of。Values for the false positive and the false negative rate which are better than those achieved by G2。

If there's no classifier in that region， then it's a good classifier。😊，Conversely， if I look at G3。

And I look at。The region consisting of better performance。Well， there are classifiers。😊。

In that region。So G3 is a bad classifier。Now the good classifiers have a name they're called peririto Opti。

They're good because no other classifier is better in both false positive and false negative rates。😊。

The set of all of these peririto optimalim classifiers so the peririto optimal classifiers are these red points。

😊，So the set of all peri optimal points is called the operating characteristic or the rock。😊。

Rock stands for receiver operating Char this is a term that goes back to the design of radar systems in World War II and almost nobody calls it the receiver operating characteristic anymore。

 almost always it's just a photo of the rock。And so what we commonly do is we develop many different classifiers。

And we plot them on this plot。We rule out the ones which are bad， which are not burrito。

 and then out of the ones that are burrito， we get to make our choice。Now。

 when we've got the name and person。Measure， that's caper times the false negative rate plus the false positive rate。

Well， what that's doing is it's measuring performance in a particular direction in this plane。😊。

And so when I think about this， I'll call I've got the false negative rate and the false positive rate。

😊，And I can， if I've got a particular capa， I can draw a vector。😊，There's a vector and that vector。

It in the direction。嗯。Kappa 1。And so。I can think about my false。

 my name and Peson metric has Kappa1 transpose。CFN on N， CFP on N。Now。

 because we're using the vector Ka1 multiplied by the vector of coordinates in this plane。

 what that measures is it measures the distance from the origin in the direction Ka1。

And so if we look at the set of all points which are for which Kappa one。Transpose。

 multiplied by the coordinates of that point is equal to say。1。That would be。The line。Here。

And then if we look at the set of all points for which that linear combination， Ka1 transpose。

 multiply by the coordinates， is equal to two， it would be a different line。And so on。And so。

 by minimizing。Caappa。Terms the false negative rate plus the false positive rate。

 we are trying to pick the point that is on。The line of these lines， which is closest to the origin。

In this particular case。😊，The point。Is G2。For this particular value of Kappa shown here。

And these lines have a slope of minus k minus Kappa。

 and so by varying kappa between zero and infinity， we have slopes when Kappa is zero we have。😊，啊。

A vector pointing in this direction， and when Ka is very large。

 we have a vector pointing in this direction。So we can pick Kappa。😊，According to our preference。

 if we make capappa。Very large。 Then we're going to try and minimize。 we're going to try。

 we're going to have a slope lines that look like this。And we're going to try。

We're going to be concerned about performance where the。Best thing one can do in order to。

Make the performance measure small is to choose a predictor that has a low false negative rate。

If instead。We。Use a capa， which is very small。 Well， then Kappa1。Looks。A vector like this。

 and we're going to have corresponding。Lines it in this direction and the best thing we can do to make that。

Performance metrics more is to pick a。Predicctor。For which the false positive rate is more。

Here's an example。😊，Here we have。The same data set that we showed before。

 we have blue points and red points， the red points are minus1 and the blue points have target variable one。

We can see there are some false negatives。The false negatives are blue points for which the classifier would predict red。

So。Whereas a false negative？There's one false negative right in there。Underneath there。

 there was a blue dot， which I will know。Make visible， there it is。So this blue dot there。

Is in the red region， is in the region which our classifier will predict red。

 That's a false negative。And then there are many false positives。😊，I all of these red dots。

Points which we would predict predict as blue would give a positive prediction。

 but it's a false positive。If you count the number of red dots。

 false in the blue region that for classifier number one， that turns out to be 16。

And we've already seen that there's one。Blue dot in the red region。And so。

This here is our false negative， this here is our 16 false positives。This。

Is our correct predictions of minus1， so these are red dots in the red region and there were 24 such red dots。

And these。Are blue dots in the blue region， and there are 5 nine such blue dots。

Now if we on this particular test。On this particular example。

 there are 100 points and so the false negative rate is 0。01。😊，And the false positive rate is 0。16。

And when we can plot those， false negative rate is 0。01， false positive rate is 0。16。Well。There's 0。

01， there's 0。16。That's predictor one。Right there。We can look at predictor too。

 This is a different predictor。 You can see it's got different regions。

 and this predictor is encompassed more。 So when you look at these this set of data set。

 this third of data points， you can see that it's largely。😊，Let me erase that。

It largely consists of blue points going across the middle here。🤢，And red points。Going this way。

And so our predictor here is focused on getting the blue points。Covered by blue region。And。😊。

Unfortunately， it's going to have some red points covered as well。

 and that's why it's got a large number of false positives because。

The red points have been classified as blue。Here we've said， well， we don't want that anymore。

 We would like to balance the。The red and blue errors。 And so we've got a predictor that。

Is classifying more of the red points。It's actually red。

 more of the region in which the red points are is as a corresponding prediction。Of red。As a result。

 we can look here and we can see， well， now there are eight false negatives。😊，There's one。嗯。

But there's only eight false positives， here's one。And that gives us corresponding false。

 positive and false negative rates of 0。08， which is right there。

Here's plot number three is a classifier at the other extreme。😊。

Here we've tried to focus on getting the rid。Points correct and in exchange we're getting some of the blue points wrong。

What does that mean in terms of false positives and false negatives。

 it means that we've got very few false positives and a large number of false negatives。😊。

Our false positives are red points that are classifiedified as blue， and there are two of them。

Here is one of them。And we've got a large number of blue points that are classified as red。

 there's one of them。😊，We resulting counts。There are 23 false negatives。And two false positives。

 and that gives us this classifier right there。So there are three classifiers。😊。

And which one you pick out of those three？That's up to you。There is no way of choosing between。

These three classifiers。Number two beats number three in false negative rate。

 but does worse in false positive rate。Number one， beats number two。In the same way。嗯。And。

Neither one of them， we would say neither one of them dominates the other。And so。

This is a design question， and depends on the particular problem。

That you're looking at whether you're interested in a classifier that has smallest overall error rate。

 let's look at what the overall error rates are。😊，So this one has an error rate of 17。

This one has an error rate of 16 and this one has an error rate。

Of 25 and those are of course error counts， error rates are 0。17，16 and 0。2，5。

So the one with the smallest error rate is number two。😊。

The one with the smallest number of false negatives is number one。

 and the number one with the smallest number of false positives is number three。

And when you look at multiclass classification。Well， there are no longer just four possible。

Values for V hat and V。 There are K squared possible values， because there are K。Classes V1，2， V。

 capital K。And when each of V hat and V can be in。Any one of those classes。

So there are k squared possible outcome pairs。U when we say V hatt is VI and V is VJ。

 it means the true value is Vj and we're predicting VI。😊。

So the only ones that are correct are when VI is VJ。And it's incorrect when VI is not Vj。

 in other words， if V hat is V， that's correct and if V hat is not V that's incorrect。😊。

So there are key different ways in which we can the same make a correct prediction。😊。

If we predict V1 and the truth is V1， that's correct， if we predict V2 and the truth is V2。

 that's also correct。But there's also a bunch of different errors。😊，If we predict V1。

But the truth is V2。Well， then that's an error。😊，But there's a different era where the truth is B2 and we predicted V3。

So there are k times k minus1 types of errors， one for each possible pair where I is not equal to J。

はい。So we have a K by K confusion matrix。And the IJth entry of the confusion matrix C is the number of data records where we guessed we predicted V hatt was VI。

 but actually the true V was VJ。😊，And you should be aware that sometimes people transpose this。

 so they swap I and J。And。Of course， that's just a convention。Of course。

 the entries and C add up to n the number of data points。

 the column sums give the number of records in each class。

CII is the number of times we predicted VI correctly。If I is not J。

 then CIJ is the number of times we mistook VJ for VI。Now these quantities CIJ。

 where I is not equal to J， if we normalize them by the number of records in。

 that's called the error rate for those particular pair of classes， EIJ。

Is the number is the fraction of the data points on which？We mistake。VJ for VI。

And the overall error rate is the sum。Of all the different error rates。

So here's an example here we've shown data points which have target value one is red。

 two is green and three is blue。And we've got a classifier that classifies points in the plane as either red。

 green or blue。😊，And you can see that it's doing okay， the green region mostly contains green points。

 the blue region mostly contains blue points and the red region mostly contains red points。😊。

There are a few cases where we have green points， but they would be predicted as red。Here's one， two。

 three。4，5。So those are green points that we would predict as red。

And there's a blue point that we will predict as red as well， that's this one right here。😊。

And so there's one of that type of error as well。what other types of error are there。

 there's a red point that we are predicting is green。で。There's this error。

And there's a green point that we're predicting is blue， that's this point right there。😊。

And that's this error。All the other points are correctly classified。

 we've got 39 reds that were classifying as red， 34 greens that were' classifying as green and 17 blues that were classifying as blue。

😊，Now I can take the error rates while there are 100 points。

 so I simply take all the non diagonal or the off diagonal entries of the confusion matrix。

 divide them by 100， and that gives me。😊，The error rate matrix there And if I sum up all of these different errors。

 I'll find this a 10% error rate。Oh。Now， just as。In the Boolean case。

 when we want to pick a classifier， it's very often convenient to have one number that measures that is our performance metric。

And the way we would do that is we would use a weighted sum of the different types of errors。Now。

 you could attach a weight to all of the different categories of errors so in our。😊。

Three class example， there are six possible types of errors。

 and so you could have six different Kappa values。😊，And use those six different Kappa values。

To weight the different errors。 And that would be a perfectly fine。Performance， measure。In fact。

 we don't do that， what instead we tend to do is we tend to use a Kappa value， which is only defined。

😊，Per column。 per true class。And so we'll have one weight which is associated with these two errors。

One weight associated with these two errors and one weight associated。

With those two errors in the last column。And so associated with each column， there's the error rate。

 which is were deing my E subj。😊，It's the number of times we missed it with VJ for some other class。

And we can divide by N and get the error rate as well as the error count。😊。

And then we take a weighted sum of these three error rates。And that's the Naman Pearson era。

So Kappa J is then how much we care about mistaking VJ for something else。

And if Kappa J is one for all of the different。😊，Eyes。

Then the name in Pearson error is the error rate， which is summing up all the different errors。

So to summarize in this section， we've talked about how you measure performance of classifiers。

 both for Boolean classifiers and for multiclass classifiers We haven't yet talked about how you。😊。

Find classifiers。And that's coming in the next section。



![](img/4791d972dc1f7ccea49d75ca32c0827a_3.png)