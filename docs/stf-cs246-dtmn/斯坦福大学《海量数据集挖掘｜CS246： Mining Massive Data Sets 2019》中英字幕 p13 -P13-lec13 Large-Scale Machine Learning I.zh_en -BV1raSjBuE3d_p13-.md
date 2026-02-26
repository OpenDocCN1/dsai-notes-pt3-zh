# 斯坦福大学《海量数据集挖掘｜CS246： Mining Massive Data Sets 2019》中英字幕 p13 -P13-lec13 Large-Scale Machine Learning I.zh_en -BV1raSjBuE3d_p13-

![](img/272a1e3d34d51ed1b268748e5c15cdb9_0.png)

Okay hello welcome to the class here is the plan for for this week so the first order of businesses that homework3 submission is this coming Thursday and the second order of businesses that thank you for filling in the midpoint survey the feedback was actually very useful and super helpful so we are all acting on it and we are preparing some new lectures which will be brand new and thank you for that so thank you everyone who sent us feedback how to improve the course we are already acting on it。

😊，So now what we talk about this week， this week we'll talk about large scale machine learning and in particular。

 we we'll touch on two classes of models。 Today， we will talk about something called large scale decision trees and how would you build these types of models over petabytes of data。

 And then on Thursday， we'll talk more about neural network models and how do you make those scale and so on。

 And kind of our goal here is not necessarily to cover everything that 229 covers。

 but focus more on the scalability and practical issues。

 So that's how we are going to think about that。Great。

 right so where we are right now is we'll be talking about this side of things and this will be very interesting because last time I talked about graph embeddings and creating feature vectors out of nodes。

 so once you have those feature vectors you would use one of the methods we'll talk today and then on Thursday to basically train the models and make predictions。

😊，What's the goal at high level， the idea is that you want to learn a function that maps the input to the output。

 That's all what machine learning is about。 So the idea is that we are given a set of training examples write some x comma Y and this y is a function of x and given these pairs x comma y I would like to learn or approximate the function F is that's essentially what we try to do right so given the x I want to predict Y。

😡，And these x can be a multidimensional vector of some features。 and y can be some output variable。

 And this is the most common form of learning。 and it's called supervised learning。

 The reason is because for every x， we are given a super supervision。

 a supervised signal Y There are other types of learning rather than supervised So， for example。

 clustering or singular value decomposition。 you can think of it as a form of unsupervised learning where basically we are given some just x。

 no y and our our goal is to learn some function of those x like the clustering structure of those x。

 Then on graphs， what many times happens is that you are in this what is called semisvised regime where you are given some labeled data and you are also given some unlabeled data and your goal is to estimate this function。

 the simplest way to do this is to ignore unlabeled data and just use the labelbeled pairs to learn the function。

 but you could use your unlabeled data。😊，X to help you figure out how this function should look like right so you can learn more then there are other examples。

 for example， active learning， the setting here is that whenever you make a prediction only then you observe the value so if you think for example in the recommender systems recommender systems play in this type of row when I make your recommendation I predict how much you like the movie and then I see whether you liked it or not right so I make a prediction。

 make a decision and then the system gives me feedback and then I can learn something about what kind of movies you like and the way you would do this in let's say when we talked about latent factor recommender systems is that you would make your predictions get the outputs and then you would reoptimize the model。

 run a couple of iterations of stochastic gradient descent to update your f based on the feedback you have received。

And then the last thing I will mention is this notion of transfer learning where I want to learn some f of x but really I want to learn in such way that it works well on some new domain on some new data Z right maybe I have a data set of movie recommendations and I want to be able this function to predict what music you will like and that is called transfer because you transfer from one domain to another domain but you see how all these different kinds at the end worry about finding this function F that can make certain kinds of predictions so now the question is how are we going to formalize this we would like to do predictions so it means we'd like to estimate this function F so that y equals f of x and then you can say what can y be and why can be different things if y is a real number then we call this regression then we call this predicting the real number we call it a regression。

😊，A predicting a categorical number， you know， like a color or know big， small medium or whatever。

 Then I would call this classification。 And then there are also prediction can be very complex。

 For example， in in the commander systems， you could imagine that what you are really predicting is not just how much you will like a certain item。

 but actually the ranking the ordering of the items or in natural language processing， you could say。

 given a sentence， I want to predict the entire parseory of that sentence right So here the output object is not just a number or or a category。

 but it's really a complex objects and things get very interesting when you go beyond a simpler regression and classification。

😊，Right and another important point is data is labeled。

 so it means we have many pairs of x comma y where x。

 you know we can think it as a long vector of some kind of binary categorical real value attributes or features and then the y value will call it a class or a real number this is the output that goes together with that with that x what is our goal our goal is that given some what we will call labeled data x comma y we want to build this function F so that it works well on some unseen data x prime and makes good predictions y prime so in some sense the interesting thing about machine learning which is this kind of this goal that will never really be able to achieve is that I'm given some data X and y and I can build my function f using this but what I will really care about is that when some unknown data。

 unseen data X x prime。😊，Comes I'm predicting these labels well。

 so I always worry about how well will I be able to do on the stuff I haven't yet seen right It's on some future data。

 In some sense， I don't care how well can I predict the movies people liked tomorrow。

 sorry yesterday， but I really care how well will I be able to predict movies tomorrow and maybe I'm making some assumption that the structure of the movie recommender yesterday will kind of generalize to tomorrow So there is and the way we think of this is we think of the red part of the data as the training data and the blue part of the data。

 we think of it as as the test data。 But if you think about deploying your model in production。

 making recommendations in our predictions in real time。

 the point is that't these data hasn't even been generated these users haven't even yet shown up to to your website or these emails if you are classifying them haven't even been written yet。

 that's the idea。Ting I want to generalize to test right so this hope where we say that we want this F of x to also work on this unknown labels data X prime or y prime this hope is called generalization right so in some sense。

 we don't care。 how well can we fit the red part What we really care about is how well do we fit this blue part that we haven't yet seen and we don't know how it is right and this formalizing this hope is called generalization。

😡，And if you don't generalize， then the notion is that you overfit and overfit means that you built your function F that predicts the data Y。

 the red data really well， but is unable to predict the data you haven't yet seen。

 So it's unable to make prediction on unseen data。 So out of sample prediction so we all we worry about is generalization out of sample so we want a model that generalizes well to this unseen data and I spent a minute talking about is because this is very important right is that in some sense。

 we want to we have training data， but we don't care about mastering the training data。

 We really care about mastering the data that hasn't yet even appeared to us right And this means we have to be very careful about how are we thinking about our models。

 How are they going to generalize what is going to happen tomorrow。

 given what we've seen today and so on and so forth right And if you think about these types of things imagine。

Like one thing that happens， for example， in data is that every day of the week。

 different type of people come to your to your application。

 So maybe you want to create a separate F of x that that you only deploy on Saturdays and Sundays because on those days。

 people that visit your application or your website are very different than you know the Mondays or you know the Tuesdays。

 people and so on。 And so this means that you really need to think about how am I generalizing to to the future And how does that future look like right So you may think about different days of the week and so on and so forth。

 because the goal is not to memorize the training data well。

 the goal is to be able to predict to unseen data So that's what I want you to take home。😊。

So now you can say， why do you care about the scale， you know， we care about fancy models。

 It turns out I'll give you two examples， one coming from Microsoft and one later coming from Google where basically the bottom line is the title of these works is essentially unreasonable effectiveness of big data。

 So and the point is this is now you know from 15 years ago from Microsoft where they were doing large scale evaluations of machine learningbased language translation。

 you are given a sentence and you want to translate it to in one language and you want to translate it to another language and what they did here is they said how much training data they have versus performance and they tested four different approaches some very simple。

 some very complex and very fancy and essentially what the bottom line is that as you have more data。

 your things will work better and it doesn't really matter that much what particular fancy model you pick。

Right。Size of the training dataset matters more than than the structure of the models itself。

 and as the data size grew the performance， the difference。

 the performance difference between the models becomes much tinier right So again。

 the idea is when you have little data。 you want to be very careful how you design your model so you can learn from little when you have a lot you just need you just need a big model and the data will take care of it。

 So this is here is here is the paper， this is one and here is now the work from Google from two years ago。

 titlereasonable unreasonable effectiveness of big data where what they did was they were trying out the latest deep learning based methods and what they find is that here is a number of training examples of millions here is the performance and you see how performance keeps increasing as you have more data right so if there is reason。

😊，For the current machine learning revolution is essentially， I would say there are two。

 One is that we have good systems and good hardware， And the other one is that we have data。

Right that we can now train big， complex models on large scale data， like in。

 if you think of it selfdriving and so on and so forth。 right。

 So the point is that large amounts of data and big models give you great results。

 But one without the other kind of won't won't work。 And when I say large models， I mean。

 models that are expressive， right， and deep learning models are kind of decadently expressive models。

 So that's the， that's the case why these matters， right。

 And especially in industrial settings where you have a lot of data Finess doesn't matter。

 what matters is that you can effectively learn from big big big amounts of data and and push up the performance of your model。

 So thats the that's the idea。😊，So now what I want to talk to you about is kind of we'll talk about two types of models next week。

 we'll talk about neural networks。 and how do you deal with that。

 And today we'll talk like about an old class of models called decision trees。

 But decision trees are kind of these workhor that it's amazingly hard to beat whenever you have well structured data with good features。

 is is kind of amazingly good。 you know， I think it's from 1980s older than I am。

 but it's good stuff。 Okay， so decision trees。 Here is how we think of this right So we are given will will be given an attribute。

 And let's say that we want to predict the value of people's lifespan by means of some other attributes of that person。

 right So you could imagine that every person， I want to predict their longevity。

 So I'll be given every person represented by D numbers are numbered which are the d features X1 to。

😊，each feature will have some domain， meaning like features can be categorical。

 Maybe it's the color of the eyes。 Okay， sorry， you cannot have maybe hair。 okay。

 you can have red hair and blue hair or sorry it doesn't work out either。 Okay。

 maybe you were taking a picture with a red sweater or a blue sweater。 Okay。

 then you have a numerical variables like H and so on right。

 and then you have the output variable that can be categorical like classification or could be numerical like regression。

😊，And then you are given data X comma Yi， where Xi is this d dimensionional vector and Yi is the output variable。

 the task is given the input vector x， predict the output variable or label y。😡。

Okay so now what is a decision 3 Dec3 is this three structured model basically it a it's a plan of a set that tells you which sequence of attributes to test to determine the output。

 So here is what I mean by this it is simply a this three type structure where the idea is that。😊。

This three has at every node of the tree。 We have a condition that says what variable。

 what attribute to look at at what value。 And then if that condition is satisfied， they go left。

 And if it's not satisfied， we go right right So this is a particular rule。 It says at node C2。

 examine the second feature and see if the value of the second feature is V1 or V2。

 then go to the left， otherwise go to the right。 Okay and that's that's called a decision 3， right。

 So we have this notion that each node splits the data into the into the directions， right。

 whether the condition at the node。😊，Is satisfied or not The data gets split to the left and to the right okay and then every leaf node makes a prediction right so for example。

 if I would take a data point I would drop it at the node day and then I would evaluate the condition the first condition whether the first feature of that data point is less than v1 the answer is yes then my prediction would be 42 and if the answer would be now I would keep evaluating the data point and I would look at the second feature。

 see whether that feature is less than v2 if it is I would go here and so on and so forth so this is a decision3 so it's essentially this sequence of rules that tell me what variable do I have to examine and what's the threshold value right and today we will simplify this a bit and say let's look at what are called binary splits where I will say only yes and no right but you would have multiway splits if you like but we will do just binary。

😊，Splits， we look at the categorical attributes and we will look at the regression。

 meaning we predict a real valued y。 Okay， so that's the simplification for today。 So now as I said。

 how do you make prediction， the way you make a prediction is that you simply kind of drop your data point X from the top。

 and then you follow down the tree until you hit a leaf node。 And in the leaf node。

 you get leaf node tells you what the prediction is for all the data for all the data points that hit that node Okay so I drop it down。

 I evaluate the condition and the point goes until it hits a leaf node and then I read out the prediction at the leaf node。

 So making predictions once the three， once you have the tree should be quite easy。

 Now the question the question will be， how do we build the three， given data。

 how do you build the tree。😊，And one way you can think of the data is the following。

 Imagine I have this type of data set in two dimensions。

 Then I can start building the three at the top。 and whenever I have a condition。

 I'm in some sense slicing this space into2 So if I say imagine this is this is x1 and this is x2 sorry。

 this is x1， and this is x2 right So if I'm saying x1 less than v1。

 then I'm saying I have this green line， something is above it。

 something is below it right So now everything that's above it。

 I could further everything that's below it， sorry。

 I could further split I could split here on attribute x2 and value v2 and say are you less than this or more than that right And if I look at this this is now perfectly blue。

 So I could decide， oh， if you end up here， I will make a prediction。Describe this area of the space。

 and if the data point comes here， then it will go left at the node A。

 it will go left at the node F and will say you are blue right now we need to look at this part right and you could say。

 okay in this part I will talk about that later。 Let me continue this part right So what do you do up here。

 What do you do up here。 you could create another split on variable x2 and value v3 And again。

 you would get like this。😡，Perfect type of thing， right。

 Everything to the left is blue and everything to the right is red。 So you would create。

This two prediction nodes that says if if the value of x2 is less than v3， go left。

 otherwise go right。Alright， and now we need to decide what to do here。

 do we want to make some prediction or do we continue splitting And if I decide to continue splitting。

 I would maybe wantna split on variable x2 on value v4 right and here is my condition。

 And then you know， everything to the left is is less than v4 and everything to the right is more than v4 right And again。

 for this part I could just decide to add a prediction note and predict a minus and here I probably need another split。

 So I would be splitting on on value of x1。 but sorry on attribute x1， but value v5。

 So I would do it here。 And again， you know everything above it is minus everything below it is plus right So I predict a plus when condition is true。

 and I predict a minus when condition is false right So what's the point。

 the point is that I can take this is just in two dimensions kind of quite。😊，Deciion boundary。

 And I can describe it very nicely you the decision 3。

And another thing that you can see is that I could keep running this decision tree all the way until every data point would be in its own square。

😡，So it means I can chop this space as finally as I like。 I， I wouldn't need to stop here， right。

 When I come here， I wouldn't need to stop， I could chop again and chop again and keep doing that until I get tired。

 right， So I can severely overfi the data， So it will be important to know when to stop training right here。

 I have no noise。 But imagine I would have a minus here。

 Do now try to split this here and here and here to capture that minus， right， It's a good question。

 when do you stop right， But what I wanted to illustrate is how these trees are getting built。

 And we will talk about how do you build a tree using this kind of top down approach， right。

 So the the point is， how do I construct the tree， given a data set D， How do I construct it。

And essentially， the way we think of this is that we say， okay。

 I have a node and I need to come up with a split condition。

 I need to come up with a variable and a value on which I will test right。

 So I need to and as I come up with this。 then the data set that comes on the top get split to the left and to the right。

 right， if I drop 100 examples from the top。 some of them satisfy the condition and go to the left。

 and some of them don't satisfy the condition and go to the right。 right， So this hundred example。

10 data point data set got now splitting to do data sets 10 on the left and 90 on the right。

 Okay And then right now this means I have a new node here。 And then again。

 I have one of the two options。 I can either decide to keep splitting or I decide to create a prediction node。

😊， and then similarly on this side， I get to decide whether to keep splitting and I have to come up with a split condition。

 meaning attribute comma value， or I create I create a prediction note right And if I would decide to keep splitting it means I have to come up with some value and some attribute right dimension where I want to split and I would keep keep doing this right And as I would keep doing that。

 my data set would get again split right is 90 data points that come in they get， for example。

 here split half half because half of the data satisfies this condition and half doesn't okay and so on and so forth right you get the idea。

😊，Okay， so in some sense， I'm taking my training data set and Im partitioning it and splitting it into smaller but more。

 more fine grained sub chunkunks and I'm splitting it based on these conditions that I encounter on the way from the top to the tree down towards the leaf。

😊，Okay， great， and so on and so forth。 That's the idea。

 So this is how we are going to construct the tree is to to make a decision whether to split a node or not。

 And if we decide to split then the question is what variable。

 what attribute and what value and if we decide not to split。

 then we have to be able to construct a prediction node right？ So basically the question is。

 whenever we come up with to a given node， let's say a node the G in this case。

 we need to decide do we continue building the tree。😊，And the answer， if the answer is yes。

 then we have to decide which variable， which attribute and which value do we want to split on。

 And if the answer is not， then we have to make a prediction We have to create a predictor node。

 a hexagonal node in my pictures。 right， Those are the two fundamental steps。

 So here is the pseudocode about how to build the tree， right， Basically。

 what I'm given in is a node。In the tree and some data that comes to that node。

 and then I have to decide whether given this data that comes into the node。

 I decide what is the best split， this split will partition the data to the lefthand side and the righthand side then for the lefthand side I check should I stop And if I decide to stop then I say。

 okay on the lefthand side， create a predictor node if you don't create a predictor node。

 I say build the sub3 on the left child with the left data set and then I do the same thing on the right。

 If I have stopping criteria on the right then you know an right child is a predictor node otherwise ends righthand child takes the data set and build the sub3 right so essentially cause this function recursively and this way our tree will get created right so I have the build sub3。

 find best split stopping。Ititeteria and， and then build the prediction note。

 Those are the three functions I have to specify。 So what I will do next is tell you how to do these three functions。

 How would you， how would you implement them and how would you do them， How do you find the split。

 How do you decide to stop， and how do you build a prediction note。How do you split？

 That's the first question， right， There are several different criteria。 If you are doing regression。

 you can use this notion of purity。 where idea is that you have the。

You have a data set set of the data points coming into the node and given the condition on the node。

 this data gets split to the left and to the right right to the left goes the data that satisfies the condition and to the right goes the data points that don't satisfy the condition then what can what you can do is you can do the following is basically say I want to find a split that will maximize what is called purity right so you are doing the following you are saying I will find the x。

 the attribute and the value such that the variance of the stuff going inside into the node and now that I have split it is the variance on the left and variance to the right multiplied by the number of data to the left and to the right I want this difference to be as big as possible so right the idea is this is the variance of the data coming in and this is the variance of the data coming out and if this difference is big it means that I have a big variance。

Small variance， which means I decrease the variance。

 which means I have increased the purity of my data。 When I say variance。

 I really mean variance in the output labels， right， So I'm saying。

 what's the variance in the in the y of the data coming in and after the split。

 What's the variance in y on the left plus the variance of the y on the right。 Okay。

 so I would want to now search over attributes and split values such that I maximize this this difference。

 okay。😊，This is sc be。This is used for regression。 What if I have classification in classification。

I would use the notion of information gain。 so let me explain what information gain is。

 It will take me a couple of slides， but this will essentially allow me to say what is the best split I can choose if I consider to split the data at the that given node so information gain measures how much how much a given attribute x me tells me about the class y right and the more x reveals about why the better split it is That's the idea so the way we formalize this will say information gain of y given x the way you can think of this is in terms of kind of Sha on entropy and codingd and transmitting information over a channel where idea is I need to transmitt information about y over a binary link and the question is how many bits on the average would it save us if both ends of the line would no value of x。

So the bigger the information gain， the more x tells you about the y。Okay。

 so let me now try to build up how do you compute information。

 So the first thing you need to define is the notion of entropy。

And the way you think of entropy is the smallest possible number of bits on average per symbol Ne to transmit a stream of symbols across a channel right and these symbols this stream of symbols is drawn from the distribution of x right so we would say entropy of x is simply a sum over the domain of x p of x times lock p of x and intuitively the idea is if I have high entropy then then distribution of x is uniform it's in some sense boring right the histogram basically would be flat and if I have low entropy then x is from a varied distribution with a lot ofs peaks and valuess and the histogram of these distribution will have narrow narrow peaks right so if you say what is high entropy。

 high entropy is this kind of uniform noise low entropy is when kind of the data is concentrated in a small。

😊，PartRight， so this is about the entropy of a single random variable。

 Now the second thing is now I want to go and and start talking about information game。

 So suppose I want to predict Y， given that I have X， right。

 Imagine X is the college major and y sees Y is whether somebody likes a given movie or not， right。

 So then I could say the following。 For example， I can say。

 what's the what's the probability that people like this movie， And I would say， okay。

 out of this8 cases for said yes， So it's 05， You know。

 what's the probability that somebody graduates in math and doesn't like this movie。

 it's0 to5 because out of all out of all the rows here that matches there is two rows that should that should match this。

 right， And then I can also now compute the the entropy。 So， for example， I could say。😊。

What is entropy of y and simply I say y has two values cs and no so it takes yes half of the time says takes no half of the time so here is you know minus1 half log base 21 half this is for ss and this is for no so the entropy of this would be1 right and then if I say what the entropy of x x now here takes three different values and again I could compute for each one of them the probability and compute the entropy okay。

Now that I have the entropy， I need to just kind of entropy of x。

 I want to define what is called specific conditional enthtropy。

 And this is simply entropy of a given variable kind of limited to the cases in which x takes value of V。

 So this is the entropy of y among only those records for which x has value V。 Okay， so， you know。

 I could say。Whats the entropy of y given that x equals math so I would simply only look records where x equals math and then I say you know what's the entropy of y here I have two yes and two knowss so based on this formula I showed you before the entropy equals1 right while here for example for history history is here and here so for these two cases I always get a value of no so the entropy is very low its actually0。

😡，Okay so that's how I compute specific conditional entropy。

 I just limit the records based on the condition after the bar okay so that's now specific conditional entropy now I need to define what is called a conditional entropy and conditional entropy is the average of specific conditional entroies over the domain of x right so the idea is if you choose a record a random will that will be the conditional entropy of y conditioned that the row value that you selected has a value x right so this is the expected number of bits y to transmit if both sides know the value of the attribute to x so how you compute it is here you essentially say I will sum up over the domain of x here is the probability that x takes that value times the specific conditional entropy of y given x just a simple。

😊，We already know how to compute this this guy now all we are doing is we try every possible x。

 say what fraction of time does x take that value and then compute the entropy of y given that value of x okay？

😡，Thats that's the idea。 and this is called now conditional anthtropy。

IThe way you can you can think of conditional enthtropy conditional enthroppy in some sense is weighted average of specific conditional anthtroies where weights come based on the probability that x takes that value V。

 That's the idea right So to give an example， given my data set os right here is the value v for x math。

 history is C， this is the prior probability of x right half of the time people major in math。

 quarter in history and quarter in C。 And then these are the specific conditional enthtroies of y。

 given that x takes that value right we already computed it for math。

 I computed it for history and then for C， I only look other records for C as we all know C S are very romantic people。

 So they know they like this movie with enthtroies。😊。

So now if I multiply these things together in this weighted average。

 I get the conditional entropy of y given x to be 05。Okay。

 so now I think I've done all the work that I can tell you now， what is the information game。Okay。

 so the information gain is simply the way you think of it is the difference between entropy of y minus the entropy of y given that you know X right So the way to interpret this is to say。

 I need to tell you why how many bits do I save if both of us no X right if I tell you that that you know imagine I want to tell you how old someone was and and maybe you know before I give you anything。

 any other information， we both say， oh， they can be any random person on the planet。

 So here is our belief， how old somebody is But you know maybe I go and I tell you the first name of that person。

 And if I tell you the first name of that person that actually tells you something about how old they are because you know in different times。

 different names are popular right So that's essentially the idea right So now you could。

Say what is the information right here is the entropy of x of y here is the entropy of y given x so you know what is the information gain of y given x it's 1 minus12 so it would be12 right so this means that X tells you about why it gives us about half a bit of information so that's essentially the idea and to give you an example how this would look like。

😡，Right， imagine you want to predict whether somebody is going to live past 80 years right and you have various features in your database about these people。

 then if you would do the information gain measurements。

 then you know information gain of long live given hair color it's essentially zero hair color doesn't tell you how long somebody is going to live right But for example。

 knowing whether they are a smoker or not that will have very high information gain because smokers tend to die younger right or gender also gives you high information gain because women tend to live longer I think about five to10 years right So if I know somebody is a woman I know something that tells me something about whether they are going to live longer And if I know last four digits of your social security number that should essentially tell me zero because those are random right So what information gain tells us it tells us how much information about why is contained in X right。

Some I ask what feature is the most informative to tell me about the outcome Y。

 right so attribute that has higher information gain is a good split。 That's a long story short。

 Okay So now we know how to split。 right So I just told you how to do this。 Find best split。

 you can evaluate information gain for classification or you evaluate purity and you try out several different splits and return the one that has high information gain or high purity。

 Okay now the next thing is stopping criteria。 That's the second thing we are doing yes。😊，呃我。

How to evaluate a particular criterion。 but it doesn't tell you how to search the space of possible。

 question。 what great， great observation。 So what we just did is if somebody tells me whether to split on this attribute。

 this is how much information again I will get。Right， because this tells me if I。

 if I split on small careers。 now， here's the information game。 Of course， I didn't。 now。

 the question is， how do you find like， how do you find the best split？

 The way you would find the best split is that you， in some sense。

 consider set of all possible splits or some kind of heuristic way evaluate a subset of possible splits。

 So there is no elegant way to optimize over the splits。

 I only tell told you if you have a split candidate， how to evaluate。😊。

But there is no elegant way to search over speed candidates。还有新天6。

Anally a variable and then a threshold great， great question。

 So what do you do with continuous variable。 Give me 10 minutes。 I'll explain。😊，Okay， now， really。

 I will。 I It's cool ways。 But if I explain now， then I won't be able to explain it later。O。

 good question。 Thank you。Good， okay， I like the question。 So， so ask them。 Okay， great。

 We talked about find best split。 If you know what split candidate is。

 Now we w to find the decide whether we wantna keep building or we stop。😊，And then you know。

 we will need to figure out what the predictor node is， right So the question is when to stop。

 And there are two strategies， when to stop。 One way to stop is when the leaf is pure， right。

 if you go back to my example when that area was full of blue pluses or full of red minuses。

 it was homogeneous， it was pure So I am done。 if I'm doing regression。

 I say when the variance in value， y is smaller than some epsilon， I got this pure leaf。

 I will stop Okay that's one way， and another way is very different。

 You would say I will stop training， splitting the node。

 when the amount of data in the leaf is too small， right。

 So you would say if I get less than 100 training instances in a given node。

 I don't feel comfortable。Further splitting the node because I don't have enough data and I worry that I will overfi right。

 So it just says if I don't have enough data， I will stop and not overfi。

 This is this kind of thinking and this thinking is I found this pure node。

 this great prediction where everything has the same value right the variance is less than some epsilon。

 I'm ready to stop。 There's nothing more for me to do right and you can use both this criteria you need to decide how much data you have and what do you feel comfortable with here and and variance you can do something similar。

😊，Okay， so this is now whether you should stop。Now that if we decided to stop now we need to create a predictor node。

 right， we have to predict create this hexagonal node in my notation， right， What do you do。

 You have a few ideas。😊，One is that just you look at the average y value of the data at that node and that's your prediction。

😡，Its it's actually fine right because if the data， So if you do this。

 then essentially what this means that you take your your high dimensional function and you are approximating with a step function。

 And given that you can split your data as finally as you want。

 you can approximate the step function like this continuous function with a very fine grain step step function。

 So this is what this would be。 Now， another option is to basically build a simple linear regression model out of the example in the leaf。

😊，That's another option。 So this would mean that then you're approximating your high dimensional function with a kind of a set of piecewise linear functions。

 right， either piecewise constant functions or piecewise linear functions。

 What do people do for classification， the idea is， you。

 your output your prediction is the most common why of the examples in the leaf， right。

 So if if this would be， for example，😊，In up there point42。

 it could be that if I'm doing binary classification。

42% of the data that comes into into that leaf node would be would be of of the of that label that I would predict。

 Okay， that's essentially the idea。 So not too much complexity here。

 Because the idea is that as you are splitting， you soon finally chop the chop the space that you don't have to be too smart about what do you put in the leaf node。

 Okay， so this is what I wanted to say about this， are there any questions。 Yes， linear when you。

 so the question was， when you build the linear regression in the leaf node。

 what features do you use， you use all the features。

 But you only build it on the data that comes into the leaf。😊，Right， that's all you。

 that's all you care about。 right， Only the data comes to the lift。 And then this。

 this linear regression will only be evaluated on the subset of of data that comes into the lift。

 So it will be evaluated only on a subrange of your data space。 if you think of it that way。Okay。

 good question。 Yes， anything else。Yes， great。in most supervised learning algorithms。

 we see one example at a time or updating some sort of objective。 So just clarify here。

 we're looking at the entire data at the same time。 correctect。

 So what you say in in when you are doing stochastic gradient updates， which is。

 you know what we did in what we did in our SVD latent factors model what you do when you train neural networks。

 those are streaming algorithms， right， you say I get a small batch of data and I update my model。

 These are not streaming algorithms， These are algorithms that say。

 I have my entire data ready for me to consume and I consume the training data to build the model。

Okay， so they are not online。 They are not streaming。All right。Good。

So now what I want to talk is actually how would you do this on super large scale。

 how would you do this on map produce？And this is actually a paper that was published by Google people a few years ago。

 And as far as I know， this is still state of the art in terms of building massive scalable parallel decision3。

s that's the idea。 right So the idea is given a data set of hundreds of attributes。

 we want to build a decision3。 And here is how this will look like。

 right This three will be relatively small10 levels。 The data set is too large to keep in memory。

 say the data set is too big to scan over it on a single machine。 So we will use mapre。

 What this was loose used that Google， maybe I have example later。

 but essentially this was used to make the most valuable prediction of them all。

 And this is predicting whether a user clicks on an ad or not。😊。

And you would be amazed how much human resources brain power goes into this problem of predicting with what pro is a given user going to click of given at。

 that's probably the most valuable prediction engine， you know， Facebook cares Google cares。

 Amazon cares， Instagram cares， Pinterest cares， LinkedIn cares， everyone cares。

 So this is where this was used。 So the algorithm is called planet。

 and it it stands for parallel learner for assembling numerous assemble trees。

 right and it's a sequence of map reduce jobs that builds a decision tree。

 and it's implemented both on Hadoop in mapreuce， but also on spark in the M Lib。

 if you would like to use it。 it can handle hundreds of numerical。

 meaning discrete and continues but not categorical attributes。 the target variables。😊。

nuummerical it is a regression so it was used to predict the probability of a click right and the splits are binary because our we are assuming variables are numerical so then we all we need to figure out is what value to split a given attribute on。

😊，The assumption is the decision tree is small enough that it can fit in memory of a single mapper。

 but the data is too large to be kept in memory。 Those are the assumptions。

 Now here is the the diagram of the entire of the entire architecture。

 So this will be a sequence of mapre jobs。 So it will be kind of a bit complex。

 But the idea is that I will have this master。 this master keeps track of everything and decides how to grow the three。

 right， we will have some three that we want to keep growing， we will grow it level by level。

 So one growing it for one level what I show in red up there， that is one one mapre jobs。

 So if I want to grow it for three levels。 I will have to go kind of through three mapre jobs。

 and then the master has the following things。 it knows what the model is it has some attribute metadata。

 And then the master goes and creates this map reduce jobs that。😊，Take the input data。

 the current model and the attribute met data and go and build one level of the tree。

And what these mapre jobs will be used for goes back to your question they will basically be given a set of split candidates and they will evaluate their quality right so the idea is master will say here is a set of split candidates each reduce will say here is the current model plus the set of split candidates let me go over the data evaluate those splits return them to the master and then master decides how to grow the three for one more level again generates a new set of split candidates I will explain what that is and this keeps going so the mapre job is essentially evaluating how good of a split how good of a split do we get so as I said3 is built in levels。

😊，And here is how building one level of the three looks。 First， master decides on candidate splits。

 Can split is a triple of node attribute value， right， Now this， for example。

 F attribute is you know， what feature are we going to split on with what value。

 This is called the candidate split。 So master will somehow decide and create a universe of candidate splits map reduce jobs。

 then take this candidate splits， take the current model。

 evaluate it on the entire data set and return the the the quality score for every of the candidate splits。

😊，The master aggregates the candidate split scores。

 decides where to grow the tree and where not to grow the tree， and then continue。😡，Okay。

 so three steps， candidate splits。😡，Quality of candidate splits， master decides what to do。Okay。

 and here is where the map job happens。Here is how to think of this。😊。

Is right master will tell the mappers which candidate splits to consider as I said。

 candidate split is a triple of node in the three variable on which we are going to split and the value on which we are splitting and then each map gets a subset of data plus the split candidates plus the current model and computes partial statistics for a given split candidate and then the reducer will collect partial statistics for the split candidates aggregate them and compute the final statistics for every split candidate and now for every split candidate now the master wakes up again takes all the scores of all the split candidates and decides whether to keep growing the three or to stop right that's essentially the idea right where input is the data sets master sends into the mappers the three and the candidate splits and then。

😊，The output here will be candidate split and some partial statistic so that the reducer can collect it and out we get the final statistic for every candidate split so that in fourth point the master can aggregate it and make a decision so let me give you now the overview and then well go step by step so this is we build three level by level man one map produce job builds one level of the three。

😊，The mapper right considers a number of candidate splits。😡。

Candid split is a triple node in the three attribute and value and each each mapper gets to see the subset of the data so it evaluates the quality of that split on that subset of the data for each split it stores this partial statistics for the subsets of data that a given mapper gets and this partial split statistics are sent to the reducer who aggregates。

 collects this partial statistics and determines the final score of a given candidate split and then you know the master collects all these and makes and makes a decision how to grow the tree。

😊，Okay that's the idea。 Now， as I said， what does Maper do Maper loads the current decision three model like as as you would have it up there。

 right imagine Maper allowss this model and mapper knows that now the trees that F G H and I needs to be grown right so the master will generate this candidate splits this triples for each mapper to consider and each mapper because the data is partitioned。

 sees a subset of the data and evaluates the quality or the score of each of the split on its own subset of data The way it does this is that it takes data point right and drops it into this partially labeled3 and then sees where the data point lands and if it lands in F then this can be used for all the splits that consider no F。

😊，Right and so on right and for each leaf node right the mapper will now keep the statistics。

 What is the data that' reaching that leaf node and then how the data gets split to the left and to the right under this candidate split S and the reduce will then aggregate the statistics about reaching the data left and right data that goes left and right of the split and aggregated across all the subsets of data over all the mappers to then determine what is the final score for a given split Okay that's the idea Now what does the master do The master controls kind of everything monitors everything and runs multiple mapre jobs and there are three types of mapre jobs First is map reduce initialization and this is run only ones and basically for。

😊，Each attribute it identifies the values that should be considered for a split。

 I will explain how to do this because this was the question before then the mapre job of find best split is around multiple times once per level and this finds the best split from the set of split candidates that we generated in the initialization。

😊，And we do this when there is too much data to fit in memory。

 and then there is a small optimization where there is another job that's called in memoryory build。

 And the idea is that this is only run once。 And the idea is if if the amount of data is small enough that it fits into the memory of the single mapper。

 then just mapper loads all the data and builds the entire sub3 from there on。😊。

RightSo this is just an optimization that says if you build your tree up here and after your summer very deep。

 I know down here and the amount of data gets so small that you can just load it into the mapper。

 then just load the data and build the rest of the tree in memory rather than running this mapre jobs because they are slow So you only want to run mapreuce when the data is big when the data is small。

 just build the tree in memory using the pseudo code I showed you。😊。

And then right towards the output， the output is the model file a file describes that describes kind of the state of the model。

 meaning the structure of the tree and and the split values and split attributes as we move down。😊。

Good， so let me now go through all these four steps， right master node， initialization。

 find best split， and then this kind of optimization that is called inmeory build。😊。

So master controls the entire process and determines the state of the tree as it grows it right it decides if the node should be split and if there is little data entering a given node。

 then the master runs inmemory build map reduced job to grow an entire sub3 from that node onward right if there is a small amount of data now reaching my node F then I would just run the inmemory build and build the entire sub3 from F downward okay。

And then if the amount of data entering a given leaf node is large。

 then the master will launch this snap producedd job called find best split to evaluate the candidates for best split。

 master would then collect the data from this best split and then decide what split to execute at a given node。

 that's essentially the idea and then of course the master would update the model and again decide whether to run in memory build or another find best split that's the master。

😊，Now we need to talk about initialization。 We need to decide what candidate splits to even consider。

 So here is the idea。 The idea is I want to figure out all attribute all attributes and all attribute values for which should be considered for a split right and this initialization process will generate what we call before attribute metadata and this will be then loaded in memory by other tasks essentially for a given for a given node we need to figure out what variable and what value to split on those are those are the things So now the question is which splits should we even consider which x and Xj and v should we even consider and the idea is that a split will be defined by a triple node attribute and value right and what what the initial attributes job will generate will generate a set of。

😊，Attribute value。 And then the master will append the node Id when it needs to do。

 But initialization only generates variable comma value。 That's the idea。

So the question is which splits should we even consider right for small data you could just sort your by your data according to your attribute value and you could consider splitting at every possible position right you could consider at every possible position a split if you have little data。

But if data are not uniformly populated， many splits may not really make any difference， right。

 in a sense that if you have lots of data very concentrated。

 then you don't necessarily need to to split that superfinly right So imagine I have a particular attribute J that has the following values right。

 you see how it's kind of super concentrated here around 10。

 and then you know something around a bit 11 and here。

 So it's kind of highly nonuniform while here I have a big gap between 2 and a 7。

 So this would be a good split。 while here maybe I don't care spliting at 1。2 or I split at 1。

3 right So there are different choices I may w to I may want to make how do even consider candidates for splits。

 So the idea how to solve this is to consider a limited number of splits such that each split moves about the same amount of data。

Right， and I will make precise。 what do I mean by move the same amount of data。 Okay。

 so the idea is that I would like to take attribute feature X J。

 And I would like to consider where to split it。 And the way I could do this is the following。😊。

I could create this type of histogram where where essentially I would account how often do I see a given value。

 right， so the idea is how often does my attribute Xj take a given value。

And then the idea is that I want to use these boundary points as the as the points at which I want to have my histogram to be split right and how would I now create this this boundary points where basically the same amount of data is in each of these regions right if you if I would sum up this heights of these bars in every of these regions。

 the sum of the bars is about equal right so this means I would consider a split here。

 another one here， another one here right So this means that the attribute this given feature takes value 10 very commonly so I would consider。

😊，I split before 10。 and I would consider a split after 10。 Okay， so now the question is。

 how would I compute。How would I do this to get this kind of what is called equid histogram， right？

 And here is， here is the idea。I will use hashing， right The idea is that I want to have an equal number of elements per bucket。

 So the way I could do this is that I could create this by sorting the the equally spaced splits。

 right I would simply take all the values of the attribute sort them And then I would consider I know splitting at every fifth value right。

 And this would this means that in every split about the same amount of data would be captured。

 and you can now notice that this would mean I split between 3 and 4， I split between 9 and 10。

10 and 11，14 and 12 and 14 and 18 and 19 right So this splitting is highly nonuni in the values。

 but it's uniform in the amount of data that that is between the split values right So that's the idea that equal amount of data gets split at。

😊，Every time。 so this would be now candidates for my， for my splits。

 for an attribute that takes these types of values。How would I make this go faster？😡，Basically。

 the way I'd go faster is that rather than taking all the data and all the all the values of the attribute。

 I could create a sample and then sort and take equally spaced splits in in in that sample。 And。

 and this will work really well in practice because it's kind of a simple， simple type of operation。

 So this allows us to decide where to split on， and the idea is to use this equi depth histogram as it is called essentially。

 we want to split such that every split captures about the same amount of data。😊，Okay。😊，m，Great。😊。

Now， number three， which is find best split。 And this is the procedure we run multiple times to generate one level of the three。

 right And here is the idea。 The idea is that we are given us a particular split candidate for for a given node。

 and we wantna find find out what is the split candidate that maximizes purity。

 And we define this purity before。 right， we said this is the variance in y of the data coming into the into the node like I have picture here。

 And then after we apply this particular candidate split。 Some data goes to the left。

 Some data goes to the right。 there is the the amount of variance on the left amount of variance on the right。

 And I want the difference between the two to be as high as possible。😊，One。

 one thing that we will exploit is if you ask how do I compute variance。

 the way you compute the variance is that this is essentially1 over n some of the squares of the values。

 minus 1 over n， some of the values squared。😡，Okay。

 and this is the same kind of sufficient stat trick I think we used in the BFR clustering if I remember。

 and here you can use the same the same trick。 and the reason why is this so useful is because these statistics are nicely agregable。

😊，Right， I can aggregate them over subset of data and then add them up。

 and some of the squares will still go， and some will still go。

 I will just have to square it at the end， Right， So what is nice about variance is that I can compute it on subsets of data and then。

😊，Keep these statistics， add them together。 and I have the variance on the entire data set。 Okay。

 so to compute purity of of a given subset of data D， We need to。

 we need to compute the following equation right and the observation is that variance can be computed from this sufficient statistic。

 which is n number of data points。 some of the vice and some of the square values of Y， right。

 So each map will process the subset of the training data， this sub B that is assigned to it。

And it will compute number of data points in M， some of the squares。

 some of the y value Cm and some of the squares of the value C M right And this is the data that comes into that into that leaf。

 and then the reducer will now combine the statistics to compute the global variance and purity right So the way now the the reducer compute the various the variance is to say。

 let me go over all the maps。 and every map gives me QM。

 I sum up QMs I sum up n the number of data points here to compute the lefthand side of the variance formula。

 and then here is sum of y's again， I sum them up over all the map divide this by one over the total number of data points and square that。

 and this is now my variance formula right so the point is that every mapper can compute this sufficient statistic。

 The reducer just。Adds them together。 And we have the global purity formula here for us to use。

 And that's， that's the， that's the， that's the elegant part。 right。

 So here is what the mapper will do。😊，Maap mapper loads the results from the initialization task。

 loads the candidate splits， loads the current model。

 and then it loads the set of candidate splits node attribute value and the value on which we want to split and then for each data record the map the map function does the following for for each node in the three it sort of the statistics about whats what's the data that reaches that node right So it it says this node Id in the three。

 This is the data that reaches it some of the y values。

 some of the squares of y values and the number of data points that reaches that node this is coming from the top and then for each split。

😊，It keeps the following data right it says split is node ID attribute and split value and for each split it says what is the data that goes to the left and what is the data that goes to the right。

😡，Right， so this is some of the， some of the， some of the y values。

 some of the squares of the y values and number of data points that go to the left。 Now。

 what goes to the right is。What goes to the right is this minus that right Whatever doesn't go to the left。

 You just subtract it from the overall。 that goes to the right。

 So all you need to do is keep track of the left side and you can compute what is on the right side from basically taking the differences because you know what goes into the into the node。

 whatever goes to the left。 what even go to the left must must have gone to the right hand righthand branch of the tree。

 Okay and this is this is now for every node and for every split are that given node。

 Okay and the mapper will compute these statistics and then push them out to the reducer。

 So what the reducer will do it will load all the node I D and then the list some of the of the y values。

 some of the squares of the y values and the number of nodes number of data points at that map。お？

And then it will also and it will aggregate these statistics per every node。

 and then it will do the same for for every split。 it will aggregate the statistics as Q and M and n over all the all the mappers that have run And now this means that for every for every split willll be able to compute the purity right for we will compute the purity according to the formula I gave you where the formula includes the computing the variance of the data coming into the node variance that goes of the data goes to the left and variances of the data that goes to the right And given this partial statistics here is how to compute the variance right so at the end what the reducer can do is for every node I it can output the best split it found by essentially aggregating data coming from all the map and then computing purity using the variance formula given here。

😊，And that should be。 That should be it， right， to give you。

A quick overall idea right The idea is that the as the master decides it wants to keep growing the tree here。

 then it will say I want to it will send to the to the map reduce job the node ID is where it wants to grow the split candidates and then the mappers are going to say what is the data coming into every of these nodes and according to each of these split candidates。

 what are these partial statistics and these mappers will output the data to the reducer who will who will now aggregate these partial statistics to to be able to compute the variance of the data coming into the node and then for every split the data that goes left and right so it can compute the purity and then。

😊，The reducer will output for every node， the split that gives us the best purity。

 And then the master will decide what to do next。 So this is what how the overall architecture for this thing for the planet algorithm looks like。

 Let me see if I want to。😊，Show this one。 Maybe I can， I can take a question， and then I'm happy to。

 to give you more of an example， yes。😊，If you don't assume that your covariates are independent from each other。

 what if you technically want to rerun this initialization at each node since it's receiving a subset of the data？

Great question。 So the question is。Why wouldn't you want to rerun the initialization for every node as you keep building the tree because the distribution of your variables or covariates has changed because you you kind of selected a subset of data based on the conditions above the tree so。

The， the answer， I think， is the following。If you would want to do this run multiple times。

 then you would have to add another round of map produced to compute these candidate splits。

And I think just for that in theory might be better in practice。

 this would create the runtime of your algorithm would increase for a factor of two。😊。

Right because you you would double the number of mapreuce iterations and then another issue would be that then you'd have a lot and a lot of split candidates。

So I think just like engineering wise， what the authors decided to do is to precomp the split candidates ahead of time and then just keep working with them and make sure you have enough that even when you kind of subset the data。

 that is still good split candidates in there。 So it's a good point。

 It's an excellent point you make。 that after you have subse the data。

 those splits might not be might not move the same amount of data， that is correct。

 I think just for practical reasons， this is why they decided to do this way。 Good question。

 Thank you。 Anything here。Anyone here？First throw。Hes oh great。 Yes， go ahead。

Since thisip split a node is trying to sort of separate the different labels better。

 why is the bucket？看得到在下面。So why is bucketing dependent， So bucketing is not。

 So the idea is you have these variables in each variable。

 each attribute can take lots of different values。Now。

 if if the number of different values it takes is small， you could split at every possible value。

But if， if your attribute takes 7 million different values。

 then you cannot split at every little thing。 So then， then you say， okay。

 I will split at a fixed number。 I will only consider a fixed number of split points。

 maybe 1 thousand00。And then you say， how would I choose thousand data points1 thousand split candidates And。

 and the best， the thing that works best in practice is to take the take the， take the。

 take the distribution and create this kind of equi depth histogram， right。

 where you kind of slice it， finally， according to the distribution of the data。

 So where there is more data， you slice more fine。 And when there is less data。

 you slice kind of with a bigger， bigger in with longer interval。 That's what this allows you to do。

😊，Good question， All， anything else？Good， so let me now give you a bit of an example of how would this work out if I really like write it down and say what happens when you want to create when you want to keep growing the tree at this level denoted in red right so then the way this would go is load the model drop every example down the tree for a given mapper if the tree hits a particular set of nodes keep the statistic。

 what data came in and then for the split keep the statistic。

 what again what data goes to the left based on the difference between what goes in and what goes to the left you can compute the sufficient statistic。

 what goes to the right and then after after the map is done it outputs the key value pairs about these statistics right and then what is the reducer。

お？ARr takes partial statistics for every node in the tree and sums up these partial statistics reducer also takes for every split candidate and the partial statistics for the split candidate it sums up those partial statistics and now using this partial statistics the reducer can evaluate purity of each node of each candidate split using using the data in T1 and using the data in T2 and then it can return the best split so the split with the smallest with the largest purity to the master who can then decide what to do and essentially this is one map reduced job to find best split for a given set of nodes with a given predefined set of splits or split。

😊，Candidates， okay。Now， as I said what would what would the master do master would collect this data from reducers so the node idea at which we want to split what the attribute feature we are splitting and what value and what is the purity value and based on this then then the master can decide what to do right if the data on the left and right is small enough then the master couldn decide to run in memory build algorithm and otherwise master would decide to run find best split algorithm right and this way the three this decision three would be run in in levels and built and this can be done over huge amounts of data。

😊，Let me now quickly conclude about decision trees。

 right So decision trees are this amazingly powerful technique。

 And if you are participating in kind of a machine learning competition。

 then usually decision three tend to win it any kind of kggle competitions where features are are clear these are the methods to go right they work really well for classification and regression and can work with many output classes。

 they can do more than binary。 you can classify into many different classes and it works really well。

 It can work with real and real value than categorical features， and it can handle a few hundred。

 maybe thousands of features， but not millions of features right So decision trees don't work well with text or with long sparse vectors。

 So these features are generally denses so that every every feature has a value and they allow us to create this kind of very。

😊，Complex feature decision boundaries。 It's important to have this early stopping when we stop when the amount of data in the node is not big enough to avoid overfitting。

 Theres a lot of applications like user profile classification， landing page bounce prediction。

 You know， whether somebody clicks and leaves the page immediately and so on and so forth。

And this is one of kind of the single most popular data mining tool because it's easy to understand。

 you can always look at the tree and say does this make sense or not。

 you can kind of debug it by hand， it's easy to implement it's amazingly easy to use when the three is built it's easy to deploy it computationally is' amazingly cheap and it's possible to mitigate overfitting either by early stopping or what I'll show you next and they do classification as well as regressionware。

😡，And one thing people do with trees is that they don't learn one3， but they learn a set of trees。

 And this is what is called an ensemble learning where the idea is that you want to learn an ensemble of models。

 right， And this in general， we give you better performance。 then if you have just one model。

 and how do you create multiple models， One way is to create to use a technique that is called begging and the idea is that you want to learn multiple trees over independent samples of the same data set。

 So how do you create these data， the idea is for a given data n on a D on n data points。

 you want to create another data， D prime that has the same number of data points which you sample from your data D with replacement。

😊，And if if you do the math about 33% of the data points in D prime will be duplicates and 66% will be unique right so essentially you take your data set D and now you create another data set D prime that you create by sampling with replacement from D and sometimes you will sample the same data point multiple times but that is fine and then the idea is that for each this type of D prime you learn a separate decision tree and when a new data point comes you ask each of these decision trees hey what do you think and then take their average prediction as your output right so here's the idea when a data point comes in each of these three that you train on different random versions of your training data set you ask it to make a prediction and then these three is do some kind of majority votinging and you make a prediction and this method is called begged decision trees and this is the way to go。

People usually don't train just one tree， they would train multiple and then take the majority voting or some kind of consensus vote between all the trees and thats your that your that's your final prediction and this works amazingly great。

 How do you create random samples of D。😊，Haashing comes into into into use where you can use a hash of the training record and the3 I D to create a bucket and then use the records of hashing to a particular range of buckets or set of buckets to learn the three And this way the the same sample is used for all the nodes of the tree And you know this is how how how you can do these things and it will work amazingly well right so。

😊，Now what's a further improvement over a bag decision trees is this method called random forests and here the idea is that you not only train over the random subset of the data you also learn on a random subset of the features and this would be called feature bagging right so so you would be bagging both the training data as well as the as the features on which you learn and again。

😊，This is the way to go， so create trees on subsets of data and subsets of features and then average their their output。

 And this is kind of what is the state of the art on many classification problems with dense features。

 because these methods are amazingly robust， amazingly scalable and they allow us to break all kinds of symmetries in the data by using this kind of bagging and boosting techniques that minimize the variances in the data。

 So with this， let me finish on Thursday， we'll talk about neural networks and Michel is going to give the lecture。

 Thank you so much。😊。