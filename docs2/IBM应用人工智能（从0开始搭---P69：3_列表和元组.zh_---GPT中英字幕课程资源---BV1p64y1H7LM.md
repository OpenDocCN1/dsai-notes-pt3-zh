# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P69：3_列表和元组.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

In this video， we will cover lists and topples。These are called compound data types and are one of the key types of data structures in Python。

Tuples。Tuples are an ordered sequence。

![](img/a34c62f14205780e033595fc4fd1d8bc_1.png)

Here is a tuple ratings。Tuples are expressed as comma separated elements within parentheses。

These are values inside the parentheses。In Python， there are different types， strings， integer float。

 They can all be contained in a tuple， but the type of the variable is tuple。

 Each element of a tuple can be accessed via an index。

 The following table represents the relationship between the index and the elements in the tuple。

 The first element can be accessed by the name of the tuple followed by a square bracket with the index number。

 In this case，0。 We can access the second element as follows。 We can also access the last element。



![](img/a34c62f14205780e033595fc4fd1d8bc_3.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_4.png)

In Python， we can use negative index。 The relationship is as follows。

 The corresponding values are shown here。

![](img/a34c62f14205780e033595fc4fd1d8bc_6.png)

We can concatenate or combine tuples by adding them。 The result is the following。

 with the following index。

![](img/a34c62f14205780e033595fc4fd1d8bc_8.png)

If we would like multiple elements from a tuple， we could also slice tuples。 For example。

 if we want the first three elements， we use the following command。

 The last index is one larger than the index you want。 Similarlyly， if we want the last two elements。

 we use the following command。 Notice how the last index is one larger than the length of the tuple。



![](img/a34c62f14205780e033595fc4fd1d8bc_10.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_11.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_12.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_13.png)

We can use the land command to obtain the length of a tuple。



![](img/a34c62f14205780e033595fc4fd1d8bc_15.png)

As there are five elements， the result is5。

![](img/a34c62f14205780e033595fc4fd1d8bc_17.png)

Tuples are immutable， which means we can't change them to see why this is important。

 Let's see what happens when we set the variable ratings 1 to ratings。

 Let's use the image to provide a simplified explanation of what's going on。



![](img/a34c62f14205780e033595fc4fd1d8bc_19.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_20.png)

Each variable does not contain a tuple， but references the same immutable tuple object。

 See the objects and classes module for more about objects。



![](img/a34c62f14205780e033595fc4fd1d8bc_22.png)

Let's say we want to change the element at index 2， because tuples are immutable。 We can't。

 Therefore， ratings 1 will not be affected by a change in rating because the tuple is immutable。 I。e。

 We can't change it。

![](img/a34c62f14205780e033595fc4fd1d8bc_24.png)

We can assign a different tuple to the ratings variable。

 The variable ratings now references another tuple。



![](img/a34c62f14205780e033595fc4fd1d8bc_26.png)

As a consequence of immutability， if we would like to manipulate a tuple， we must create a new tuple。

 instead。For example， if we would like to sort a tuple， we use the function sorted。

 The input is the original tuple。 The output is a new sorted list For more on functions。

 see our video on functions。

![](img/a34c62f14205780e033595fc4fd1d8bc_28.png)

A tuple can contain other tuples， as well as other complex data types。 This is called nesting。

 We can access these elements using the standard indexing methods。

 If we select an index with a tuple， the same index convention applies as such。

 we can then access values in the tuple。

![](img/a34c62f14205780e033595fc4fd1d8bc_30.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_31.png)

For example， we could access the second element。 We can apply this indexing directly to the tuple variable N T。



![](img/a34c62f14205780e033595fc4fd1d8bc_33.png)

It is helpful to visualize this as a tree。

![](img/a34c62f14205780e033595fc4fd1d8bc_35.png)

We can visualize this nesting as a tree。 The tuple has the following indexes。

 If we consider indexes with other tuples， we see the tuple index 2 contains a tuple with two elements。

 We can access those two indexes。

![](img/a34c62f14205780e033595fc4fd1d8bc_37.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_38.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_39.png)

The same convention applies to index 3。 We can access the elements in those tus as well。

 We can continue the process。

![](img/a34c62f14205780e033595fc4fd1d8bc_41.png)

We can even access deeper levels of the tree by adding another square bracket。

 We can access different characters in the string or various elements in the second tuple contained in the first Ls are also a popular data structure in Python。

 Ls are also an ordered sequence。

![](img/a34c62f14205780e033595fc4fd1d8bc_43.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_44.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_45.png)

Here is a list， L。A list is represented with square brackets。In many respects， lists are like tuples。

 One key difference is they are mutable。 Ls can contain strings， Fs， integers。

 We can nest other lists。

![](img/a34c62f14205780e033595fc4fd1d8bc_47.png)

We also nest tuples and other data structures。 The same indexing conventions apply for nesting。

 like tuples， each element of a list can be accessed via an index。



![](img/a34c62f14205780e033595fc4fd1d8bc_49.png)

The following table represents the relationship between the index and the elements in the list。

The first element can be accessed by the name of the list followed by a square bracket with the index number。

 in this case，0。We can access the second element as follows。We can also access the last element。

In Python， we can use a negative index， the relationship is as follows。



![](img/a34c62f14205780e033595fc4fd1d8bc_51.png)

The corresponding indexes are as follows。

![](img/a34c62f14205780e033595fc4fd1d8bc_53.png)

We can also perform slicing in lists， for example， if we want the last two elements in this list。

 we use the following command。Notice how the last index is one larger than the length of the list。

 The index conventions for lists and tuples are identical。 Check the labs for more examples。



![](img/a34c62f14205780e033595fc4fd1d8bc_55.png)

We can concatenate or combine lists by adding them。 The result is the following。

 The new list has the following indices。

![](img/a34c62f14205780e033595fc4fd1d8bc_57.png)

Listists are mutable。 Therefore， we can change them。 For example。

 we apply the method extends by adding a dot followed by the name of the method， then parentheses。

The argument inside the parentheses is a new list that we are going to concatenate to the original list。

 In this case， instead of creating a new list， L 1。

 the original list L is modified by adding two new elements。



![](img/a34c62f14205780e033595fc4fd1d8bc_59.png)

To learn more about methods， check out our video on objects and classes。



![](img/a34c62f14205780e033595fc4fd1d8bc_61.png)

Another similar method is a pen。 If we apply a pen instead of extended。

 we add one element to the list。If we look at the index， there is only one more element。

 Index 3 contains the list we appended。

![](img/a34c62f14205780e033595fc4fd1d8bc_63.png)

Every time we apply a method， the list changes。If we apply extend。

 we add two new elements to the list。The list L is modified by adding two new elements。



![](img/a34c62f14205780e033595fc4fd1d8bc_65.png)

If we append the string A， we further change the list， adding the string A。As lists are mutable。

 we can change them。 For example， we can change the first element as follows。

 The list now becomes hard rock 101。2。We can delete an element of a list using the Dell command。

 We simply indicate the list item we would like to remove as an argument。 For example。

 if we would like to remove the first element， the result becomes 101。2。

 We can delete the second element。 This operation removes a second element of the list。



![](img/a34c62f14205780e033595fc4fd1d8bc_67.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_68.png)

We can convert a string to a list using split。 For example。

 the method split converts every group of characters separated by a space into an element of a list。

 We can use the split function to separate strings on a specific character known as a delimiter。

 We simply pass the delimiter， we would like to split on as an argument。 In this case， a comma。

 The result is a list， Each element corresponds to a set of characters that have been separated by a comma。

 When we set one variable。 B equal to A。 Both A and B are referencing the same list。

 Multi names referring to the same object is known as aliasing。😊。



![](img/a34c62f14205780e033595fc4fd1d8bc_70.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_71.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_72.png)

![](img/a34c62f14205780e033595fc4fd1d8bc_73.png)

We know from the list slide that the first element in B is set as hard rock。

 If we change the first element in a to banana， we get a side effect。 The value of B will change。

 as a consequence。A and B are referencing the same list； therefore， if we change A。

 list B also changes。If we check the first element of B after changing list A。

 we get banana instead of hard rock。

![](img/a34c62f14205780e033595fc4fd1d8bc_75.png)

You can clone listist A by using the following syntax。Variable A references one list。

 Vaable B references a new copy or clone of the original list。



![](img/a34c62f14205780e033595fc4fd1d8bc_77.png)

Now， if you change A， B will not change。

![](img/a34c62f14205780e033595fc4fd1d8bc_79.png)

We can get more info on list， Tus and many other objects in Python using the help command。

 simply pass in the list， Tuple or any other Python object。

See the labs for more things you can do with lists。



![](img/a34c62f14205780e033595fc4fd1d8bc_81.png)