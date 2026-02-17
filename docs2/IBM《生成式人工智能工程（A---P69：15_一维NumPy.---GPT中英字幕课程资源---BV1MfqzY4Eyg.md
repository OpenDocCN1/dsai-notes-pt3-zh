# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P69：15_一维NumPy.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

In this video， we will be covering Numpy in 1 D， In particular， N D arrays。

 Numpy is a library for scientific computing。 It has many useful functions。

 There are many other advantages like speed and memory。 Numpy is also the basis for pandas。

 So check out our pandas video。😊。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_1.png)

In this video， we will be covering the basics and array creation， indexing and slicing。

 basic operations， universal functions。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_3.png)

Let's go over how to create a nuy array。A Python list is a container that allows you to store and access data。

Each element is associated with an index。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_5.png)

We can access each element using a square bracket， as follows。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_7.png)

A numpy array or N D array is similar to a list。 It's usually fixed in size。

 and each element is of the same type。 In this case， integers。

 We can cast a list to a numpy array by first importing numpy。We then cast the list as follows。

 We can access the data via an index。 As with the lists。

 we can access each element with an integer and a square bracket。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_9.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_10.png)

The value of a is stored as follows。 If we check the type of the array we get numpy dot N D array。

As nuy arrays contain data of the same type， we can use the attribute D type to obtain the data type of the arrays elements。

 In this case， a 64 bit integer。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_12.png)

Let's review some basic array attributes using the array。 A。

 the attribute size is the number of elements in the array。As there are five elements。

 the result is5。The next two attributes will make more sense when we get to higher dimensions。

 But let's review them。 The attribute N dimm represents the number of array dimensions or the rank of the array in this case。

 one。The attribute shape is a coupleple of integers indicating the size of the array in each dimension。

 We can create a numpy array with real numbers。 When we check the type of the array。

 we get numpy dot and D array。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_14.png)

If we examine the attribute D type， we see Fat 64 as the elements are not integers。

 There are many other attributes。 Check out Nmpy dot org。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_16.png)

Let's review some indexing and slicing methods。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_18.png)

We can change the first element of the array to 100， as follows。The array's first value is now 100。

 We can change the fifth element of the array， as follows。 The fifth element is now 0。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_20.png)

Like lists and tuples， we can slice a numpy array。 The elements of the array correspond to the following index。

 We can select the elements from one to 3 and assign it to a new Numpy array D， as follows。

The elements， indeed correspond to the index。 Like lists。

 We do not count the element corresponding to the last index。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_22.png)

We can assign the corresponding indices to new values as follows。 The array C now has new values。

 See the labs or Nmpy do org for more examples of what you can do with Numpy。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_24.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_25.png)

Numpy makes it easier to do many operations that are commonly performed in data science。

These same operations are usually computationally faster and require less memory in numpyI compared to regular Python。

Let's review some of these operations on one dimensional arrays。

We will look at many of the operations in the context of Euclidean vectors to make things more interesting。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_27.png)

Vectctor addition is a widely used operation in data science。

 Consider the vector U with two elements。 The elements are distinguished by the different colors。

 Similarlyly， consider the vector V with two components。 In vector addition， we create a new vector。

 In this case， Z。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_29.png)

The first component of Z is the addition of the first component of vectors U and V。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_31.png)

Similarly， the second component is the sum of the second components of U and V。

 This new vector Z is now a linear combination of the vector U and V。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_33.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_34.png)

Representing vector addition with line segment or arrows is helpful。

 The first vector is represented in red。 The vector will point in the direction of the two components。

 The first component of the vector is one。 As a result。

 the arrow is offset one unit from the origin in the horizontal direction。The second component is 0。

 We represent this component in the vertical direction。 as this component is 0。

 The vector does not point in the vertical direction。We represent the second vector in blue。

 The first component is 0。 Therefore， thearrow does not point to the horizontal direction。

The second component is one。As a result， the vector points in the vertical direction 1 unit。

When we add the vector U and V， we get the new vector Z。 We add the first component。

 This corresponds to the horizontal direction。We also add the second component。

 It's helpful to use the tip to tail method when adding vectors。

 placing the tail of a vector V on the tip of vector U。

The new vector Z is constructed by connecting the base of the first vector U with the tail of the second V。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_36.png)

The following three lines of code will add the two lists and place the result in the list， Zed。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_38.png)

We can also perform vector edition with one line of numpy code。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_40.png)

It would require multiple lines to perform vector addition on two lists。

 as shown on the right side of the screen。In addition， the Nmpy code will run much faster。

 This is important if you have lots of data。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_42.png)

We can also perform vector subtraction by changing the addition sign to a subtraction sign。

 It would require multiple lines to perform vector subtraction on two lists。

 as shown on the right side of the screen。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_44.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_45.png)

Vectctor multiplication with a scalar is another commonly performed operation。 Consider the vector Y。

 Each component is specified by different color。 We simply multiply the vector by a scalar value。

 in this case，2。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_47.png)

Each component of the vector is multiplied by two。 In this case， each component is doubled。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_49.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_50.png)

We can use the line segment or arrows to visualize what's going on。

 The original vector Y is in purple。 After multiplying it by a scalar value of  two。

 the vector is stretched out by two units， as shown in red。

 The new vectors twice as long in each direction。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_52.png)

Vector multiplication with a scalar only requires one line of code using numpy。

 It would require multiple lines to perform the same task as shown with Python lists as shown on the right side of the screen。

 In addition， the operation would also be much slower。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_54.png)

Haammar product is another widely used operation in data science。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_56.png)

Consider the following two vectors， U and V。 The hadam mard product of U and V is a new vector Z。

 The first component of Z is the product of the first element of U and V。 Similarly。

 the second component is the product of the second element of U and V。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_58.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_59.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_60.png)

The resultant vector consists of the entry wise product of U And V。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_62.png)

We can also perform Haammard product with one line of code in Nmy。

 It would require multiple lines to perform Haamama product on two lists as shown on the right side of the screen。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_64.png)

![](img/08fc78bb14007605d1a2a0bf4d8091e6_65.png)

The dot product is another widely used operation in data science。 Consider the vector， U and V。

The dot product is a single number given by the following term and represents how similar two vectors are。

 We multiply the first component from V and U。 We then multiply the second component and add the result together。

The result is a number that represents how similar the two vectors are。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_67.png)

We can also perform dot product using the NmpI function dot and assign it with the variable result as follows。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_69.png)

Consider the array U。 The array contains the following elements。

 If we add a scalear value to the array， Numpy will add that value to each element。

 This property is known as broadcasting。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_71.png)

A universal function is a function that operates on ND arrays。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_73.png)

We can apply a universal function to a numppy array。 Consider the arrays a。

 We can calculate the mean or average value of all the elements in a using the method mean。

 This corresponds to the average of all the elements。 In this case， the result is 0。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_75.png)

There are many other functions。 For example， Consider the nuier arrays B。

 We can find the maximum value using the method 5。 We see the largest value is 5。 Therefore。

 the method max returns a 5。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_77.png)

We can use Nmpy to create functions that map Nmpy arrays to new Ny arrays。

 Let's implement some code on the left side of the screen and use the right side of the screen to demonstrate what's going on。

 We can access the value of pi in Numpy as follows。

 We can create the following Numpy array in raddiance。This array corresponds to the following vector。

We can apply the function sign to the array X and assign the values to the array Y。

 This applies the sine function to each element in the array。

This corresponds to applying the sine function to each component of the vector。

The result is a new array Y， where each value corresponds to a sine function being applied to each element in the array X。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_79.png)

A useful function for plotting mathematical functions is line space。

 Line space returns evenly spaced numbers over specified interval。

 We specify the starting point of the sequence。 The ending point of the sequence。

 The parameter nu indicates the number of samples to generate In this case，5。

 the space between samples is one。😊。

![](img/08fc78bb14007605d1a2a0bf4d8091e6_81.png)

If we change the parameter nu to 9， we get 9 evenly spaced numbers over the interval from negative2 to 2。

The result is the difference between subsequent samples is 0。5， as opposed to one as before。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_83.png)

We can use the function line space to generate 100 evenly spaced samples from the interval 0 to2 pi。

We can use the nuy function sign to map the array X to a new array Y。

We could import the library pie plot as PLT to help us plot the function。

As we are using a Jupiter notebook， we used the command matte plot lib in line to display the plot。

 The following command plots a graph。The first input corresponds to the values for the horizontal or x axis。

The second input corresponds to the values for the vertical or y axis。

There is a lot more you can do with Nmpy。 Check out the labs at numpy。org for more。



![](img/08fc78bb14007605d1a2a0bf4d8091e6_85.png)

Thanks for watching this video。