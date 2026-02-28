# 杜克大学｜机器学习运维｜DevOps⧸DataOps、Azure、MLFlow和抱脸｜MLOps ｜ Machine Learning Operations p09 16_01_03_微服务持续集成.zh_en -BV1yE421c7uA_p9-

![](img/9a040aeb1c848bab59e7b58fbcb31de1_0.png)

Let's take a look at how you could set up a continuous integration ecosystem for microservices really to start out with your project is the most important first step and this is a project structure that we'll go through in a second。

 but in general it's the ability to test to Li and to format or code every time the human。

 the developer that's you pushes the changes into a Gitbased repository。

 So this would be Git in this case I'm going to show you Github but the real key characteristics here are that there is a make file that can do all of these actions right this make file corresponds to the it corresponds to the format it corresponds to this test and I do those locally。

 but then I can also replicate that by having this robot up here。

 which is the build server that always is making my project high quality because it's checking for things like the L of the。

the formatting the code， the testing of the code and then later when I get into deployment to deploy the code so really this is a key concept。

 set up this local continuous integration environment so that your project is ready to go when you want to push that into production So next let's go ahead and take a look at how that would work in practice with a GiHub project。



![](img/9a040aeb1c848bab59e7b58fbcb31de1_2.png)

Let's take a look at a project structure that is really set up for you to do everything you need to do to do both continuous integration and then later continuous delivery。

 What are the key components First up in this repo Noagift continuous integration。

 It have a Github workflows section。 This is where the built system。 In this case。

 it will be Github actions， but it could be things like Jenkins or Aws code build or some other build system。

 It will go through and test my code and do exactly what I tell to do In this case。

 we can look at the commands by going to this main Don yamel file。

 And we can see that on every push or every change a human makes andll go through and it will spin up in a bountu virtual machine。

 It will use Python 38， and it will do these steps make install。

 make Li and make test and then later make format。 And this is a great structure I would recommend for all continuous integration projects is to have this kind of a structure set up now。

What we can do next here is take a look at the environment for the code itself and that would be the different sub componentsents of this project so we can see here that there is a readme file。

 always a good idea， I have a build system badge， I also have a really basic file here that adds two numbers。

 I also have a test file that was able to go through here and test our code。

And then I also have a requirements file which has versioned packages。

 And this is important so it's reproducible so that I know that the version I tested my Python project with will be reproducible for the build system。

 Finally， if we go ahead and we take a look at our make file itself。

 you can see that this structure is really a set of recipes right and make install and make test I make format and make Li。

 So that's the structure。 But how would I use this in the real world。

 Well we can take a cloud based development of armmin here， which is Github code spaces。

 and we can spin it up and take a look at it。😊，And from here。

 actually go through and exercise the components of the project and also see what happens if something fails and how it's easy to detect the failure because of the fact that we have this great scaffolding for our project。

Okay， so we're inside of this GitHub codespaces environment here and notice that I have a terminal and I have all of the code here on the left and notice there's a virtual environment that I created you can create your own by using the virtual environment command and then putting it in some location in my situation I actually edited my BshRC file here and I put in the source command directly into that BshRC file we cover that in another lesson and the B section about how to edit your BshRC。

 but for now I'm going to go through here and look at the structure again you see all these files here and I'm going to run make all。

And when I do make all we can take a look at this， what does it do it installs。

 it linkss it tests our code and what's great about all this is I get a great kind of feedback loop that says hey everything works now what happens if there's a problem in the code in this case this would be a great little bug is that if I assign a variable to itself。

 it doesn't necessarily break our code but it does cause a potential problem in the future and so in this case look we can see that oh there's two different problems we're assigning a variable to itself plus I never actually made this variable do anything。

I never assigned it。 and now if I change it， we can see that that variable is still got a warning problem。

 So the first one was an exception or an error where it would the code would not run。

 the other one is just a warning in either case， the Li was able to catch this bug。

 Now let's go ahead and push this change。Okay， great now I'll go ahead and do a get push。

And we'll push those changes perfect。 And now if I go back here and I say open repository or go to repository。

 we can watch this build system in action and this is the benefit of a continuous integration system is it's a robot that's watching our code that's one of the best ways to think about it It's sitting there constantly cleaning up things looking for installation problems。

 Lintting problems， testing problems， it'll fail right here with this Lint because we have a bad message oh the code has actually had alynting problem。



![](img/9a040aeb1c848bab59e7b58fbcb31de1_4.png)

Theres there's an issue what do we do Well fortunately it's very straightforward I don't even need to go into my development environment。

 I can just go to this file right here and I can edit it and I can say oh this was a problem I don't need these two lines of code let's go ahead and fix this and let's have our robot or a build server go ahead and take a look at this and see if it can fix it。



![](img/9a040aeb1c848bab59e7b58fbcb31de1_6.png)

![](img/9a040aeb1c848bab59e7b58fbcb31de1_7.png)

Okay， so we're waiting for this build server to run the job。There we go。

 It's going to set up the code， install the dependencies。

 and then finally now we see that the Li itself has actually gone through。

 the format has gone through， everything's gone through。

 So really this is the process is it's something that every project should have if you're doing microservice development a command and tool development。

 really anything in software development in Python。

 and you can see how we can easily test those changes even inside of a Gitthub project。



![](img/9a040aeb1c848bab59e7b58fbcb31de1_9.png)

![](img/9a040aeb1c848bab59e7b58fbcb31de1_10.png)