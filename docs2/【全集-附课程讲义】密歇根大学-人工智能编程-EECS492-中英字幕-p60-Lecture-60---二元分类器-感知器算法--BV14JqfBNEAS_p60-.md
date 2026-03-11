# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p60-Lecture-60---二元分类器-感知器算法--BV14JqfBNEAS_p60-

Lets begin， considering simple classifiers。A binaryical asifier is a function which can decide whether or not an input vector belongs to a specific as。

Binary classification often refers to two layers classification。Its a type of linear classifier。

Which he makes。As predictions based on a linear predictor function。The examples are perceptron。

A the line， logistic regression and supportive。These are artificial neurons。

Durs are interconnected noble cells involved in the processing and twistt signals。

They can be summarized in this figure。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_1.png)

嗯。Signals will come to the neuron through dendrite。And the cell body。Will integrate the signals。Then。

 the accumulated the signal。It says a certain fit short then。An output will be made。

That's the schematic description of neuron。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_3.png)

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_4.png)

Here we have definition for binary classifier。X I YI 레ド 데이터 set。And with the X in。아디 디디메저널。And why。

Is either0 or1。A binary classifier finds a hyperplane in I。

That separates data points into two classess， as in this figure。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_6.png)

So， binary classifiers will find。Such hyperplane to separate。The data set into two parts。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_8.png)

Labels， we choose the labels0 and 1 are chosen for simple。 You may choose some other values。

 minus-1 and1。 You can choose them。A hyperplane can be formulated by a normal vector and a shift to and double0 so that hyperplane can be written in this range。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_10.png)

For that line in 2D， the line is a hyperplane， and W is a normal vector of the line。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_12.png)

To learn W and W 0， you may have to formulate a cost function to minimize。

This formulation has the sum of squared error， error squared summed。

So it is called the sum of a schedule error。And now for this input。

 this one is called the one Z is called net input。And。Many cases。

 we try to use certain activation function。So the F to activation。

 the value is compared with the given label。And we try to。Minimize this objective function。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_14.png)

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_15.png)

Let's go to the peral algorithm。The perceptron is a piary classifier of supervisored learning。

It began in 1957， from。こ年。Or notutical laboratory。And later on， it is。Refined。

 And then here even it is implemented as a hardware。And that means that once input came。

 then immediately through a filter and immediately output came out。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_17.png)

This is a definition of the perceptron。As a binary classifier。XS input values， input vector。

And W is weight vector。That was betrayed during the training。And here， we choose。2 class levelss。

1 and -1。 You can choose a 0 and 1。Or-1 and1， Either way， you can choose the labels。Now。

 once input values and rates are here the selected， then now we try to get。Net input。

 that is weighted the sum of input values with this rate values。Now， in activation in the perceptron。

 we are using a thresholdholding scheme。Once the Z net input is larger than or equal to theta。

P threshold， then the value is one。And otherwise， we we get minus-1。So after getting this。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_19.png)

Actation value。 and we eventually try to minimize that once we chose W so that it is completely separating。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_21.png)

The data set into two parts， then。Now， this activation will make for every point superscript I is indicating I the I theta point。

 So if once w is chosen accurately then for all I， the value must be0。 so that。

The sum of error was visible， and is done in training。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_23.png)

Okay。So along with this activation and we try to get the value and compare with the label。

And once it is wrong， then through iteration， we try to update。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_25.png)

Okay。Now here for simplicity， rather than theres a thera value。

We may try to move the theaterta to left and side。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_27.png)

So that。And move with this one。And then here we define Z in this range。

So there's sometimes we yet writing in this form。But practically， they on。And for this one now。

 because it is moved to left and side rather than Theta， and we are using0。So that for activation。

 once C is a larger than or equal to Cdo， then activate the values1， otherwise minus1。

In the literature of machine learning， the variable W0 is called the bias。

 so sometimes you are using the letter B to indicate the bias， but here double 0。The equation。

 equal C 레 Hy플lae。And w0 decide the intercept。 Okay， then I'm using here now M。

 but then must be D okay。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_29.png)

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_30.png)

Here we have perceptron learning room。The rosen bloods initial perception rule is given in this rh In the beginning。

 we initialize weight to 0。Or small， random numbers。And for each training sample， X I。

We tried to compute。The activation value that is predicted level value。 And biasing that。

 we try to update the weight。The practical。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_32.png)

Opate rule is here。For W。And2 again 뉴W。Stuff from older the one。 And we try to get。

There's correction vector。 the correction vector。Is obtained in this vein and measure the difference。

This is 오리지1。And that is predicted the label from here。And。Now， X I the。

Data set theta point heres now multiplied by this one， and then again， scaled by Yta。

We have to choose yetta， small。And along with this correction vector is updated for double0。

 what's the sameA？But now we are without this X I， we try to update W 0。Here， Eta is called the。

Learning rate and Y is the true Cus label and Y H I denotes the pre to the Cus label。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_34.png)

Therefore， this update。Let's try to do a simple thought experiment。

Let the perceptum predict the cholesterolssal label correctly， then。

Y I minus Y I had more spec so that the widths remained unchanged。Once he's wrong， then。Here。

 this one can be is one， for example， then is a minus1。Then it'll be 2。If it is a minus1。

 if it is plus 1， then must be minus2。So that this whole thing is the same as here， plus minus-2 yta。

um。X， so that the which W chain is pursued。Toward the direction of the positive or。

Nガativeィブ target class。So either one。It is not。Z。 and then along with this one and try to push the hyperplane so that try to locate the Hyplane between the classes。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_36.png)

Here we have a program perceptron PI。 I implemented this class for perceptron。In the beginning， okay。

NowYou have to give Ting of。X， the data points and initial Epa is 10 and running rate is 0。201。

 So you can assign this values or you can use this default， but that is necessary in the beginning。

Now， along with the input。That is initialization。Self EPA is defined in self learning rate and self。

Wait， open。initialize the zero weight。Here， in class。Start with self。

P fixes self means that these variables are shared in every functions method in the。Cls。So yeah。

 once you call activate and along with a point。Then， the point。Will be。Here are that product。

 along with weight。 And once during the iteration， rates are updated。

 then the last updated weight will be used to to get that product and double 0 editor。

 So it is net import。Once that input is larger than 0， then return 1， if not。

 then return 0 right now， we consider label1 and 0。That is now fear。 this is a training operation。

Ex train， Y train are given then。Yeah。Number E pop。 So K E pop is executed。And in each hip part， and。

From X wide train， each point each rebel is selected for their own。

Activate by using last updated weight and。Yue。That' is activated， and this is a predicted wide value。

And by using the exactly the formula， we try to organize this correction vector and correction term for w0 and add it to weight。

So in each itition， it is updated and next dictation will use the in updated value。And automatically。

 it is shared in this function activate。Now， predict。And start with why hat empty。

And all test to data points。And you may get， okay， either this way and that way you can implement。

So from M Y head， you append the activations activity value for each x in X data set。

 you can implement it this way over。And you commit that one and use that one for X in X test。

 and you can。Here append each activation， or you may write down in separate two line。

Python is quite flexible。You can write in various ways。And also， this is square function。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_38.png)

Is counting the correct answers and the stuff from Cdo。 And once for each X Y in X test。Why test？

In after activation。That is activated value is the same as the label value。

Then we count an added by one。After counting all of the。

 the collected answer and divide by length of the number of a point。

Then we can get accuracy in percentage。Right。These are major functions in。Most of。Clifiers。Okay。

 now here I added one more。 That is fit and fee。And wait or start with this one， and。Try to get here。

 appended。The rates。That' is for。Figure purpose。 So that is changing modification of fit function。

 Only Okay， this one is added。

![](img/9f96e9c4b0239af39227eac9ebc0b9d7_40.png)

And then that line is added though， in return。So in main program。

 we want to see how rates are changing and how。The hyperplanes are changing to convert to a certain final hyperplane。

Okay。So in reality， you don't have to implement this portion， okay。Now， that is the main program。

Calling perceptron， we are using IIS data San。We start with nuy packaging， and plot。And here。

 from cyclone with touchs。Now。Okay， that is a train test split。 And also fromcyclone。

 we get data set。And yet， that line is for print out。And for engineering number， for example。

Sometimes you see 0。0000。Eat to this you。라든데。And along with this option， you can get0 dot。

 so it's very simplified。So I'm using this option， most cases。

Now we call we import the perceptron implemented。 Okay for that on from data set。

We choose I this data set。 From there on， we collect data into X and。Now， we the target key。

 we can get here now를。呃。The labels， the label names are not 0，1，2。 There are 3 classes。

 so that itll include 0，1，2。But here。And， basically。They have some target。

 critical target name and also the features for columns。And this is4 image。Data set。

 and you have original future names。Okay。Now， for。The 대。有 mean。Now here。

 try to get the number of data points and the dimension and also for y we consider as a set that is only 01012 are remained and length will be 3 so that you can print out to see how the data set is given。

And from the data set to test the perception on， we need to order simplify the data。

So we try to choose two classes。So from X， just we try to get。Only the push where。

Y is less than O equal to one。 So y equals 0， y equal 1，2 classes are selected also for。

Why the labels we collected them the same name。And， again。Now。Once you selected the two classes。

Then again， yet it has four columns is four dimensional data set。Out of that。

 we to choose the first column and the third column to get two dimensional data set。Okay。

 after selecting their one。Now， for x 2。Y2。We try to split by using the function x to Y 2 with the twin size。

0。7。And they make this separation and。Yang。😔，We open。The perceptron classifier。

 And now this object is made， along with dimension， it is required。And the。

 And that is optional that we chose。E part is 2。The percepttuion is updating。The object。

The rates for each single data points。 So a number of re is the same as。The number of points。

E park means go through all data said twice。So， that is enough。

And you can call for the classifier fit。But rather than fit。

 we try to use fit and fee so that we get weights on。

And accuracy can be obtained by calling the scope of method。

 and you can put it out for their own output。The accuracy is one。

Now you may try to get predicted values for each。Test the point。 and you can save there。

 But here is committed out。 We don't have to call here。 Now， below portion is for figuring。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_42.png)

I eliminated， and we see here。Of figures。That is for two dimension general two class data set we made from here。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_44.png)

There on， and。Now， perceptron。Is initialized with the0 that。 and then。And after tenit， after passing。

Using 10 data points， it becomes that lion。And now after using train points， now it becomes that one。

Its passing 30 points。It came here， and。This hyperplane。🤧。We'll make every point。嗯。

The right prediction so that after that， and it is not moving。But here。

 this one is a bit near to this points。So once it is done。Go out here？And。

That is it can be this line， it can be that line or I be different slope like that anyway。

 among these lines， once the perception diches add one of these lines， then never move。嗯So that。

Depending on your initialization and dependinging on your choice of。The learning rate。

 the your final。Even though it is converged。And your final separation line。Its different， so that。Oh。

It's not really ideal classifier， however， once given data set is separable。

 like in this subset of areas。And once it's a separateable， then certain number of iteration later。

 you can get right。A separating hyperplane。Even though it is not opt， you can get it anyway。

 that's the probability of。The perceptron algorithm。Okay。That's the end of part1， thank you。



![](img/9f96e9c4b0239af39227eac9ebc0b9d7_46.png)