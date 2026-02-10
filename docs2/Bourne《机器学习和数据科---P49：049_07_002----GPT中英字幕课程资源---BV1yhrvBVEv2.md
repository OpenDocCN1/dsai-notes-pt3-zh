# Bourne《机器学习和数据科学训练营｜Zero to Mastery Data Science and Machine Learning Bootcamp》 - P49：049_07_002 NumPy 简介.zh_en - GPT中英字幕课程资源 - BV1yhrvBVEv2

![](img/a651f60fdac4b2ee5aa56398ccd8db26_0.png)

Welcome back In this section， we're going to look at NmpyI。

 and now I'm very excited about this section because NmI is basically the backbone of all data science。

 machine learning and numerical computing and Python。 and that's actually what Nmy stands for。

 It stands for numerical Python。😊，And what is Numpy Well， in all of machine learning。

 no matter what kind of data that you're working with。

 now this could be a data frame like we saw in the previous section on pandas。

 Numpy is going to form the foundation of turning your data into a series of numbers。

 And then what a machine learning algorithm will do is work out the patternss in those numbers。

So if we refer back to our machine learning modeling framework。

 we've got step one as problem definition， step two is data， evaluation， features。

 modeling and experiments。Then if we have a look at what tools we can use。In this section。

 we're going to be focused on NumpI。 Numpy comes into the data analysis section。 However。

 as you'll see in the future and what we just referenced before， is that machine learning。

 although it's referred to as modelling。Is essentially taking data， turning it into numbers。

 and in this case with nuumpy， usually the form of a nuumpy array which we'll have plenty of experience with after this section。

 and then finding patterns in those numbers。Almost across this entire pipeline。

 nuumpy will come into play。Now， why nuumpy or the main reason we use nuy instead of pure Python。

 I mean， you can do numerical calculations in Python。

 but usually if we want to do large scale numerical calculations， we refer to。Numpy。

 it's because it's fast。 And now the reason why it's fast is because behind the scenes。

 there's optimizations written in C code。 The beautiful thing about the Numpy package is that you can use these C code optimizations。

Using pure Python that means you don't have to know C to be able to use nuumppyy and Python is a bit easier to write than pure C。

 so that's the advantage of using Numpy Now it gets these optimizations in speed through a process called vectorization via a term nupyy users called broadcasting。

 which is essentially just avoiding writing loops when you're writing calculations because if you're writing loops to make calculations such as in Python to calculate over a list。

 that can form some eventual slowdowns if you have a list， say of millions of different numbers。

 which becomes common practice when we're working on machine learning projects。

 and as we mentioned before， Numppyy is the backbone of other python scientific packages。

 Numpy actually forms the basis of the pandas package。

So what are we going to cover in this section Well， of course。

 we're always going to be focused on the most useful functions。

 the ones that you can start using straight away We'll have a look at different Ny data types and attributes of those data types。

 Now the main one is an ND array， but we'll have a look at that in another video。

 We'll look at how to create arrays arrays you can think of as a list of numbers。

 We'll have a look at how to view arrays and matrices Now a mat or a matrices you can imagine as a combination of different arrays We'll then look at how to manipulate and compare arrays We'll then finish out with sorting arrays which is sorting out different list of numbers。

 and then some practical use cases of where arrays get used or where nuy can be used to turn data into list of numbers。

So where can you get help if you get stuck？ Well， the steps you want to try and follow is to follow along with the code。

 So as we're going through the video， as we're working through our Jupiter notebook。

 through the introduction to Ny lessons。You want to follow along as best you can now if you can't keep pace or if I'm going too fast。

 that's alright， feel free to stop it， go back， practice something on your own。

 but you should be practicing writing the code and running it as much as possible。So that's step 2。

 try it for yourself， try to run the code。 Remember the saying if in doubt， run the code。

 If you get stuck on a certain function or a certain thing that we've covered。

 you can try to search for it here you'll probably come across stack overflow or the official nuy documentation。

Then after that， once you've searched for it， if you find something on stack overflow or the nuie documentation。

 the important thing is to keep trying again。 enter the code that you find in the Jupyter notebook。

 practice running it。 if in doubt， run the code。 And then finally， if you're still star。

 don't forget， you can always ask for help。 There's no such thing as a stupid question。

 because if you have a question。 It's likely someone else has the same question。

 You can ask on stack overflow or in any other resource you can find。All right， with that being said。

 that's an introduction of NI， it's the foundation。

 it's the backbone of other data science and scientific packages， but let's get in and code。

 let's see what it's all about。😊。

![](img/a651f60fdac4b2ee5aa56398ccd8db26_2.png)