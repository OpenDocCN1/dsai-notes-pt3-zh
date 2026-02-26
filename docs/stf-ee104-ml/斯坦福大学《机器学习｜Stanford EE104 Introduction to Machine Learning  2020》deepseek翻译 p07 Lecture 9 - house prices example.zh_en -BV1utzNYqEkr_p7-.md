# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p07 Lecture 9 - house prices example.zh_en -BV1utzNYqEkr_p7-

![](img/55d4b812c5f68cbb1f6617730806f095_0.png)

![](img/55d4b812c5f68cbb1f6617730806f095_1.png)

Welcome to。Introduction to machine learning， this lecture is an example。😊。

And the idea is that we will go through a very simple example using all of the topics that we've discussed so far。

😊，And take a little bit of a look at the sort of results one can expect。哦，所 the。

codeode that's necessary to。Get it to work。Oh。So this is a data set that comes from Caggle。

 Caggal is a Google owned company that organizes machine learning competitions。

And you can go to Kagggle and download。Data for a range of different domains。In this case。

 this is house prices。Kagle also keeps data sets in escrow so that one can compare the results of your own machine learning algorithm against。

A validation set which you've not seen before and other people haven't seen before。

And it also keeps track of other people's performance on particular data sets。

 so it's a worthwhile place to go。To get experience with trying machine learning a variety of domains。

This is a data set that consists of prices and features for 1，456 homes in Ames， Iowa。

And those were homes that were sold between 2006 and 2010。And。Here。

 our goal is going to be to try to use the features of the houses in order to predict the price。

 And we're going to focus on predicting the log of the price， because the prices。

Relative price is much more important than absolute price。

And house prices typically vary over a significant range。😊。

So our performance metric is going to be the RMSMS error on the test set of the log of the house price。

😊，In particular， if you have an RMS error of say 0。1。

 then it means that you can predict house prices within a factor of e to the 0。1。

 which is about 10 and a5%。Here is the sort of thing one sees in this data here we have a plot of the target variable。

 which is the log of the price against one of the。😊，Independent variables。

 the living area of the house in this case。And you can see well， first of all。

 there's quite a lot of variation， just knowing the living area doesn't narrow down the price very much。

嗯。Here we've got house prices varying between e to the 10 and a half。And E to the 13 or E to the 14。

W which is must be less than 100，000 to more than 500，000。And so we're seeing quite a variation here。

Now， the data set actually contains some 80 features。 We're going to use maybe。The first。

20 features and。Focus on those。So for our embedding for embedding the target variable。

 we're going to let V be the price and y be the log of V hits the log of the price。😊。

And then for the independent variables X we're going to embed them as follows we have some of those fields of a house record are numerical and those we can just embed unchanged so in particular we have the year of the house was built。

 the area of the living space， the area of the first floor， the area of the second floor。

 the area of the garage， the area of the wooden deck， the area of the basement。

 the year of the last remodel and the area of the lot， so all of the area are in square feet。

 they're just numbers and the years are simply years they're just integers。😊。

And we will just embed those as numbers as they are。There are also ordinal fields in our features。

 and we will embed those as integers。 So we have number of bedrooms， number of kitchens。

 number of fireplaces， number of half bathrooms， number of。Rooms。

Condition conditiond is a number that's scored between one and 10 that's assigned by an expert。嗯。

Would you be an araer or a realtor？We have the quality of the materials in the finish again assigned by an expert。

 but it's a score between one and 10。😊，And the number of cars that the garage can hold。

 So these are all small integers， typically between zero and 10。And we just embed them as they are。

No kitchen quality。Is a。A field which is stored on a like scale。The kitchen is rated， excellent。

 good， typical， fair or poor， although I don't think there are actually any entries in the data set that receive a poor rating。

And this is encoded as an integer between one and five。😊，After we embed it。

The building type is a categorical。😊，Field。This is embedded one hot。

And so it's embedded as a five dimensional vector， one of the canonical unit vectors with a one in one position in zero and all the other positions。

😊，The five different categories are single family， townhouse and unit， to family conversion。

 townhouse inside Uni and duplex。There's also a neighborhood。😊，Field。

 there are 25 different neighborhoods， so it's a categorical data。Field。

And this is also one hot embedded。As a result， we have looking back at our fields here。

 we have 17 numerical。😊，Fields。And we have the kitchen quality， which is 18。And then we have。30。

Components， which are one hot。So the total dimension of our x data variable is 48。

 and we're going to add one more， which will be the constant。Now。

 when we do the standardization and the data splitting， we do this in a particular way。

So we split the data randomly 80，20， 80% for training and 20% for test。

And that gives us an x0 training set and a corresponding Y train and an x0 test set and a corresponding Y test。

Now the way we do standardization is we use the training set to compute the means and the standard deviations of each of the features。

 so that means we'll get 48 numbers corresponding to the means each column of x0 train and 48 numbers correspond to the standard deviations of each column of x0 train。

And then we can use the means and standard deviations to standardize x0 train。

Simply by subtracting off the means and dividing by the standard deviations。

And we use the same means and standard deviations to standardize the test set。

Now in particular here we don't want to use the test set to compute the means and the standard deviations。

 because that would be including information from our test set into our predictor。

There's also a particular caveat that you should be aware of。

 and that is because many of our wearables are categorical。😊。

It often happens that particular columns of x train are actually all zeros。Data record， for example。

 that corresponds to a house in a particular neighborhood。

And that will give you a standard deviation of zero and so if you try to apply the straightforward standardization。

😊，Then of course， that will fail because we'll be trying to divide by zero。

But that's very simple all we do is we simply include that as a column of zeros in the data。😊。

So after we've standardized both the training and the test set using these means and standard deviations。

 we can then apply append a constant feature to both of them。And then we'll have Xtrain and X test。

An X train will be 1165 by 49， and X test will be 291 by 49。😊。

So now we're going to do mid regression， So we're going to。Use the。Remember the RMS。

Log price is our performance metric。And so our loss will be the quadratic loss。

We'll be minimizing the meat there。Empirical mean。Square。Error in the log of price。And。

Regularization， we use bridge regression， so we will use the quadratic regular vior。

So remember how we do regularized empirical risk minimization。😊。

We choose a range of Lada values logarithmically spaced here。

 we choose them between 10 to the minus3 and 10 to the three。And for each one of those lands。

We solve the regularized empirical risk minimization problem to find a theater， we choose a theater。

 we find the theater that minimizes this quadratic function。Of the vector Thear。

Notice that we've used a capital Y here， even though capital Y here is actually just a vector。

 not a matrix because M is one， we've only got a single target variable。嗯。

And notice also that we're not regularizing the constant term。In the theater。Once we've got these。

Theatre values。 I think we have 50 different。Lambda values。

 And so we get 50 corresponding seeta values。Then。啊。For each one of those the values。

 we can compute the training error simply by computing the RMS of x train times theta minus y train。

 that's just a vector。So。We take。啊，One on n times the sum of the squares of that vector and then square root that quantity。

And similarly， the test error， x test， Theta minus y test。And for this data set， this is what we see。

😊，Here on the left， we have。😔，Two curves plotted against theater， we have the empirical risk。

Of the different thes， so at any given lambda value， we have a corresponding the。

 we have a corresponding test error and a corresponding train error。We can see that at all theaters。

 the test error does a little bit worse。デデや。trainingraining。And。In fact。

 regularization of pest offer no benefits here。The data is sufficiently。

 we have a sufficiently large amount of data compared to the number of features that we have that there's no danger of overfitting。

And。As a result， the regularization does little for us。The minimum Rms error is about 0。12。

Which corresponds to about a 13% error in house price。Over here on the right。

 we have the plot of The versus Lada， the regularization path。 We can see that。

Even with Lambda about。0。1。We're starting to see。Some shrinkage。

 the components of the are getting smaller without any loss in performance。

 so a reasonable choice of Lambda would be something。😊，Of that order， somewhere between 0。1 and 1。

Here we have the test data and each point on this plot shows two values。True price， why this is。

 of course， the true log price。And the predicted low price Y hat。And ideally。

 we would expect we would want to have all points。On the diagonal indicating that weve predicted perfectly。

And the points are clustered reasonably well about。😊，There I can know， we're not doing badly。

We have some outliers。Here and hair。Where we are vastly overestimating。The price。And also here。

But otherwise we're doing okay and perhaps one thing one might do after making these kind of predictions is to go back and look at those data records and figure out why。

😊，The true price for those is so much less than the predicted price。We can also look at the The。

 the entries of The tell us something about the importance of the different features。😊。

And we can see。That this one， this one， this one and this one。Are important features， as is this one。

 this one and this one。 those are the theater entries that have the largest。Magnitudes。

They correspond to。These。Seven features。Four of those arent。😊，About the size of the house。

 area of living space， area of first floor， area of second floor， area of basement。

Very reasonable things that would drive the price of a house。

One of them is the year in which it was built， so how new is the house？😊，And the other two are the。

Expert assessments of the condition and quality。And so it's quite reasonable to see that these things sharp as the most important determinants。

😊，Of the。A price of a house。You can also notice that there are interesting points here last。25。

Features and inks。One hot encoding of the neighborhood。And if we look， for example。

 at this point and this point。This one's about 0。02 and this one's about minus 0。02。

And that means that。If。I move from this neighborhood。Over here to this neighborhood over here。😔，Well。

 then this first component here。The 3s，1，32nd，33rd component。Of x。Go switches from a1 to a zero。

And the 30th component。Of x， which is from a zero to one。And so。My contribution of theater transpo。

Times x from those two components changes from minus 0。02 to plus 0。02。Which means that。House price。

Chaangnge by about 4%。So just by moving from one neighborhood to another， we can see。

That much change in house price and this these last。Few entries of The。

 tell us which are the desirable neighborhoods and which are the undesirable neighborhoods。O。

Let's take a look at the code。嗯。First of all， we can just run it and see。

That it does what we think it should do。Let's include。The file is called house。gl。And。

The main function here is what we're going to run。And that should。To the computation。Yeah， produce。

Relause。Every time you run it， it will produce slightly different plots because remember the test and train split is chosen randomly。

We can see here。This is just the。Or data file。This is another piece of raw data。Here we can see。

 I think these features， we can see what we've plotted here。啊。No。

So this code will be available on the website， there are two files in particular house。jL。

 which does all the computation and then there's another file called housepls。jL。😊，And houseplots。

jl does the plotting。That requires。Py plot。Or you'll have to modify it to use whatever plotting package。

You are using。So here we're plotting two things which plotting the lot area and the living area。

And so versus price and so here are our two features。Living area。

And this is lot area and we can see that there's quite a few。😊，啊。Very extremely large。

Houses which shift。Which are really outliers in our data set。

And so if we were to go through and remove those or adjust for those in some way。

 we might find ourselves doing slightly better in our fits。One can open the。

Data file in a spreadsheet。No one can see the。1500 or so different records。In the corresponding。

 80 or so different fields。If we look at the plots that were generated。

 this is our regularization path。😊，And some。I don't need the plotting file anymore。🤢。

This is our test and train errors as a function of Lada。And what's back there is are。Prediction。

Versus true value。Let's take a look at how this works。😊，So I have two windows on the screen。

 the one is my Julia terminal and the other is my editor containing the Julia code。

 this Julia code is about 150 lines long to do everything that we did today。诶。

The first thing it does is it loads the data， we can just take that and paste it。Into here。

Now that gives us two things， it gives us D。Which is a matrix， which is an array of strings。

1456 rose by 81 columns。The 81 different fields， I guess the first field there was simply an identifier。

 so there's really 80 different。fieldsiels。And every entry in this matrix is a string and that's loaded by a function at the top of this file called load data。

Which doesn't do anything very interesting， it just caused the CSV library to load it。

It does one thing here， which is it removes what turns out to be a couple of outliers。

 I think there are four of them which have。A living area greater than 4，000 square feet and are。

 been quite extraordinary。Houses in this data set。So we remove those。

And then it just returns for us the data。D and the header， which is a list of the field。Names。

Now we can take in。It's the number of records we're going to have。对ね。Now we do two embeddings。

 one is y， so embed y， let's take a look at that， what that does。

 this is the function definition here。It's a one line function definition。Some things to notice。

 let's take a look at this。So get data field， simply pause out。😊，啊。That column of the data。

So there's the prices。Let's just call that something new。There we go。And now string to number。

 these are all strings just from the way the CSV format is stored。So we can string to number it。

Let's just cool that U1。And now we've got an array of floating point numbers。

One thing to notice about this， this is a feature of Julia that's worth being aware of is the dot notation。

So string to number。We'll happily take a string。And return you back in number。

But actually what U is is not a string， it's an array of strings or a list of strings。

 and so by using the dot notation。So if we were to call string to number on just you。

 it would say error。This， you can't。Coal。The function that string to number calls。

 which is the parse function on an array。But you can。

Do this and what that does is it causes string to number to be applied to each entry of the array U and it constructs an array of the results。

So if I give it an away。Of strings。It will happily give me back an array。😊，Of numbers。

 if I call it with the dot。And so we're just applying the string and number to each of the entries of that data record。

嗯。That's what U want is， and then we're applying the log to each of the entries of that to get Y。

And so if I call andbed。Y D hiter。It returns me back a vector， which is the log of all the prices。

That's what Y is。Now we can embed X， this is substantially more complicated because we've got a bunch of different fields。

Let's take a look at that， first of all， let's see what it does。😊，That returns for us X。

 which is our 1456 by 48 array。Of。对。Different fields that we have， 20 fields。

 some of which are encoded as one hot， and so they correspond to more than one column of this matrix。

And all of our data records of 1456 different houses。😊，And the way this works is that。

In the embed X function here， this is the function definition。We can see this too。

Convenient functions defined at the top。 These are just for convenience。

What they do is their closures， they store the value of D and header so that whenever I call field name inside this function embedex。

 I don't need to supply D and header。Similarly， when I call real F name。

 that's just the same as calling string to number dot of get data field of D header name。

So real F here stands for real field。And so what we're doing is we are。

And we can define these functions。In the。Julia Lo here on the left。And then if I do real if。

A year built。We can see what it's going to do， it's going to strengthen number the data field corresponding to year built。

Which is just a list of those numbers。And we we do this for each one of these。

And we get simply the list of the corresponding field numbers。Now we can also look at。

Some of the more complicated ones， one here that's more complicated is the kitchen quality field。

If we look at the kitchen quality field。😊，T a lirt scale， the entries in it are GD for good TA。

 for typical。Excellent and。There maybe there are others。

 we can unique that and see all of the unique entries in it。Good。Typical， excellent or fair。

The unlike Kt function。What that does is it maps these particular strings to numbers。Here it is。

So unlike her sets a pre dictionary， which maps x to5， good to4， T to 3， fair to two and poor to one。

And returns the corresponding number。And so if I apply。Unlike like hert。To that。

I get a list of numbers。Notice the dot again because I'm applying the unlike it function to each entry of the array separately and returning back an array of the results。

😊，There's one more little piece of。Conversion that goes on and that's the one hot conversion。

If I look at， say the field building type， let's look at the smaller of the two。明 that。Again。

 there's a list of strings， categories， five different possible categories。

 we can look at what they are by doing unique。😊，There are the five categories。And the one hot。Here。

 One hott does not work entry wise， One hott works on the entire list of 1456。Strings。

And it simply finds the categories which are here are unique。You。So we have U is equal to。

That unique of you is going to be the categories。And then it constructs a matrix。

 which is each row is a canonical unit vector， which is five dimensional。

 which is five is the number of categories。So we can see what it does if we do one hot。All of you。でザ。

One hot encoded。Building types。Here we have HcaAT， which joins all of these columns together into one large matrix。

And so that if I call embed X， I get the large matrix。Of all of our data。

Now train rows and test rows are just lists of rows which are randomly selected。

 the split there is 8020 when we call it we'll get a new split， let's see what that looks like。Yeah。

 so train rows just says， well， you should use these particular rows as your training set。And。

This particular rows as your test set and there。Let's all of the rows together and there's a disjoint。

Now what we do is we split up the feet， the data set apply split does the year。嗯。Does the。

The thing you might expect， let's look at what a applyly split does。

Apply split simply splits the data， picks out the corresponding rows for the train and the test set。

Let me just run that。 And now I've got。An X train zero。And next test to0。

My sets of features corresponding to the training and the test sets and then corresponding。Wise。

Now the Get statistics function gets the means and the standard deviations of each column very simply。

好。So let's look at what that does。So now how many means have I got。

 I've got 48 means because x train0 remember had 48 columns and I've got 48 standard deviations。

 you can see there's quite a variation in their means and in their standard deviations which is why it's important to standardize。

Standardized plus one。Convenience function that。Goes through。

And does the standardization transformation on each column divides。

 subtracts the mean and divides by the standard deviation。

 except in the case when the standard deviation is zero， which can happen？In which case。

 we simply subtract the mean。And then it does one more thing after doing the standardization。

 which is it appends a column of ones。😊，Of course， we can't do that before standardizing because that will just have its means subtracted off。

So if we do that x train and X test， well that gives us our true x train and X test from x train0 and x test zero。

Now we're constructing Las。Which is our list of lambers。

 note what we're doing here is dot to the power of， which means。😊，Again。

 it's a broadcasting call of the function， call of the function power this time。

 so it applies 10 to the power of each of the elements of the range， so we have the range here。

Wwhich is between minus3 and3 that has a particular data type which has a code on in its's a range。

 if you want to see it as a list you can by doing collect。😊，And then you'll see it as a list。Yeah。

 I do lambdas to it。Then I'll get my list of logarithmically spaced between 10 to the minus3 and10 to the three。

Clam this。Now we do a ridge regression， we've seen that function before。

 this is applying it one by one to each of the lands for each lambda in Las。😊。

Call a bridge regression to give me at which returns a theater and make a list of the theaters。

 that's what this notation means this is called a list comprehension。We run it。There we go。

 we've got a list of theaters。We can look at the size of the Thes variable and it's just a 50 dimensional list。

 Thes one， the first entry is a 49 dimensional。Vectctor。sameme for all the others。

 each one of those is the theater corresponding。Toland的。Now for each one of those。

We do another little for loop here， another list comprehension for reach The。

 we compute X train times The， which is remember the prediction of y on the training set elements。

When we compute the RMS error over all of the training elements。And the same for the test errors。

So now we can do one more thing which is find the minimum of the test errors。Here。

This tells us that the 16th element of test errors was the smallest and the corresponding test errors0。

122。😊，We can also see what the corresponding theta is by looking at the corresponding entry of theta。

 we can see what the corresponding lambda is。😊，There's the corresponding Lada。

And we can just work out what those are right there。😊，And everything else in now is printing。

We print。Our results。Print the optimal train， optimal test。Otimal lambda， optimal feeder。

And then there's a plotting， which we'll go through and make the plots that you saw。

 it needs all of these data elements to do that。And this is really how one would do。

Everything that we've seen so far in the class to do with regression。

We can create more complicated features for X。😊，We could create， for example， more。

One hot features for， instead of our。Sple real number embedding of our ordinals。

 we could create product features。And we could pick out the outliers。

And there's a few things we could do。In fact， for this data set。

 none of those things seems to make a great deal of difference。Which is why we haven't done them。

Now we'll see other examples where we can do some of the more fancy things。

That involve more fancy embeddings and more fancy regularizations。



![](img/55d4b812c5f68cbb1f6617730806f095_3.png)