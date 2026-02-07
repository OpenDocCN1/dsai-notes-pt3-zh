# mrdbourke《一天学会pytorch深度学习｜Learn PyTorch for deep learning in a day Literally》中英 - P25：28. PyTorch and NumPy.zh_en - GPT中英字幕课程资源 - BV1kx4y1r79d

Back， How'd you go。 Did you give the challenge go， I finished the last video with issuing the challenge to index on x to return 9 and index on x to return 36。

9。 Now here's what I came up with。 Again， there's a few different wayss that you could approach both of these。

 but this is just what I've found。 So because X is13，3 of size。 Well that's his dimensions。😊。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_1.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_2.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_3.png)

If we want to select 9， we need0， which is this first outer bracket to get all of these elements。

 and then we need two to select this bottom one here。

 and then we need this final two to select the second dimension of this bottom one here。

 and then for 3，6，9， we need all of the elements in the first dimension。

 all of the in the zeroth dimension， all of the elements in the first dimension， and then we get two。

 which is。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_5.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_6.png)

This 3，6，9 set up here。 So that's how I would practice indexing。

 Start with whatever shape tensor you like， create something like this。 and then see how you can。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_8.png)

Write different indexing to select whatever number you pick。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_10.png)

So now let's move on to the next part。Which is pietorrch。Tenss and numpy。

So nuumpy is a popular scientific， very popular Pytch actually requires nuumpy when you install Pytch popular scientific。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_12.png)

Python。numericalmer computing library， that's a bit of a mouthful。And because of this。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_14.png)

Pie torch。As functionality to interact with it。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_16.png)

So quite often。You might start off with， let's change this into markdown。

 you might start off with your data because it's numerical format。

 you might start off with data in Numpy。Numpie array。

Want in p torch Tensor because your data might be represented by nuumppy because it started in nuumppy but say you want to do some deep learning on it and you want to leverage piy torches。

 deep learning capabilities Well you might want to change your data from nupyy to a pi torch Tensor and Py torch has a method to do this which is torch。

From Numpy， which will take in an ND array which is NumpI's main data type and change it into a torch tensor we'll see this in a second and then if you want to go from P torch Tensor to Ny because you want to use some sort of nuumpy method well the method to do this is torch dot Tensor and you can call dot nuumpy on it。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_18.png)

But this is all just talking about in words。 Let's see it in action。 So nuy array to tensor。

 Let's try this out first。 So we'll import torch so we can run this cell on its own and then import。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_20.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_21.png)

Numpy as N， the common naming convention for Numpy， we're going to create an array in Numpy。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_23.png)

And we're going to just put one to eight。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_25.png)

A range。 and then we're going to go tensor。Equals torch from Numpy。

Because we want to go from Numpy array to a torch tensor。

 so we use from Numpy and then we pass in array， and then we have array and tensor。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_27.png)

Wonderful， so there's our Numpy array and our torch tensor with the same data。

 but what you might notice here is that the D type for the tensor is torch dot floatat 64。

 Now why is this， It's because Numpy's default data type。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_29.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_30.png)

D time。Is floatat 64， whereas Tensor， What have we discussed before。

 What's Pi Torch's default data type。Float 64 Well that's not Pi Torch's default data type if we were to create torch a range 1。

0 to 8。0。😊，By default， Pto is going to create it in。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_32.png)

Float 32。 So just be aware of that。 if you are going from nupy to pi torch。

 the default nupy data type is floatat 64。 And Pytorrch reflects that data type When you use the from nupy method。

 I wonder if there's a D type。 Can we go D type equals torch dot float 32。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_34.png)

Takes no keyword， okay？

![](img/3d79ac863a4bbc04d06057c6f6d2006b_36.png)

But how could we change the data type here or we could go type torch Float 32？



![](img/3d79ac863a4bbc04d06057c6f6d2006b_38.png)

Yeah， that will give us a tensity type of floatat 32 instead of floatat 64 beautiful。

 but I'll just keep that there so you know。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_40.png)

Warning when converting。From Namai。Pie to watchch。Pytorch reflects。Numps default data type。Of Fat 64。

 unless specified。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_42.png)

Otherwise， because what have we discussed？

![](img/3d79ac863a4bbc04d06057c6f6d2006b_44.png)

When you're trying to perform certain calculations， you might run into a data type issue。

 so you might need to convert the type from Flo 64 to Float 32。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_46.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_47.png)

Now。Let's see what happens， What do you think will happen if we change the array？



![](img/3d79ac863a4bbc04d06057c6f6d2006b_49.png)

We change the value of an array。Well let's find out。So change the value of array。 The question is。

 what will this do to。Ta。Because we've used the from nu P method。

 do you think if we change the array。The tensor will change。

So let's try this array equals array plus one。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_51.png)

So we're just adding one to every value in the array。Now。

 what is the array and the tens are going to look like？啊hu。So array。

 we only change the first value there or sorry， we change every value because we have  one to 7。

 Now it's 2，3，4，5，6，7，8。 We change the value from the array。

 It doesn't change the value of the tensor。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_53.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_54.png)

So that's just something to keep in mind。 If you use from nuy， we get a new tensor in memory here。

 So the original， the new tensor doesn't change if you change the original array。

 So now let's go from tensor to nuumpy。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_56.png)

If you wanted to go back to Numpy， Tensor to Numpy array， so we'll start with the tensor。

 we could use the one we have right now， but we're going to create another one but we'll create one of ones just for fun。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_58.png)

One rhymes with fern， nuy tensor equals。How do we go to Numpy？Well， we have tarch。tented。numpy。

 so we just simply call nuumpy on here。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_60.png)

And then we have Tensor and nuy tensor， What data type do you think the nuy tensor is going to have because we've returned it to Numpy？



![](img/3d79ac863a4bbc04d06057c6f6d2006b_62.png)

Py To's default data type is。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_64.png)

Float 32。 So if we change that to Numpy， what's going to be the D type of the Numpy tensor？



![](img/3d79ac863a4bbc04d06057c6f6d2006b_66.png)

Numbietenser。d type。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_68.png)

It reflects the original D type of what you set the tensor as So just keep that in mind if you're going between Pytorrch and nupyy default data type of nu is float 64。

 whereas the default data type of pytorrch is float 32 so that may cause some errors if you're doing different kinds of calculations Now what do you think is going to happen if we went from our tensor to an array if we change the tensor。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_70.png)

Change the tensor。What happens to？

![](img/3d79ac863a4bbc04d06057c6f6d2006b_72.png)

Numbie。T so。So we go tensa equals tensa plus one。And then we go nuie tensor。we'll get tenor as well。

So our tensor is now all twos because we added one to the ones， but our nuy tensor remains the same。

 remains unchanged， so this means they don't share memory。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_74.png)

![](img/3d79ac863a4bbc04d06057c6f6d2006b_75.png)

So that's how we go in between pie torch and nuumpy if you'd like to look up more I'd encourage you to go pietorrch and nuumpy。

So warm up nuumpy beginner， there's a fair few tutorials here on Pytorrch because Ny is so prevalent。



![](img/3d79ac863a4bbc04d06057c6f6d2006b_77.png)

They work pretty well together。 So have a look at that。 There's a lot going on there。

There's a few more links I'd encourage you to check out。

 but we've covered some of the main ones that you'll see in practice。With that being said。

 let's now jump into the next video where we're going to have a look at the concept of reproducibility。

 And if you'd like to look that up， I'd encourage you to search piy towards reproducibility and see what you can find。

 Otherwise， I'll see in the next video。😊。

![](img/3d79ac863a4bbc04d06057c6f6d2006b_79.png)