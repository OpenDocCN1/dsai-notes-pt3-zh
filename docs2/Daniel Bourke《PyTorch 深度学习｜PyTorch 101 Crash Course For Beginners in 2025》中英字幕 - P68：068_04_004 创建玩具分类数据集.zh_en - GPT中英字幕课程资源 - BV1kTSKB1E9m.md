# Daniel Bourke《PyTorch 深度学习｜PyTorch 101 Crash Course For Beginners in 2025》中英字幕 - P68：068_04_004 创建玩具分类数据集.zh_en - GPT中英字幕课程资源 - BV1kTSKB1E9m

Welcome back Now we've done enough theory of what a classification problem is。

 what the inputs and outputs are and the typical architecture。

 let's get in and write some code so I'm going get out of this and going to go to coabab。research。

google。com so we can start writing some Pytorch code I'm going to click new notebook we're going to start exactly from scratch。

😊。

![](img/93d6341a887c5861c7cf4e554ca9581c_1.png)

![](img/93d6341a887c5861c7cf4e554ca9581c_2.png)

![](img/93d6341a887c5861c7cf4e554ca9581c_3.png)

I'm going to name this section two and let's call it neural network。Classification with。

Pine to watch。I'm going to put underscore video because I'll just show you。

 you'll see this in the Github repo。 But for all the video notebooks。

 the ones that I write code during these videos that you're watching。

 the exact code is going to be saved on the Github repo under video notebooks。 So there's 00。

 which is the fundamentals and there's the workflow underscore video。

 But the reference notebook with all the pretty pictures and stuff is in the main folder here。

 So Pytor classification that I poem V。 Oh actually， it will just rename it that。😊。

Pyetor classification， but we know it's with neural networks。Pine to watch， classification。Okay。

 and let's go here。 We'll add a nice title to O2。Neural network。Classification with pieytorch。

 And so we'll remind ourselves， classificationification is a problem of predicting。

Whether something is。One thing or another。And there can be multiple。Things。

As the options such as email， spam or not spam， photos of dogs or cats or pizza or sushi or steak。

Lots of talk about food。 And then I'm just going to link in here this。Resource。

 because this is the book version of the course。 These are what the videos are based off， so。

Book version。Of this notebook。And then all the resources are in here。All other resources。

In the Github。 and then。Stock。Ask a question here。Which is under the Discions tab。

We'll copy that in here that way we've got everything linked and ready to go， but as always。😊。

What's our first step in our workflow， This is a little test。 See if you remember。Well， it's data。

 of course， because all machine learning problems start with some form of data。

 We can't write a machine learning algorithm to learn patterns in data that doesn't exist。

 So let's do this video。 We're going to make some data。Of course。

 you might start with some of your own that exists， but for now。

 we're going to focus on just the concepts around the workflow so we're going to make our own custom data set and to do so。

I'll write the code first， and then I'll show you where I get it from。

 We're going to import the Psyit Learn library。 One of the beautiful things about Google Coabab is that it hassyit Learn available。

 If you're not sure what psyit loan is。 It's a very popular machine learning library。

 Pytorrch is mainly focused on deep learning， but Psyit loan is focused on a lot of things around machine learning。

 So Google Coab。 Thank you for having psyt Learn already installed for us。😊。

But we're going to import the make circles data set。 And rather than talk about what it does。

 let's see what it does。 So make 10 samples。We're going to go N samples。Equals 1000。

And we're going to create circles。You might be wondering why circles。 Well。

 we're going to see exactly Y circles later on。 So x and Y we're going to use this variable。

 How would you say nomenclature as capital X and y， Y is that because x is typically a matrix。

 features and labels。So let's go here， mate circles and we're going to make and samples。

 so 10 different samples。 We're going to add some noise in there just for a little bit of randomness。

 Why not you can increase this as you want。 I've found that 0。

03 is fairly good for what we're doing and then we're going to also pass in the random state variable。

 which is equivalent to sitting a random or setting a random seed。

 So we're flavoring the randomness here。😊，Wonderful。So now let's have a look at the length of x。

 which should be。What。😡，And length the Y。Oh we don't have Y underscore getting a bit trigger happy with this keyboard here。

10， so we have1000 samples of x caught with10 or paired with1000 samples of y features labels。

 So let's have a look at the first five of x， so print first five samples of X。

 and then we'll put in here X and we can index on this。5， cu we're adhering to the data。

 explorelorerss motto of。Visualize， visualize， visualize。First， five samples of why。

 And then we're going to go Y， same thing here。Wonderful， let's have a look。

I we'll get a new line in here just so。Looks a bit better。Wonderful， so numerical。

 Our samples are already numerical。 This is one of the reasons why we're creating our own data set。

 We'll see later on how we get non numerical data into numbers。 But for now。😊，Our data is numerical。

 which means we can learn it with our model， or we can build a model to learn patterns in here。

 So this sample has the label of one。And this sample has the label of one as well。 Now。

 how many features do we have per sample， if I highlight this line， how many features is this。

It would make it a bit easier if there was a comma here， but we have two features of x。

 which relates to one label of y。And so far， we've only seen， let's have a look at all of why。

We've got zero on one， so we've got two classes。 What does this mean， zero or one。

 one thing or another。Well， it looks like binary classification to me because we've got only 0 or only one。

 If there was 0，1，2， it would be。Multti class classification， because we have more than two things。

 So let's x out of this。 Let's keep going and do a little bit more data exportation。

So how about we make a data frame with pandas of circle data？

There is truly no real definite way of how to explore data for me。

 I like to visualize at multiple different ways， or even look at random samples in the case of large data sets such as images or text or whatnot。

 if you have 10 million samples， perhaps visualizing them one by one is not the best way to do so。

So random can help you out there。 So we're going to create a data frame。

 and we can insert a dictionary here。 So I'm going to call the features in this part of X X1。

 And these are going to be x 2。 So let's say I'll write some code to index on this。

 So everything in the zeroth index will be x1。 and everything in the。First index。

 there we go will be x2。 let me clean up this code this should be on different lines。En唱。

And then we've got， let's put in the label。As why。So this is just a dictionary here。 So x1 key to x0。

 x2， a little bit confusing because of0 indexing， but x feature 1， x feature 2， and the label is Y。

 Let's see what this looks like。We'll look at the first 10 samples。Okay， beautiful， so。We've got x1。

 some numerical value， x2， another numerical value correlates to or matches up with label 0。

 But then this one。😊，0442208 and negative that number。Matches up with label 0。

 So I can't tell what the patterns are just looking at these numbers。 You might be able to。

 but I definitely can't。 We've got some ones。 All these numbers look the same to me。

 So what can we do next。Well， how about we visualize， visualize， visualize。

 And instead of just numbers in a table， let's get graphical this time。 Viualize， visualize。

 visualize。So we're going to bring in our friendly mappl lib。Import mappl lib， which is。

A very powerful plotting library。I'm just going to add some cells here。

 so we've got some space mappl Li dot pie plot。As PLT。That's wrong。We've got this plot dot scatter。

 We're going to do a scatter plot equals x。 and we want the first index。

 and then y is going to be x as well。So that's going to be on the Y axis。

 And then we want to color it with labels。 We're going to see what this looks like in a second。

 and then the color map。C map stands for color map is going to be plot dot color map， PL T。

 and then red， yellow， blue， one of my favorite colour outputs。 So let's see what this looks like。

 You ready。There we go。 There's our circles。 That's a lot better for me。😊，So。

What do you think we're going to try and do here？If this is our data and we're working on classification。

We're trying to predict if something is one thing or another。

So our problem is we want to try and separate these two circles。

 So say given a number here or given two numbers and an x1 and an x2， which are coordinates here。

 we want to predict the label， is it going to be a blue dot or is it going to be a red dot。

So we're working with binary classification。 So we have one thing or another。

 Do we have a blue dot or a red dot。 So this is going to be our toy data here。 And a toy problem is。

 let me just write this down。 This is a common thing that you'll also hear in machine learning note。

😊，The data we're working with is often referred to。As a toy data set。

A data set that is small enough to experiment on。But still sizable。

Enough to practice the fundamentals。 And that's what we're really after in this notebook is to practice the fundamentals of neural network classification。

 So we've got a perfect data set to do this。 And by the way， weve got this from psyt learn。

 So this little function here made all of these samples for us。

 And how could you find out more about this。😊，Function here。 Well。

 you could go psyt learn classification data sets。 There are actually a few more in here that we could have done。

 I just like the circle1。 toy datas。 We saw that。 So this is like a toy box of different dataset sets。

 So if you'd like to learn more about some data sets that you can have a look in here and potentially practice on with neural networks or other forms of machine learning models from psyt learn。

 Check out this psyt learn， I can't speak highly enough。 I know this is a piytorch course。

 We're not focused on this。 but they kind of all come together in terms of the machine learning and deep learning world。

 You might use something from psyt learn， like we've done here to practice something。

 And then you might use pytorch for something else like what we're doing here。 Now。

 with that being said。😊，What are the input and output shapes of our problem？

Have a think about that and also have a think about how we'd split this into training and test。

So give those a go， we covered those concepts and some previous videos。

 but we'll do them together in the next video。 I'll see you there。😊。



![](img/93d6341a887c5861c7cf4e554ca9581c_5.png)