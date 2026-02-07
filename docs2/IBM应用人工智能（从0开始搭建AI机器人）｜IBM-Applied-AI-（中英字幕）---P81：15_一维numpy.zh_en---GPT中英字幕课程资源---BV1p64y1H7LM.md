# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P81：15_一维numpy.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/e690c93beb7dc0474e89ee5f0af68774_0.png)

In this video， we will be covering Numpy in 1 D， In particular， N D arrays。

 Numpy is a library for scientific computing。 It has many useful functions。

 There are many other advantages like speed and memory。 Numpy is also the basis for pandas。

 So check out our pandas video。😊。

![](img/e690c93beb7dc0474e89ee5f0af68774_2.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_3.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_4.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_5.png)

In this video， we will be covering the basics and array creation， indexing and slicing。

 basic operations， universal functions。

![](img/e690c93beb7dc0474e89ee5f0af68774_7.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_8.png)

Let's go over how to create a numpy array。A Python list is a container that allows you to store and access data。



![](img/e690c93beb7dc0474e89ee5f0af68774_10.png)

Each element is associated with an index。

![](img/e690c93beb7dc0474e89ee5f0af68774_12.png)

We can access each element using a square bracket， as follows。



![](img/e690c93beb7dc0474e89ee5f0af68774_14.png)

A numpy array or N D array is similar to a list。 It's usually fixed in size。

 and each element is of the same type。 In this case， integers。

 we can cast a list to a numpy array by first importing nuumpy。



![](img/e690c93beb7dc0474e89ee5f0af68774_16.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_17.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_18.png)

We then cast the list as follows。 We can access the data via an index。 As with the lists。

 we can access each element with an integer and a square bracket。



![](img/e690c93beb7dc0474e89ee5f0af68774_20.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_21.png)

The value of a is stored as follows。 If we check the type of the array we get numpy dot N D array。



![](img/e690c93beb7dc0474e89ee5f0af68774_23.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_24.png)

As nuy arrays contain data of the same type， we can use the attribute D type to obtain the data type of the arrays elements。

 In this case， a 64 B integer。

![](img/e690c93beb7dc0474e89ee5f0af68774_26.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_27.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_28.png)

Let's review some basic array attributes using the array。 A。

 the attribute size is the number of elements in the array。



![](img/e690c93beb7dc0474e89ee5f0af68774_30.png)

As there are five elements， the result is5。

![](img/e690c93beb7dc0474e89ee5f0af68774_32.png)

The next two attributes will make more sense when we get to higher dimensions， but let's review them。

 The attribute N dimm represents the number of array dimensions or the rank of the array in this case。

 one。

![](img/e690c93beb7dc0474e89ee5f0af68774_34.png)

The attribute shape is a tuple of integers indicating the size of the array in each dimension。

 We can create a numpy array with real numbers。 When we check the type of the array。

 we get numpy dot and D array。

![](img/e690c93beb7dc0474e89ee5f0af68774_36.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_37.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_38.png)

If we examine the attribute D type， we see Fat 64， as the elements are not integers。

 There are many other attributes。 Check out Ny dot org。



![](img/e690c93beb7dc0474e89ee5f0af68774_40.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_41.png)

Let's review some indexing and slicing methods。

![](img/e690c93beb7dc0474e89ee5f0af68774_43.png)

We can change the first element of the array to 100， as follows。



![](img/e690c93beb7dc0474e89ee5f0af68774_45.png)

The array's first value is now 100。 We can change the fifth element of the array， as follows。

 The fifth element is now 0。

![](img/e690c93beb7dc0474e89ee5f0af68774_47.png)

Like lists and tuples， we can slice a numpy array。 The elements of the array correspond to the following index。

 We can select the elements from one to 3 and assign it to a new nuumpy array D， as follows。



![](img/e690c93beb7dc0474e89ee5f0af68774_49.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_50.png)

The elements， indeed correspond to the index。 Like lists。

 We do not count the element corresponding to the last index。



![](img/e690c93beb7dc0474e89ee5f0af68774_52.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_53.png)

We can assign the corresponding indices to new values as follows。 The array C now has new values。

 See the labs or Nmpy org for more examples of what you can do with Numpy。



![](img/e690c93beb7dc0474e89ee5f0af68774_55.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_56.png)

NumpI makes it easier to do many operations that are commonly performed in data science。



![](img/e690c93beb7dc0474e89ee5f0af68774_58.png)

These same operations are usually computationally faster and require less memory in NmpPyI compared to regular Python。



![](img/e690c93beb7dc0474e89ee5f0af68774_60.png)

Let's review some of these operations on one dimensional arrays。



![](img/e690c93beb7dc0474e89ee5f0af68774_62.png)

We will look at many of the operations in the context of Euclidean vectors to make things more interesting。



![](img/e690c93beb7dc0474e89ee5f0af68774_64.png)

Vectctor addition is a widely used operation in data science。

 Consider the vector U with two elements。 The elements are distinguished by the different colors。

 Similarlyly， consider the vector V with two components。 In vector addition， we create a new vector。

 In this case， Z。

![](img/e690c93beb7dc0474e89ee5f0af68774_66.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_67.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_68.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_69.png)

The first component of Z is the addition of the first component of vectors U and V。



![](img/e690c93beb7dc0474e89ee5f0af68774_71.png)

Similarly， the second component is the sum of the second components of U and V。

 This new vector Z is now a linear combination of the vector U and V。



![](img/e690c93beb7dc0474e89ee5f0af68774_73.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_74.png)

Representing vector addition with line segment or arrows is helpful。

 The first vector is represented in red。 The vector will point in the direction of the two components。

 The first component of the vector is one。 As a result。

 the arrow is offset one unit from the origin in the horizontal direction。



![](img/e690c93beb7dc0474e89ee5f0af68774_76.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_77.png)

The second component is 0。 We represent this component in the vertical direction。

 as this component is 0。 The vector does not point in the vertical direction。



![](img/e690c93beb7dc0474e89ee5f0af68774_79.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_80.png)

We represent the second vector in blue。 The first component is 0。 Therefore。

 the hour does not point to the horizontal direction。



![](img/e690c93beb7dc0474e89ee5f0af68774_82.png)

The second component is one。As a result， the vector points in the vertical direction 1 unit。

When we add the vector U and V， we get the new vector Z。 We add the first component。

 This corresponds to the horizontal direction。

![](img/e690c93beb7dc0474e89ee5f0af68774_84.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_85.png)

We also add the second component。 It's helpful to use the tip to tail method when adding vectors。

 placing the tail of a vector V on the tip of vector U。



![](img/e690c93beb7dc0474e89ee5f0af68774_87.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_88.png)

The new vector Z is constructed by connecting the base of the first vector U with the tail of the second V。



![](img/e690c93beb7dc0474e89ee5f0af68774_90.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_91.png)

The following three lines of code will add the two lists and place the result in the list Zed。

 We can also perform vector edition with one line of Ny code。



![](img/e690c93beb7dc0474e89ee5f0af68774_93.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_94.png)

It would require multiple lines to perform vector subtraction on two lists。

 as shown on the right side of the screen。 In addition， the Nmpy code will run much faster。

 This is important if you have lots of data。

![](img/e690c93beb7dc0474e89ee5f0af68774_96.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_97.png)

We can also perform vector subtraction by changing the addition sign to a subtraction sign。

 It would require multiple lines to perform vector subtraction on two lists。

 as shown on the right side of the screen。

![](img/e690c93beb7dc0474e89ee5f0af68774_99.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_100.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_101.png)

Vectctor multiplication with a scalar is another commonly performed operation。 Consider the vector Y。

 Each component is specified by different color。 We simply multiply the vector by a scalar value。

 in this case， too。

![](img/e690c93beb7dc0474e89ee5f0af68774_103.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_104.png)

Each component of the vector is multiplied by two。 In this case， each component is doubled。



![](img/e690c93beb7dc0474e89ee5f0af68774_106.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_107.png)

We can use the line segment or arrows to visualize what's going on。

 The original vector Y is in purple。 After multiplying it by a scalar value of 2。

 the vector is stretched out by two units， as shown in red。

 The new vector is twice as long in each direction。



![](img/e690c93beb7dc0474e89ee5f0af68774_109.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_110.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_111.png)

Vector multiplication with a scalar only requires one line of code using numpy。

 It would require multiple lines to perform the same task as shown with Python lists as shown on the right side of the screen。

 In addition， the operation would also be much slower。



![](img/e690c93beb7dc0474e89ee5f0af68774_113.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_114.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_115.png)

Hatammar product is another widely used operation in data science。



![](img/e690c93beb7dc0474e89ee5f0af68774_117.png)

Consider the following two vectors， U and V， the had mard product of U and V is a new vector Z。

 The first component of Z is the product of the first element of U and V。 Similarly。

 the second component is the product of the second element of U and V。



![](img/e690c93beb7dc0474e89ee5f0af68774_119.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_120.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_121.png)

The resultant vector consists of the entry wise product of U And V。



![](img/e690c93beb7dc0474e89ee5f0af68774_123.png)

We can also perform hadammard product with one line of code in Nmy。

 It would require multiple lines to perform Haamama product on two lists as shown on the right side of the screen。



![](img/e690c93beb7dc0474e89ee5f0af68774_125.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_126.png)

The dot product is another widely used operation in data science。 Consider the vector， U and V。



![](img/e690c93beb7dc0474e89ee5f0af68774_128.png)

The dot product is a single number given by the following term and represents how similar two vectors are。

 We multiply the first component from V and U。 We then multiply the second component and add the result together。



![](img/e690c93beb7dc0474e89ee5f0af68774_130.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_131.png)

The result is a number that represents how similar the two vectors are。



![](img/e690c93beb7dc0474e89ee5f0af68774_133.png)

We can also perform dot product using the NmpPI function dot and assign it with the variable result as follows。



![](img/e690c93beb7dc0474e89ee5f0af68774_135.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_136.png)

Consider the array U， The array contains the following elements。

 If we add a scalear value to the array， Numpy will add that value to each element。

 This property is known as broadcasting。

![](img/e690c93beb7dc0474e89ee5f0af68774_138.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_139.png)

A universal function is a function that operates on ND arrays。



![](img/e690c93beb7dc0474e89ee5f0af68774_141.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_142.png)

We can apply a universal function to a nupy array。 Consider the arrays A。

 We can calculate the mean or average value of all the elements in a using the method mean。



![](img/e690c93beb7dc0474e89ee5f0af68774_144.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_145.png)

This corresponds to the average of all the elements。 In this case， the result is 0。



![](img/e690c93beb7dc0474e89ee5f0af68774_147.png)

There are many other functions。 For example， Consider the nuier arrays B。

 We can find the maximum value using the method 5。 We see the largest value is 5。 Therefore。

 the method max returns a 5。

![](img/e690c93beb7dc0474e89ee5f0af68774_149.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_150.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_151.png)

We can use Nmpy to create functions that map Nmpy arrays to new Ny arrays。

 Let's implement some code on the left side of the screen and use the right side of the screen to demonstrate what's going on。

 We can access the value of pi in Nmy as follows。 We can create the following numpy array in radance。



![](img/e690c93beb7dc0474e89ee5f0af68774_153.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_154.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_155.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_156.png)

This array corresponds to the following vector。

![](img/e690c93beb7dc0474e89ee5f0af68774_158.png)

We can apply the function signed to the array X and assign the values to the array Y。

 This applies the sine function to each element in the array。



![](img/e690c93beb7dc0474e89ee5f0af68774_160.png)

This corresponds to applying the sine function to each component of the vector。



![](img/e690c93beb7dc0474e89ee5f0af68774_162.png)

The result is a new array Y， where each value corresponds to a sine function being applied to each element in the array X。



![](img/e690c93beb7dc0474e89ee5f0af68774_164.png)

A useful function for plotting mathematical functions is line space。

 Line space returns evenly spaced numbers over specified interval。

 We specify the starting point of the sequence。 The ending point of the sequence。

 The parameter nu indicates the number of samples to generate in this case，5。

 the space between samples is one。😊。

![](img/e690c93beb7dc0474e89ee5f0af68774_166.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_167.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_168.png)

If we change the parameter nu to9， we get9 evenly spaced numbers over the interval from negative 2 to 2。



![](img/e690c93beb7dc0474e89ee5f0af68774_170.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_171.png)

The result is the difference between subsequent samples is 0。5， as opposed to one as before。



![](img/e690c93beb7dc0474e89ee5f0af68774_173.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_174.png)

We can use the function line space to generate 100 evenly spaced samples from the interval 0 to2 pi。



![](img/e690c93beb7dc0474e89ee5f0af68774_176.png)

We can use the Nmpy function sign to map the array X to a new array y。



![](img/e690c93beb7dc0474e89ee5f0af68774_178.png)

We can import the library pie plot as PLT to help us plot the function。



![](img/e690c93beb7dc0474e89ee5f0af68774_180.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_181.png)

As we are using a Jupiter notebook， we use the command matte plot lib in line to display the plot。

 The following command plots a graph。

![](img/e690c93beb7dc0474e89ee5f0af68774_183.png)

The first input corresponds to the values for the horizontal or X axis。



![](img/e690c93beb7dc0474e89ee5f0af68774_185.png)

The second input corresponds to the values for the vertical or y axis。



![](img/e690c93beb7dc0474e89ee5f0af68774_187.png)

There is a lot more you can do with Nmpy。 Check out the labs at numpy。org for more。



![](img/e690c93beb7dc0474e89ee5f0af68774_189.png)

![](img/e690c93beb7dc0474e89ee5f0af68774_190.png)

Thanks for watching this video。