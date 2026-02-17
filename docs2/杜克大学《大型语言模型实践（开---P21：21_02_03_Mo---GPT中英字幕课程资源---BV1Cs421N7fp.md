# 杜克大学《大型语言模型实践（开源大语言模型方案）｜Large Language Model Operations 》 - P21：21_02_03_Mozilla的LlamaFile概述.zh_en - GPT中英字幕课程资源 - BV1Cs421N7fp

![](img/a03a538cde8cc68867787ba670f07691_0.png)

Hey there， my name is Stephen Hood， I work for Mozilla and my role at Mozilla is to oversee open source AI projects and initiatives and one of my projects is Lmaophil which we're here to talk about today Lmaophil is is a project that makes it very easy to use open models on any consumer hardware without much technical understanding or knowledge with very little installation or configuration it makes what is really a stack of complexity for using open source AI and collapses it down to just a file that you download and run。

We were inspired to create Lmmophile from our own research into the state of open source AI technology。

 we found that there's a tremendous amount of activity today in the open source AI space but a lot of the tech is still too hard to use so there are a huge number of models to choose from to begin with but once you have those models they come in different formats。

 the formats keep changing as the technology evolves and then you have to make decisions once you have a model about what runtime you're going to use so how you're actually going to get it up and running in order to do inference against that model and depending on your model your platform and your chosen runtime solution you may have a lot of things you have to do you may have to compile C or C++ code and make sure you have the right tool chain installed to do that you may have to install and manage Python dependencies in some cases you have to install native software。

And sometimes all these things sort of come together and it can be complicated。

 and our concern has been that the harder it is to use open source AI。

 the less likely developers are to adopt it， or the more slowly they will adopt it。

 and that could hinder its evolution， which we think is incredibly important。

 we think that having competitive advanced open source AI technology in the hands of the public is critical to ensuring that AI does not end up being dominated by a handful of commercial interests。

 the way the internet has arguably become。 and that's a cause we care about a lot being Mozilla。

 the makers of Firefox， we care about the web， and therefore we have to care about AI as well because it's already transforming the way we all use the web and the way we use computers。

So with that in mind， we createdllma file and what we did is we took two different projects and we combined them in a unique way。

The first project is Lama。cppP， this is a very popular open source project that makes it possible to run quantized open models on everyday consumer hardware。

 so these are models that are compressed down so they require less memory to run and then the software itself is a very highly efficient C++based inference engine that can execute these models on everyday hardware whether it' be MacBooks or Windows machines or Linux boxes。

So we took that project and we combined it with another one called cosmopolitan。

Cosmopolitan is a project created by Justine Tney and what it does is it makes it possible to compile C and C++ programs in a way that they will run on almost any computer and I don't mean。

You create different executables， one for Windows， one for Linux，1 for Mac and so forth。

 The same compiled file runs unaltered on all these different platforms。

 You can even run them on Raspberry Pis。 It's a pretty remarkable little bit of technology there that she has created。

 And we working with Justine combine these two projects together。

 And what we it allows us to do is take any open weights in the Gg Uf format。

 which is a popular open model format today。 You can find these unhuging face and other various places。

😊，And you can then wrap it in the Luma file executable code。

 which adds only 40 or 50 megabytes to what is a multigabyte file that's basically a rounding error and now that file you can distribute and people can download it no matter what kind of computer they're running and it will just work when they run it。

 it brings up their web browser with a webbased locally hosted chatbot interface。

The AI is running entirely on the user's local machine。

 you could unplug it from the internet at that point and it will continue to work so it's 100% local。

 it's 100% private to the user so they can use it with confidence that no one else is listening in。

 no one else is doing anything with their data。And this works like I said in almost any computer。

 if you have a GPU， a graphics processing unit which can accelerate large language model inference。

 then it will detect it， whether it be NviIDdia or AMD and this is a big deal because quite often AMD does not have the same support that NVIDdia has in the AI machine learning space。

 so we've been able to address that as well。We have on our website on our GitHub repo。

 a number of Lama files example LaMma files that you can download and use。

 and I will in future videos， I can talk more about how to create your own LAMma files。

 how to use LaMma file yourself， and how to also use it as a developer。

 as a drop in replacement for open AI。Hope you enjoy using Lamaophil thanks a lot。

