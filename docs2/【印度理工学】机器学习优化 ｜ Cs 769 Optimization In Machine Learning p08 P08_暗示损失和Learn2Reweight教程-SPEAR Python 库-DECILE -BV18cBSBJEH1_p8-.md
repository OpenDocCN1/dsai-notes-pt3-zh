# 【印度理工学】机器学习优化 ｜ Cs 769 Optimization In Machine Learning p08 P08_暗示损失和Learn2Reweight教程-SPEAR Python 库-DECILE -BV18cBSBJEH1_p8-

Hello everyone， I am Pa of the Turia an undergraduate from the Department of Computer Scienceense and Engineering at IIT Bombay。

I just completed my third year of undergraduate studies and I am a core contributor to SpR module of data efficient machine learning research。



![](img/f18966fb0d0bd1b69cb671210459d7ba_1.png)

Here we will go through the end to end tutorial for labeling of the SMS spam data set using high level supervission algorithm。



![](img/f18966fb0d0bd1b69cb671210459d7ba_3.png)

As we start， we first need to define an enum to hold labels。

These genomeum are used in an algorithm below。As seen。

 the spam data set contains two classes that is ham and spam。

Note that the number to which these classes are mapped2 can gain anything。

 but it is suggested to use a continuous mapping from 0 to number of classes minus1。



![](img/f18966fb0d0bd1b69cb671210459d7ba_5.png)

Then as we move further， we define pre processes， continuous scores and labeling functions。

Since this wall demonstrated earlier， we do not iterate over all these elements again and just show how to declare a preprocesor for the sake of demonstration。



![](img/f18966fb0d0bd1b69cb671210459d7ba_7.png)

![](img/f18966fb0d0bd1b69cb671210459d7ba_8.png)

As seen， we define the preprocessor convert to lower in the way shown。



![](img/f18966fb0d0bd1b69cb671210459d7ba_10.png)

Here we have two different kinds of train modes。Namely F D and FD U。

These are based on the data on which algorithm is trained。

The former that is MD specifies that the training of the model is done on label data only while the letter that is FDu specifies that the model is being trained on label as well as unlabeled data。



![](img/f18966fb0d0bd1b69cb671210459d7ba_12.png)

The next block shows the importing of the required functionalities and libraries。As displayed。

 we also save the models checkpoints for future use the number of checkpoints that need to be saved can be passed as an input to the function as shown。

And it completely up to the user's discretion。

![](img/f18966fb0d0bd1b69cb671210459d7ba_14.png)

Further。We initialize different directories corresponding to the different log records and results that are being stored in them。



![](img/f18966fb0d0bd1b69cb671210459d7ba_16.png)

We create these directories if they do not already exist。



![](img/f18966fb0d0bd1b69cb671210459d7ba_18.png)

Then we initialize different parameters that will decide the output of the model。For instance。

 some of the common parameters。And hyperpar that initialize here for Fd include as learning rate。

Bad size。And number of epochs。These are also initialized for the FDU training method。

We also initialize the primary metric。We evaluate how well our model predicts on the test sample。

It can be set to accuracy or F1 score 1 that is F1 score as shown。



![](img/f18966fb0d0bd1b69cb671210459d7ba_20.png)

Gamma and Lambda are the two other hyperparameters having their usual purposes。



![](img/f18966fb0d0bd1b69cb671210459d7ba_22.png)

![](img/f18966fb0d0bd1b69cb671210459d7ba_23.png)

Further， since high level supervision module supports many kinds of training algorithms to train the model。

 we need to choose which training algorithm has to be used by us。

We do this choice by initializing the mode variable with the required training algorithm to train our data。

For instance， we have set the mode here to implication also referred to as implied laws in some places in the repository and the paper。

It signifies here that we will be using the I algorithm to train our data。

The possible algorithm choices available for training our data are learned to evade implication。

 PR loss or MDD MDds here signifies majority label voter。

Further since the entire high level supervision algorithm is based on two networks。

 namely F network that is classification network。And W network， that is rule network。While testing。

 we have an option regarding which network to test， we can test either the F network。The W network。

Or both the networks。For the desired accuracy。We need to initialize the test mode variable by this intended test choice。



![](img/f18966fb0d0bd1b69cb671210459d7ba_25.png)

Further， the number of classes。Theyote the number of classes utilized in the labeling functions。

The use joint FW variable is a Boolean variable， which is set through means that both the F andW networks will be used during inference and test time。

If it is set false， only the F network will be used。We need to initialize。

This use joint FW network variable as required。After this。

 different pickers storing different relevant data are also initialized here。

Then we initialize the output test file by a name consisting of the mode。The gamma， the Lambda。

 and some other hyperparameters declared earlier。This is just for the sake of systematic analysis。

After this， we create a data feeder class。With the parameters shown to initialize the member variables of this class。

The main objective of this class is pre processings of the data at this point we have a data feeder object of the data feeder class that we will now use in the commands below。



![](img/f18966fb0d0bd1b69cb671210459d7ba_27.png)

To get an idea of the structure of our input， we can extract number of features of the input。

 number of classes being used， number of rules being used and number of rules on which the input is trained。



![](img/f18966fb0d0bd1b69cb671210459d7ba_29.png)

Then we initialize the F network and the W network that were mentioned earlier。



![](img/f18966fb0d0bd1b69cb671210459d7ba_31.png)

After this， we create an object named Hls that is an object of the high level supervision network class。

This object has member functions in it like train， test， etc。

 which will be used for training and testing the model on the data available。



![](img/f18966fb0d0bd1b69cb671210459d7ba_33.png)

As seen if the training algorithm chosen is Fd that is majority label voter。

Then label data is essential for training。Hence。The train F on D method is being called。However。

 in case of all other training algorithms like implication learn to re NPR loss。

 the training data can involve both labeled and unlabeled data。Hence， train on FDU is called。

Similarly， different test functions are used for the corresponding testing modes。



![](img/f18966fb0d0bd1b69cb671210459d7ba_35.png)

![](img/f18966fb0d0bd1b69cb671210459d7ba_36.png)

This is the end of this tutorial on how to utilize high level supervision module for training the data labeled using labeling functions and other aforementioned elements in case of any queries suggestions or feedbacks feel free to reach out to the SpR group thank you for watching this video。



![](img/f18966fb0d0bd1b69cb671210459d7ba_38.png)