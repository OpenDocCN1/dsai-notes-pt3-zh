# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p21 P21 Big data and scalability _21_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p21-

Okay， so welcome， everybody to。The。Class on advanced machine learning or something like that。

 So this what we're going to be covering today。 Actually， could somebody please close the door。

It's going to be。A little bit more advanced。So this is。Advanced at the point of where。

You'll actually see a couple of results that we got in the last year this year。嗯。

But the ideas behind it are sufficiently simple that you can just use them regardless and you'll actually do pretty well by using those ideas。

啱。So the first thing to look at is。Basically， when you want to build a large system。

How you actually write multiqure code。Okay。Let me ask a first quick question。

 who's written multicor code so far？Okay。Well， that's， I think maybe 15% of the audience。Okay。

Who's used MAlaap before？Okay okay， so that means you have written multicorre code。

Except that you probably didn't notice it。So。First of all。

 I guess nobody should be surprised that there are more than one core in your laptop。

 who knows how many cores your laptop has？Okay， if you don't， you should find out。Now。

Who knows how fast your laptop is？Okay， again， you should try to find out so here's。

Here's why those things matter。If you write code。And inevitably。

 your code will be slow because all the code is， it's never fast enough for what you want to do。

Let's say you're working for a lips deadline line or IL， Lo or whatever， then you have two options。

Either you pretty much get all the experimental settings and everything right straight out of the box。

 which is not going to happen， right？Or you need to iterate。Now if your coat takes a day to run。

Then you can basically make changes maybe two， three times a day。

 assuming that you have two or three computers， right？But that may not be enough， right。

 because then you make a small change， you spend an hour on that， you start the code again。

 and then maybe you can watch TV for a day or agonize over the fact that your code isn't running or that it's not working。

It's another way of multitasking。Okay。So。Yeah， so basically。

reasona why you want to write multicore code is because by now the speed on a per corere basis isn't actually increasing that much anymore。

 it's going up by 10 15% per year。But the core count is still increasing。So for instance， by now。

 for I think $4，000 apiece， Intel will happily sell you an 18 core processor。Which， as it so happens。

 has well 36 hyperths。So I guess everybody knows the difference between hypoths and cores， right？

Basically hyperths are just like fake cores and for all practical purposes you can treat them like one。

 but they don't scale perfectly so if you're running scaling experiments and you increase the number of threads and so on。

 then at some point your code will probably top out at you know if I have this fancy Intel 18 core processor at about 18 threads or maybe 20 only if my code is really inefficient well I need a lot more so if you want to know more details you should read up on an antitic and other sites which explains this in a lot more detail okay。

So hyperpost is good， but you don't really have real core there， okay。

The thing why MALb is actually using multicore is because if you're doing any linear algebra operations。

So like， you know， I define some matrix A， I define some matrix B。

 and then I have something of the form。 you know， C equals a times B。

 The Matlet will not just use a single core。 It'll actually go and take。

Each of those matrices block them neatly together and they do them multiplications。And you know。

 write them over here as appropriate。And there's highly optimized code for doing this。Okay。

So the morale of that story is actually never ever write your own linear algebra code until you really know what you're doing。

You will know。What you're doing once you start thinking about the details of this， right？

So don't think about writing on algebra code， use either MATLb。

Which is just fine following the algebra or octave， which is fine if you compile it right。

 otherwise it won't be， or then you can use something like glass。And a pack。

And this is neatly hidden， for instance， in C++ in a library called Eigen。

Stroly recommend you to look at that， okay。So that's all fine if you're doing， let's say。

 spectral method or if you're doing PCA or other things， then yeah， MATL will do。If you don't。

 the mathle won't do。And so you need to think a little bit about how on earth am I actually going to write multiportre code？

And so one of the key issues with that kind of code is that， well， if it runs on multiple cores。

Please don't sit there otherwise you gets un pluglugged。 There's a seat just right behind you。

Thank you。嗯。And see to there。So then you need to address the issue of， well， know， if I'm doing this。

 how will the various processes actually talk to each other and usually the purpose of all of this nice algorithm these algorithms is to estimate some numbers。

 how do I actually jointly update a number， right？So let's look at a very。

 very simple case first because this is sort of kind of prototypical for what we're going to do。

The simple task is。I have a bunch of numbers， x1 up to。Exm。And I want to compute their average。

And I want to map this into one over M sum over I going from1 to M X I。Okay。So。

How would I solve this imperil？Was multicore， how would I do this？So I have maybe a million numbers。

 actually make it a billion because for a million it's almost not worth bothering。

How would I do this？Its been the sound。Exactly， perfect。 That's exactly the right answer。 So take。

欢迎三三。Preak it into， let's say， I have 16 cores and each core gets116th of the data。You have。

Compute partial sums there。Then in the end， you hit that barrier。

 most barrier is basically wait until all the cores are done， and then sum everything up。

So what we've just seen is actually two important parts in that code， namely parallel execution。

 which runs independently， and then at some point a barrier at which basically all the traits have to hit and then you just。

Can he happily sum everything up， okay。C++ by now actually provides very nice primitives for that。

 also look at Intel trading building blocks， so Intel TBB。

But C plus plus 11 also has a whole bunch of nice features in there。Also OMP。

Don't bother with P threads until you really know what you're doing， it's very painful。Okay。

So basically what was just described， namely the will compute partial sums and then add everything up。

 then you know basically go and update this and then write it to disk so this works very nicely for instance all the data fits nicely into memory or if I can you know easily proportion things to individual course。

If it doesn't， in other words， if I want to have something that's asynchronous。Then what could I do？

Well， so imagine I give you all some。Task to do。 Let's say some， you know。

 programming assignment or whatever。And because you have more or less sleep or because youre a more or less proficient programmer。

 it will take you more or less time to actually finish this task。

So now if I say well everybody has to wait until the last person is done。

 there will be a lot of people very unhappy， namely， well。

 you know those who are really quick will just sit there and twist their thumbs or you know play with your game so that's not good So instead what you actually want to do is you want to have asynchronous。

