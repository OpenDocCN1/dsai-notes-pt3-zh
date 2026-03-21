# 【EDUCBA】数据分析高级Python：构建与优化-｜-Advanced-Python-for-Data-Analysis：-Build---Optimize-p34-05_02_02_列表大小--BV1nmcKzBEU3_p34-

When I have this list， what I'm going to do is I'm going to store in a variable。

 Let me see a size of list， size of list and size of list is a variable。



![](img/79b39d43f9db93d45f816ae94aaf856c_1.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_2.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_3.png)

And I'm going to get the size by using the get size of function if you remember the get size of function from the Ss module I have called a size and I'm going to use that function now and Im going to say size off and I'm going to pass the LSD right？

😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_5.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_6.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_7.png)

Okay， let me just size of list。

![](img/79b39d43f9db93d45f816ae94aaf856c_9.png)

Soll print。Size of listers。And I can say， comma。

![](img/79b39d43f9db93d45f816ae94aaf856c_11.png)

Size of list。And there we are。So size of list is 88。

Now comes a question is this the total size of the list， is this the total size of the list。

 the size of the list of course of just three elements is 88 by its okay that's fair enough but is this the size of the list or is this the size of these three elements along with the list or is there more to a list let's understand let's first take an empty list let me call it as an empty list empty LSD and an empty list what is the size of an empty list let's have a look so I'm going to say size of empty list。

😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_13.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_14.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_15.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_16.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_17.png)

Is equal to size of， and then I can。Use the list。 I can pass it into the， and then I can， of course。

 print up the size of empty list。

![](img/79b39d43f9db93d45f816ae94aaf856c_19.png)

Right so the size of the empty list itself without any of these elements is 64。

 which means each each element inside this list takes how much 88 minus-64 that is that is we have 24 24 dividete by 3 that is 8 bytes each so 64 bytes is for an empty list 8 bytes each4。

😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_21.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_22.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_23.png)

Each element in this list，8 bys each for each element in this list， right now if I dive further。

 if I ask you further， what are these elements， What are these elements。

 Are they elements directly or are they objects or are they references to an object。

 if you remember in Python， none of these are elements itself， None of them are values itself。

 they are references to objects， right， how do I come to know that， if I print the type of of。



![](img/79b39d43f9db93d45f816ae94aaf856c_25.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_26.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_27.png)

LST of0 that is the first element if I put in the type of that it says class in teacher which means this is a reference to an object of type class in teacher so that means the size which we have got here is an empty list size plus another 24 bytes those that 24 bytes does not belong to these exact element values they actually belong to。

😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_29.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_30.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_31.png)

They actually belong to。Not just element values， but they belong to the references to an object。

 So that means the size of each of these elements。

![](img/79b39d43f9db93d45f816ae94aaf856c_33.png)

Will be is is it added the size of this is just reference so the list is basically when I say size of list。

 this is just in the memory space it is going to create a list。😊。



![](img/79b39d43f9db93d45f816ae94aaf856c_35.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_36.png)

which is going to have some overhead data of 64 bytes along with as many number of elements then along the corresponding to those number of elements they will be number of references those references are stored in 64 bytes sorry in 24 bytes right for each element8 bytes is taken to store a reference but those reference are nothing but pointing to another it is a completely different those references are finally pointing to pointing to。



![](img/79b39d43f9db93d45f816ae94aaf856c_38.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_39.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_40.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_41.png)

Element of type in teacher， right， So that means each of the elements in this list finally have more。



![](img/79b39d43f9db93d45f816ae94aaf856c_43.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_44.png)

More size。 that means if I would say size of。LST of0 size of LST of 0。

 this will now give me the actual size of each of the elements more than the reference size okay where there so the size of each element is what 28 so if I say total size total size when you define a list total size when you define a list will be first of all。



![](img/79b39d43f9db93d45f816ae94aaf856c_46.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_47.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_48.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_49.png)

The size of list， as we just saw over here， the size of list， but also along with that。

 the size of each elements plus。

![](img/79b39d43f9db93d45f816ae94aaf856c_51.png)

So maybe just before this， I can just you know， I can just keep this aside and I can first say。

 I can let me just define size of each element。😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_53.png)

Inlist right each element， let me just put that up in of each element and that can be size of LST of 0。

 right？

![](img/79b39d43f9db93d45f816ae94aaf856c_55.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_56.png)

LSD of0， and that's size of each element。 Now if you want to print it， of course。

 you can have size of each element being printed， that's 28。 we already we saw that。

 but total size is going to be that size， which is going to be equal to the size of。



![](img/79b39d43f9db93d45f816ae94aaf856c_58.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_59.png)

List。Plus。😡，Plus。The length of Le of， I can say。

![](img/79b39d43f9db93d45f816ae94aaf856c_61.png)

Of each the length of the total number of， you know， total number of elements in the list。

 I can get that with La of LSD， and then I multiply it with size of each element right size of each element。

 and this would be the total size。 So if I print the total size， this is going to be total size。



![](img/79b39d43f9db93d45f816ae94aaf856c_63.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_64.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_65.png)

So you can have a look for a list of three elements， the total size is 172。



![](img/79b39d43f9db93d45f816ae94aaf856c_67.png)

Wow so that's the size of or the memory consumption in the list the memory consumed in the list is actually the total size is the list size of the entire list plus the size of each element because the size of the list only consists of references of objects whereas each object has its own size multiplied by the number of objects in the list so total size will be 172 that's the total memory consumed by a list now let's go on to figure out what will be the memory consumed in an ND area right？

😊。

![](img/79b39d43f9db93d45f816ae94aaf856c_69.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_70.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_71.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_72.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_73.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_74.png)

![](img/79b39d43f9db93d45f816ae94aaf856c_75.png)