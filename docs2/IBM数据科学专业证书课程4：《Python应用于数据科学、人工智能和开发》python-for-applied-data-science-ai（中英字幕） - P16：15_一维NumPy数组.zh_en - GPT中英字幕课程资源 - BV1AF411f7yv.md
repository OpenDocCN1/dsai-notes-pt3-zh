# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P16：15_一维NumPy数组.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_0.png)

In this video， we will be covering Numpy in 1 D， In particular， N D arrays。

 Numpy is a library for scientific computing。 It has many useful functions。

 There are many other advantages like speed and memory。 Numpy is also the basis for pandas。

 So check out our pandas video。😊。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_2.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_3.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_4.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_5.png)

In this video， we will be covering the basics and array creation， indexing and slicing。

 basic operations， universal functions。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_7.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_8.png)

Let's go over how to create a numpy array。A Python list is a container that allows you to store and access data。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_10.png)

Each element is associated with an index。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_12.png)

We can access each element using a square bracket， as follows。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_14.png)

A nuy array or N D array is similar to a list。 It's usually fixed in size。

 and each element is of the same type。 In this case， integers。

 we can cast a list to a numpy array by first importing nuumpy。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_16.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_17.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_18.png)

We then cast the list as follows。 We can access the data via an index。 As with the lists。

 we can access each element with an integer and a square bracket。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_20.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_21.png)

The value of a is stored as follows。 If we check the type of the array we get numpy dot N D array。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_23.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_24.png)

As nuy arrays contain data of the same type， we can use the attribute D type to obtain the data type of the arrays elements。

 In this case， a 64 B integer。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_26.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_27.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_28.png)

Let's review some basic array attributes using the array。 A。

 the attribute size is the number of elements in the array。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_30.png)

As there are five elements， the result is five。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_32.png)

The next two attributes will make more sense when we get to higher dimensions， but let's review them。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_34.png)

The attribute N dimm represents the number of array dimensions or the rank of the array。

 in this case， one。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_36.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_37.png)

The attribute shape is a tuple of integers indicating the size of the array in each dimension。

 We can create a numpy array with real numbers。 When we check the type of the array。

 we get numpy dot and D array。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_39.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_40.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_41.png)

If we examine the attribute D type， we see Fat 64 as the elements are not integers。

 There are many other attributes。 Check out Nmpy dot org。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_43.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_44.png)

Let's review some indexing and slicing methods。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_46.png)

We can change the first element of the array to 100， as follows。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_48.png)

The array's first value is now 100。 We can change the fifth element of the array as follows。

 The fifth element is now 0。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_50.png)

Like lists and tuples， we can slice a nuy array。 The elements of the array correspond to the following index。

 We can select the elements from  one to 3 and assign it to a new numpy array D， as follows。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_52.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_53.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_54.png)

The elements， indeed correspond to the index。 Like lists。

 We do not count the element corresponding to the last index。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_56.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_57.png)

We can assign the corresponding indices to new values as follows。 The array C now has new values。

 See the labs or Nmpy dot org for more examples of what you can do with Numpy。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_59.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_60.png)

NumpI makes it easier to do many operations that are commonly performed in data science。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_62.png)

These same operations are usually computationally faster and require less memory in NmpPyI compared to regular Python。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_64.png)

Let's review some of these operations on one dimensional arrays。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_66.png)

We will look at many of the operations in the context of Euclidean vectors to make things more interesting。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_68.png)

Vectctor addition is a widely used operation in data science。

 Consider the vector U with two elements。 The elements are distinguished by the different colors。

 Similarlyly， consider the vector V with two components。 In vector addition， we create a new vector。

 In this case， Z。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_70.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_71.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_72.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_73.png)

The first component of Z is the addition of the first component of vectors U and V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_75.png)

Similarly， the second component is the sum of the second components of U and V。

 This new vector Z is now a linear combination of the vector U and V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_77.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_78.png)

Representing vector addition with line segment or arrows is helpful。

 The first vector is represented in red。 The vector will point in the direction of the two components。

 The first component of the vector is one。 As a result。

 the arrow is offset one unit from the origin in the horizontal direction。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_80.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_81.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_82.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_83.png)

The second component is 0。 We represent this component in the vertical direction。

 as this component is 0。 The vector does not point in the vertical direction。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_85.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_86.png)

We represent the second vector in blue。 The first component is 0。 Therefore。

 the hour does not point to the horizontal direction。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_88.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_89.png)

The second component is one。As a result， the vector points in the vertical direction 1 unit。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_91.png)

When we add the vector U and V， we get the new vector Z。 We add the first component。

 This corresponds to the horizontal direction。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_93.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_94.png)

We also add the second component。 It's helpful to use the tip to tail method when adding vectors。

 placing the tail of a vector V on the tip of vector U。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_96.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_97.png)

The new vector Z is constructed by connecting the base of the first vector U with the tail of the second V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_99.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_100.png)

The following three lines of code will add the two lists and place the result in the list Z。

 We can also perform vector edition with one line of Nmpy code。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_102.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_103.png)

It would require multiple lines to perform vector subtraction on two lists。

 as shown on the right side of the screen。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_105.png)

In addition， the Nmpy code will run much faster。 This is important if you have lots of data。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_107.png)

We can also perform vector subtraction by changing the addition sign to a subtraction sign。

 It would require multiple lines to perform vector subtraction on two lists。

 as shown on the right side of the screen。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_109.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_110.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_111.png)

Vectctor multiplication with a scalar is another commonly performed operation。 Consider the vector Y。

 Each component is specified by different color。 We simply multiply the vector by a scalar value。

 in this case， too。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_113.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_114.png)

Each component of the vector is multiplied by two。 In this case， each component is doubled。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_116.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_117.png)

We can use the line segment or arrows to visualize what's going on。

 The original vector Y is in purple。 After multiplying it by a scalar value of 2。

 the vector is stretched out by two units， as shown in red。

 The new vector is twice as long in each direction。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_119.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_120.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_121.png)

Vector multiplication with a scalar only requires one line of code using numpy。

 It would require multiple lines to perform the same task as shown with Python lists as shown on the right side of the screen。

 In addition， the operation would also be much slower。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_123.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_124.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_125.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_126.png)

Haammar product is another widely used operation in data science。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_128.png)

Consider the following two vectors， U and V， the hadamamad product of U and V is a new vector Z。

 The first component of Z is the product of the first element of U and V。 Similarly。

 the second component is the product of the second element of U and V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_130.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_131.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_132.png)

The resultant vector consists of the entry wise product of U And V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_134.png)

We can also perform hadammar product with one line of code in Nmy。

 It would require multiple lines to perform Haamard product on two lists as shown on the right side of the screen。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_136.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_137.png)

The dot product is another widely used operation in data science。 Consider the vector， U and V。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_139.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_140.png)

The dot product is a single number given by the following term and represents how similar two vectors are。

 We multiply the first component from V and U。 We then multiply the second component and add the result together。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_142.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_143.png)

The result is a number that represents how similar the two vectors are。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_145.png)

We can also perform dot product using the NPI function dot and assign it with the variable result as follows。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_147.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_148.png)

Consider the array U。 The array contains the following elements。

 If we add a scalear value to the array， Numpy will add that value to each element。

 This property is known as broadcasting。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_150.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_151.png)

A universal function is a function that operates on ND arrays。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_153.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_154.png)

We can apply a universal function to a nupy array。 Consider the arrays A。

 We can calculate the mean or average value of all the elements in a using the method mean。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_156.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_157.png)

This corresponds to the average of all the elements。 In this case， the result is 0。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_159.png)

There are many other functions。 For example， Consider the nuier arrays B。

 We can find the maximum value using the method 5。 We see the largest value is 5。 Therefore。

 the method max returns a 5。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_161.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_162.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_163.png)

We can use Nmpy to create functions that map Nmpy arrays to new Ny arrays。

 Let's implement some code on the left side of the screen and use the right side of the screen to demonstrate what's going on。

 We can access the value of pi in Nmy as follows。 We can create the following numpy array in radance。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_165.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_166.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_167.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_168.png)

This array corresponds to the following vector。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_170.png)

We can apply the function signed to the array X and assign the values to the array Y。

 This applies the sine function to each element in the array。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_172.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_173.png)

This corresponds to applying the sine function to each component of the vector。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_175.png)

The result is a new array Y， where each value corresponds to a sine function being applied to each element in the array X。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_177.png)

A useful function for plotting mathematical functions is line space。

 Line space returns evenly spaced numbers over specified interval。

 We specify the starting point of the sequence。 The ending point of the sequence。

 the parameter nu indicates the number of samples to generate。 in this case，5。

 the space between samples is one。😊。

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_179.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_180.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_181.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_182.png)

If we change the parameter nu to 9， we get 9 evenly spaced numbers over the interval from negative 2 to 2。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_184.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_185.png)

The result is the difference between subsequent samples is 0。5， as opposed to one as before。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_187.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_188.png)

We can use the function line space to generate 100 evenly spaced samples from the interval 0 to2 pi。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_190.png)

We can use the numpy function sign to map the array X to a new array y。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_192.png)

We can import the library pie plot as PLT to help us plot the function。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_194.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_195.png)

As we are using a Jupiter notebook， we used the command matte plot lib in line to display the plot。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_197.png)

The following command plots a graph。The first input corresponds to the values for the horizontal or X axis。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_199.png)

The second input corresponds to the values for the vertical or y axis。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_201.png)

There is a lot more you can do with Nmpy。 Check out the labs at numpy。org for more。



![](img/401ef7fdd8ee9093bf6fc6a11bb90342_203.png)

![](img/401ef7fdd8ee9093bf6fc6a11bb90342_204.png)

Thanks for watching this video。