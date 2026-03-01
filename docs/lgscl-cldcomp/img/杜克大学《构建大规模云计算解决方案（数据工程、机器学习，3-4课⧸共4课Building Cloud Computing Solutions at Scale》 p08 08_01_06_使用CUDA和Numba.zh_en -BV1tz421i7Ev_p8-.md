# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p08 08_01_06_使用CUDA和Numba.zh_en -BV1tz421i7Ev_p8-

![](img/781afb037732f8020224f42da4898056_0.png)

So let's get into some facts here and actually play around with a real example to use a GPU or a just in time compiler。

 you can use a library called NumbA so let's go ahead and take a look at what that is it's a way of programming GPU or just in time compiler lots of different techniques you can use with NumbA and you can see all the different examples of this so what we're going to do is we're going to go into coab notebook。

 I'm going to use coab Pro and I'm going to turn on a GPU hardware accelerator。

And a couple things to point out here is that you'll want to just double check after you install a N that the doSO output appears here。

 so you could recreate exactly what I'm doing without using N， but in this example。

 I'm going to go ahead and open up this coLab notebook and get started。Okay。

 so I've got this checked in。I'm gonna go ahead and click on this link open in coab and a couple of things that I'll do here is first step I'll check the runtime this is really important you also see I'm using the pro version so I get a fancier GPU let's go ahead and select that okay great that's good runtime standardy why don't we make it HiRAM as well okay now that this is set up I can just click connect and it'll establish a connection to a Nvidia GPU that I have access to and you can see here I also have something like 25 gigs of Ram so first step I'll install number and then I'll double check here that this SO driver is available for me。



![](img/781afb037732f8020224f42da4898056_2.png)

![](img/781afb037732f8020224f42da4898056_3.png)

And this will be really the shared library that I'll need to do coUDa coding later and coUDa coding really is a way of doing GPU programming for NVIDdia。

 so we'll give this a second here， it's installing number。

And then looks like NMbo is actually already installed on this machine。

 and then I also am verifying that I do have two versions of Kuda I have version 10。

0 and I also have version 10。1 So this will take just a second here the next thing that I'll do is I'll just import some libraries So I'll import nu I'll use some specific imports like the just in time compiler。

 the Kuda library some data types here and once I do that。

 the first thing that I'll play around with is a Manelbrot and a Mandelbrot is really a visualization that that is very taxing to compute and so first what I'm going to do is I'm going to just do it on the CPU。

 So if I go through here and I say some Manlebrot code here I then go through and I create a fractal。

Let's go ahead and run that and then let's go ahead and create it。 Now， when we run this。

 you can see it takes quite a while， right it's going to take a few seconds。 In fact， it takes 4。

37 seconds to calculate this really fancy image。 So that's why a lot of people use this as a benchmarking tool。

 So so next up can we do better than that。 Well， yes。

 let's go ahead and use the number version which is a version that uses a justin time compiler。

 So what this does is it takes our Python code and it turns it into machine code。

 So it can potentially run much， much faster because it's going to go directly to instruction for a CPU So let's go through here and run the just in time compiler I'll put at Jt there。

Next up， I'll go through here and I'll run this version。

And you can see here it it's almost instantaneous right it's basically 39 0。

39 seconds to actually generate this version Okay， can we also try the GPU out yeah let's go ahead and do that let's use the coUa GPU here and what I'll do is I'll say kuda。

 Jit and I tee this up here and then what I do is I say at couda。

giit and I put in these different data types here and this just it allows me to use these data types on the GPU and now I go ahead and run this version and in fact look how much faster this is。

 you can see that it's 005 seconds where the machine level code even at that assembly level of the CPU it's actually much much faster so really a GPU is a great way to to speed up code that is highly parallellyzable so what else can we do you also can just directly get into。

The coa library and start playing around with code Now to do this。

 you have to take your code and move it specifically into the GPU vectorize it。

 so turn it into a form where it can be highly parallel and then run the code So here's an example that's kind of contrived but what I do is I take a data frame in pandas here and then I convert it to a form that the number library can utilize and then I return it as an array and then I vectorize it right here so this allows it to run on the GPU and then what I do is I take those arrays and I copy those to the GPU that's really one of the things that you have to specifically do when you do GPU programming is make sure you copy from your current memory to the GPU memory then I go through and I do the calculation on the GPU so if it's something that would take let's say four days。

This is where you would really take advantage， but there's a cost to moving that calculation to the GPU Next up you can see that I went through and I ran a vectorized function on a GPU so tons of different fun things you can do with Kuta and with a GPU and fortunately with something like coabB Pro you have effectively a supercomputer right at your fingertips。



![](img/781afb037732f8020224f42da4898056_5.png)

![](img/781afb037732f8020224f42da4898056_6.png)

![](img/781afb037732f8020224f42da4898056_7.png)