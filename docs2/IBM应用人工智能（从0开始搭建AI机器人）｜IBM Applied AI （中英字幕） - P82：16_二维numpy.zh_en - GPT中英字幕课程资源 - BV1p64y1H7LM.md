# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P82：16_二维numpy.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

We can create numpy arrays with more than one dimension。 This section will focus only on 2 D arrays。

 but you can use numpy to build arrays of much higher dimensions。



![](img/c1cad779d7c3a68b87a91e85045b6b10_1.png)

In this video， we will cover the basics and array creation in 2D， indexing and slicing in 2D。

 and basic operations in 2 D。

![](img/c1cad779d7c3a68b87a91e85045b6b10_3.png)

Consider the list A。 The list contains three nested lists， each of equal size。

 Each list is color coatd for simplicity。 We can cast the list to a nump array， as follows。😊。

It is helpful to visualize the nuy array as a rectangular array。

 Each nested list corresponds to a different row of the matrix。



![](img/c1cad779d7c3a68b87a91e85045b6b10_5.png)

We can use the attribute and dim to obtain the number of axes or dimensions referred to as the rank。

The term rank does not refer to the number of linearly independent columns like a matrix。

 It's useful to think of N dimm as the number of nested lists。

 The first list represents the first dimension。This list contains another set of lists。

 This represents the second dimension or axes。 The number of lists the list contains does not have to do with the dimension。

 but the shape of the list。As with the1 D array， the attribute shape returns a tuple。

 It's helpful to use the rectangular representation as well。

 The first element in the tuple corresponds to the number of nested lists contained in the original list or the number of rows in the rectangular representation。

 In this case，3。The second element corresponds to the size of each of the nested lists or the number of columns in the rectangular array 0。

 The convention is to label this axis 0， and this axis 1， as follows。

We can also use the attribute size to get the size of the array。 We see there are three rows。

 and three columns。Multiplying the number of columns and rows together。

 We get the total number of elements。 in this case，9。

Check out the labs for arrays of different shapes and other attributes。



![](img/c1cad779d7c3a68b87a91e85045b6b10_7.png)

We can use rectangular brackets to access the different elements of the array。

 The following image demonstrates the relationship between the indexing conventions for the lists。

 like representation。 The index in the first bracket corresponds to the different nested list。

 Each a different color。 The second bracket corresponds to the index of a particular element within the nested list。



![](img/c1cad779d7c3a68b87a91e85045b6b10_9.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_10.png)

Using the rectangular representation， the first index corresponds to the row index。

 The second index corresponds to the column index。

![](img/c1cad779d7c3a68b87a91e85045b6b10_12.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_13.png)

We could also use a single bracket to access the elements as follows。



![](img/c1cad779d7c3a68b87a91e85045b6b10_15.png)

Consider the following syntax。 This index corresponds to the second row， and this index。

 the third column。 The value is 23。

![](img/c1cad779d7c3a68b87a91e85045b6b10_17.png)

Consider this example。 This index corresponds to the first row。

 and the second index corresponds to the first column and a value of 11。



![](img/c1cad779d7c3a68b87a91e85045b6b10_19.png)

We can also use slicing in nuy arrays。 The first index corresponds to the first row。

 The second index accesses the first two columns。

![](img/c1cad779d7c3a68b87a91e85045b6b10_21.png)

Consider this example， the first index corresponds。 The first two rows。

 The second index accesses the last column。

![](img/c1cad779d7c3a68b87a91e85045b6b10_23.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_24.png)

We can also add arrays。 The process is identical to matrix addition。 Consider the matrix X。

 Each element is colored differently。 Consider the matrix Y。 Similarlyly。

 each element is colored differently。 We can add the matrices。😊。



![](img/c1cad779d7c3a68b87a91e85045b6b10_26.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_27.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_28.png)

This corresponds to adding the elements in the same position。 I。e。

 adding elements contained in the same color boxes together。

 The result is of new matrix that is the same size as matrix Y or X。

 Each element in this new matrix is the sum of the corresponding elements in X and Y to add to arrays in nump pi。

 we define the array in this case。 X。 Then we define the second array。 Y。 We add the arrays。

 The result is identical to matrix addition。 Multiplying in nupy array by a scalar is identical to multiplying a matrix by a scalar。

😊。

![](img/c1cad779d7c3a68b87a91e85045b6b10_30.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_31.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_32.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_33.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_34.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_35.png)

Consider the matrix Y。 If we multiply the matrix by the scalar2。

 we simply multiply every element in the matrix by 2。

 The result is a new matrix of the same size where each element is multiplied by two。

 Consider the array Y。 We first define the array。 We multiply the array by a scalar as follows and assign it to the variable Z。

 The result is a new array where each element is multiplied by two。

 Multiplication of two arrays corresponds to an element Y product or hadamamad product。

 Consider array X and array Y。 hadammard product corresponds to multiplying each of the elements in the same position。

 I。e。 multiplying elements contained in the same color boxes together。😊。



![](img/c1cad779d7c3a68b87a91e85045b6b10_37.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_38.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_39.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_40.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_41.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_42.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_43.png)

The result is a new matrix that is the same size as matrix Y or X。

 Each element in this new matrix is the product of the corresponding elements in X and Y。

 Consider the array X and Y。 We can find the products of two arrays X and Y in one line and assign it to the variable Z as follows。

 The result is identical to hadmar product。😊。

![](img/c1cad779d7c3a68b87a91e85045b6b10_45.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_46.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_47.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_48.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_49.png)

We can also perform matrix multiplication with nuy arrays。

 Matrix multiplication is a little more complex， but let's provide a basic overview。



![](img/c1cad779d7c3a68b87a91e85045b6b10_51.png)

Consider the matrix A， where each row is a different color。 Also， consider the matrix B。

 where each column is a different color in linear algebra before we multiply matrix A by matrix B。

 we must make sure that the number of columns in matrix A in this case。

3 is equal to the number of rows in matrix B In this case。

3 for matrix multiplication to obtain the Ieth row and jaeth column of the new matrix。

 we take the dot product of the Ih row of a with the jaeth columns of B。😊。



![](img/c1cad779d7c3a68b87a91e85045b6b10_53.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_54.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_55.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_56.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_57.png)

For the first column， first row， we take the dot product of the first row of a with the first column of B as follows。

 The result is 0。

![](img/c1cad779d7c3a68b87a91e85045b6b10_59.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_60.png)

For the first row and the second column of the new matrix。

 we take the dot product of the first row of the matrix A。 But this time。

 we use the second column of matrix B。 The result is 2 for the second row and the first column of the new matrix。

 we take the dot product of the second row of the matrix A with the first column of matrix B。

 The result is 0。 Finally， for the second row and the second column of the new matrix。

 we take the dot product of the second row of the matrix A with the second column of matrix B。

 The result is 2。😊。

![](img/c1cad779d7c3a68b87a91e85045b6b10_62.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_63.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_64.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_65.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_66.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_67.png)

![](img/c1cad779d7c3a68b87a91e85045b6b10_68.png)

In Ny， we can define the numpy arrays A and B。 We can perform matrix multiplication and assign it to array C。

 The result is the array C， It corresponds to the matrix multiplication of array， A and B。

There is a lot more you can do with it in Nmy。 Check out Nmy dot org。 Thanks for watching this video。

😊。

![](img/c1cad779d7c3a68b87a91e85045b6b10_70.png)