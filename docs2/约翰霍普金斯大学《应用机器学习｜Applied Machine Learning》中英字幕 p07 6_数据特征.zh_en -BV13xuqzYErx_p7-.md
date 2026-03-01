# 约翰霍普金斯大学《应用机器学习｜Applied Machine Learning》中英字幕 p07 6_数据特征.zh_en -BV13xuqzYErx_p7-

![](img/49f0344245e6591a4342c85ff4afda82_0.png)

🎼。

![](img/49f0344245e6591a4342c85ff4afda82_2.png)

Dear students。In this module， we will look at the data features。

Recall that machine learning is solving a computation problem using a program without an explicit program。

Data clearly is the core of the machine learning。The data is captured through some process。

Which might be independent of our model development。But we need it for any kind of data analytics。

 pattern discovery or generation of a model for some prediction problem。 for example。

 in the last module， we looked at hundreds and digit images。

For detection of digits automatically to help post workersers Now， when it comes to machine learning。

 the representation of the data， the features of the data and the relevancy of the data are of utmost importance。

We will set a particular standard for data representation and that is this x matrix which is the collection of our data points。

 these x matrix dimensions are n by m where n is the number of data points in this example from one to five data points and M is the number of columns in this example 3 corresponds to the features of the data。

 our dependent variable is stored in y we do not keep the dependent variable in the x matrix because in a classification problem we are going to predict them so we keep all the data which are independent features in x matrix and keep our labels or dependent variables dependent variable in this case in the y column vector when it comes to data we can talk about certain types。

nominal binary string date and some more complicated features。

 Our data representation on the computer is the machine representation。

 It can be integers floating point， for example，32 bit floating point 64 B floating point or text as sequence of characters in Java。

 for example， it corresponds to string numerical can be integer or floating point。 Z or R。

 It is safe to convert all numerical variables to floating point variables。

 Sometimes this is also processed faster because of the GPus。 we can keep the nominals。

 as a set of levels drawnmed from an alphabet， and again。

 even though the corresponding nominal variable can be a long string for example。

 something like hot weather， cold weather， warm weather， we can represent them as integers，012。

 and there would be a lookup table which。Rerespond to hot weather to value 0。

 warm weather to value 1 and cold weather to value 2。 In some cases。

 we may need to convert nominal to numerical and numerical to nominal。

Because there are a variety of algorithms when it comes to machine learning。

 some of these algorithms work very well with numerical features。

 and some of them work very well with nominal features is a guideline probability-based approaches。

 frequency based entropy based approaches， they like nominal variables， because we count them。

 The other side of the coin where the machine learning algorithms like numerical variables are distance based or costbased approaches。

 such as support vector machines K means clustering neural networks where a function is fitted to the data。

 One hat encoding is necessary， when we need a nominal variable to be converted to numerical variable。

 If the nominal variable takes L different levels， then we will create L binary variables for each of those level。

 If the number of levels， a nominal variable requires is 100。

That means 1000 different features are generated， and this is also a waste of space。 understandably。

 however， that's the most straightforward and safe approach when it comes to nominal to numerical conversion。

 we will use one hot encodecoding numerical to nominal conversion。

 as we will see involves histograms binning and bin boundaries。 Basically。

 for the range of that particular numerical variable， say minus 100 to plus 100。

 we will decide on a number of bins， for example，20 and then equally map the numerical values to those 20 bins and then represent the variable with those 20 levels。

 and then we can1 hat encode those variables back to the numerical realm。

 all these conversions help the algorithms。 and if we do not do these conversions ourselves。

 the algorithms。In their black box programs， we do them automatically。

 we will look at the online data sources in another module where we will download。

 we will visit these web pages and then download the data sets。

 an important note about all these when a physical data set file is shared among teams。

 that physical data set file has to be exactly same with every little detail and also for repeatability。

 a script must be saved where the raw data is used to generate the actual experimentation physical data file using that script。

 multiple rounds of that script should generate the exact same data file The relation between the independent variable and a dependent variable is important。

 machinech learning model will be built upon this relation。

 One of the metrics piercing correlation coefficient gives a measure of correlation。

variableable data pointsI x is an independent variable and y is the dependent variable。

 multiplication of each point and the summation would give a positive value or the negative value of one normalized by two standard deviations is a proper metric to measure the correlation between variables when we ranked variables generally the independent variable that carries the highest correlation to the dependent variable is generally ranked higher。



![](img/49f0344245e6591a4342c85ff4afda82_4.png)

![](img/49f0344245e6591a4342c85ff4afda82_5.png)