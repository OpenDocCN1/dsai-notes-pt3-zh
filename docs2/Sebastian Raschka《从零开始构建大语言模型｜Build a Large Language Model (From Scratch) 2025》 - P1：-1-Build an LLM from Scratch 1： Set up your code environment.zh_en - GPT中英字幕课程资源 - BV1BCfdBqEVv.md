# Sebastian Raschka《从零开始构建大语言模型｜Build a Large Language Model (From Scratch) 2025》 - P1：-1-Build an LLM from Scratch 1： Set up your code environment.zh_en - GPT中英字幕课程资源 - BV1BCfdBqEVv

Yeah， hi and welcome， everyone to this coding a long video for theBuild a largege language model from scratchbook。

 My name is Sebastian Rashka， and I'm the author of this book。

 and I'm planning to record a couple of videos for this book as a supplementary resource。

 So as you might know， there are seven chapters in this book and the videos will be from each of these chapters where I will hopefully provide a more。

 I would say casual but also interesting take on some of the code examples。 However， of course。

 the videos won't be as comprehensive as the book itself。

 So they work best in combination with a book。 That being said So I'm planning to record videos for each chapter。

 However， Cha 1 if we go to chapter 1 here。😊。

![](img/27d9e63635c240722240233451dbd5dd_1.png)

![](img/27d9e63635c240722240233451dbd5dd_2.png)

![](img/27d9e63635c240722240233451dbd5dd_3.png)

Does not have any code examples， So I thought for this first video。

 I would show you how you can set up your Python environment so that you can then run the code for chapter 2 to7。

And of course， there are many different ways you can set up a Python environment and here in this video I'm planning to show you my personal preference so how I would set up Python on a new computer。

And yeah even I sometimes think about how I would ideally set up Python so recommendations change and I try you know to try to keep it simple but also use the latest I would say recommendations and tools to provide an ideal experience So I do have a supplementary resource here on Github So Github is the place where I share some of the code for this book。

 And if you go to my account RABT and then LLM dash from scratch yeah you can get to the GiHub repository。

 And then there is this convenient setup folder that I yeah set up here where you can find some recommendations like I mentioned before I will be showing you how you can set up。

😊，Your own compute environment for this book on your own computer。 personally。

 I will be using a Macbook mini sorry MacBook error， which is almost five years old now。

 And the code hopefully will run perfectly there because I made sure when I wrote the book that it runs on different different hardware。

 So the book will automatically run on GPUus if you have a GPU。

 but it will also run just fine on older hardware because yeah。

 the goal for this book was to make it accessible to different operating systems。

 different compute environments， All the hardware and so forth。 However， if for some reason。

 the setup instruction here doesn't work for you。

![](img/27d9e63635c240722240233451dbd5dd_5.png)

You may also want to consider instead of running things locally to， for example。

 consider cloud resources so I can highly recommend， for example， Lightning Studio。

 which is one of the most convenient ways to run code in the browser or executing code via your browser where it runs on a different machine in the cloud and there' is of course also Google ColllE which is also very widely used platform to run Jupyter notebooks and for this book all the chapters are available as Jupyter notebooks。

 which you can upload in Google Colllab and execute there in case you have any problems setting up your own computer environment on your own computer。



![](img/27d9e63635c240722240233451dbd5dd_7.png)

![](img/27d9e63635c240722240233451dbd5dd_8.png)

![](img/27d9e63635c240722240233451dbd5dd_9.png)

![](img/27d9e63635c240722240233451dbd5dd_10.png)

But yeah to make this video interesting， let me actually show you how I would set up Python on my own computer。

 So for this actually this is a fresh awesome environment and set up on this computer just to mimic how you know I would set up Python on a new computer in this case it's me S and I do have a subfolder year that is called optional Python setup preferences So the emphasis is an optional that this is something I recommend but you don't have to follow it。

 I mean you can install Python your own way however this is how I would personally do it。



![](img/27d9e63635c240722240233451dbd5dd_12.png)

And。Even there， there are multiple ways you can do it。 so I used to be a Conda user for a long time。

So Connda is a package manager for Python and a bit more than that and I used it for a long time to manage yeah my Python libraries and in combination with Connda I also used Pip。

 which is like the native official way in Python to install packages。

 However recently there is a new package called U and this one is essentially providing the same or similar syntax as Pip but also has some advantages and is very fast。

 So actually recently also moved to just using U because it's just much faster and is' a really nicely designed package manager and the Python community is very excited about this a lot of people in the Python community are using this So I also thought I will show you how you can set up your environment using U and it's actually relatively simple。

 It's not more complicated necessarily than using any of the other two。That being said。

 there are also multiple ways you can use UV， so there is the U PP syntax。

 which is very similar to the original Python Pip package manager。

 but there's also the native U syntax for this tutorial I will be using the UPP interface because it's a bit more familiar to PP users。

 but if you are you know more advanced and you're ready to explore the native syntax。

 also feel free to check out this tutorial here。

![](img/27d9e63635c240722240233451dbd5dd_14.png)

So the first step here in our journey would be of course installing Python itself。

 so we can actually check if we have Python installed by for example。

 typing Python version in our terminal， so this is in Mac S。

 but I think it's similar in Linux and Windows。

![](img/27d9e63635c240722240233451dbd5dd_16.png)

![](img/27d9e63635c240722240233451dbd5dd_17.png)

So here it says Python not found， which means I don't have Python the command set up like this that it would work this way。

 Another thing I usually also try is typing on Python 3。And here you can see in this case。

 I already have Python installed or my operating system has Python installed。 And actually right now。

 while I'm recording this， there is Python 3。13 available。 And now this is 3。9。

 which means it's four version numbers behind the most recent python release。

 and that tells me this must be some old version of Python that came with my operating system。

 So usually when you set up a new computer， it already has Python on it。

 but it's used by the operating system。 and I highly recommend not modifying this python version and also not just working with it because you might break something and then it could cause trouble for your operating system。

 So I highly recommend not touching this python here at all。

 And so what I recommend is just installing a separate version of Python and you can do that in multiple ways the official way。

😊。

![](img/27d9e63635c240722240233451dbd5dd_19.png)

![](img/27d9e63635c240722240233451dbd5dd_20.png)

Would be， for example， going to Python。org and yeah installing it from there so they have a menu here and you can download it for a different operating system so I can。

 for example， go to Mac S and then look for the latest release and here it says Python 3。

13 and another thing I wanted to highlight is I would recommend installing a slightly older version of Python that's because packages like Pythtorch。

 which we will be using in this book。 they actually they are not always supporting the latest version of Python。

 It usually takes a few months till yeah Pytorch supports。

 let's say the latest release of Python So I would recommend to be on the safe side to adopt a version that is one or two version numbers behind for example Python 3。

12 or 3。11 and you actually won't miss out on anything because you know you don't use these most recent features in Python anyway when you do scientific computing。



![](img/27d9e63635c240722240233451dbd5dd_22.png)

![](img/27d9e63635c240722240233451dbd5dd_23.png)

So in this case， it's safe to install a slightly older version。 and so for this book。

I tested it on all versions like 3。10，1112 and also 13 it works just fine。

 but to be on the safe side as a general rule of thumb。

 I recommend installing a slightly lower or smaller version， for example， 3。

11 or something like that。

![](img/27d9e63635c240722240233451dbd5dd_25.png)

That being said， there are many ways to install Python I on this computer use Homebrew。

 which is another package manager， so if I go here。



![](img/27d9e63635c240722240233451dbd5dd_27.png)

![](img/27d9e63635c240722240233451dbd5dd_28.png)

![](img/27d9e63635c240722240233451dbd5dd_29.png)

Ty Homebrew。 you don't have to use it， by the way。 It's just something I happen to use on this computer and it's called the missing package manager for MacOS。

 And so it allows you to install certain tools that don't already come with MacOS。 but you can also。

 for example， use it to install Python。 that's just personal preference。

 but you know you can also just download it from the website。 There are multiple ways。

 You can install Python， but that is just how I would do it personally。



![](img/27d9e63635c240722240233451dbd5dd_31.png)

![](img/27d9e63635c240722240233451dbd5dd_32.png)

So you can type brew install Python， let's say， 3。11。UYeah， and that would then install Python。

 so that would be the first step。

![](img/27d9e63635c240722240233451dbd5dd_34.png)

And then the second step would be setting up UV so UV is this package manager and you can install it via Pip install UV so if you have Python already installed this would be PIip would be the Python package manager and we use that to install another package manager and the reason we do that is because UV is actually faster than Pip and it's just more convenient to use it in my opinion。



![](img/27d9e63635c240722240233451dbd5dd_36.png)

Now， looking at the output here， it says Python is installed now， it's installed in this folder。

 and there are some advanced ways you can actually link it so that when you type Python。

 it will automatically use this Python。 But for simplicity， let's just。

Use the commands from here and it says， for example。

 you can install Python packages with this command。

 so it's slightly different from what's shown here， but yeah， I will just use this command。

 you can link it on your computer that it is just Pip。

 but you know for br I don't want to overcomplicate things here we are now installing the U package manager。

And so this was very quick， it's installed now， and the next step after that is creating a virtual environment。



![](img/27d9e63635c240722240233451dbd5dd_38.png)

This is not strictly necessary， but I highly recommend this。

 This means virtual environment means that it is a separate folder on your computer where all the packages are installed。

 And in this case， it will also bring its own version of Python。

 This means if you are messing anything up by accident you can just delete this virtual environment and start over without you know messing up your whole computer。

 So this is actually something yeah I highly recommend。 So before I execute this though。

 let me do one more thing。 So let me actually。

![](img/27d9e63635c240722240233451dbd5dd_40.png)

Download the Skit upub code here。

![](img/27d9e63635c240722240233451dbd5dd_42.png)

So I can go to my Gitthub repository and then you can click on download the zip。

And it will download this here in this case to the download notess folder let me just open the download notess folder。



![](img/27d9e63635c240722240233451dbd5dd_44.png)

And then let me drag this to the desktop because then it's a bit easier to see。

 So I have now this folder。

![](img/27d9e63635c240722240233451dbd5dd_46.png)

And I can go in here and you can see the contents of the folder here are the same contents that are shown。



![](img/27d9e63635c240722240233451dbd5dd_48.png)

![](img/27d9e63635c240722240233451dbd5dd_49.png)

Here on Gitthub， so I just。

![](img/27d9e63635c240722240233451dbd5dd_51.png)

Yeah， copied or downloaded this， this Github repository。



![](img/27d9e63635c240722240233451dbd5dd_53.png)

Now。Let me actually navigate to this folder。It might be a bit different on Windows。

 but this is how you do it on Mac S and Linux。And then I can also show the contents of this folder here。



![](img/27d9e63635c240722240233451dbd5dd_55.png)

Now， let me create this virtual environment。 So there was this command。

 I just showed you where was it here， this command。 So this U vent。



![](img/27d9e63635c240722240233451dbd5dd_57.png)

This will create a virtual environment and let's just use Python， let's say， 3。

11 and this will create a folder called Venf。 We can double check now it's here and it has its own version of Python。

 So in case we mess anything up it will actually not be a problem。

 we can just delete this folder and then we should be able to set it up again。

 So what I mean is if we mess anything up later on， can just delete it。



![](img/27d9e63635c240722240233451dbd5dd_59.png)

![](img/27d9e63635c240722240233451dbd5dd_60.png)

And then recreate it like this。Now there is one more thing I want to say is also you may not be able to see this folder because it starts with a dot and files or folders starting with a dot by default invisible in the finder so there is a finder option that you have to enable to make invisible files and folders visible but here let's say it is visible assume yeah you have created this vent folder。

 the next step would be activating this So creating the virtual environment is only something you have to do once unless you delete it。

 but then every time you work with it you activate it。



![](img/27d9e63635c240722240233451dbd5dd_62.png)

![](img/27d9e63635c240722240233451dbd5dd_63.png)

So now this is active and I type Python。So I can type Python and this is command which which shows you which python version you are using。

 I think on Windows， you have to type where。But let's stick with this because this is meOS and you can see it's now using when I'm executing Python。

 it's using this Python from my virtual environment。 So let me do this。So this should be Python 3。11。

From from this path here， again， I can delete this。 So let me just get rid of this。



![](img/27d9e63635c240722240233451dbd5dd_65.png)

![](img/27d9e63635c240722240233451dbd5dd_66.png)

If I type Python version， it won't be available because I just deleted it So in this case we have a virtual environment that is just very specific to this folder and if we mess anything up we can just yeah start over again and yeah installing packages works like this you can do U Pip install and then there's a package called packages let's just install that so it will then yeah install this package or if we want to install Pythtorch we can type U Pip install。

Torch So for some reason the Pytorrch team named the Python package torch instead of Pytorrch so something to remember Pytorrch is the main deep learning library we are using in this book。

So now I installed torch or Pytorrch and yeah so we could do that for all the packages that are used in this book and in the chapter itself I'm usually telling you which package needs to be installed。

 but if you want to make this super convenient and not just you know executing this one by one。

 you can actually go here and there's a file called requirements text it's also the same here on GiHub。



![](img/27d9e63635c240722240233451dbd5dd_68.png)

![](img/27d9e63635c240722240233451dbd5dd_69.png)

I go to the main。😔，View， theres a requirements or text。

 and it lists the latest of the the packages that are required for running this book。

 So if you do Pip or U V Pip install minus R requirements。



![](img/27d9e63635c240722240233451dbd5dd_71.png)

Os， you can install all the packages all at once like this。 And yeah， so in this way， you are done。

 you don't have to do anything。 In addition， this should install all the packages that you need for this book。

 Now， if you're running this on Windows。You might encounter an issue with Tensorflow IO GCS file system。

And this is a bit annoying， so the reason why we need this is that Open AI released the GPT weights for the GPT2 model。

 and LLM that we are using in chapter5。S Tensorflow code back then。

 and the weights are in Tensorflow， we are not working with Tensorflow In this book。

 We are using Pytorch， which is the most widely used deep learninging library at the moment。 However。

 just to open these open weight files， we have to briefly use Tensorflow。

 And this is why it's a requirement。 However， it might create some problems on windows， so。

If you don't want to worry about this， you could either go into this requirements file。Here。

Delete Tensor floor。 save it， and then。Just run this command again and then worry about yeah worry about installing Tensorflow at a later time。

 you can also without having to delete this， I think what works because it will build it from source you can leave it in here and just run Pip install without Uv and this this should also work。

 So like this。However， in case this also doesn't work。 Theres another backup option。

 and this would be using Google Colllap。 So if you go to Google Colllap。



![](img/27d9e63635c240722240233451dbd5dd_73.png)

![](img/27d9e63635c240722240233451dbd5dd_74.png)

This is a way you can run notebooks in the cloud。 It's free。



![](img/27d9e63635c240722240233451dbd5dd_76.png)

And what you could do here， let me do a new notebook。



![](img/27d9e63635c240722240233451dbd5dd_78.png)

Yeah， so you can install， for example， again， Uv， so you can type Pip install Uv。

Usually it's not always required， but it's usually a good idea to add this exclamation mark if you are running this in a notebook。

And then so what you can do is you can go here。To this main folder。Click on requirementsqui or text。

 click on raw。And copy this link here。Go here。And type U Pip， install minus R。

 and it will install all the required packages here。

 one more thing to say is we are not we have not created this virtual environment。

 So this is why we are seeing this error here。 and in Google coll。

 it would be overkill to create this virtual environment。 I mean， we could do it with this U vent。

 for example， but this would be overkill because Google collab is already a virtual environment。

 So every time you open the notebook in a new session， it will be a fresh environment。

 So in this case， since it is already a virtual environment。

 we can just type system and it will treat it like such so that it is not creating a separate virtual environment。

 but it's really up to you。 This is like just a bit simpler。 It's one less step to worry about。

 oops one mistake。Oh， I made a typo。 I forgot an S。 So yeah。

 so this is installing all the packages in Google Colll now。 And then we could， for example。

 execute the code for this book in Google Colll。 And by the way。😊。



![](img/27d9e63635c240722240233451dbd5dd_80.png)

This command。Also works。Locally， so if you don't want to download the Github repository。

 you could also just copy this in here with this URL and install all the packages right here here it already I mean。

 already has the packages so it didn't do much。 But if you run this for the first time this will install all the packages。

 And then once we have this installed， we can do Uv run and open a new Jupyter lab environment。

 So Jupyter La is a way to open Jupyter notebooks by default。

 this will open up in your primary browser and then yeah we can open the code for the different chapters for example。

 or we could make a new notebook So that's what I recommend when you're following along with this book either。



![](img/27d9e63635c240722240233451dbd5dd_82.png)

![](img/27d9e63635c240722240233451dbd5dd_83.png)

![](img/27d9e63635c240722240233451dbd5dd_84.png)

To make a new notebook and run the code here or another thing is you can open an existing notebook。

 but you know it would be a little bit of a spoiler if you see already the output。

 so I highly recommend going here and selecting clear outputs of all cells which will delete the output so you're not seeing the output but I think to get the most out of the book。

 I highly recommend just doing a fresh notebook and actually it's a lot of work but actually typing the code because it's actually a really good learning experience because then you also see or you pay more attention to the code than just you know copy pasting it or just starting with an existing notebook。

 but yeah， I don't want to go too much ahead here and start already talking about the code in chapter2 we will do this in the next video I hope this video was useful to you and showed you one way you can set up your computing environment and yeah if you have questions please feel free to comment I'm happy to answer。

You might have and also know if nothing works， you know。

 there's always Google Col or there are other environments I can also share where there will always be a possibility that you can run the code。

 so don't worry about it。 But if you have any questions please let me know and I hope this video was useful And yeah I hope I will see you in the next video。



![](img/27d9e63635c240722240233451dbd5dd_86.png)