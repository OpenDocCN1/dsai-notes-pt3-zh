# UCB《数据100数据科学原理与技术｜Data 100 Principles and Techniques of Data Science 24SP》中英 - P12：-12-Data 100 Spring 2024 Lecture 12.zh_en - GPT中英字幕课程资源 - BV1Bc2dYCEbc

Yeah。

![](img/3bc08febc7648ea8e0631d43334e1199_1.png)

All right， good morning everyone， We back to another data 100 lecture This time we're going to talk about ordinary release scores Before we get it started。

 it looks like that there is an issue but the slido app so if you want to participate or you want to ask questions go ahead and get logged in on your browser on your laptop I believe the application might have an issue or you might also want to try browser on your phone as well just know that the app has an issue but we're still monitoring questions as they come in in the lecture if you have trouble connecting and also doing questions know that there is going be also a synchronous poll that we're going to send that you can fill it out after the lecture so today we are going to conclude basics of modeling so today I'm going to talk about ordinary release scores or multiple linear regression I started kind of motivating the idea of multiple linear regression in the previous lecture but technical。

What we want to take a look is we want to go ahead and see multiple linear regression。

 We want to see how we can incorporate multiple different features together in order to do a linear regression prediction。

 and then we will try to look at the geometric perspective of multiple linear regression。

 What happens if we have more than one feature and how do you combine them in order to do a prediction we're also going to look at the performance of multiple linear regression compared to simple linear regression compared to constant model that we also saw in the previous lecture and then we're going to also talk a little bit about some properties of linear regression。

So let's dive right in the equation for multiple linear regression is this kind of combination of features and weights that we have so that we can get one single prediction in the output so let me explain what this equation is basically telling you this equation is telling you that I have a number of features I'm going to call them x1 x to all the way to Xp so we have p features for one observation and the way that this equation is going to work is that the equation is going to say that I'm going to calculate a way the combination of these features together so there is weight associated with feature Peter weight associated with every single one of features that we have along with the bias term or y intercept that we have been always adding as set to0 and this way the combination of features is going to give you the y hat or the prediction that you have for a single data point so this is how we are going to make a prediction。

On a single data point having multiple different features instead of having only one feature or not having any feature at all so the way that I want you to think about this and why we call this a linear regression we call this a linear regression because it's technically a linear combination oftetas and the way that we're thinking about it is that all of thosetetas are weighted or a scaled by a factor of Xj or a factor of those features that we have so every time that we're talking about a linear model we're thinking about a linear model from the perspective of parameters not from the perspective of inputs or the features we're gonna to see more about this a little bit later。

 but this is how I want you to think about a linear regression model that has multiple different features that's why we call it multiple linear regression that are a scaled those parameters are scaled using those features then then there's also the y interest orteta0 that we're adding in order to get the prediction in the output。

😊，So what you will be able to see is this is how the model is going to change The model was always that blue thing in the middle that was the vector of parameters that we had。

 remember with simple linear regression I had only two values or two parameters there it wasteta0 andteta 1 right now I haveteta0teta 1 all the way toteta P meaning that I have parameters associated to each one of those features and then I also have the y interest of or teta0 as well so these are the model parameters and this is how we say that the model is parameterized by theteta vector so think about all of these values as theteta vector that we have in the model so I'm showing it by the vector notation and then what I want you to also notice is that the input to the entire model is a vector of those features so every observation instead of the observation being only a single feature now it's a single vector and the vector is going to include all of those features。

One given observation， obviously once you have those parameters and one input comes in。

 you know the equation you'll plug in those values or those features into the equation and then you'll be able to get the Y hat or the production that you want for multiple linear regression This is the entire framework that we're going to work with in today's lecture。

In today's lecture， the data set that they'll be using is the 2018-2019 NBA dataset set and we'll try to build a multiple linear regression with different loss with one loss function today and we're going to take a look at how we can do a prediction so the prediction path that we want to do today is that we want to be able to predict the average number of points that the player is going to score in a given game given a number of features that we have for the player so what are those features so I would say that those features are going to be FG which is the average number of two pointers that the player is has a score in that game AST or the number of assist that the player has done in the game and then3PA which is the number of three pointers that they attempt it so notice the difference between FG and3pa FG is the case that the two pointer is a scored and then3PA is the number of。

Point attempts so if they look at the data the data set that I have you'll see that all of those features are in different columns there is one feature for FG。

 there is one feature for AC there is one feature forpa and then there is also the target value that I'm trying to predict which in this case is the number of points that we have。

So how do we think about this multiple linear regression from the perspective of this specific application technically what we're doing is we're looking at each individual player。

 each player has multiple different features and those features are those three features that we specifically talked about and then what we're trying to do is we're trying to find out the parameter or the parameter vector that's going to help us calculate a weighted combination of these features so that it gives us the prediction and hopefully that prediction is going to be as close as possible to 1。

7 or generally on average compared to all of the target values that we have so this is again the shematic view of the multiple linear regression there's a model parameterized by all of those sets of values input goes in notice that the input this time is my vector right one observation is one vector so notice that I have 0。

4 as the first feature 0。4 is here I have 0。8 the second features right here。

And then the third feature 1。5 is going to be the input。

 but I'm getting as a result is going to be Y hat， which is calculated based on the equation that we had seen in the first slide that it's equal toteta 0 plusteta1 times x1 x1 is the first feature。

teta 2 times x2 x2 is the second feature plusteta3 times x3。

 and then hopefully if thesetetas we learn thesetetaas as accurately as possible。

 meaning that Tes areteta hat， on average all of those y hat predictions are going to be as close as possible to my target values that I have。

So you've seen this modeling pipeline quite a few times in the past few lectures the first step of us doing a modeling is deciding about which model we want to use so we know that we have multiple features so we're going to go with multiple linear regressions so the first step is going to be done the second step that we're going to take a look as what happens with the choice of the loss function so today I'm going to go ahead and use minus scoredd error which we we all know what that is that's taking the average of the scores of the residual values that the prediction that we have between the prediction and the target values that we have and these two together is what's known as ordinary least scores that's why the lecture is called O or ordinary least dis scores multiple linear regression is the general form but if you use the loss function that is a specifically minus scoredd error then the result that you're going to get is ordinary least dis scores the least scores term is familiar to you。

We've been using least dis scoress in the simple linear regression lecture we said that all of those parameters that we are learningteta0 andteta1。

 there are least dis scores estimates here， but since here we're working with a general form of this model and we can have any number of features that's why we call it or release dis scores so the framework is very similar we're just generalizing it because now we have more knowledge and more tools to just learn what's happening with multiple different features。

😊，In the second half of the lecture i'm going to fit the model this was the scariest part that we had in the prior two lectures。

 but what's happening today is I'm going to not walk you through the calculus but this time I'm trying to show you a proof from the geometric perspective that's a little bit easier to understand as opposed to doing matrix calculus that is beyond the scope of data 100 so。

We have a choice of model， we have the for any N observations that we have。

 all of those layers that we have during statistics and we want to predict the number of points that are going to score for them we need to go ahead and calculate why hat using this equation。

What I want to show you is this lecture is designed in a way that I'm going to tell you what I want。

 I'm going to make a segue into linear algebra just remind you of the linear algebra concept that I need to that I need you to know and then we're going to write everything in terms of linear algebra or in terms of matrix calculation so before I dive into all of the details of OLS know that this lecture is going to be very math heavy。

 I'm not expecting you to be able to understand everything that I'm going to talk about today but what I'm expecting you to do is to watch this lecture recording one more time at least before the meter or before doing the homework so watching it for the second time or the third time is going to kind of help you understand all of the details that I'm going to talk about in today's lecture。

So I'm going to just basically take the equation that's at the top。

 I want to write it in terms of that matrix multiple location and I'm going to show you how that's going to look like for us so let's take a look at what we had how we were representing or working with the data before but the simple linear regression there was one input column one output vector that we have been using in order to match the input to the output with the constant model there was no input there was only all of these Yi values and we were making simplifying assumptions to come up with a summary statistic for the model parameter for the constant model what we have with multiple linear regression is a little bit more complex but I have is I have a number of data points so I can eliminate those rows that I had I have end data points regardless but now I have multiple different features for each one of them that's why what you're seeing is I have multiple different columns also in addition to。

The target value that I have this is the target value that I'm expecting to have and then what you're also observing is that I have one column for every given feature so this is the column for feature one。

 this is the column for feature two this is the column for all the way to the feature P so this is how I'm going to combine all of the features together into one matrix or one data frame that you have。

Note the notation of those subscripts there， so I have two values in the subscript the first value in the subscript is going to tell you which observation you're looking at so for example here I'm saying that for the first row right here so this is observation observation1 so for observation1 what I'm looking at is that all of these first subscript values is equal to 1 but what I have is that the second subscript is telling me which feature of data。

1 am I looking at so here the feature one of data。1 is shown as x11 the feature 2 of data。

1 is shown as X12 and then all the way to feature P of data。

1 is shown by x1p so generally if I'm looking at X I J I is going to refer to the observation and j is going to refer to the feature。

That the data point is that is represented by that is specific value。

And this is how we're going to use this notation moving forward。

Kind of connecting it with the data frame that we had seen before notice that what I have is I have all of these observations laid out in each one of the rows and we know that for every given observation。

 the first index is going to be the same so for example。

 for observation I right here I'm using the first index always to be equal to I and the second index is all of those different features that we have and also for the columns each column is representing a features so the second so the first value or the first index in each one of those rows is going to change because the observation ID is going to change but the feature is going to be the same this is how we're taking a look at mapping a matrix to the data frame that weve seen and how we can connect how we can understand the differences between how to reference observations。

 how to reference different features that we have。With the multiple linear regression model。

 this was our template。 So technically what's happening is that I need to do a prediction pair each one of those rows because each observation needs to have a prediction for me so what I need to do is I need to rewrite this equation for each one of those rows separately So notice that for observation1 my prediction is going to bete20 plusteta 1 times feature1 of data。

1 timeste to 2 of feature 2 of data。1 and then all the way toteta p times feature p of data 。

1 and that's how I can get how I can get the prediction for data。

1 and I can replicate exactly the same things so that I can get the prediction for all of the different data points that I have such as y2 hat and then all the way to y and hat。

So let's take a look at how this can be represented with linear algebra。

 I want to remind you of the notation of the dot product or the inner product between the two vectors。

So the dot product or the inner product between the two vectors。

 we can only apply the dot product between the two vectors of the same lengths and what's happening is that if I have two vectors of the same lengths。

 I'll be able to multiply corresponding elements to each other so multiplying one to1 multiplying2 to1 multiplying 3 to1 and then I will be able to sum up all of these values and the result here is going to be the dot product between the vector U and the vector B that we have here So the result of the dot product between the two same lengths vector is going to be just a simple scalar value or just the real value number that we can get at the end So this is how we can generally write it vector U dot vector v and be read it as u dot v in terms of the matrix calculation this is equal to thinking that you transpose one of these vectors and multiply it with the second one so you transpose signs V。

retranspose times u and the result here is going to be the dot product between these two vectors is equal to six because of the way that the dot product is being calculated。

What I want you to also remember is that this dot product has multiple different implications we can think about the dot product either as something that's calculated by this element by multiplication and the summation overall or you can think about it as the magnitude that the multiplication of the magnitude of the two vectors times the cosine of the angle between the two vectors and there's also another interpretation that says that okay if you have two vectors project one to the other one。

 look at the length of the projection and then multiply the length of the projected vector onto the length of the second vector and that's the result of the dot product between the two vectors。

 but what I want you to remember is that if I was representing this U and V in terms of say for example。

 my u was equal to u1 U to u3 and my V was equal to v1 v2 and then V3。

The dot product between these two vectors was technically U1， V1 plus U2 V2 plus U3 V3。

 so every time that youve seen you had seen that there are corresponding elements that are being multiplied with each other。

 you should think about that there should be some dot product calculation going on someber。

How does this relate to what we we had been doing Notice that I have all of these similar indices hereteta1 being multiplied with x1teta to be multiplied with x2 and so on and so forth。

 So this might make us think that the result or what's happening in this part of the equation right here might be a dot product between two vectors So whether those two vectors I can say that these two vectors are a vector of all of these parameters that are associated with each one of these featuresteta1 all the way toteta P and then multiplied with the feature one all the way to feature p and then the only thing that I've left with is just to addte to0 to the result of this dot product calculation So this seems to be a lot simpler than just summing up。

N plus one different things。 Instead， we're multiplying， we're， we're calculating that product。

 and then we're summing it up with the cutta 0。Right so the only thing that I can do is still and I'm not happy with is that everything is not calculated in terms of the dot product between the two vectors。

 I just want to simplify my operation so that everything that I'm doing is in terms of vector calculation and there is no additional sum that I need to do so this tta0 I have to find a way of bringing thisteta0 into this dot product calculation so that I can only do one dot product calculation and then I'll be done with having the prediction for any given data point。

So the way that I can do it is I can say that okay thisteta0 is something that can go into this vector of ttas because it looks like that's very de because all of the parameters are in one vector but the issue is that there is no corresponding partner element forteta0 in the feature vector or the vector of all of those input values that I have unless I try to make up a partner for it and I can think of this partner to be a value of one right so if I think about the summation as the summation of all of theteta is times X plusteta0 being multiplied with a value of one which doesn't change the summation then technically what I can do is I can rewrite this as the dot product between one vector that has myteta0 that I had from before right along with all of these otherteta values that I had and now I know that from before each one of myteta values。

Use here they already had a weight that associated with them。

 they already had all of those feature values associated with them。

 and I can also say that now I found a partner for T20。

 which was a value of one so I can condense them together so that the entire summation of the prediction is going to be or the multiple linear regression can be written in terms of the dot product between these two vectors。

So what I've done is that I added a bias term or intercept term in order to account for the case that my my multiple linear regression needs to have a y intercept。

 this is also called bias trick as well because it's kind of a trick for us to simplify our calculations by just augmenting the feature vector by one value of one so that everything is going to be this vector operation。

Okay， how are we doing so far？Good， so far， so good， not so much linear algebra。

 We're just trying to build all of these。A vector calculations that we need to do。

 but remember that what I have right here， this dot product between these two vectors。

 I can think about it as x transpose times theta because that's another way that we can think about writing or calculating the dot product between the two vectors is equal to x transpose times theta theta comes from the first vector and then x transpose comes from x actually refers to this augmented feature vector that I have。

 which is augmented by the biasstr that I got。So looking at what we had to calculate。

 I had to calculate this prediction for all of the n different data points that I had for each one of them I'll say that each one of these predictions can be calculated by the transpose of I'm going to use pink the transpose of the feature vector for data specific observation times theteta vector so thisteto vector is going to be the same with all of them and then what you're seeing is that the observation transpose is going to be multiplied with all of theseteta vectors and then the result is going to give me y1 hat y2 hat and then all the way to yn hat and one more thing that I want you to observe is that this x1 transpose is actually the augmented version of the feature input so there is the bias term but for the value of1 and then x11 x12 and then all the way to x1p are the rest of the features that I have for observation。

One， okay， and this is kind of the same pattern for all of the and observations that I have。

So we're building a step by step。 It looks like that what I had been doing right here was that I kept getting each one of these observations I was transposing them and I was multiplying it by the same vector。

 So what if I go ahead and say that for each one of these observations that I had in the original data set that I had for predicting。

For predicting the number of points that a player is going to score I will I know that my X I for this second player is equal to the features that we have for this player。

 which is 0。4。8 and 1。5 and notice that here I'm also augmenting it automatically with the biasstr that I had and what I'm looking for is to be able to get the the prediction Y2 had that is as close as possible to this Y2 value。

So if I have thisteta vector， which is something that I need to learn and I need to find out。

 which has theta0 all the way toteta3， I can go ahead and calculate x2 transpose times theta。

 which is going to give me theta0 plus theta 1 times 0。4 theta 2 times 0。8 and theta 3 times 1。5。

 and that's going to give me my y2 hat value。Let's do dimensionality check here each one of the observations that we have so say for example here I'm looking at my observation two they're going to be in p plus one dimensional space if I have p features why is that because I need to have one representation one dimension for each one of the features plus the bias term which was this value of one that I kept adding here that's why the dimensionality is going to be p plus one in this case that I had three features the dimensionality is going to be r4 because it's3 plus1 equal to four。

What's the dimensionality of my Teta vector， the Teta vector is going to actually need to be also in R4 or Rp plus1 because I have TeEta0 and then I have one parameter associated with each one of those features that I have。

What gonna be my。dic prediction what's the dimensionality of by prediction and my ground truth every time with regression we're just predicting one value and that's why the predicted values and the target values are both going to be a real value number or scar values in R so that's how you can think about the dimensionality of the x with respect to x or the observation for a given data point。

 the dimensionality of theteto vector and the dimensionality of the ground truth and also the prediction that we have。

So let's see what's happening across the entire data set so I'm doing prediction per given data point。

 I have all of those X transposes that are going to be multiplied with Teta but because Teta is going to be is going to be a common factor in all of these calculations I can say that what if I'm going to combine all of these row vectors into a matrix so that all I can do afterwards is I can say that now I have a matrix multiplication between this matrix that is the result of just combining all of those row vectors together and then multiplying it with that one singleteta vector the Teta vector didn't change here I'm just going to stack all of those rows together and when I stack all of those rows together。

 all of the predictions are going to be stacked together into a y vector or into a vector of all of those predictions so instead of dealing with n different values I'm now dealing with only one single。

Vectctor， which has the dimensionality of n。But I want you to notice that nothing has changed in everything that we've been calculating。

 How do we multiply two matrixes or a matrix and a vector I'm just going to take one row at a time and multipied it with the column with the column vector that I have So every time I'm taking a row multiplying it with theteta vector that gives me a single value or a scalar value and that's going to be my y1 hat then moving on to the second row doing the same calculation I'll get y2 hat and then moving on to all of those rows one at a time up until the point that I calculate all of those n predictions and then I'm installoring all of these values into one vector of y So this is how we can make use of our knowledge of。

Matrices， which technically means that if I give you a data set with n different observations。

 each observation has different P features， I can combine them into something that's called a design matrix What's the dimension look at the design matrix I have n rows。

 the number of observations here and then I have p plus one different columns Y p plus one。

One column going back here， one column has all of these values of one because each one of them。

 each one of those row vectors were augmented for the bias trick。

 then I have feature one feature2 all the way to feature p。

 so p features plus one bias term makes it p plus one dimensional n by p plus one dimensional design matrix。

Now let's take a look at what's happening or what's the correspondence between this design matrix that I saw and also the observation that we had from before from our data set so what I'm doing here is I said that okay I had all of these features FGD and3pa I'm going to go ahead and add a column called bias with all of the values in the bias column B equal to1 and this is exactly my design matrix the only thing that I need to learn is a set of parameters or a set of vector that I can just directly multiply with this matrix and then be able to get n predictions altogether so that then I can compare all of those n predictions in a vector with a vector of ground truth values so I can just look at the distance between these two vectors or look at the element by distances between a vector of predictions and a vector ground truth values that I have。

So just again， reminding you of the notation that we're using with this design matrix。

 each one of these rows represents one observation。

 each one of the columns actually represents one feature or if or that's how we basically design this design matrix and how we arrived at the design matrix。

 so you would notice that every time that we give you a data set and we would say that the features are in columns technically we gave you a design matrix。

 the only thing that you need to add on top of that is this bias column that you need to add with all of those values of once。

Okay。Let's move on and talk about the dimensionality of all of these vectors that we had been creating and the equation that we have for all of those productions together。

So I'm going to refer to the column vector of all of those predictions that we have Y1 hat Y2 hat all the way to yn hat with big vector of y hat。

 so that's what I'm referring to so this is how you can distinguish between a vector of y and a single value of y so I'm writing it with the matrix notation of y which is equal to the design matrix。

 so this is my design matrix right here which is what you're seeing here that I'm showing it with the bold x。

 and then I also have all of these theta vectors orteta values in a vector so I'm referring to that as a vector of theta values the dimensionality of all of these vectors the matrixes is that the prediction is going to be an Rn for every data point or in the prediction so that's why it's in Rn so that's what you're seeing right here the dimensionality of my design matrix is going to be n by p plus1 right I have n。

Different observations and then I have p plus one different features p for features and then one for the bias term and then out the parameters are going to be in p plus one dimensional space one forteta zero and one parameter for each one of those other features if you just double check the possibility of me being able to multiply x withteta you would see that because of the dimensionality of them。

I can multiply the design matrix with this Theta vector。

 so it's an n by p plus one matrix multiplied by a p plus1 by one vector。

 which is going to give me the result of an n by one result and that's why the Y hat vector is going to be in RN。

So this is how we are going to just write all of those predictions for multiple linear regression equation into one matrix calculation and that's what I wanted you to take away from from the first kind of summary of what we're choosing in terms of our model but I want to do a secondgue and going back to the fact that this model is a linear model right I said that the definition of the linear model is a model that is linear in terms of the parameters so it's a combination of parameters that are is scaled by X values so technically what that means is that you should be able to always factor out all of the parameters into a column vector of Tetas and then everything else all of the features or transformed version of the features are going to be all of those coefficients that you're going to apply or you're going to multiply with all of thoseteta values so my question to you is to think about all of these five equations。

And I want you to tell me each of these following expressions are linear in TEA based on the description that I gave you。

One， two， three， four， five， or none of them。Or some of them。Think about it。Again。

 if you have trouble logging in on the app， try browser， and then you should be able to get on。

Let's take a look together， there is going to be another slide of question if you didn't get a chance to respond to this one。

You are saying1 to124 and5 so four and5 are kind of trivial for us because based on the definition that I gave you any way that you're able to isolate all the parameters into one vector and everything else is going to be in another vector or another matrix is going to be a linear model so4 and5 are kind of satisfying that constraint for us what about the equation1 but the equation one。

 the way that I can write it as is as I can isolate all of thoseteta values into a vector and then all of those coefficient if I factor them out into a row vector this is going to give me1 to4。

8 and log of 42 you would say log of 42 and you might think that now it's not linear but it is linear the only thing that we care about is linearity of theteta values right and all of the theta values in a linear way being。

In one column vector what about the second equation So in the second equation is still the same thing all of theteta gals are isolated into one vector。

 but you do see that there are someline combination of the input features which is fine so we're going to have a full lecture of feature and general you're going to see that we will actually go ahead and do all those kinds of transformations and combination of features so that our model is going to perform better and still we're going to be able to get a linear regression model at the end with the equation tree。

 this is not linear because of two things there's one thing that here we're taking the log of this parameter so we need to make sure that all of those parameters are linear and then in addition to that the multiplication oftateta3 timesteta4 is going to make them show aline relationship right there so that's why item3 is。

Only one that's not a linear equation in terms of k。

So let's move on and talk about the minus squared error。

 remember that we had these three steps scenario， four steps scenario and then with the model I wrote that entire fancy equation in terms of just a simple matrix multiplication or a matrix multiplied with a column vector but I'm going to walk you through another round of linear algebra to show you that the minus chd error can be written simply as this equation right here。

 it might not make sense right now but we'll see what that is exactly。

 so let's do another round of reminders of linear algebra。

Remember two lectures ago I was talking about L1 and L2 and I was saying that there is L1 norm and L2 norm norm of a vector is some kind of a measure of the lengths of a vector or length or size of the vector with the L2 norm the definition of L2 norm or the notation of how we're writing L2 norm of a vector so this is vector x and L2 norm of a vector x is that we're showing it with these two vertical bars and with the subscript of 2 which basically shows us that the equation of L2 norm is equal to a square root of the summation of a squares of the elements inside the vector x so if my vector x is equal to x1 x2 all the way to xn L2 norm of this vector is equal to a square root of the summation of a squares of all of these elements inside this vector so in a condensed way I can simply write。

As a score root of this sum of i from 1 up to n of X is squares。

 so this is the definition of L2 norm， so that notation that you saw was basically some notion of L2 norm that we had been using。

But what is L2 norm in practice so L2 norm is technically a general a generalized way of what you' had seen in pythagorean theorem in your high school so with the pythagorean termem you saw that if if you have one side as a and one side as B。

 then the lengths of the other side is going to be a score root of a squared plus b squared so this is technically what's happening in two dimensional space。

 but what we are doing is we're looking at calculating this measure of lengths in n dimensional space that's why it's kind of a generalization of the pythagorean theorem in n dimensional space that we're calling it L2 norm。

There are different ways that you can think about L2 norm。

 so L2 norm is going to give you a sense of a length of a vector why is that it's because if I have a vector right here so this blue vector that the dimensionality of this vector is A and B A across the x axis B across the y axis which technically here is going to be a here is going to be B the length of this vector in two dimensional space is going to be equal to the square width of a squared plus b squared so that's why L2 norm is an indication of the length in two dimensional space。

In addition to that， the other thing or the other way that we can use L2 norm is by calculating the distance between two vectors。

 so say I have vector a and I have vector B， and I'm interested in calculating the delta or the distance between a and B which I'm going to show here that this vector right here is a vector of a minus B right so if I want to calculate the length of a minus B。

 which is the delta between a and B， I can just go ahead and calculate the L2 norm of the vector a minus B which is exactly going to give me the length of this side right here or this vector right here。

 which is the distance between the two vectors Why is it important it's important because this L2 norm was similar to the minus squared error equation that we have been calculating remember with the minus squared error everything that we had been calculating so I'm going to write minus squared error。

Here for his sec。So I'm saying that MSE that we have been calculating was1 over n times the summation of I from1 up to n of EI is squares right EI was the residual for data point for data point1 look at the similarity of minus squared error with L2 norm of a vector so assume that if all of those EI values are inside one vector。

 so if I have one vector of E， which is going to give me E1 E2 all the way to EN all of these residual values for n different data points。

 then technically part of my calculation of MSC can be calculated using calculating the L2 norm some notion of the L2 norm of that residual vector or that vector E。

So let's take a look at how that's going to look like so this is the cost function that we had been using with minus squared error it's parameterized by TeEta depending on differentteta values I'm going to get different YI hats and the MSD was equal to one over n times the sum of a squares of these error values。

So I want to show you that this is exactly similar to saying that I'm going to go ahead and calculate L2 norm of the residual vector。

 so this is L2 norm of the residual vector， I'm going to square root so that I can get rid of that as square root factor that was there because L2 norm was equal to let me rewrite it as。

If I have L2 norm of a residual vector。B， this is equal to a square root of E1 is squared plus p2 is squared all the way to E squared。

 but if I'm interested in calculating one over n of the summation of i from 1 up to n of all of these EI squares。

 this is equal to me saying that this is equal to one over n times L2 norm of E。

A squared and that's exactly what's happening here one over n times L to norm is squared and e is equal to as you know。

 y minus y hat all of those predictions and grand truth values that you can really subtract those two vectors one vector from the other one and then you get the E or the residual vector that we have so you can see that with me writing the entire multiple linear regression in terms of a matrix calculation I can also write my cost function in terms of the L2 norm or the length or some measure of the length of the distance between y and y hat in this case。

 so this is technically the new cost function that we'll be working with。

 this is a constant factor one over n times the a square of the lengths of the residual vector that we have between the residual between y and y hat and that's what we're looking at。

So the question that I have for you is based on this cost function and based on your understanding of this geometry of why and why hat and the design matrix and also myteta vector。

 what do you think my OLS model is going to do because the OLS model has multiple linear regression as its model and it's going to try to optimize or find the minimum point of this cost function。

So think about it， what does this OLS problem trying to achieve and the options are given there。

This is going to be the last slide of the day， so if you didn't get a chance to respond to the other one。

 respond to this one。So let's take a look together Op A says that we want to minimize the minus squared error for the linear model that the linear model is defined as y hat equal to x times theta。

That seems to be right because that's what I said I want to do， I have a model。

 I've showed you that my model is y hat equal to x times theta I said that my last function is going to be minus squared error。

 so option A is correct。The second thing I'm going to go to the option C option C says that it wants to minimize the length of the residual vector。

 I showed you that the cost function technically is equal to one over n times the length of the vector is squared right so if you're minimizing the length of the residual vector in a sense you're minimizing your cost function because it's a factor of that so technically option C is also correct what about option B option B says that it minimizes the distance between true and the predicted predicted value。

 which is it tries to minimize the distance between y and y hat。Is that right？

It is right because it kind of follows from option C and option C I want to minimize the residual residual vector how do I minimize the residual vector that means that these two vectors should be very close to each other that's exactly what option B is so the correct option in fact is going to be all looked above so this is how you can really think about OLS or ordinary release squares with the multiple linear regression as its model and then MSc as its loss function so that was option D。

So let's take a look at how can I find the optimum Tetahat because so far I've been just building the template for the model。

 I didn't tell you how you can derive this Tetaha value that you need so as I said I'm not going to walk you through the matrix calculus because that's beyond the scope4 data 100 because otherwise you know the deal you know that the step is that I have an equation I want to find its minimum I should go ahead and take the derivative of equal equal to0 and solve it right but I'm not going to do that。

 but instead I'm going to walk you through a geometric argument and a geometric interpretation of what's happening in n dimensional space。

The last piece of algebra for today so the definition that I want to remind you is about the span of a matrix what is the span of a matrix or a column is space of a matrix。

 this means that if you're looking at your entire matrix of x so this is think about this from the perspective of your design matrix I have the design matrix X and I say that my design matrix has two columns this is the first column and this is my second column。

😊，So the span of x is every point that is achievable by every combination or by linear combination of the columns。

 So for example， here， this entire blue sheet is going to be the span that that can be defined by x1 and also x2。

 the column vector for feature1 and the column vector for feature2， So for example。

 here I would be able to achieve any point on here because I just need to think about what weight do I multiply with with the first column and what weight do I multiply with the second column so that I can arrive at this specific point。

Because each one of the columns that we have are going to be n dimensional space。

 because this entire design matrix was n by P， then span of a design the span of a matrix or the column is space for the matrix is going to be a subspace of n。

 so it's not going to be exactly equal to Rn but it's going to be a subspace of Rn。

 so this is the definition of the span of a matrix。

And I want to tell you why I'm talking about this span of x because the entire equation that I've showed you so far。

 we were thinking about it from the perspective of one observation at a time。

 we were saying that okay， I'm thinking about my design matrix in terms of a bunch of rows that each one of these rows represents one observation。

 I'm going to multiply each one of them and then I'm going to get one prediction。

 I'll stack them and I'll have all of those y hat values into one vector。

But there is another way that I can think about it and I can think about it in terms of having a vector of features so I have feature1。

 I have feature2 and feature one across all of the observations so this is one column feature two across all of those observations and I can say that in order to get the prediction for all of the n data points。

 this is equal to me saying that I'm going to scale my feature vector1 by a factor ofteta 1 and I'm going to scale my feature2 across all of these data points with the scale ofteta 2 and the result is going to be my y hat vector and the result is going to be in RN meaning that I'll have n different values。

 each one of them is going to be a prediction for one given data point so if you just write the math you will see that technically these two are exactly the same because that's what you're doing in the first case in the first case when you're multiplying each one of those rows with the column vector you're just assuming that the Teta。

is exactly the same for all of the data points right ifteta1 is going to be the same for all of the data points。

 what if you just go ahead and a scale feature one for all of those data points with the factor that you're going to scale it anyways right and then combine it with the scale factor for feature two and then do it all the way for all of the data points so here in this example I'm just showing you two columns and'm just simplifying things that you think that I only have two features and two weights and I'm going to combine them together this way。

How does this second approach relate to a span of x。

 This is exactly a span of x right because a span of a design matrix。

 I want to go back to the previous slide here， I said that the span of a matrix is going to be all the points that are achievable by every weighted combination of columns of x。

which is exactly what's happening here when I'm going to calculate all the points or making a prediction by weighting each one of those columns by different weight factors。

 then technically all of the points that I can get with the Y hat are going to be the points that are going to be in my span of x。

But I know that for different values of Teta， I'll get one point in our n in this span of x。

 but which point is the optimum point or which set of predictions are going to be closer to my grarous values。

 that's the thing that we're trying to solve。So let's see what's happening there so I said that we have all of those features so I'm looking at all of these column values that I have all of those columns are going to build a column space or a span in my design matrix so what I'm looking at is I'm trying to find a point on this space I'm going to say for example this point right here that I know that I can achieve achieve that point by a weighted combination of these columns so I would say that okay for this data point that I'm going to call it y hat or this vector y hat if I multiplyteta1 multiply column1 withteta1 multiply column2 withteta2 I will be able to get y hat but what I'm interested in is I want to make sure that the distance between y hat and y is as small as possible this is what we saw in this slide a question that our goal is to make sure that the distance between the vector of y hats and the vector of y in the n dimensional space is as minimum。

As possible， but why did I draw why had really outsided I this fan？

Because I said that the span of x is the subspace of Rn It does not include all the possible vectors that it can get in Rn。

 There is a possibility that your y hat is going to sit outside of this entire span so in that case then technically what we're dealing with is were really bounded by this is span so I can only walk on this space and I'm just trying to figure out what point is going to make me closer to this target value so let me make you an example let's think about this area as this span of x so all of these points here so let's assume that these are my two coordinates these are my two columns so I would say that with these two columns if I weight them in appropriate way I will be able to get a vector or a transition vector that is going to be anywhere in this area right but if I'm interested in for example getting something in n dimensional space or my vector my target vector in n dimensional space which is。

Li bulb up up there I'm really bounded by this surface I can travel vertically so the closes that I can get to this light bulb right here is going to be go ahead and stand really under it so I can still minimize the x kind of distance and the y distance but I can't minimize the Z or the vertical distance that I have so that's technically what we're trying to do and notice that again y is going to generally be outside of this span of x but we're bounded by this span of x when we're trying to find those parameters so this is kind of the analogy that I was trying to make that I need to basically find a point on this entire sheet that has the minimum distance to this light bulb which technically means that I need to be really right under it so that I can at least minimize that horizontal horizontal distance and then the only thing that I can basically that I can accommodate it is that vertical distance that I'll get。

So what I was doing by standing right under this light bulb right here was technically that I was trying to say that this light bulb。

 I'm going to project it or I want to find the orthogonal projection of that vector onto this space and that's basically how I got this point and that's exactly what we're going to do we're going to say that I'm going to find y hat in a way that this y hat is calculated by a set of theta values and those theta values are going to give me the direction to the right place that where is that right place that right place is going to be this orthogonal projection of y un this span of x so this is why this is y right here this is y hat right here this right here is my residual vector y minus y hat and what I'm saying is that y minus y hat should be perpendicular to this entire space or orthogonal to this entire span of x that I。

あ？Okay， does that make sense why it needs to be orthogonal to this entire span because I just need to make sure thatm my distance is minimized so I can't compensate for the vertical distance。

 but I can compensate or go and explore this space up until the point that I at least minimize whatever I can in this span that we have the proof of this orthogonality is beyond this scope of data 100 but that's why I said that this is electro geometric intuition of what's happening that this residual vector has to be perpendicular to this span of x。

So what does it mean for a vector to two vectors to be orthogonal to each other。

 we know that the angle between them should be 90 degrees or the dot product between the two vectors should be equal to zero。

That's in twodimensional a space between the two vectors When I say that a vector V is going to be orthogonal2 is span of m。

 which is exactly what we're looking for， I have a vector of all of those y values I have a design matrix that using a design matrix I'm I'm going to build that as space or that is span of x in order for a vector to be orthogonal to the entire span of x it has to be orthogonal to each individual column of the matrix right that's the definition from linear algebra I promise you this is the last reminder from linear algebra so a vector wants to be orthogonal to the entire span of x a span of M it means that it has to be orthogonal to each individual column that we have this is column one column2 all the way to column D if the matrix has the different columns。

So what does it mean for a vector to be orthogonal to another vector that means that the dot product between those two vectors has to be equal to zero or I can write the dot product as the column transpose times the vector be equal to zero so this is equal to me saying that the first column right here。

 the dot product between the first column and V be equal to zero and you know that the that I can write it is I can transpose one of those columns into a row vector and then simply multiply it with the second column。

So this is kind of the same trick that we've seen， I have V as a constant vector that is multiplied to each one of those trans transpose columns。

 which technically means that I can combine them into one vector and I can also factor out V and then just combine or stack all of those row vectors together into one matrix。

When I stack all of those Mi transpos， this technically means that I'm transposing the entire matrix。

 so when I transpose the entire matrix and I multiply it with the result has to be equal to0 because I know that when I look at each one of those columns。

 which are now my row vectors and I multiply them with the V。

 they all should give me a value of 0 that's why the result is going to be a0 a value of0 so this is the definition or the takeaway from what happens if you want to ensure that a vector is orthogonal to the entire span of x you have to basically transpose that matrix and then multipied it with the vector itself and then instead it to be equal to0 in order to get the result that you want which is exactly what I'm going do here。

 I want to show that this digital vector right here。Is orthogonal to this span of X。Right。

 I'm just going to write the equation and I'm going to borrow what I had from before。

 This was a definition of orthogonality of a vector V onto this span of M。

 which technically meant that go ahead and grab the your。

Your matrix transpose it multiplied by V and then you'll be you'll need to set it to be equal to zero at the point that my residual is orthogonal to the entire span of x this is the optimumteta that I have so I can technically say that this is going to be myteta hat that that gave me that y that y hat prediction vector that I got So I'm going go ahead and write it out so I'm saying that I want this vector right here if I think about it as V to be orthogonal to this span of x meaning that I should just go ahead and say that I have x transpose so is span of m I'm looking at an m here is my design matrix x x transpose times V is equal to zero what was my V my V was that residual vector that I had so I'm going to write it as Y minus x times。

And here， when I said it to be equal to 0， this technically means that I have myteta hat or optimumteta at this point。

 because that was the closest I could get to buy。So what do I do from here。

 I can just go ahead and solve it a little bit， so I'm going to simplify or rearrange terms a little bit。

 so I'll say that I can say x transpose times y minus x transpose times x timesteta hat is equal to0。

So I'm going to rewrite this as so I'm just going to negate it so that I haveteta0 on the left hand side orteta hat on the left hand side so that it's easier to read so I'm going to say that x transpose times x this is transpose times x timesteta hat is equal to。

Ex transpose。Actually。Let me write it this way。呃。Yes。

 why not x transpose times y so this is exactly the same equation that we have So x transpose times x timesteta hat is equal to x transpose times y and what I can what I can do is I can say that this right here is a normal equation this is the estimating equation If I find theteta hat that satisfies this equation then thatteta value is going to be myteta hat so I'm going to go ahead and isolated and find the exact value ofteta hat using those matrix values that I have but before being able to do that I need to basically make sure that I get rid of this x transpose times x。

The way that I'll do it is I'll assume that if x transpose times x is invertible。

 I'm going to multiply both sides by x transpose times x inverse。 So let me do it here。

 I'm saying that x transpose times x inverse is going to be multiplied with the left hand side and also with the righthand side x transpose times x times thesta hat equal to x transpose times x inverse times x transpose times y。

Okay what do I get from the left hand side x transpose times x inverse is multiplied by x transpose times x this right here together is going to give me identity matrix right so this is how I'm canceling out x transpose times x term that I had so that I can only deal withteta hat in the left hand side so technically what I'll have at the end is thatteta hat is going to be equal to x transpose times x inverse x transpose times y。

And this is only true if and only if x transpose times x is invertible。

 because otherwise I didn't have the inverse of x transpose times x to be able to cancel the left hand side or whatever that was multiplied but theteta had right there。

This is the solution so we used an argument， we used a lot of intuition from linear algebra and this geometric interpretation that we had so that we know that the residual vector has to be perpendicular has to be orthogonal to the span of x and then what I was doing was using the notion of what happens what should be the condition that the residual vector is is orthogonal to the span of x I wrote it out and then with the assumption of x transpose times x being invertible this is the result that I'll get that theteta hat is equal to x transpo times x inverse times x transpose times y and this is kind of a clean version of everything that we talked about and this is your really final takeaway from the OLS lecture with the OLS lecture OLS was what or at least the squares we've been trying to minimize least the squares of a multiple linear regression of a multiple linear regression model what I did was I wrote the entire multiple。

Lar regression in terms of a matrix calculation I said that MSC is a factor of L2 norm and then I basically said that okay if you're trying to minimize L2 norm and minimize the distance that vector has to be has to be orthogonal to this span of x I wrote the entire equation and then we arrived at pitta hat or optimumteta hat to be exactly this equation that you have you have all of the values on the right fun side so you can directly go ahead and calculate all of these values and then be done with this so this is a very important result if x transpose times x is inverible you have a direct solution to the Os problem and this is kind of a final takeaway from today's lecture。

So we are done with tree steps， we came a long way。

 we saw a lot of linear algebra that might sound a little bit boring or unnecessary。

 but now we have a model that with this model I can go ahead and visualize what's happening with the model and be able to evaluate the performance of the model。

 which is what we're going to do in the next little bit so let me go ahead to the demo and show you few things and finally kind of in practicing what happened with our MBA dataset set。

So let me。Reload this。All right， wonderful。Loading my pandas N and all of those things you have the data sets so this is the data that we have that i'm going to load just looking at the data frame so you'll see that there are a lot of features in the data frame that i'm not going to use all of those features so what i'm going to do instead is i'm going to focus on all of those tree features that I said we can take a look at so in this case what I'll say is i'm going to look at all of those three features and also the target value that I want to predict on and the result is going to be in the data frame format right here。

Because I want to go ahead and write the entire equation of my OLS in terms of this matrix multiplication。

 I need to separate out my target value， I need to only keep the features and I also need to add the bias term remember the bias trick or the column of all of those one values that I need to add I'll go ahead and do it so what we have right here is all of these three features that we have and I said that I'm going to insert at the position zero a column with the label bias and the values be filled in with values of one and then the result is going to be。

What's happened there？嗯。let's see。 all right， wonderful So I'm rerunning it again。

 There's that bias column that's now being added and all of those three features that I have。

 I'm going to convert it to Ny because that's what I need to do but I want to multiply two matrices or a matrix and a vector。

 so it shows me that there are 708 different rows and then four different features which is what we were expecting one for bias term and three features that I got what I'm going to do is I'm going to do exactly the same thing for y so I'm going to isolate the target value into one column vector and you can see that my column vector has the same length。

 my n in this case our number of samples is 708。So what I'm going to do is I'm going to say that。

I looking at this entire data set that I have or the X or the design matrix that I have with every combination of parameters。

 I will give you a prediction， but that prediction might not be optum so let's see what the prediction is gonna to look like if I just throw in a random set ofteta values So if I throw in a random set ofteta values and I go ahead and say that okay let's go ahead and get the prediction so this act means that I'm multiplying x with theteta vector or this arbitrary column vector that I created and I'll go ahead and do a prediction and side by side check all of the predictions that I made versus the ground truth values which you see that there's a lot of differences between there's a large error between my prediction and the ground truth value。

But we learned about minus squared error we saw that the minus squared error is one over n times L2 norm is squared of the residual vector so everything that we have is inside matrixrices and vector so I can directly use the tools that are available to me in NI in order to do any kind of vector calculation or matrix calculation so I'll go ahead and say that I'm going to go ahead and calculate minus squared error with any giventeta you give meteta by you giving meteta I can go ahead and get the prediction because that's my x times theta and I have the ground trace values once I have those to everything else's math calculation so I can go ahead calculate L2 norm is squared and then squared and then also is scale it by one over n which is exactly what's happening here one over n multiplied by the norm from lineage library the calculating norm of this residual vector y minus。

Y hat which is x times theta and then scoring the result and then the result is going to tell me that on average I don't need to like visually eyeball the predictions on average my MSC is equal to not on average my MSC is equal to 57。

000 something okay。What if now with the tool that I have。

 I go ahead and calculate the Teta hat for you， I know that the Teta hat is equal to this very complicated equation。

 which for the purpose of the exam we're going give you the equation。

 So you don't need to remember all the madness that's happening there。 I need to transpose my X。

 I need to multiply it with X。 I need to inverse it。

 All of those operations are available to us from nu。 So I'm transposing it， multiplying it with x。

 I'm calculating the inverse using this inverse function that I imported right here。

 then I'm gonna multiply it with x transpose。 Then I'm multiplying it with Y so I can just double check the equations are exactly the same。

 And the result is going to。The result is going to give me all of these Tetahat values the Tetahas that I have right now are going to be obviously different than the Tetahats that I got randomly from randomly sampling a normal distribution so let's take a look at the MSC side by side notice that the MSC for the arbitrary  Teta is 57000 the MSC for this specific Tetahat is much more beautiful right so this is all the time that like everything that we learned from math and all the process that we came through is actually paying off here because I can directly calculate whatever it is that I want to calculate get the best Tetahat the best Tetahat is going give me the minimum MSC and I'll be done with it。

I can go ahead and make the predictions using the Teta hatt that I got。

 just simply multiplying my design matrix， with the Teta hat and then I'll get all of those optimum y hat values that I got。

The next thing obviously is to just look at the predictions and visualize the result and then see if we're actually satisfied or not or if we had to change something if we needed more features or if we need to go back around the cycle of data science lifecycle that you remember the way that I'm going to visualize what's happening with the residuals is that instead of plotting residuals with respect to a single feature because I have multiple features I can have an ndimensional kind of plot and make sense of that but instead what I'll do is Ill plot residuals with respect to the predictions so what I'm expecting is kind of the same thing I'm expecting that all of the points to be as close as possible to residual being equal to zero and there is also another concept of heteroceasticity which technically means that the error that I'm getting for a small small predictions and large predictions I want them to be the same which is not quite so much happening here and we're going to take a look at some of these elements。

Later。The second concept that we can take a look， this is kind of how we're plotting the residuals the second thing that we can also take a look at is remember that we have been looking at the correlation。

We've been looking at the correlation when we were in simple linear regression correlation was giving us the strengths of linear association between input and output。

 the concept that we're using here is called multiple R score。

The multiple r squared is going to tell us what ratio of the entire variance in the target values into y' am I capturing with the y hat predictions So multiple r squared is defined as the variance of y hat divided by the variance of ys Again。

 this technically tells us what percentage of the variance in the what ratio of the variance in the actual data that am I capturing with all of these values that I have there's some other notations here that are not super necessary can you can take a look at them later。

 technically what we're also saying is that for an OLs with the intercept the multiple r squared is equal to correlation which y and y hat this squared which is not going to be so much useful in future also for simple linear regression your correlation is squared is equal to multiple r squared the proof is again beyond this scope。

Of this course， but just so that you know that there is some correspondence between multiple r score and correlation score in some of the cases that we have。

So if I go back and calculate multiple R score in this case。

 so I'm going to go ahead and get the variance of y hats and all predictions that I had and divided by the variance of y that I get。

 I am going to be able to see a value very close to one。

Why is that this technically means that I was able to explain all the variance or most of the variance that's happening in the entire data set and this is technically because of all of the features that I had I had a feature for the number of the two point goals and then three pointers and the number of us is what else do you need in order to calculate or in order to be able to figure out what the score is if a player is going to get three shots maybe that's the only thing that's missing and that's probably not going to be that's much of a variance that you're seeing in the entire data set so that's why we're going to be able what these features to explain 98% of the variance that we have in the data。

I'm going to also show you that if I keep removing these features because the features were so good and generally this is just too good to be true。

 if I go ahead and remove the two pointers or field goals and I say that I'm going to only look at ASD and 3pa and I'm going to use that follow exactly the same process all of these features adding the bias term turning it into a nu array calculating Lisa scoress estimate getting theteta value and multiplying the input with thisteta value in order to get the predictions and then calculating the multiple r score by calculating the variance of this model predictions from this model divided by the entire data the result is going to be 60% or 0。

6 so you see that we are now able to explain less from the variance of the data so this is going to tell you how good your model is trying to match the exact target values that you have if I go crazy and only use ASD you'll see that now I'm。

Explaining less than 50% of the data because I just don't have any information about field goals or three pointers and so on and so forth so this is kind of a takeaway why multiple R square is going to be helpful for you to know if you have enough features and if you're explaining the underlying trend in your data well enough or not。

I want to quickly go over some properties of the residuals and this is also for you to take a look in Homework5。

 so that's why I'm not going to explain it that much。

With the properties that I was talking about that the residual vector has to be orthogonal to the entire span of x。

 it follows that x transpo times e should be equal to0。

 this is the exact definition of orthogonality， it also follows that y hat vector is also going to be orthogonal to the entire to the entire residual vector。

 which is exactly what we saw in the equation that we exactly wrote that y hat is equal to is orthogonal to the residual vector that we have。

Also it follows that when we say that a vector is going to be orthogonal to the entire span of x。

 it had to be orthogonal to each individual column including the column of ones that we got therefore that means that sum that means that this entire vector of ones do E is going to be equal to0 and if you just write it out this will tell you that the summation of residuals is equal to0。

And why is it important， this is something that you're going to prove in your homework this is important because when I was talking about model cost。

 I was saying that we're not going to use the actual value of the residuals in order to use it as a cost function this is the exact proof if the model has ateta0 or bias term。

 the sum of residuals is going to be exactly equal to zero so they in fact cancel each other out so that's why we have been looking at the absolute values or the s squares of the residuals but L1 less sum with L2 less than calculation of the cost。

The last thing that I want to talk to you about is just a summary of everything that we had seen we had seen constant model with MSC。

 we had seen constant model with MAE， we had seen linear regression。

 simple linear regression which uses simple linear regression equation with MSC today we've seen multiple linear regression with MSC which gave us ordinary release squares。

 the models are written in the second column and the estimations are also written in the third column and you're all familiar with it。

 but the important part that I want to talk about that we're going to come back to that a little bit later is the uniqueness so with all of these cases the solution that we have is unique but the case that I was using MAE depending on the number of data points。

 the solution could be unique or could not be unique I circled the other way。

 but with the all what I want you to remember and the proof is beyond the scope of data 100 for now is that。

X to have for the solution to be unique in this case。

 we need to know that x transpose times x has to be invertible which if you go through the proof it will tell you that your x should be full column rank What does that mean that means that all of the columns should be independent of each other if columns are not independent of each other then there will be multiple solutions to the OLS this is equal to me saying that if I want to find a solution for being as close as possible to this light bulb thing that I had in RN and my span is based on two columns that are really parallel to each other say for example this is one column this is one column there is linear dependences between them by only a space is going to be a1d space right here that there is going be basically a space or multiple solutions that are going to be perpendicular from that target point to this span that I have that's why there will be multiple。

Solutions there。I'm going to leave you with that， we're going to come back to distant feature engineering to make sure that we design a design matrix that does not have linear dependencies between the features in the matrix。

Thank you for coming。 We'll see you next week。😊。

![](img/3bc08febc7648ea8e0631d43334e1199_3.png)