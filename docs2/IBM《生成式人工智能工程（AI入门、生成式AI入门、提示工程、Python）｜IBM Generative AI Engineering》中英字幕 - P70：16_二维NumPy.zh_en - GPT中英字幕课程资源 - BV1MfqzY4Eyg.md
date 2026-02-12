# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P70：16_二维NumPy.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

We can create numpy arrays with more than one dimension。 This section will focus only on 2 D arrays。

 but you can use numpy to build arrays of much higher dimensions。



![](img/6ac597160bcfcb93f958aa869dac9b94_1.png)

In this video， we will cover the basics and array creation in 2D， indexing and slicing in 2D。

 and basic operations in 2D。Consider the list A。 The list contains three nested lists。

 each of equal size。 Each list is color coatd for simplicity。 We can cast the list to a numpy array。

 as follows。😊，It is helpful to visualize the numpy array as a rectangular array。

 Each nested list corresponds to a different row of the matrix。



![](img/6ac597160bcfcb93f958aa869dac9b94_3.png)

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

 and three columns。Multiply the number of columns and rows together。

 we get the total number of elements， in this case，9。

Check out the labs for arrays of different shapes and other attributes。



![](img/6ac597160bcfcb93f958aa869dac9b94_5.png)

We can use rectangular brackets to access the different elements of the array。

 The following image demonstrates the relationship between the indexing conventions for the lists。

 like representation。 The index in the first bracket corresponds to the different nested list。

 each a different color。 The second bracket corresponds to the index of a particular element within the nested list。



![](img/6ac597160bcfcb93f958aa869dac9b94_7.png)

Using the rectangular representation， the first index corresponds to the row index。

 the second index corresponds to the column index。

![](img/6ac597160bcfcb93f958aa869dac9b94_9.png)

We could also use a single bracket to access the elements as follows。



![](img/6ac597160bcfcb93f958aa869dac9b94_11.png)

Consider the following syntax。 This index corresponds to the second row， and this index。

 the third column。 The value is 23。

![](img/6ac597160bcfcb93f958aa869dac9b94_13.png)

Consider this example。 This index corresponds to the first row。

 and the second index corresponds to the first column and a value of 11。



![](img/6ac597160bcfcb93f958aa869dac9b94_15.png)

We can also use slicing in nuy arrays。 The first index corresponds to the first row。

 The second index accesses the first two columns。

![](img/6ac597160bcfcb93f958aa869dac9b94_17.png)

Consider this example， the first index corresponds。 the first two rows。

 The second index accesses the last column。

![](img/6ac597160bcfcb93f958aa869dac9b94_19.png)

We can also add arrays。 The process is identical to matrix addition。 Consider the matrix X。

 Each element is colored differently。 Consider the matrix Y。 Similarly。

 each element is colored differently。 We can add the matrices。😊。



![](img/6ac597160bcfcb93f958aa869dac9b94_21.png)

This corresponds to adding the elements in the same position。 I。e。

 adding elements contained in the same color boxes together。

 The result is of new matrix that is the same size as matrix Y or X。

 Each element in this new matrix is the sum of the corresponding elements in X and Y to add to arrays in nump pi。

 we define the array in this case。 X。 Then we define the second array。 Y。 We add the arrays。

 The result is identical to matrix addition。 Multiplying a nupy array by a scalar is identical to multiplying a matrix by a scalar。

😊。

![](img/6ac597160bcfcb93f958aa869dac9b94_23.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_24.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_25.png)

Consider the matrix Y。 If we multiply the matrix by the scalar2。

 we simply multiply every element in the matrix by 2。

 The result is a new matrix of the same size where each element is multiplied by two。

 Consider the array Y。 We first define the array。 We multiply the array by a scalar as follows and assign it to the variable。

 Z。 The result is a new array where each element is multiplied by two。

 Multiplication of two arrays corresponds to an element Y product or hadamad product。

 Consider array X and array Y。 hadammard product corresponds to multiplying each of the elements in the same position。

 I。e multiplying elements contained in the same color boxes together。😊。



![](img/6ac597160bcfcb93f958aa869dac9b94_27.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_28.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_29.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_30.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_31.png)

The result is a new matrix that is the same size as matrix Y or X。

 Each element in this new matrix is the product of the corresponding elements in X and Y。

 Consider the array X and Y。 We can find the products of two arrays X and Y in one line and assign it to the variable Z as follows。

 The result is identical to hadammar product。😊。

![](img/6ac597160bcfcb93f958aa869dac9b94_33.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_34.png)

We can also perform matrix multiplication with numpy arrays。

 Matrix multiplication is a little more complex， but let's provide a basic overview。

Consider the matrix A， where each row is a different color。 Also， consider the matrix B。

 where each column is a different color in linear algebra before we multiply matrix A by matrix B。

 we must make sure that the number of columns in matrix A in this case。

3 it is equal to the number of rows in matrix B In this case。

3 for matrix multiplication to obtain the Ieth row and Jeth column of the new matrix。

 we take the dot product of the Ih row of a with the jaeth columns of B。😊。



![](img/6ac597160bcfcb93f958aa869dac9b94_36.png)

![](img/6ac597160bcfcb93f958aa869dac9b94_37.png)

For the first column， first row， we take the dot product of the first row of a with the first column of B as follows。

 The result is 0。For the first row and the second column of the new matrix。

 we take the dot product of the first row of the matrix A。 But this time。

 we use the second column of matrix B。 The result is 2 for the second row and the first column of the new matrix。

 we take the dot product of the second row of the matrix A with the first column of matrix B。

 The result is 0。 Finally， for the second row and the second column of the new matrix。

 we take the dot product of the second row of the matrix A with the second column of matrix B。

 The result is 2。😊。

![](img/6ac597160bcfcb93f958aa869dac9b94_39.png)

In Nmpy， we can define the numpy arrays A and B。 We can perform matrix multiplication and assign it to array C。

 The result is the array C， It corresponds to the matrix multiplication of array， A and B。

There is a lot more you can do with it in Nmy。 Check out Nmy dot org。 Thanks for watching this video。

😊。

![](img/6ac597160bcfcb93f958aa869dac9b94_41.png)