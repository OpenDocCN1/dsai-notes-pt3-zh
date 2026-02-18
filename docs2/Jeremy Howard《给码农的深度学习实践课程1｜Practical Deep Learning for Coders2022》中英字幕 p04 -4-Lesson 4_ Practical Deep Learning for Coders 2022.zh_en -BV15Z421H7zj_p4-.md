# Jeremy Howard《给码农的深度学习实践课程1｜Practical Deep Learning for Coders2022》中英字幕 p04 -4-Lesson 4_ Practical Deep Learning for Coders 2022.zh_en -BV15Z421H7zj_p4-

Hi， everybody。 and welcome to practical deep learning for codes lesson 4。

 which I think is the lesson that a lot of the regulars in the community have been most excited about because it's where we're going to get some。

😊，Totally new material。 Tot new topic we've never covered before。

We're going to cover natural language processing in LP。

 And you'll find there there is indeed a chapter about that in the book。

But we're going to do it in a totally different way to how it's done in the book in the book。

 we do NLP using the fast AI library。Using recurrent neural networks， Air andNs。Today。

 we're going to do something else， which is we're going to do transformers。

And we're not even going to use the fast AI library at all， in fact。

So what we're going to be doing today is we're going to be fine tuning a pre trained NLP model using a library called Huging F Transformers。

Now， given this is the fast dot AI course， you might be wondering why we'd be using a different library other than fast AI。

The reason is that I think that。It's really useful for everybody to have experience and practice of using more than one library。

😊，Because you'll get to see the same concepts applied in different ways。

 And I think that's great for your understanding of what these concepts are。Also。

 I really like the Hging Feast Transformers Library。

 it's absolutely the state of the art in NLP and it's well worth knowing。😊，嗯。

If you're watching this on video by the time you're watching it。

 we will probably have completed our integration of the Transformers library into Fast AI。

 so it's in the process of becoming the main NLP kind of foundation for Fast AI。

 so you'll be able to combine transformers and Fast AI together。Um。Yeah。

 so I think there's a lot of benefits to this。 And in the end。

 you're going to know how to do an LP in， in a really fantastic library。 Now， the other thing is。😊。

Howing face transformers。Doesn't have the same layered architecture that Fast A has。Which means。

Particularly for beginners。The kind of high level， you know。

 top tier API that you'll be using most of the time。Is not as。Kind of ready to go for beginners。

 as you're used to from Fast A A。And so that's actually， I think， a good thing。

 You have to lesson for。 You know， the basic idea now of how gradient descent works and， you know。

 how parameters are learned as part of a flexible fu function。😊，I think you're ready to。

To try using a somewhat lower level library that does a little bit less for you。 So it's going to be。

 you know， a little bit more work。 It's still， it's a very well designed library， and it's still。

Reasonably high level， but you're going to learn to go a little bit deeper。

 And that's kind of how the rest of the course in general is going to be on the whole is we're going to get。

A bit deeper and a bit deeper and a bit deeper。Now， so， first of all， let's talk about。嗯。

What we're going to be doing with fine tuning a pre trained model。

 We've talked about that in passing before， but we haven't really been able to describe it。

In any detail， because you haven't had the foundations。 Now you do。

You played with these slidrs last week that hopefully。

 you've all actually gone into this notebook and dragged them around and tried to get an intuition for this idea of what。

Moving them up and down makes the loss go up and down， and so forth。So， I imagine that。

Your job was to move these sliders to get this as nice as possible。But when it was given to you。

The person who gave it to you said， oh， actually， slider A， that should be on 2。0。We know for sure。

 And slider B， we think it's like around two and a half。Slide to C。 We've got no idea。Now。

 that'd be pretty helpful， wouldn't it， right， Because you could like immediately start focusing on the one we have no idea about。

 get that in roughly the right spot。 And then the one you kind of got a vague idea about。

 you could just tune it a little bit。 And the one that they said was totally confident you wouldn't move it all。

 you would probably tune these sliders really quickly。That's what a pre trained model is。

 A pre trained model is a bunch of parameters that have already been fit。

Where some of them were already pretty confident of what they should be。And some of them。

 we really have no idea at all。 And so fine tuning is the process of taking those ones。

 We have no idea what they should be at all and trying to get them right and then moving the other ones a little bit。

The idea of。Fine tu。A pre trained NLP model in this way was pioneered by an algorithm called UM Fi。

Which was first presented， actually， in a fast A A course， I think the very first fast A O course。

It was later turned into an academic paper by me in in conjunction with a then PhD student named Sebastian Ruda。

 who's now one of the world's top N LP researchers and went on to help inspire。A huge change。

 you know， a huge of step improvement in LLP capabilities around the world。

 along with a number of other important innovations at the time。

This is the basic process that ULM Fi described。Step 1 was to build something called a language model。

 using basically nearly all of Wikipedia。And what the language model did was it tried to predict the next word of a Wikipedia article。

In fact， every next word of every Wikipedia article。Doing that is very difficult。 You know。

 there are Wikipedia articles， which would say things like。嗯。You know， the 17th prime number is dot。

 dot dot。Or。The 40th president of the United States， Blair， said at his residence， Blair， that。

You know， filling in these kinds of things requires understanding a lot about how language is structured。

And about the world and about math and so forth。So to get good at being a language model。

 a neural network has to get good at a lot of things。

It has to understand how language works at a reasonably good level。

 and it needs to understand what it's actually talking about and what is actually true and what is actually not true and the different ways in which things are expressed and so forth。

So this was trained。Using a very similar approach to what we'll be looking at for fine tuning。

 but it started with random weights and at the end of it。

 there was a model that could predict more than 30% of the time correctly what the next word of a Wikipedia article would be。

嗯。So in this particular case for the ULM Fi paper， we then took that and we were trying to the first task I did。

 actually， for the the fast A A course back when I invented this。

Was to try and figure out whether IMDB movie reviews were positive or negative sentiment。

 Did the person like the movie or not。So what I did was I created a second language model。

 so again a language model here is something that predicts the next word of a sentence。

 but rather than using Wikipedia， I took this pre-trained model that was trained on Wikipedia and I ran a few more epochs using IMDB movie reviews so it got very good at predicting the next word of an IMDB movie review。

And then finally， I took those weights。And I fine tuned them for the task of。

Preticecting whether or not a movie review was positive or negative sentiment。

 So those were the three steps。This is a particularly interesting approach because this very first model。

 In fact， the first two models。 If you think about it， they don't require any labels。

 They didn't have to collect any kind of document categories， or do any kind of。

Surveys or collect anything。 All I needed was the actual text of Wikipedia and review reviews themselves。

Because the labels was， what's the next word of a sentence。Now， since we built ULM Fi。

And we used R&Ns， the current neural networks for this at about the same time ish that we released this。

 a new kind of architecture， particularly useful for NLP at the time。

 was developed called transformformers。And transformers were particularly built because they can take really good advantage of modern accelerators。

 like， like Google's T Ps。They didn't really kind of allow you to predict the next word of a sentence。

 it's just not how they're structured。 for reasons we'll talk about probably in part2 of the course。

So they threw away the idea of predicting the next word of a sentence。 and then instead。

 they did something just as good and pretty clever。

They took kind of chunks of Wikipedia or or whatever text they're looking at and deleted at random。

 a few words。And asked the model to predict which what were the words that were deleted。 essentially。

 So it's a pretty similar idea。Other than that， the basic concept was the same as U1 fit they replaced our R andN approach with a transformer model。

 They replaced our language model approach with what's called a masked language model。

 but other than that， the basic idea was the same。So today we're going to be looking at models using what's become the you know。

 much more popular approach than U M fit， which is this transformers master language model approach。

 Okay， John， do we have any questions， and I should mention， we do have。

Professor from University of Queensland， John Williams joining us who will be asking the highest word questions from the community。

 What do you got John Yeah， thanks Jeremy I mean look and we might be jumping the gun here。

 I suspect this is where you're going tonight， but we've got a good question here on the forum which is how do you go from a model that's trained to predict the next word to a model that can be used for classification？

Sure， so， yeah， we will be getting into that in more detail。 And， in fact。

 maybe a good place to start would be the next slide。Kind of give you a sense of of this。

 You might remember in lesson1， we looked at this fantastic Xiler and Fergus paper。😊。

Where we looked at visualizations of the first layer of a imagenet classification model。

And layer 1 had sets of weights that found diagonal edges。

 And here are some examples of bits of photos of that。

Successfully matched with and opposite diagonal edges。And kind of color gradients。

 And here has some examples of bits of pictures that matched。And then layer 2 combined those。

 And now you know how those were combined， right， these were rectified linear units that were added together Okay。

 and then sets of those rectified linear units， the outputs of those they got activations where then themselves run through a matrix modelplayer rectified linear unit added together。

 So now you don't just have to have edge detectors， but layer2 had corner detectors。

AndHere's some examples of some corners that that corner detector successfully found。 And remember。

 these were not。Engineered， in any way， they just evolved from the gradient asscent training process。

Layya2 had examples of circle detectors， as it turns out。

And skipping a bit by the time we got to layer of 5， we had bird and lizard eyeball detectors。

And dog face detectors。And。Flower detectors， and so forth。Now， you know， nowadays。

 you'd have something like a Re 50 would be something you'd probably be trading pretty regularly in this course so that。

 you know， you've got 50 layers， not just5 layers。嗯。Now， the later layers。

Do things that are much more specific to the the training task。

 which is like actually predicting really what， what is it that we're looking at。The early layers。

Pretty unlikely， you're going need to change them much as long as you're looking at like some kind of natural photos。

 right， you're gonna need edge detectors and gradient detectors。So， what we do。In。

 in the fine tuning process is there's actually one extra layer after this。

 which is the layer that actually says， what is this， You know， it's， it's a di or a cat or whatever。

 We actually delete that。 We throw it away。So now that last matrix multiply has one output or one output per category you're predicting。

 We throw that away。 So the model now has that last matrix that's spitting out。You know， it depends。

 but generally a few hundred activations。And what we do is as we'll learn more shortly in the coming lesson。

 we just stick a new random matrix on the end of that。And that's what we initially trained。

 So it learns to use。These kinds of features。To predict whatever it is you're trying to predict。

And then， we gradually。Train all of those layers。So that's basically how it's done。

 And so it's a bit hand wavy， but we'll particularly in part two。

 actually build that from scratch ourselves。 and in fact， in this lesson。

 time' permitdding we're actually going to start going down the process of actually building a real world deep neural net in Python。

 so we'll be starting to actually make some progress towards that goal。Okay， so。

Let's jump into the notebook。 So we're going to look at a cha competition that's actually on as I。

 as I speak。And I created this notebook book called Gettinging Start with NLP for absoluteute Beners。

And so the competition is called the US Pat phrase to phrase matching competition。

And so I'm going to take you through。You know， a complete submission to this competition。

 and Cal competitions are interesting， particularly the ones that are not playground competitions。

 but the real competitions with real money applied。

 they're interesting because this is an actual project that an actual organization。😊。

Is prepared to invest money in getting solved using their actual data。

So a lot of people are a bit dismissive of capital competitions as being kind of like。Not very real。

 And it's certainly true。 You're not worrying about stuff like productionizing the model。But。

 you know， in terms of like getting real data about a real problem that real organizations really care about and a very direct way to measure the you know。

 accuracy of your solution， you can't really get better than this。 So this is a good place。

 a good competition， to experiment with for trying N LP。Now， as I mentioned here。

 probably the most widely useful application for NLP is classification。

 And as we've discussed in computer vision， classification refers to taking an object and trying to identify a category that object belongs to。

 So previously， we've mainly been looking at images。 today， we're going to be looking at。😊，Documents。

 now， an NLP， when we say document。We don't specifically mean， you know， a 20 page long。You know。

 essay， a document could be three or four words。Or a document could be the entire encyclopedia。

 So a document is just an input to an NLP model that contains。Text。Now， classifying a document。

 So deciding what category a document belongs to is a surprisingly rich。Thing to do。

 There's all kinds of stuff you could do with that。 So， for example。

 we've already mentioned sentiment analysis。 That's a cat that's a classification task。

 We try to decide on the category， positive or negative sentiment。

Author identification would be taking a document and trying to find the category of author。

Legal discovery would be taking documents and putting them into categories。

 according to in or out of scope for a court case。Triaging inbound emails will be putting them into categories of。

 you know。Throw away， send to customer service， send to sales， etc cetera， right。

Classification is a very， very rich area。 And for people interested in。Trying out N LP in real life。

 I would suggest classification would be the place I would start for looking for kind of。Accessible。

 real world， useful problems you can solve right away。Now。

The cagul competition does not immediately look like a classification competition。What it contains。

Let me show you some data。What it contains is data that looks like this。

It has a thing they call anchor， a thing they call target， a thing they call context and a score。Now。

 these are。I， I can't remember the exact details， but I think these are from patents。

And I think on the patents， there are various like。Things they have to fill in in the patent。

And one of those things is called An。One of those things is called Ta。And in the competition。

 the goal is to come up with a model that automatically determines which anchor and target pairs are talking about the same thing。

So a score of one here。Wood article and wooden article， obviously talking about the same thing。

 A score of 0 here。 abatement and forest region， not talking about the same thing。So。

 the basic idea is that we're trying to。C guess the score。And it's kind of a classification problem。

 Kind of not。 We're basically trying to classify things into either these two things are the same or these two things aren't the same。

It's kind of not because we have not just one and 0， but also 025。5 and 。75。

There's also a column called context， which is， I believe。

 is like the category that this patent was filed in。

And my understanding is that whether the anchor and the target count as similar or not， depends on。

You know what， what the patent was filed under。So how would we take this。

And turn it into something like a classification problem。So the suggestion I make here。

Is that we could basically say， okay， let's put the you know some constant string like text1 or field one before the first column and then something else like text2 before the second column。

maybe the also the context。 I should have this well， T 3 in the context。

 and then try to choose a category of meaning， similarity， different， similar or identical。

 So it could basically concatenate those three pieces together。

Call that a document and then try to train a model that can predict。These categories。

 That would be an example of how we can take this basically similarity problem and turn it into something that looks like a classification problem。

 And we tend to do this a lot in deep learning， is we kind of take。

Problems that look a bit novel and different and turn them into a problem that looks like something we recognize。

Right， so on Caggle。This is a， you know， larger data set that you're going to need a GPU to run。

 so you can click on the accelerator button and choose GPU to make sure that you're using a GPU。

 If you click copy and edit on my document， I think that'll happen for you automatically。Personally。

 you know， I like using things like paper space generally better than kggle。

 like kgggel is pretty good。 but you know， you only get 30 hours a week of GPU time and their notebook editor for me is not as good as a real Jupiter lab environment。

 So there's some information here I won't go through。

 but it basically describes how you can download stuff to paper space or your own computer as well if you want to。

 So I basically。😊，Create this little boleion always in my notebook called I Cagel。

 which is going to be true if it's running on kle and false otherwise and any little changes I need to make。

 Id say if is kggle and put those changes。So here you can see here。

 if I'm not on Caggle and I don't have the data yet， then download it。 And Cagel has a little API。

 It is quite handy for doing stuff like downloading data and uploading notebooks and stuff like that。

 submitting competitions。If we are on Caggle， then the data is already going to be there for us。

 which is actually a good reason for beginners to use Cagggel is you don't have to worry about grabbing the data at all。

 It's sitting there for you as soon as you open the notebook。

Cagle has a lot of Python packages installed， but not necessarily all the ones you want。

 and at the point I wrote this， they didn't have hugging faces data sets package for some reason so you can always just install stuff。

 so you might remember the excation mark means this is not a Python command but a shell command。

 a bash command， but it's quite niche you can even put bash commands inside Python conditionals。

 so that's a pretty cool little trick in notebooks。Another cool little trick in notebooks。

Is that if you do use a batchsh command like L S。But you then want to insert the contents of a Python variable。

 Just chuck it in parentheses。 So I've got a Python variable called path。

And I can go LS path in parentheses， and that will LS the contents of the Python variable path。

 So there's another little trick for you。Alright， so when we L that。

 we can see that there's some CSB files。 So what I'm gonna to do is kind of take you through。

Roughly the process， the kind of process I you know， went through as， you know。

 when I first look at a competition。 So the first thing is like already data set， indeed。

 what what's in it， Okay， it's got some CSV files。You know， as well as looking at it here。

 the other thing I would do。As I would go to the competition website。And if you go to data。

A lot of people skip over this， which is a terrible idea because it actually tells you what the dependent variable means。

 what the different files are， what the columns are， and so forth。So don't just rely on。

Looking at the data itself， but look at the information that you're given about the data。

So for CSV fail， the CSV files are comma separated values。

 So they're just text fail with a comma between each field。And we can read them， using pandas。

Which for some reason， always always called P D。Pands is one of。I guess like。

 I'm trying to think probably like four key libraries。

That you have to know to do data science in Python。And specifically。Those four libraries are。N play。

嗯。Mattpltleb。Paandndas。And Pytoch。So nuy is what we use for basic kind of。A numerical programming。

 that plot lib were used for plotting。 Padas were used for tables of data， and pipetorrch were used。

F take money。Those are all covered。In a fantastic book。By the author is pandas。

 which the the dear version is actually available for free， I believe。嗯。Python for data analysis。

 So if you're not familiar with these libraries。Just read the whole book。

 It doesn't take too long to get through， and it's got lots of cool tips， and it's very readable。

I do find a lot of people doing this course。Often， I see people kind of trying to jump ahead and。

 and want to be like， oh， I w to know how to like create a new architecture or。

Build a speech recognition system or whatever。 And that it then turns out that they don't know how to use these fundamental libraries。

 So it's always good to be bold and be trying to build things。 but do also take the time to。

 you know make sure you finish reading the first AI book and read at least We McKinney's book。That。

 that would be enough to really give you all the basic knowledge you need， I think。So with pandas。

 we can read a CSV file， and that creates something called a data frame。

 which is just a table of data， as you see。So now that we've got a data frame。

We can see what we're working with。And when we ask， when in Jupiter。

 we just put the name of a variable containing a data frame。 we got the first five rows。

 the last five rows and the size。 So we've got 36473 rows。Okay。

So other things I like to use for understanding a data frame is the described method。嗯。

If you pass include equals objects， that will describe that will describe basically all the kind of the string fields。

 the nonnumeric fields。 So in this case， there's four of those。

And so you can see here that that anchor field we looked at。 there's actually only 733 unique values。

 Okay， so this thing， you can see that there's lots of repetition out of 3036000。

So there's lots of repetition。😊，This is the most common one。 It appears 152 times。And then context。

 we also see lots of repetition。 There's 106 of those contexts。 So this is a nice little method。

 We can see a lot about the data， in a glance。😊，And when I first saw this in this competition。

 I thought， well， this is actually。Not that much language data。 When you think about it， you know。

 each document is very short， you know，3 or four words， really， and lots of it is repeated。

So that's like， as I'm looking through it， I'm thinking， like。

 what are some key features is this data set， And that would be something I'd be thinking， wow。

 that's， you know， we've got to do a lot with not very much unique data here。

So here's how we can just go ahead and create a single string， like I described。Which contains。

You know， some kind of field separator plus the context， the target。And the anchor。

So we're going to pop that into a field called input。

Something slightly weird in pandas is there's two ways of referring to a column。

 You can use square brackets and a string to get the input column。

Or you can just treat it as an attribute。When you're setting it。

 you should always use the forms in here。When reading it， you can use either。

 I tend to use this one because it's less typing。 So you can see now we've got this these concatenated rows。

 so head is the first few rows。So we've now got some， some documents。To do an LP with。Now。

 the problem is， as you know from the last lesson。😊，Neural networks work with numbers。

 we've got to take some numbers， and we've got to bold to play them by matrices。

We're going to replace the negatives with zeros and add them up。 We're going to do that a few times。

That's our neural network with some little wrinkles， but that's the basic idea。

So how on earth do we do that。For these strings。So there's basically two steps we're going to take。

The first step is to split each of these into tokens。Tokens are basically words。

 We're going to split it into words。嗯。There's a few problems with putting things into words， though。

 the first is that some languages like Chinese don't have words。Right。

 or at least certainly not space separated words。 And， in fact， in Chinese， it sometimes。

It's a bit fuzzy to even say where a word begins and ends。

AndAnd some words are kind of not even the pieces are not next to each other。

Another reason is that what we're going to be doing is after we've split it into words or something like words。

We're going to be getting a list of all of the unique words that appear， just called the vocabulary。

And every one of those unique words is gonna get a number。As you'll see later on。

 the bigger the vocabulary， the more memory is going to get used。😊，The more data we'll need to train。

In general， we don't want a vocabulary to be too big。So， instead。Nowadays。

 people tend to tokenise into something called sub wordss， which is pieces of words。

 So I'll show you what it looks like。So the process of turning it into smaller units like words。

 is called tokenization， and we call them tokens instead of words。

 a token is just like the more general concept of like whatever we's spliting it into。

So we're gonna get hugging face transformers and hugging face data sets doing our work for us。

And so what we're going do is we're going to turn our pandas data frame into a into a hugging face data data set。

It's a bit confusing。 Pytorch has a class called data set， and Huging F has a class called data。

 and there are different things。 Okay， so this is a hugging face data， hugging face data， data set。

So we can turn a data frame into a data set just using the from pandas method。

 And so we've now got a data set。So if we take a look， it just tells us story。

 it's got these features。Okay。And remember， input is the one we just created with the conincat notice strings。

And here's those 36000 rows。Okay， so now we're gonna do these two things。 Tokenization。

 which is to split each text up into tokens。And then numericalization。

 which is to turn each token into its unique Id based on where it is in the vocabulary。

 the vocabulary。 Remember being the unique， the list of unique tokens。Now。Particularly in this stage。

 tokenization， there's a lot of。Little decisions。That have to be made。

The good news is you don't have to make them。Because whatever pre trained model you used。

 the people that pre traineded it made some decisions。

 and you're going to have to do exactly the same thing。 Otherwise。

 you'll end up with a different vocabulary to them。 and that's going to mess everything up。

So that means before you start tokenizing， you have to decide on what model to use。

Hocking face transformers is a lot like Tim。 It has a library of， I believe， hundreds。Of muddle。

I guess I shouldn't say huging face transformers。 It's really the hugging face model hub。

44000 models。 So even many more， even than。Tim's image models。And so these models。

 they vary in a couple of ways。 There's a variety of different architectures。Just like in Tim。

 But then something which is different to Tim， is that each of those architectures can be trained on different corpusees for solving different problems。

 So， for example， I could type patent。And see if there's any pre trained patent。 there is。 Okay。

 so there's a patent。 There's a whole lot of pre trained。Patent models。 Isn't that amazing， so。

Quite often， thanks to the Hing face model hub， you can start your pretrain model with something that's actually pretty similar to。

 to what you actually want to do， or at least was trained on the same kind of。Documents。

Having said that， there are some just。Generally， pretty good。Models that work for a lot of things。

 a lot of the time。And Albertera V3。Is is certainly one of those。U。This is a very new area， N LP。

Has been like。Practically really effective for， you know， general users。For only a year or two。

Where else for computer vision， it's been quite a while。 So you'll see。

 you'll find that like a lot of things aren't as quite well bettered down。 I don't have a。

Picture to show you of which models are the best are the fastest and the most accurate and whatever。

 right There' a lot of this stuff is like。Stuff that we're figuring out as a community using competitions like this。

 In fact， And this is one of the first。NLP competitions actually in the kind of modern NLP era。So。

 you know， we've been studying these competitions closely。 And yeah。

 I can tell you that Daberta is actually。A really good starting point for a lot of things。

 So that's why we've picked it。 So we pick our model。 And just like in Tim for image， you know。

 a bottle there's often got to be a small， a medium， a large。😊，And， of course。

 we should start with small。Right，Because small is going to be faster to train。

 We're gonna be able to do more iterations。And so forth， okay。So at this point， remember。

 the only reason we've picked our model is because we have to make sure we tokenize in the same way。

To tell transformers that we want to tokenise the same way that the people that built a model did。

 We use something called auto tokenizer。 It's nothing fancy。

 It's basically just a dictionary which says， oh， which model uses which tokenizer。

 So when we say auto tokenizer from pretrained。 It will download the vocabulary and the details about how this particular model tokenized data set。

So at this point， we can now take that。Tokenizer and pass the string to it。So if I pass the string。

 good day， folks， Sandra from Fast AI。You'll see， it's kind of putting it into words。 kind of not。

So if you've ever wondered whether God A is one word or two。You know， it's actually three tokens。

 according to this tokenizer。And I Mr three tokens。And faster AI is three tokens。

 This punctuation is a token。And so you kind of get the idea。These underscores here。

That represents the start of a word， right。 So that's kind of this this concept that like the start of a word is kind of part of the token。

 So if you see a capital I in the middle of a word versus the start of a word。

 that kind of means a different thing。 So this is what happens when we tokenise this sentence using the tokenizer that the deerta V3 developers used。

So， here's a。Less common， unless you're a big platypus fan like me， less common sentence。

A platypus is an orinca Santanus。And so， okay， in this particular voculary。

 platypus got its own word。 its own token， but On Sinus didn't。And so I still remember grade1。

For some reason， our teacher got us all to learn how to spell or through incacus。

 So one of my favorite words。So you can see here it's been split to a knee， though， R。Us。

So every one of these tokens you see here is going to be in the vocabulary。

 right the list of unique tokens that was created when this when this particular model。

 this pretrain model was first trained。 So somewhere in that list we'll find underscore capital A。

And it'll have a number。And so that's how we'll be able to turn these into numbers。So， this first。

Process is called tokenization。 And then the thing where we take these tokens and turn them into numbers is called numericalization。

So our data set， remember， we put our string into the input field。So here's a function that takes。

A document。Perhaps it's input and tokenizes it。 Okay， so we'll call this our tokenization function。

Tkenization can take a minute or two， so we may as well get all of our processes used doing it at the same time to save some time。

 So if you use the data dot map， it will parallelse that process and just pass in your function。

Make sure you pass batch decs true so it can do a bunch at a time。And behind the scenes。

 this is going through something called the Tokens library。

 which is a pretty optimized rust library that uses you know，70 and parallel processing and so forth。

 So with batched equals true， it'll be able to do more stuff at once。So look。

 it only took six seconds， so。Pretty fast。So now when we look at a row of our tokenized data set。

 that's going to contain exactly the same as our original data set。No。

 sorry it's not going to take exactly the same as the original data。

 It's going to contain exactly the same input as our original data set。

 and it's also going to contain a bunch of numbers。These numbers are the position in the vocabulary。

Of each of the tokenized， each of the tokens in the string。

So we've now successfully turned a string into a list of numbers。So that is a great first step。

So we can see how this works。We can see， for example， that we've got of a separate word。

 so that's going to be an underscore OF in the vocabulary。We can grab the vocabulary。Look at of。

Find that。 It's 2，65。And check here。 Yep， here it is，2，65。Okay， so it's not rocket science， right。

 It's just looking stuff up in a dictionary to get the numbers。Okay。

 so that is the tokenalization and numericalization necessary in N LP to turn our。Documents。

Enter numbers to allow us to put it into our model。 Any questions so far， John。Excuse me， thanks。

 Jeremy。 So there's a couple， and this seems like a good time to throw them out。

 And it's related to how you've formatted your input data into these sentences that you've just tokenized。

 So one question was really about how you choose those keywords。

 yeah and the order of the fields that you you know。

 so so I guess just you know interested in an explanation。

 is there any is it is it more art or science， how you no arbitrary I tried a few things， I tried X。

 you know I tried putting them backwards， you know， doesn't matter。

 we just want some way something that it can learn from right So if I just concatenated it without these headers before each one。

 wouldn don't know where abatement of pollution ended and where abatement started right So I did just something that it can learn from。

 This is a nice thing about neural nets。 They're so flexible。

As long as you give it the information somehow， it doesn't really matter how you give it to give it the information as as long as it's there。

 right， I could have used punctuation。 I could have put like， I don't know。

 one semicolon here and two here and three here。 Yeah， it's not a big deal， like。

At the level where you're like trying to get an extra half a percent to get up the leaderboard or k competition。

 you may find tweaking these things makes tiny differences， but in practice。

You won't generally find it。 It matters too much。Right， thank you。

 And I guess the second part of that。Excuse me again。 somebody's asking if one of their。

 their fields was particularly long。 say it was 1000 characters。

Is there any special handling required there， Do you need to。

 Do you need to reinject those kind of special market tokens， Does it。

 Does it change if you've got much bigger fields that you're trying to learn and query yeah。

Long documents。And you will M fit。to require no special consideration。So IMD B， in fact。

 has multi thousand0 word。Move your reviews。 And it works great。To this day。

 U M Fi is probably the best approach。You know， for。

 for reasonably quickly and easily using large documents。嗯。Other。

 if you use transformer based approaches， large documents are challenging， specifically。

Transformers has to basically have to do the whole document at once。

 whereas UM fit can split it into multiple pieces and read it gradually。

 and so that means you'll find that people trying to work with large documents tend to spend a lot of money on GPUs because they need the big fancy ones with lots of memory。

嗯。So， yeah， generally speaking， I would say if you're trying to do stuff with documents of over。2。

000 wordss。You might want to look at your infinite。嗯。Try transformers， see if it works for you。 But。

 you know， I'd certainly try both for under 2000 words。You know。

 transformers should be fine unless you've got a， you know。

 nothing but like a laptop GPU or something with not much memory。嗯。

So hacking face transformers has these。You know， as I say it right now that I find them somewhat obscure and not particularly well documented expectations about your data that you kind of have to figure out。

 And one of those is that it expects that your target。Heres a column code labels。

So once I figured that out， I just went。Got our tokenized data set and renamed our score column to labels。

 and everything started working。So probably as， you know， I don't know if at some point。

 they'll make this a bit more flexible， but probably best to dis your target labels and life will be easy。

You might have seen back when I joined LS Path that there was another data set there called test。

 CSV。And if you look at it， it looks a lot like。Our training set train our other CSV that we've been working with。

 but it's missing。The score， the labels。This is， this is called a test set。

And so we're going to talk a little bit about that now， because。

My claim here is that perhaps the most important idea in machine learning is the idea of having separate training。

 validation and test data sets。Yeah。So test and validation sets are all about identifying and controlling for something called overfitting。

 and we're going to try and learn about this through example。

So this is the same information that's in that。Cackle notebook。

 I've just put put it on some slides here。So I'm gonna create a。A function here called plot polyly。

 And I'm actually going to use the same data that I don't know if you a member。 We used it。

earlierli for trying to fit this quadratic， we created a x and some x and some y data。

 this is the data we're going to use， and we're going to use this to look at overfitting。U。

So the details of this function don't matter too much。 What matters is what we do with it。

Which is that it allows us to basically pass in。The degree of a polynomial。 So for。

 for those of you that remember。A first degree polynomial is just a line。 It's y equals a X。

 A second degree polynomial will be y equals a squared x plus B X plus C。

 third degree polynomial will have a cubic， fourth degree， you know， cortex and so forth。

And what I've done here is I've plotted what happens if we try to fit a line。To our data。

It doesn't fit very well。So what happened here is we。We did a linear regressiong。

And what we're using here is a very cool library called psyitL PsyitL is something that。

 you know Id think it be fair to say it's mainly designed for kind of classic machine learning methods like kind of linear regression and stuff like that。

 very advanced versions of these things and it's also great for doing these quick and dirty things So in this case I wanting to do a what's called a polynomial regression。

 which is fitting to polynomial to data And it's just these two lines of code it's a super nice library So in this case a degree one polynomial is just a line so I fit it and then I show it with a data and there it is。

😊，Now， that's what we call underfi， which is to say there's not enough kind of complexity in this model I fit。

To， to match the data that's there。So an underfit model is a problem。

 It's got to be systematically biased。 You know， all the stuff up here。

 we're going be predicting too low all the stuff down here。 we're predicting too low。

 or the stuff in the middle。 We'll be predicting too high。

A common misunderstanding is that like simpler models are kind of。More reliable in some way。

 but models that are too simple。Will be systematically incorrect， as you see here。

What happens if we fit a 10 degree polynomial。That's not great either。In this case。

 it's not really showing us。What the actual remember， this is originally a quadratic。

 this is meant to match， right， particularly at the ends here。

 it's predicting things that are way above what we would expect in real life。And it's trying to get。

 it's trying really hard to get through this point。 But clearly， this point was just some noise。

 So this is what we call overfit。It's done a good job of fitting to our exact data points。

 But if we sample some more data points from this distribution。Honestly。

 we probably would suspect they're not going to be very close to this。

 particularly if they're a bit beyond the edges。So that's what overfitting looks like。

 We don't want underfitting or overfitting。 Now， underfitting is actually pretty easy to recognize because we can actually look at our training data and see that it's not very close。

Overfitting is a bit harder to recognize because the training data is actually very close。Now。

 on the other hand。Here's what happens if we fit the quadratic。

And here I've got both the real line and the fit line。 And you can see they're pretty close。

And that's， of course。What we actually want。So how do we tell whether we have something more like this。

Or something more like this。Well， what we do is we do something pretty straightforward is we take our original data set these points。

And we remove a few of them。 So let's say，20% of them。We then fit our model。Using only those points。

 we haven't removed。And then we measure how good it is。By looking at only the points we removed。

So in this case， let's say we had removed。嗯。I'm just trying to think if I had removed this point here。

Then it might have kind of gone off down over here。And so then when we look at how well it fits。

 we would say， oh， this one's miles away。The model the data that we take away and don't let the model see it when it's training is called the validation set。

So on first A I， we've seen the splitters before， right。

 The splitters are the things that separate out the validation set。Fast A。

 I won't let you train a model without a validation set。Fast A I always shows you your metrics。

 So things like accuracy measured only on the validation set。 So this is really unusual。

 most libraries。Make it really easy to shoot yourself in the foot by not having a validation set or accidentally not using it correctly。

 So fast A， I won't even let you do that。So you've got to be particularly careful when using other libraries Hing face transformers is good about this。

 so they make sure that they do show you your metrics on a validation set。Now。

 creating a good validation set is not generally as simple as just randomly pulling some of your data out of your model。

Out of the data that you pass that you train for your model。 The reason why is。

Imagine that this was the data you were trying to fit something to。 and you randomly remove some。

 So it looks like this。That looks very easy。Doesn't it。

 Because you've kind of like still got all the data you would want around the points。

 And in a time series like this， this says dates and sales。In real life。

 you're probably going to want to predict future dates。

 So if you credit your validation set by randomly removing stuff from the middle。

 it's not really a good indication of how you're got to be using this model。 Instead。

 you should truncate and remove the last couple of weeks。

So if this was your validation set and this is your training set。

 that's going to be actually testing whether you can use this to predict the future rather than using it to predict the past。

😊，嗯。Cagal competitions are a fantastic way to test your ability to create a good validation set。😊。

Because ca competitions only allow you to submit generally a couple of times a day。

The data set that you are scored on in the leader board during that time is actually only a small subset。

 in fact it's a totally separate subset to the one you'll be scored on on the end of the competition。

And so most beginners on kggle overfit。And it's not until you've done it that you will get that visceral feeling of like。

 oh my God， I overfit。In the real world， outside of Kale。

You will often not even know that you're overfit。You just destroy value of your organization。

 silently。So it's a really good idea to do this kind of stuff on kggle a few times first in real competitions to really make sure that you are confident you know how to avoid overfitting how to find a good validation set and how to interpret it correctly and you really don't get that until you screw it up a few times。

😊，AGood example of this was there was a distracted driver competition on Kagel。

 There are these kind of pictures。From inside a car。

And the idea was that you had to try and predict whether somebody was driving in a distracted way or not。

And on Kale， they did something pretty smart。 the test set。

 so the thing that they scored you on on the leaderboard contained people that didn't exist。At all。

 in the competition data that you train the model with。

So if you wanted to create an effective validation set in this competition。

 you would have to make sure that you separated the photos so that your validation set contained photos of people that aren't in the data you're training your model on。

There was another one like that， the Cagel Fisheries competition。Which had birds。That didn't appear。

 So they were basically pictures of boats。 you meant to try to guess。

 predict what fish were in the pictures。And it turned out that a lot of people accidentally figured out what the fish were by looking at the boat because certain boats tended to catch certain kinds of fish。

 And so by messing up their validation set， they were really overconfident of the accuracy of their model。

I'll mention in passing。If you've been around Kale a bit。

 you'll see people talk about cross validation a lot， I'm just going to mention be very。

 very careful。 Cross validation is explicitly not about building a good validation set。

 so you've got to be super， super careful if you ever do that。😊。

Another thing I'll mention is that Psyt Learnn conveniently offers something called train test split as does hugging face data sets。

 as does fast AI， we have something called random splitlitter， it can be。

Encourage you can almost feel like it's encouraging you to use a randomized validation set because there are these methods that do it for you。

 but yeah， be very， very careful because very， very often that's not what you want。😊，Okay。

 so you've learn what a validation set is。 So that's the bit that you pull out of your data that you don't train with。

 but you do measure your accuracy with。So what's a test set。It's basically another validation set。

But you don't even use it for tracking your accuracy while you build your model。Why not？Well。

 imagine you try two new models every day for three months。

 That's how long a capital competition goes for。So he would have tried 180 models。

And then you look at the accuracy on the validation set for each one。Some of those models。

 you would have got a good accuracy on the validation set， potentially because of pure chance。

 just a coincidence。And then you get all excited， and you submit that to Kackll。

 and you think you're gonna win the competition。😊，And ambassador。

 And that's because you actually overfit。Using the validation set。

So you actually want to know whether you've really found a good model or not。So in fact， on Kaggle。

 they have two two test sets。 They've got the one that gives you feedback on the leaderboard during the competition and a second data test set。

 which you don't get to see until after the competition is finished。😊，So， in real life。

You've got to be very careful about this not to try so many models during your model building process that you accidentally find one that's good by coincidence。

😊，And only if you have a test set that you've held out， well you know that。Now。

 that leads to the obvious question， which is very challenging。 I you spent three months。

Working on a model。Worked well on your validation set。

 you did a good job of locking that test set away and is safe。

 so you weren't allowed to use it and at the end of the three months。

 you finally checked it in the test set。And it's terrible。What do you do。Honestly。

 you have to go back to square 1。You know， there really isn't any choice other than starting again。

So this is tough， but it's better to know， right， Better to know than to not know。

 So that's what a test sets for。So you've got a validation set。 What are you going to do with it。

What you're gonna to do with a validation set is you're going to measure。Some metrics。

So a metric is something like accuracy。 It's a number that tells you how good is your model。

Now on Kale， this is very easy。What metric should we use。While they tell us。Go to overview。

 click on evaluation。And find out。 And it says， oh。

 we will evaluate on the Pearson correlation coefficient。Therefore。

 this is the metric you care about。So one obvious question is， is this the same as the lost function。

Is this the thing that we will take the derivative of？

And find the gradient and use that to improve our parameters during training。And the answer is。Maybe。

 sometimes。But probably not。For example， consider accuracy。Now。

 if we were using accuracy to calculate our derivative and get the gradient。

You could have a model that's actually slightly better。 You know。

's slightly like it's doing a better job of rec dogs and cats。

But not so much better that it's actually caused any。Incorrectly classified cat to become a dog。

So the accuracy doesn't change at all。So the gradient zero。You don't want stuff like that。

 You don't want bumpy functions because they don't have nice gradients。

 Often they don't have gradients at all。 They're basically zero， nearly everywhere。

You want and function。 that's nice and smooth。Something like， for instance。

 the average absolute error， mean absolute error， which we've used before。

So that's the difference between your metrics and your loss。 Now， be careful， right。

 because when you're training， your model is spending all of its time trying to improve the loss。

 and most of the time that's not the same as a thing you actually care about， which is your metrics。

 So you've got to keep those two different things in mind。The other thing to keep in mind。

Is that in real life。🤧Okay。You can't go to a website and be told what metric to use。In real life。

 the model that you choose， there isn't one number that tells you whether it's good or bad。

 and even if there was， you wouldn't be able to find it out ahead of time。In real life。

 the model you use is a part of a。Complex process， often involving humans。

 both as users and customers and as people， you know， involved in in as part of the process。

 there's all kinds of things that are changing over time。

 and there's lots and lots of outcomes of decisions that are made。

Who un metric is not enough to capture all of that。 Unfortunately， because it's so。Convenient。

To pick one metric and use that to say， I've got a good model that very often finds its way into into industry。

 into government。Where people roll out these things that are good on the one metric that happened to be easy to measure。

And again and again， we found。People's lives turned upside down because of how badly they get screwed up by models that have been incorrectly measured using a single metric。

So my partner Rachel Thomas， has written this article。

 which I recommend you read about the problem with metrics is a big problem。AI。U。

It's not just an AI thing。 There's actually this thing called Guhart's law that states when a measure becomes a target。

 it ceases to be a good measure。The thing is， so when I was a management consultant， you know。

20 years ago。We were always kind of part of these strategic things。

 trying to like find key performance indicators and ways to kind of you know set commission rates for salespeop。

 and we were really doing a lot of this like stuff， which was basically about picking metrics。And。

 you know， we see that happen go wrong in industry all the time。

AI is dramatically worse because AI is so good at optimizing metrics。

And so that's why you have to be extra， extra， extra careful about metrics。

When you are trying to use a model in real life。Anyway， as I said in Kale。

 we don't have to worry about any of that。We're going to use the Pearson correlation coefficient。

 which is all very well。 As long as you know what the hell the Pearson correlation coefficient is。🤧嗯。

If you don't， let's learn about it。So P S and correlation coefficient is usually a B V using letter R。

 and it's the most widely used measure of。How similar two variables are。

 And so if your predictions are very similar to the real values。

Then the Pearson correlation coefficient。Will be hi， and that's what you want。

R can be between -1 and1。-1 means you predicted exactly the wrong answer。

Which in a cha competition would be great because then you can just reverse all of your answers。

 and you'll be perfect。😊，Plus1 means you got everything exactly correct。Generally speaking。

 in courses or textbooks， when they teach you about the Pes and correlation coefficient。

 at that point， at this point， they will show you a mathematical function。

I'm not going to do that because that tells you nothing about the Pearson correlation coefficient。

 What we actually care about is not the mathematical function， but how it behaves。

And I find most people， even who work in data science。

 have not actually looked at a bunch of data sets to understand how R behaves。

 So let's do that right now so that you're not one of those people。

The best way I find to understand how data behaves in real life is to look at real life data so there's a data setsit Learn comes with a number of data sets and one of them is called California Housing and it's a data set where each row is a district。

And it's kind of demographic，'s sorry， It's information。

 demographic information about different districts。And about the value of houses。In that district。Um。

I'm not going to try to plot the whole things。 It's too big。

 And this is a very common question I have from people is。

 how do I plot data sets with far too many points。The answer is very simple。Detless points。

So I just randomly grab 1000 points。 Whatever you see with 1000 points is going to be the same as what you see with a million points。

 There's no point， no reason to plot huge amounts of data。 General。 Just grab a random sample。Now。

 nu has something called core co F to get the correlation coefficient between every variable and every other variable。

And it returns a matrix。So I can look down here So， for example。

 here is the correlation coefficient between variable 1 and variable 1。Which， of course。

 is exactly perfectly 1。0， right， because variable 1 is the same as variable 1。😊。

Here is the small inverse correlation between variable 1 and variable 2 and medium sized positive correlation between variable 1 and variable 3 and so forth。

This is symmetric about the diagonal， because the correlation between variable 1 and variable 8 is the same as the correlation between variable 8 and variable 1。

So， this is a。Correlation， coefficient matrix。So that's great when we wanted to get a bunch of values all at once for the Kagal competition we don't want that we just want a single correlation number if we just passed in a pair of variables。

 we still get a matrix。😊，Which is kind of weird。 It's kind of， that's not weird。

 but it's not what we want。 So we should grab one of these。

So when I want to grab a correlation coefficient， I'll just return the zero through first column。

So that's what core is。 That's going to be our single correlation coefficient。

So let's look at the correlation between two things。For example。MaMn income and medium house value。

67。 Okay， is that high medium。L， how big is that？ What does it look like。

So the main thing we need to understand is what these things look like。

 So what I suggest we do is we're going to take a。10 minute break，9 minute break。

 We'll come back at half past， and then we're going to look at some examples of correlation coefficients。

Okay， welcome back。So what I've done here is I've created a little function called show correlations。

Im to pass in a data frame in a couple of columns as strings。

 going to grab each of those columns as series。 Do us get a plot。And then show the correlation。

So we already mentioned medium income and medium house valuation。Of 0。68。 So here it is。

 here's what 0。68 looks like。 So you know， I don't know if you had some intuition about what you expected。

 but as you can see， it's still plenty of variation even at that reasonably high correlation。嗯。Also。

 you can see here that visualizing your data is very important if you are working with this data set。

 because you can immediately see all these dots along here， that's clearly truncation right。

 So this is like when it's not until you look at pictures like this that you're going to pick stuff like this。

😊，Pictures are great。Oh， little trick on this scatter plot。 I put Al is 0。5。

 That creates some transparency for these kind of scatter plots that's。

Really helps because it like kind of creates darker areas and places where there's lots of dots。 So。

 yeah， Al in scatter plots is nice。Okay， here's another pair。 So this one's gone down from 0。68 to 。

43 median income versus the number of rooms per house。As you would expect。More rooms。

It's more income。But this is a very weird looking thing。Now。

 you'll find that a lot of these statistical measures like correlation。

 rely on the square of the difference。And when you have big outliers like this。

 the square of the difference goes crazy。And so this is another place we you'd want to look at the data first and say。

 oh， that's。That's going to be a bit of an issue。 There's probably more correlation here。

 but there's a few examples of some houses with lots and lots of room where people that aren't very rich live。

 Maybe these are some kind of shared， shared accommodation or something。

So R is very sensitive to outlas。So let's get rid of the house the rooms with 15 rooms。

 the houses with 15 rooms or more。And now you can see it's gone up from 。43。To 068。

 even as though we probably only got rid of 1，2，3，4，5，6， even only got rid of 7 data points。

So we're gonna be very careful of outliers。 And that means if you're trying to win a ca competition。

😊，Where the metric is correlation。 and you just get a couple of rows really badly wrong。

 Then that's going to be a disaster to your score。 right。

 So you've got to make sure that you do a pretty good job of every row。😊。

So that's what a correlation of 0。68 looks like。Okay， here's a correlation of 034。

 And this is kind of interesting， isn't it， because  point。34。Sounds like quite a good relationship。

 but you almost can't see it。So this is something I strongly suggest as if you're working with a new metric is draw some pictures。

😊，Of a few different levels of that metric to kind of try to get a feel for like， what does it mean。

 You know， what does 06 look like， What does 。3 look like and so forth。

And here's an example of a correlation of minus0。2。Thiss very slight， negative slope。Okay。

 so there's just more of a kind of a general tip of something I like to do when playing with a new metric。

 And I recommend you do as well。 I think we've now got a sense of what the correlation feels like。

 Now， you can go look up the equation on Wikipedia if you're into that kind of thing。😊。

We need to report the correlation after each epoch。

 because we want to know how our training is going。

Hugging face expects you to return a dictionary because it's going to use the keys of the dictionary to like label each metric。

 So here's something that gets the correlation。And。Returns it as a dictionary， with the label。

 Pearson。Okay， so we've done metrics。 We've done our training validation。Split。Oh。

 we might have actually skipped over the bit where we actually did the split today。I did。

 So to actually do the split。Because in this CAgle competition。

 I've got another notebook we'll look at later where we actually split this properly。

 but here we're just going to do a random split just to keep things simple for now of 25% of the data will be our validation set。

So if we go DSs train test split。It returns a data deck。Which has a train and a test。

So that looks a lot like a data sets object in FA AI， very similar idea。

So this will be the thing that we'll be able to train with。

 So it's going to train with this data set and return the metrics on this data set。

 This is really a validation set， but。Hing face。Data sets calls it test。Okay。

 we're now ready to train our model in Fast D A， we use something called a learner。

 The equivalent in hugging face transformers is called trainer。 So we'll bring that in。😊。

Something we'll learn about quite shortly is the idea of mini batches and batch sizes， in short。

 each time we pass some data to our model for training。

 it's going to send through a few rows at a time to the GPU so that it can calculate those in parallel。

Those bunch of rows is called a batch or a mini batch。

 and the number of rows is called the batch size。So here we're gonna set the batch size to 128。

Generally speaking， the larger your batch size， the more it can do in parallel at once and it'll be faster。

 but if you make it too big， you'll get an out of memory error on your GPU。So， you know。

 it's a bit of trial and error to find a batch size that works。Epochs， we've seen before。

Then we've got the learning rate we'll talk in the next lesson unless we get to this lesson about a technique to automatically find a or semi me automatically find a good learning rate。

 we already know what a learning rate is from the last lesson I played around and found one that seems to train quite quickly without falling apart。

So I just try it a few。嗯。Generally， I kind of， you know if I don't have a so hacking face transformers doesn't have something to help you find the learning rate。

 the integration we're doing in fast DIA will let you do that。

 but if you're using a framework that doesn't have that。

 you can just start with a really low learning rate and then kind of double it and keep doubling it Angel it falls apart。

Hing face transformers uses this thing called training arguments。

 which is a class we just provide all of the kind of configuration。 So you have to。

Tell it what your learning rate is。This stuff here is the same as what we call basically fit one cycle in fast AI。

You always want this to be true because it's going to be faster， pretty much。

And then this stuff here， you can probably use exactly the same every time。

 there's a lot of boilerplate compared to fast eye， as you see。嗯。This stuff。

 you can probably use the same every time。 Okay， so。We now need to create our model。

 so the equivalent of the vision learner function that we've used to automatically create a reasonable vision model in hug face transformers。

 they've got lots of different ones depending on what you're trying to do so we're trying to do classification as we've discussed of sequences。

So if we call auto model for sequence classification。

 it we'll create a model that is appropriate for classifying sequences from a pretrained model。

 and this is the name of the model that we did earlier the deerta V3。

It has to know when it adds that random matrix to the end， how many outputs it needs to have。

 So we have one label， which is the square。So that's going to create our model。

 And then this is the equivalent of creating a learner。 It contains a model。😊，And the data。

The training data and the test data。 again， there's a lot more boilerplate here than fast AI。

 but you can kind of see the same basic steps。 So here。

 we just have to do a little bit more manually， but it's not， you know， it's nothing too crazy。

So it's going to tokenise it for us using that function。

 And then these are the matrix metrics that will print out each time。

 That's that little all function we created， which returns the dictionary。😊，嗯。At the moment。

 I find hugging face transformers very verse。 It spits out lots and lots and lots of text。

 which you can ignore。😊，And we can finally call train， which will spit out much more text again。

 which you can ignore。And as you can see， the trains， it's printing out the loss。

And he is our pieing correlation coefficient。So it's training。 And we've got a 。834 correlations。

 That's pretty cool， right， I mean。😊，It took， I doesn't actually say but it does took here we are five minutes to run。

 maybe that's five minutes per epoch on kle， which doesn't have particularly great GPUs。

 but good for free。 And we've got something that is you know got a very high level of correlation in assessing how similar the two columns are。

And the only reason it could do that is because it used a pre trained model。 right。

 There's no way you could just have that tiny amount of information and figure out whether those two columns are very similar。

This pre trained model already knows a lot about language。

 It already has a good sense of whether two phrases are similar or not， and we've just fine tuned it。

 You can see given that after one epoch， it was already at 0。8。You know。

 this was a model that already did something pretty close。To what we needed。

 it didn't really need that much extra tuning for this particular task。We've got any questions there。

 John。Yeah， we do It's actually a bit back on the topic before where you were showing us the visual interpretation of the Pearson coefficient and you were talking about outliers and we've got a question here from Kevin asking。

How do you decide when it's okay to remove outliers， like you pointed out some in that data set？

And clearly， your model is going to train a lot better if you clean that up。But。

 I think Kevin's point here is， you know， those kinds of outliers will probably exist in the test set as well。

 So I think he's just looking for some practical advice on。

 on how you handle that in a more general sense。So， outliers。Should never just be。Removed。

 like for modeling。So if we take the example of the California housing data set， you know。

 if I was really working with that data set in real life， I would be saying， oh， that's interesting。

It seems like there's a separate group of districts with a different kind of behaviour。 Yeah。

 my guess is that they're got to be kind of like dorms or something like that， you know。

 probably low income housing。And so I would be saying like， oh。Clearly from looking at this data set。

 these two different groups can't be treated the same way。 They have very different behaviours。

 and I would probably split them into two separate analyses。You know， they word outlier。

And it kind of exists in a statistical sense， right。

 there can be things that are well outside our normal distribution and mess up our kind of metrics and things。

 It doesn't exist in a real sense。 It doesn't exist in a sense of like， oh。

 things that we should like ignore or throw away。You know。

 some of the most useful kind of insights I've had in my life in data projects has been by。

Thinkicking into outliers， so called outlayers and understanding， well。

 what are they and where did they come from？And it's kind of often in those edge cases that you discover really important things about where processes go wrong or about kinds of behaviours you didn't even know existed。

 or indeed about know kind of labeling problems or process problems which you really want to fix them at the source because otherwise when you go into production。

 you're going to have more of those so- called outlays。So yeah， I would say never。Deelete。

Outlayers without investigating them and having a strategy for like understanding where they came from and like。

 what should you do about them。Alright， so now that we've got a trained model。

You'll see that it actually behaves， you know， really a lot like a fast A eye learner。 And， you know。

 hopefully， the impression you'll get from going through this process is。

Largely a sense of familiarity。 with like， oh， yeah， this looks。Like stuff I've seen before。

 you know， like a bit more wordy and some slight changes， but it really is very。

 very similar to the way we've done it before。 because now that we've got a trained trainer rather than learner。

 we can call predict。And now， we're going to pass in。Our data set from the Cagal test file。

And so that's going to give us how predictions。Which we can cast af float。And here they are。

So here are the predictions we made。Of similarity。Now， again， not just for your inputs。

 but also for your outputs， always look at them always， right， And interestingly。

 I looked at quite a few。Cackle notebooks from other people for this competition。

And nearly all of them had the problem we have right now， which is。

Negative predictions and predictions over one。So I'll be showing you how to fix this in more。

Proper way， maybe hopefully in the next lesson。But for now， you know。

 we could at least just round these off right because we know that none of the scores are going to be bigger than one not smaller than zero。

 so our correlation coefficient will definitely improve if we at least round this up to zero and round this down to one。

As I say， there are better ways to do this， but that's certainly better than nothing。So in paytorch。

 you might remember from when we looked at R， there's a thing called clip。

And that will clip everything under 0 to 0 and everything over one to one。And so， now that looks。

Much better。So here's our predictions。So CaggL expects submissions to generally be in a CSV file。

And hacking face data sets it kind of looks a lot like pandas。 really。

 we can create our submission file from with our two columns called CSV。And。There we go。

That's basically it。So。Yeah， you know， it's， it's， it's kind of nice to say how。😊，You know。

 it's the sense how far deep learning has come since we started this course a few years ago that that nowadays。

 you know， there are multiple libraries around to kind of do this the same thing。 we can， you know。

Use them in multiple application areas。 They all look kind of pretty familiar。

 They're reasonably beginner friendly。 And N LP， because it's kind of like。

The most recent area that's really become effective in the last year or two is probably where the biggest opportunities are。

For。You know， big wins， both in research and commercialization。嗯。

And so if you're looking to build a startup， for example， one of the key things that Vcs look for。

 you know， that they'll ask is like， oh。Why now， you know， why， Why would you build this company now。

 And， of course， you know， with N LP， the answer is really simple。 It's like， it can often be like。

 well。Until last year， this wasn't possible， you know。

 where it took 10 times more time or it took 10 times more money or whatever。

So I think NOP is a huge opportunity area。Okay， so。It's。

We thinking about both use and misuse of modern NLP。And I want to show you a subredit。

 Here is a conversation on a subredit from a couple of years ago。

 I'll let you have a quick read of it。So the question I want you to be thinking about is。

 what subdit do you think this comes from， this debate about military spending？And the answer is。

 it comes from a subredit that posts automatically generated conversations between G P2 G2 models。

Now， this is like a totally previous generation of model。 They're much， much better now。

 So even then， you could see these models were generating context appropriate。Believable。Prose。嗯。

You know， I would strongly believe that like。Any of our kind of like。

Our a tier of competent fast AI alumni would be fairly easily able to create a bot which could create context appropriate prose on。

Twitter or Facebook groups or whatever。 you know， arguing for a side of an argument。

 And you could scale that up such that 99% of Twitter was these bots， and nobody would know。You know。

 nobody would know。And that's。Very worrying to me， because a lot of。嗯。You know。

 a lot of kind of the way people see the world is now really coming out of their。

 their social media conversations， which at this point， they're they're controllable。

 Like it would not be that hard to create something that's kind of optimized towards。

Moving a point of view amongst a billion people， you know， in a very subtle way。

 very gradually over a long period of time by multiple bots each pretending to argue with with each other and one of them getting the upper hand and so forth。

嗯。Here is the start of a article in the Guardian， which I'll let you read。

This article was quite long， these are just the first few paragraphs。



![](img/1c5c667c817ee17d60af73a391b9d3b3_1.png)

And at the end， it explains that this article was written by G 3。It was given the instruction。

 Please write a short up around 500 words， keep the language simple and concise。

 focus on why humans have nothing to fear from Ao。So Jputy3 produced eight outputs and then they say basically the editors at the Guardian did about the same level of editing that they would do for humans。

 in fact they found it a bit less editing required than a humans so you know again。

 like you can create longer pieces of context appropriate prose designed to argue a particular point of view。

What kind of things might this be used for， You know， we won't know probably for decades， if ever。

 but sometimes we get a clue based on older technology。 Here's something from back 2017 and the pre。

Kind of deep learning in our pays。There were millions of submissions to the F TC about the net neutrality situation in America。

Very， very heavily biased towards the point of view of saying we want to get rid of net neutrality。

An analysis by Jeff C showed that something like 99% of them。 and in particular。

 nearly all of the ones which were pro removal in net neutrality were clearly auto generated。

 by basically， if you look at the green， there's like selecting from a menu。 So we got Americans。

 as opposed to Washington bureaucrats deserve to enjoy the services they desire。  individualss。

 as opposed to Washington bureaucrats should be as little people like me。

 as opposed to so called experts。 And you get the idea。 Now， this is an example of。A very， very。

 you know， simple approach to auto generating huge amounts of text。We don't know for sure。

 but it looks like this might have been successful because this went through， you know。

 despite what seems to be actually overwhelming。Disagreement from the public that everybody。

 almost everybody likes net neutrality， the FTC got rid of it。

 and this was a big part of the basis was like， oh。

 we got all these comments from the public and everybody said they don't want net neutrality。

So I imagine a similar thing where you absolutely couldn't do this。

 you couldn't figure it out because everyone was really very compelling and very different that's。

 you know， it's kind of worrying about how we deal with that。😊，You。

 I will say when I talk about this stuff， often people say， oh， no worries， we'll be able to model。

To recognize。You know， bot generated content。But， you know， if I put my black hat on， I'm like。

 that's not going to work。 right， If you told me to build something that beats the bot classifiers。

 I'd say no worries， it's easy。You know， I will take the the code or the surface or surface。

 whatever that does the bot classifying， and I will include beating that in my loss function。

 and I will fine in my model until it beats the bot classifier。 You know。

 when I used to run an email company， we had a similar problem with spam prevention。

And O spamers could always take a spam prevention algorithm and change their emails until it didn't get the spam prevention algorithm anymore。

 for example。嗯。So yeah， Im， I'm really excited about the opportunities for， for。😊。

Students in this course， to build。You know， I think。Very valuable businesses。

 really cool research and so forth using these pretty new N LP techniques that are now pretty accessible。

😊，And I'm also really worried about the things that might go wrong。 I do think， though。

 that the more people that understand these capabilities， the less chance they'll go wrong。 John。

 was there some questions。Yeah， I mean， it's a throwback to the workbook that you had before。



![](img/1c5c667c817ee17d60af73a391b9d3b3_3.png)

Yeah， that's so。 The question Manan is asking， shouldn't nu labels be 5。00。250。50。751。

 instead of one， isn't the target a categorical， or are we considering this as a regression problem。

 Yeah， it's a good question， so。There's one label because there's one column。U。

Even if this was being treated as a categorical problem with five categories。

 it's still considered one label。In this case， though， we're actually。嗯。

Treating it as a regression problem。 It is one of the things that's a bit tricky。

 I was try to figure this out just the other day。 It's not documented as far as I can tell。

 But on the Huging F transformers website。 But if you pass in one label。

To auto model for sequence classification， it turns it into a regression problem。

 which is actually why we ended up with。Predictions that were less than 0 when and bigger than one。

 so。We'll be learning next time about the use of sickigoid functions to resolve this problem。

 And that should， that should fix it up for us。Okay， great。 Well， thanks everybody。

 I hope you enjoyed learning about NLP as much as I enjoyed putting this together。

 I'm really excited about it and can't wait for next week's lesson。 See。😊。



![](img/1c5c667c817ee17d60af73a391b9d3b3_5.png)