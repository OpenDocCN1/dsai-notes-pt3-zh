# LLM训练营 - 2023年春季 LLM Bootcamp - Spring 2023 - P2：-02-LLM Foundations (LLM Bootcamp).zh_en - GPT中英字幕课程资源 - BV1Wf421B7mP

🎼，🎼，All right， I'm going to get started I'm going to talk about。



![](img/852ad884d0e10a4e3ff4251a6291c576_1.png)

4 things。Lun is in an hour。

![](img/852ad884d0e10a4e3ff4251a6291c576_3.png)

嗯。I'm going to speed around some key ideas and just machine learning。 we have a diverse audience。

 we have machine learning experts and research scientists we also have。



![](img/852ad884d0e10a4e3ff4251a6291c576_5.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_6.png)

Executives and investors that have never trained a logistic regression or anything like that。



![](img/852ad884d0e10a4e3ff4251a6291c576_8.png)

We're going to talk about the transformer architecture。



![](img/852ad884d0e10a4e3ff4251a6291c576_10.png)

We're going to talk about notable LLMs you might have heard of。



![](img/852ad884d0e10a4e3ff4251a6291c576_12.png)

You know， a little thing called GPT， there's also other ones like T5。

 Brch and chillla and so on that you should probably know。



![](img/852ad884d0e10a4e3ff4251a6291c576_14.png)

And we'll talk about some just details of running a transformer。



![](img/852ad884d0e10a4e3ff4251a6291c576_16.png)

So the foundations of machine learning this， I expect this to be。



![](img/852ad884d0e10a4e3ff4251a6291c576_18.png)

Not needed for most of you。I still think it's worth sharing because for some of you。

 it is needed and also just to get on the same page about what's happening。



![](img/852ad884d0e10a4e3ff4251a6291c576_20.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_21.png)

You know， softwareft 1。0 and Andre Kpathy's terminology。



![](img/852ad884d0e10a4e3ff4251a6291c576_23.png)

Is traditional programming right where a person writes basically a robot that then takes input and produces output and the robot is entirely algorithmic so you know the person has to specify all possible edge cases for the input。



![](img/852ad884d0e10a4e3ff4251a6291c576_25.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_26.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_27.png)

And have a robust test with the output， and so on。With Soft 2。0 mindset。

 which is the machine learning mindset。

![](img/852ad884d0e10a4e3ff4251a6291c576_29.png)

The person。

![](img/852ad884d0e10a4e3ff4251a6291c576_31.png)

rs a robot that then takes a bunch of training data and produces another robot that that's going to take input data and produce an output。



![](img/852ad884d0e10a4e3ff4251a6291c576_33.png)

And you can't really test that second one becauses that second robot is not algorithmic。

 it's now driven by a bunch of parameters。

![](img/852ad884d0e10a4e3ff4251a6291c576_35.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_36.png)

That you don't really have much visibility and you only have visibility into your training system。

 so that really changes the mindset of what's actually happening。



![](img/852ad884d0e10a4e3ff4251a6291c576_38.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_39.png)

What type of machine learnings are there？There's unsupervised learning。

 it's like generative AI used to find structure in the data to generate more data。



![](img/852ad884d0e10a4e3ff4251a6291c576_41.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_42.png)

They supervised learning， which you get some data as input and you produce something that looks a little different as output。

 usually a label for that input data。

![](img/852ad884d0e10a4e3ff4251a6291c576_44.png)

Or maybe a prediction about what's going to come next。



![](img/852ad884d0e10a4e3ff4251a6291c576_46.png)

And then you have reinforcement learning which you have agents that act in an environment。

 they collect rewards， learn to act， and these have traditionally been pretty separate but。



![](img/852ad884d0e10a4e3ff4251a6291c576_48.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_49.png)

They mostly converged on just。

![](img/852ad884d0e10a4e3ff4251a6291c576_51.png)

Really it iss just supervised learning， sometimes called self supervised learning。



![](img/852ad884d0e10a4e3ff4251a6291c576_53.png)

Where you can formulate everything is just a supervised problem。

 So if you're doing generative problems， you can formulate it as this first bit of data。



![](img/852ad884d0e10a4e3ff4251a6291c576_55.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_56.png)

Is labeled with the continuation of the data， so that's kind of supervised formulation。



![](img/852ad884d0e10a4e3ff4251a6291c576_58.png)

And then reinforcement learning， you can formulate as given the state of the world。

 what is the next move that would collect the most rewards， you don't have to do anything special。

 you can just treat it as supervised learning。

![](img/852ad884d0e10a4e3ff4251a6291c576_60.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_61.png)

To a computer， inputs and outputs are always just numbers。



![](img/852ad884d0e10a4e3ff4251a6291c576_63.png)

And that's kind of important to remember because we might see something like this。 I mean。

 it really isn't a photograph， but we definitely see it as a photograph of Abe Lincoln。



![](img/852ad884d0e10a4e3ff4251a6291c576_65.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_66.png)

And then we read output， and it's really just a bunch of letters。

 but we have meaning to the word Lincoln， a machine doesn't have any of that， right。

 they just see a bunch of numbers。

![](img/852ad884d0e10a4e3ff4251a6291c576_68.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_69.png)

And then they see some other numbers that are token vocabulary IDs。



![](img/852ad884d0e10a4e3ff4251a6291c576_71.png)

So everything is just a vector or a matrix of numbers to a machine learning computer。



![](img/852ad884d0e10a4e3ff4251a6291c576_73.png)

And we ask it to predict things about the natural world why is that hard。

 Well there's an infinite variety of inputs that all can mean the same thing。

 so let's say people are talking about a movie they watched， someone might say you know。

 I love the movie， that's pretty easy to interpret they used the word love and movie。

 but then someone else might say you know as good as the godfather。



![](img/852ad884d0e10a4e3ff4251a6291c576_75.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_76.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_77.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_78.png)

Now you need to know like is the godfather another movie would this person consider it to be a good movie and so on。

 or you know someone might just say something unintelligible to you。

 but it might mean the same thing and the computer has to learn all of that。



![](img/852ad884d0e10a4e3ff4251a6291c576_80.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_81.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_82.png)

And meaningful differences can be very tiny， so like you know。

 these muffins really do look like Chihuahuas but。

![](img/852ad884d0e10a4e3ff4251a6291c576_84.png)

Very different in function。

![](img/852ad884d0e10a4e3ff4251a6291c576_86.png)

And the structure of the world is complex even if。You have a face recognizer。



![](img/852ad884d0e10a4e3ff4251a6291c576_88.png)

And you trained it on well lit faces， but now you're in this dramatic lighting setting and you only see half to face it might totally fail。

 and it's because there's physical structure to how the image is formed。



![](img/852ad884d0e10a4e3ff4251a6291c576_90.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_91.png)

That。Just makes everything way more complex than it seems like it should be。



![](img/852ad884d0e10a4e3ff4251a6291c576_93.png)

But how is it done？So there's many methods for machine learning through the years。

 the simplest one is called logistic regression， probably learned that in some college course。



![](img/852ad884d0e10a4e3ff4251a6291c576_95.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_96.png)

In the '90s， people you support vector machines。

![](img/852ad884d0e10a4e3ff4251a6291c576_98.png)

There's decision trees that people do for tabular data a lot， like the XGBose library。



![](img/852ad884d0e10a4e3ff4251a6291c576_100.png)

But one approach to machine learning really is dominant nowadays， and that's neural networks。



![](img/852ad884d0e10a4e3ff4251a6291c576_102.png)

And it's also called deep learning。嗯。

![](img/852ad884d0e10a4e3ff4251a6291c576_104.png)

And the inspiration for that comes from the brain， which is like the one thing that we know to be really intelligent in the world。



![](img/852ad884d0e10a4e3ff4251a6291c576_106.png)

People started working on this in the 40s and the 50s。



![](img/852ad884d0e10a4e3ff4251a6291c576_108.png)

T a look of what the brain is doing， it's composed of a bunch of neurons。

 and neuron receives electrical inputs on one end， and if there's enough input to the neuron。

 then it fires and sends。

![](img/852ad884d0e10a4e3ff4251a6291c576_110.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_111.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_112.png)

Its output down to other neurons。

![](img/852ad884d0e10a4e3ff4251a6291c576_114.png)

And the brain itself has inputs like through my vision and my senses and outputs like me speaking or moving。



![](img/852ad884d0e10a4e3ff4251a6291c576_116.png)

And the formalization that people came up with is that they decided to represent the neuron as this model called the perceptron。



![](img/852ad884d0e10a4e3ff4251a6291c576_118.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_119.png)

Which has inputs coming in， which are just numbers， and the numbers get multiplied by some weights。



![](img/852ad884d0e10a4e3ff4251a6291c576_121.png)

If the sum of the weighted inputs is past some kind of threshold。

 then the neuron the perceptron fires， in a sense， that's modeled with a step function mathematically。



![](img/852ad884d0e10a4e3ff4251a6291c576_123.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_124.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_125.png)

And then to create a brain， you take a bunch of perceptrons。

And you stack them in layers and you connect every perceptron and one layer to every perceptron。

 the next layer， and that's called the multilayer perceptron， and it's kind of like a brain。Now。

 how is it stored to in a machine， it's just a vector of numbers right so like what's important about the perceptron are the weights。



![](img/852ad884d0e10a4e3ff4251a6291c576_127.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_128.png)

And that's just what are the things you're multiplying inputs by？



![](img/852ad884d0e10a4e3ff4251a6291c576_130.png)

And then a layer of perceptrons is then a matrix of numbers。



![](img/852ad884d0e10a4e3ff4251a6291c576_132.png)

And the whole neural network is a set of matrices of numbers。And we call these parameters。

 so parameters of the neural network are just all the perceptron weights inside of that network。



![](img/852ad884d0e10a4e3ff4251a6291c576_134.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_135.png)

Or sometimes you call them weights as well。And all the neural network operations are just matrix multiplications for this reason。



![](img/852ad884d0e10a4e3ff4251a6291c576_137.png)

And one thing people figured out is that GPUs， which were developed for graphics like video games。

 are really fast at matrix multiplications， neural networks are just doing matrix multiplications。

 so that kicked off the deep learning revolution when people applied GPUs to actually running neural networks。



![](img/852ad884d0e10a4e3ff4251a6291c576_139.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_140.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_141.png)

How do you train in neural own network， so let's say you have big X data， so maybe it's images。

 maybe it's text。

![](img/852ad884d0e10a4e3ff4251a6291c576_143.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_144.png)

And you have labels why， so like labels like cat and a dog。



![](img/852ad884d0e10a4e3ff4251a6291c576_146.png)

Do you take a little batch？Sometimes called a mini batch of data， little X。



![](img/852ad884d0e10a4e3ff4251a6291c576_148.png)

You use your current model， so you use your current neural network。

 which starts out with just random weights。

![](img/852ad884d0e10a4e3ff4251a6291c576_150.png)

To run the x kind of through the network and outcomes of prediction， so it's called that y prime。

 we'll compute what's known as a loss function on the ground truth label Y and the prediction y prime。



![](img/852ad884d0e10a4e3ff4251a6291c576_152.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_153.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_154.png)

The most。You know， prevalent loss is the cross entropy loss， which sounds complicated。

 but it really is just this function。

![](img/852ad884d0e10a4e3ff4251a6291c576_156.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_157.png)

Multiply the ground truth by the log of the predictions and you sum it up。



![](img/852ad884d0e10a4e3ff4251a6291c576_159.png)

And then that gives you。

![](img/852ad884d0e10a4e3ff4251a6291c576_161.png)

Some numbers that you then what's known as bat propagate through all the layers of the model。

 This is too complicated to go into。

![](img/852ad884d0e10a4e3ff4251a6291c576_163.png)

But basically。

![](img/852ad884d0e10a4e3ff4251a6291c576_165.png)

You just think of the network worth pushing a prediction， if the prediction is correct。

 it gets signaled that the parameters are great， if the prediction is not correct。

 it gets signaled that the parameters need to be adjusted in the direction of making the predictions more correct。



![](img/852ad884d0e10a4e3ff4251a6291c576_167.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_168.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_169.png)

And then you repeat that until your loss stops decreasing essentially。



![](img/852ad884d0e10a4e3ff4251a6291c576_171.png)

And in order to actually do machine learning you always split your data into a training set。

 a validation set and a test set， the training set is the largest。

 why do you need the validation set because you might overfit so if you train too much。

 the parameter might you know the network might be really good on just your training data。

 but actually it becomes worse than it used to be on the validation data so we kind of look at the validation loss and when that stops improving that's when stop training。



![](img/852ad884d0e10a4e3ff4251a6291c576_173.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_174.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_175.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_176.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_177.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_178.png)

Or maybe we set some hyper parametersameter about the model， such as how many layers does it have。

 how many or like what activation function doesnt have？



![](img/852ad884d0e10a4e3ff4251a6291c576_180.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_181.png)

And the test set should really be left alone as much as possible， and it's really for measuring。



![](img/852ad884d0e10a4e3ff4251a6291c576_183.png)

How your train model is going to work in production。

 So it's like you shouldn't be looking at the test that。

 You should only look at it basically once when you're done。



![](img/852ad884d0e10a4e3ff4251a6291c576_185.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_186.png)

And all of this applies to your experimentation with prompts too。

 so if you're not doing traditional machine learning。

 it's not like you have to forget about the validation set。



![](img/852ad884d0e10a4e3ff4251a6291c576_188.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_189.png)

You really should be having this mindset。

![](img/852ad884d0e10a4e3ff4251a6291c576_191.png)

Even if you're not doing like if you don't have a loss function。

 but you're just kind of looking at some prompts。

![](img/852ad884d0e10a4e3ff4251a6291c576_193.png)

And you're trying to figure out which one's better。

 there's still that notion of a validation set and a potentially a test set。



![](img/852ad884d0e10a4e3ff4251a6291c576_195.png)

Some more terminology， pre training you might hear， so that just basically means training。

 like training a large model on a lot of data。

![](img/852ad884d0e10a4e3ff4251a6291c576_197.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_198.png)

And the reason it's called pre training is because oftentimes you would take that large model。



![](img/852ad884d0e10a4e3ff4251a6291c576_200.png)

And then train it a little bit more with less data。

And that's called fine tuning and the reason you do that is because maybe you have a lot of label data in just general internet imagery like liquor style images。

 but you don't have a lot of data in。

![](img/852ad884d0e10a4e3ff4251a6291c576_202.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_203.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_204.png)

You know， medical imaging， Xrays or something， but you might train a model on just flickr images and then fine tune it on your medical images。

 and it'll work better than if you only trained on the medical images。



![](img/852ad884d0e10a4e3ff4251a6291c576_206.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_207.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_208.png)

People share pre trained models， thankfully， there's a number of model hubs。



![](img/852ad884d0e10a4e3ff4251a6291c576_210.png)

Hugging face is the most popular。

![](img/852ad884d0e10a4e3ff4251a6291c576_212.png)

It has 180，000 models， and last time I gave this lecture， they only had like I think， 90，000 models。



![](img/852ad884d0e10a4e3ff4251a6291c576_214.png)

And they have 30，000 data sets and last time was like you know。

 a year or two ago and they only had like 5，000 data sets。

 so they growing very rapidly and they have models for anything you might。



![](img/852ad884d0e10a4e3ff4251a6291c576_216.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_217.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_218.png)

Want to do machine learning。And before around 2020。



![](img/852ad884d0e10a4e3ff4251a6291c576_220.png)

Like that might mean that each type of model in the model hub is its own neural network architecture。

 like people would use convolutional neural networks for computer vision。

 if they would use recurrent neural networks for national language processing。



![](img/852ad884d0e10a4e3ff4251a6291c576_222.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_223.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_224.png)

They would have special things for reinforcement learning and so on。



![](img/852ad884d0e10a4e3ff4251a6291c576_226.png)

But。Nowadays， basically a transformer model is all that's used for all kinds of machine learning tasks。



![](img/852ad884d0e10a4e3ff4251a6291c576_228.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_229.png)

So the transformer architecture came out of a paper called attentiontention is All You need from 2017。

 and attention is all you need today， you don't really need the wF， you know， you just pay attention。



![](img/852ad884d0e10a4e3ff4251a6291c576_231.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_232.png)

嗯。

![](img/852ad884d0e10a4e3ff4251a6291c576_234.png)

And they formulate an architecture that set state of the art results on translation tasks。

 that's kind of all they applied to， but then other people quickly started applying the same architecture to like other NLP tasks。

 be state of the art on those。

![](img/852ad884d0e10a4e3ff4251a6291c576_236.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_237.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_238.png)

And then vision and so on。But it looks pretty complicated when you like see the whole diagram。

 but it's actually just like two of the same thing like there's two halves to it that are basically the same so we're just going to look at one half of it。



![](img/852ad884d0e10a4e3ff4251a6291c576_240.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_241.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_242.png)

That's called the decoder。So the overview of the transformer decoder。



![](img/852ad884d0e10a4e3ff4251a6291c576_244.png)

Is。In this exposition， let's say the task is to complete text just like GPT models are doing。



![](img/852ad884d0e10a4e3ff4251a6291c576_246.png)

So if you see text， like the ground truth text is like it's a blue sundress。



![](img/852ad884d0e10a4e3ff4251a6291c576_248.png)

For whatever reason that's like text that the model is being trained on right now。

 so you would see it's a blue and the task is to predict the word sunras。



![](img/852ad884d0e10a4e3ff4251a6291c576_250.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_251.png)

嗯。The inputs down here on the bottom。

![](img/852ad884d0e10a4e3ff4251a6291c576_253.png)

It's not going to be text， it's going to be a sequence of tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_255.png)

So like it's a blue。And the output is going to be a probability distribution over the potential next token。



![](img/852ad884d0e10a4e3ff4251a6291c576_257.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_258.png)

So the input is a sequence of vectors， the output is a vector that's a probability distribution。



![](img/852ad884d0e10a4e3ff4251a6291c576_260.png)

And to run inference， which means like to get results out of this network。



![](img/852ad884d0e10a4e3ff4251a6291c576_262.png)

What we're going to do is we're going to take that probability distribution。

 sample an actual token from it。

![](img/852ad884d0e10a4e3ff4251a6291c576_264.png)

Then appended to the inputs， so let's say we sampled the word， it's a blue。

 but we sampled the word house， so now we have the input， it's a blue house。



![](img/852ad884d0e10a4e3ff4251a6291c576_266.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_267.png)

And then we're going to run that through the model again。

 see the probability distribution over the next token， sample it， append it and so on。



![](img/852ad884d0e10a4e3ff4251a6291c576_269.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_270.png)

And that's how that's how Chad GPT is doing what it's doing， it's seeing what you typed。

 then its sample to the next wordd， it offendends it， samples the next word and so on。



![](img/852ad884d0e10a4e3ff4251a6291c576_272.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_273.png)

So in more detail， the inputs need to be vectors of numbers。



![](img/852ad884d0e10a4e3ff4251a6291c576_275.png)

And so we have text， how do we turn text into vectors of numbers？



![](img/852ad884d0e10a4e3ff4251a6291c576_277.png)

So first we turn it into tokens。This is the actual tokenization that GPT Free is doing。



![](img/852ad884d0e10a4e3ff4251a6291c576_279.png)

So there's like the start sequence token， it， apostroppy S， a blue， sun， rest， and so on。

So each one of those tokens we'll talk about in a second。

 or we'll talk about how this tokenization was found a little later。

 but for now just like this is what it is， and each one is actually an ID right in a vocabulary。

 it's not a word， it's just a number。

![](img/852ad884d0e10a4e3ff4251a6291c576_281.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_282.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_283.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_284.png)

And furthermore， it's not actually just a number。 it's actually a vector。

 and you can represent a number as a vector with this thing called one hotencod。



![](img/852ad884d0e10a4e3ff4251a6291c576_286.png)

So like the number three， you can represent by an all zero vector that has one in the third position and zero is everywhere else。



![](img/852ad884d0e10a4e3ff4251a6291c576_288.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_289.png)

And that could be the input to our network。

![](img/852ad884d0e10a4e3ff4251a6291c576_291.png)

That we could just go with this。

![](img/852ad884d0e10a4e3ff4251a6291c576_293.png)

But we're going to do something different， a little bit different， which is called embedding。



![](img/852ad884d0e10a4e3ff4251a6291c576_295.png)

So the reason we're doing this is because one hot factories are bad representations of words or tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_297.png)

So like the word cat is going to have vocabular ID， you know， 30。

 the word kitten is going to have vocabular ID， you know 32 or something。

 but the distance between them is as large as the distance between the word cat and any other word in the vocabulary。

 so there's no notion of similarity of any token。

![](img/852ad884d0e10a4e3ff4251a6291c576_299.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_300.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_301.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_302.png)

And there's a simple solution to us， which is we can learn an embedding matrix。

 which takes your one hot vocabulary coding and embeds it。



![](img/852ad884d0e10a4e3ff4251a6291c576_304.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_305.png)

Into something that is a dense vector of your choice or like of the dimensionalities of your choice。



![](img/852ad884d0e10a4e3ff4251a6291c576_307.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_308.png)

So let's say if your voculary size is like 30，000。

![](img/852ad884d0e10a4e3ff4251a6291c576_310.png)

You can turn that into an embedding size of like 512 and all you have to do is just learn a matrix that's size 30。

000 by 512， and this is like the simplest neural network layer type。



![](img/852ad884d0e10a4e3ff4251a6291c576_312.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_313.png)

That's kind of all you need to understand is like we're turning boards into dance embeddings。



![](img/852ad884d0e10a4e3ff4251a6291c576_315.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_316.png)

We're going to send those embeddings into the model。

 I'm going to skip position encoding for now and go into this。



![](img/852ad884d0e10a4e3ff4251a6291c576_318.png)

Msaskked multihead attention， but we're going to ignore the words masked and multihead for now。

 we're just going to talk about attention。

![](img/852ad884d0e10a4e3ff4251a6291c576_320.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_321.png)

So the key insight of attention is as tokens come into the。



![](img/852ad884d0e10a4e3ff4251a6291c576_323.png)

，The model， remember the task is to predict the most likely next token we're seeing some previous tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_325.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_326.png)

But they're not all equally important to what the next token should be， right like。



![](img/852ad884d0e10a4e3ff4251a6291c576_328.png)

There's some things that just very closely follow previous tokens and there's some things at the beginning of the sentence that don't even matter to like what you're going to predict next。



![](img/852ad884d0e10a4e3ff4251a6291c576_330.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_331.png)

So this notion of attention was introduced in 2015 for translation tasks。



![](img/852ad884d0e10a4e3ff4251a6291c576_333.png)

And in translation， let's say we're translating English to French。



![](img/852ad884d0e10a4e3ff4251a6291c576_335.png)

And in the English， the agreement on the European E area was signed。



![](img/852ad884d0e10a4e3ff4251a6291c576_337.png)

In August 1992， so the word signed like to predict the word signed。



![](img/852ad884d0e10a4e3ff4251a6291c576_339.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_340.png)

What do you actually need to know about the previous sequence， which is in French。



![](img/852ad884d0e10a4e3ff4251a6291c576_342.png)

You don't really care V was sign。But what you do care is like。

 how do you say signed in French because we're translating French to English？



![](img/852ad884d0e10a4e3ff4251a6291c576_344.png)

So in French， there's Ete sier。

![](img/852ad884d0e10a4e3ff4251a6291c576_346.png)

Which it's just like you know it's like the past tense of signed and in English it's just was signed。

 but the word signed itself already is past tense so you don't actually need even the word was so you can kind of see why it was useful for translation。

 but the idea is very general。

![](img/852ad884d0e10a4e3ff4251a6291c576_348.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_349.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_350.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_351.png)

And the formalization is like， let's say you have a sequence of vector x。



![](img/852ad884d0e10a4e3ff4251a6291c576_353.png)

And you have an output sequence of vectories。And each output vector is going to be a weighted sum of the inputs。



![](img/852ad884d0e10a4e3ff4251a6291c576_355.png)

And the weights。

![](img/852ad884d0e10a4e3ff4251a6291c576_357.png)

Are going to be just the dot products between the input vectors。

 There's no learning at all right now。 We're just saying we have to produce some outputs。

 All we have are inputs。

![](img/852ad884d0e10a4e3ff4251a6291c576_359.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_360.png)

each output is going to be sum of the inputs， but we're going to weight the sum by basically that product。

 which is kind of like similarity between the input batteriesies。



![](img/852ad884d0e10a4e3ff4251a6291c576_362.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_363.png)

And to make it nice， we're just going to make the weight sum to one， but it's not very important。



![](img/852ad884d0e10a4e3ff4251a6291c576_365.png)

So looking graphically， this is a figure from Lucas Be's Transformers lecturer。



![](img/852ad884d0e10a4e3ff4251a6291c576_367.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_368.png)

嗯。You know， we have input vectors and。

![](img/852ad884d0e10a4e3ff4251a6291c576_370.png)

We're producing output。Let's say y sub I。 So what we're going to do is we're going to take the vector x sub I that。

 you know， I part of the input and kind of like。

![](img/852ad884d0e10a4e3ff4251a6291c576_372.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_373.png)

Nott product it with all the other inputs。

![](img/852ad884d0e10a4e3ff4251a6291c576_375.png)

And then the value of the dot product is going to be our attention weight。



![](img/852ad884d0e10a4e3ff4251a6291c576_377.png)

So now we have an attention weight。A little vector。

 and then we're going to apply that attention weight again to the inputs to this time sum them up and produce the output。



![](img/852ad884d0e10a4e3ff4251a6291c576_379.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_380.png)

That's kind of all that's happening here's another view of this， this is from Peter Gloom。



![](img/852ad884d0e10a4e3ff4251a6291c576_382.png)

So we're producing output y sub 2， and what we're going to do is sum the weighted inputs， so x of 1。

 x of 2 x of 3 x of 4。

![](img/852ad884d0e10a4e3ff4251a6291c576_384.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_385.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_386.png)

And the weight for each one is going to be as described and what we can notice is that every input。



![](img/852ad884d0e10a4e3ff4251a6291c576_388.png)

iss used in three different ways， so it's used as a query， so for like y sub2。

 the vector x sub2 is used as the query and it gets compared to the keys。

 which are all the other input vectors。

![](img/852ad884d0e10a4e3ff4251a6291c576_390.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_391.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_392.png)

And then that produces the weight and then the weight is multiplied by the values and then summed up to produce the output。

 so each input vector plays three different roles in the course of this attention mechanism as a query as a key to some other query and then as a value to be summed up to the output。



![](img/852ad884d0e10a4e3ff4251a6291c576_394.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_395.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_396.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_397.png)

And that's fine and dandy， but like why do we do this and also there's like no like it might help。

 but it might not help， there's no learning involved so far。



![](img/852ad884d0e10a4e3ff4251a6291c576_399.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_400.png)

So what we're going to do is we're going to project the inputs into different roles。

 project means you take a vector you multiply by a matrix。

 now you have a different vector that's like you can think of it as like being rotated or stretched or both in some space。



![](img/852ad884d0e10a4e3ff4251a6291c576_402.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_403.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_404.png)

And so what we're going to do is we take the input projected one way to be the query。

 another way to be the key， and a third way to be the value。



![](img/852ad884d0e10a4e3ff4251a6291c576_406.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_407.png)

And graphically you know you have your inputs， you might actually even change the dimension of them。

 right so it's like you might have。

![](img/852ad884d0e10a4e3ff4251a6291c576_409.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_410.png)

Four dimensional vectors coming in， but the projection makes them eight dimensional in practice this isn't really done for GPT style models。

 but it could be done。

![](img/852ad884d0e10a4e3ff4251a6291c576_412.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_413.png)

And。The key thing here is like now we have three matrices that we can learn and once we learn them。

 we've basically learned a good way to do attention。



![](img/852ad884d0e10a4e3ff4251a6291c576_415.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_416.png)

What does it mean to be multihead attention？So we can learn simultaneously。



![](img/852ad884d0e10a4e3ff4251a6291c576_418.png)

Several different ways of transforming inputs into queries， keys and values。



![](img/852ad884d0e10a4e3ff4251a6291c576_420.png)

So here's like three headed of de tension。 And we're showing the query matrix。

 So there's like three different ones that。

![](img/852ad884d0e10a4e3ff4251a6291c576_422.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_423.png)

We can do simultaneously。When we actually implement it in the math。

 it's just a single matrix anyway so its。

![](img/852ad884d0e10a4e3ff4251a6291c576_425.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_426.png)

It seems more scary than it is。And then the last thing is masked， why are we masking attention？



![](img/852ad884d0e10a4e3ff4251a6291c576_428.png)

So I talked about inference， but in training， what we have is a sequence of tokens。

 like it's a blue and then it's kind of blanked out。



![](img/852ad884d0e10a4e3ff4251a6291c576_430.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_431.png)

And then we have the ground truth outputs， which is like we know it's supposed to be at the blue sundress。

 so we actually started a blue sundress and blinked out。



![](img/852ad884d0e10a4e3ff4251a6291c576_433.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_434.png)

And that's our ground truth outputs， the actual outputs of the model are probability distributions over potential tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_436.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_437.png)

So。Crucially the thing to understand is probability all of the outputs are computed at the same time。

 so it's like I put in the sequence and I produce the potential outputs for every sub sequenceequence at the same time。



![](img/852ad884d0e10a4e3ff4251a6291c576_439.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_440.png)

So， like。If I'm predicting the word A， I should only see the word it's。

 if I'm predicting the word blue， I should see it's a blue。

 and then if I'm predicting the word sundress， I should see it's a blue sun dress。



![](img/852ad884d0e10a4e3ff4251a6291c576_442.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_443.png)

And so that means that when I'm predicting the wordsdra or when I'm predicting the word blue。

 I shouldn't see future things， I should only see the things that have already happened。



![](img/852ad884d0e10a4e3ff4251a6291c576_445.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_446.png)

In the input， so instead of the full self attention， we have this mask self attention。

 which is limited to just the part of the input that's already been seen。

 it's implemented by multiplying the attention weight matrix by just a mask matrix。



![](img/852ad884d0e10a4e3ff4251a6291c576_448.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_449.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_450.png)

And。Conceptually， what's this doing？

![](img/852ad884d0e10a4e3ff4251a6291c576_452.png)

So like a token comes in。It gets augmented in some way with like previously seen tokens that seem relevant。



![](img/852ad884d0e10a4e3ff4251a6291c576_454.png)

So the previously scene means math is like the math part， the seem relevant。

 that's the learned attention part。

![](img/852ad884d0e10a4e3ff4251a6291c576_456.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_457.png)

And then we do this in several ways simultaneously， that's the multiple head part。



![](img/852ad884d0e10a4e3ff4251a6291c576_459.png)

And the thing that's kind of counterintuitive is actually there's no notion of position so far and there's a notion of what you've seen。

 what you haven't seen， but inside of what you have seen。



![](img/852ad884d0e10a4e3ff4251a6291c576_461.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_462.png)

There's no ordering。And so that's where the positional encoding comes in。



![](img/852ad884d0e10a4e3ff4251a6291c576_464.png)

So if you look at these equations， there's no order anywhere。

 it's like you just have a bag of vectories and you're producing and you're just summing them up。



![](img/852ad884d0e10a4e3ff4251a6291c576_466.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_467.png)

But if you see like something like this movie is great。

 it's exactly the same as any other permutation of that。



![](img/852ad884d0e10a4e3ff4251a6291c576_469.png)

So a trick to fix that is like。

![](img/852ad884d0e10a4e3ff4251a6291c576_471.png)

We're going to add special position encoding vectories to our embedding vectories。

And it seems like it shouldn't work， but like it really is that simple。

 there's some complication as to how you。

![](img/852ad884d0e10a4e3ff4251a6291c576_473.png)

How do you like formulate these position en coding vectors， but you can do it like very。



![](img/852ad884d0e10a4e3ff4251a6291c576_475.png)

You don't have to do anything very complicated， you could just like have a incrementing vector that you just add。



![](img/852ad884d0e10a4e3ff4251a6291c576_477.png)

And the magic of attention figures out that it should pay attention to the position if it's relevant。



![](img/852ad884d0e10a4e3ff4251a6291c576_479.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_480.png)

Then when stuff comes out of the attention， we're going to add it up and norm it。



![](img/852ad884d0e10a4e3ff4251a6291c576_482.png)

So the adding part is like you see all those arrows that go around the attention block。



![](img/852ad884d0e10a4e3ff4251a6291c576_484.png)

So that is often called a skip connection or a residual connection。

 and basically we want to like the output， we want to not only go through the module。

 like the attention module， but we also just want to add a little bit of the original input。



![](img/852ad884d0e10a4e3ff4251a6291c576_486.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_487.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_488.png)

And the reason we do this is because when we backdrop。

 we're going to go through all of the arrows backwards。



![](img/852ad884d0e10a4e3ff4251a6291c576_490.png)

And the fact that we can go around a layer is quite nice because we can propagate the loss all the way from the end of the model back to the first layer of the model。



![](img/852ad884d0e10a4e3ff4251a6291c576_492.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_493.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_494.png)

And by the way， this is possible because we're not changing the dimension of the output， it's always。

 it's all the same shape， so it's like the input embedding determines the dimension of this whole transformer model。



![](img/852ad884d0e10a4e3ff4251a6291c576_496.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_497.png)

And then the later norm is。Like basically the motivation is neural nets learn the best when everything is。

 has uniform mean and standard deviation。

![](img/852ad884d0e10a4e3ff4251a6291c576_499.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_500.png)

But as you actually apply these matrices to your inputs。

 the means and standard deviations get blown out。

![](img/852ad884d0e10a4e3ff4251a6291c576_502.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_503.png)

And so normalization is like。It's a hack where you basically take things and you just reset them back to a uniform mean and standard deviation。



![](img/852ad884d0e10a4e3ff4251a6291c576_505.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_506.png)

And you do that between every operation。It seems inelegant。

 which is why I think it took people a while to start doing it， but once you start doing it。

 it's very effective。

![](img/852ad884d0e10a4e3ff4251a6291c576_508.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_509.png)

And then the feed forward layer is like that standard multi layerer perceptron that I showed you in the beginning with just one hidden layer。



![](img/852ad884d0e10a4e3ff4251a6291c576_511.png)

And the conceptual view is like the token that's been augmented with other relevant tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_513.png)

Comes into this few forward layer and it like upgrades its representation。

 so that's like the best intuition I have about it like。



![](img/852ad884d0e10a4e3ff4251a6291c576_515.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_516.png)

You know， if you start out at word level， then okay， we're going to mix with other words we've seen。

 now we're going to go into the feed forward layer and like upgrade to something more like thoughts or something like more semantic meaning than the nominal meaning of the words。



![](img/852ad884d0e10a4e3ff4251a6291c576_518.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_519.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_520.png)

And then this whole thing gets repeated a number of times。



![](img/852ad884d0e10a4e3ff4251a6291c576_522.png)

Like in the GPT3 model， for example， it ranges from 12 layers to 96 layers of this transformer layer。



![](img/852ad884d0e10a4e3ff4251a6291c576_524.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_525.png)

There's also the embedding dimension that you can change。

And then there's the number of attention heads。

![](img/852ad884d0e10a4e3ff4251a6291c576_527.png)

In practice， I think people scale， I'm saying。People scale all these hyperparameter together。

 so it's like if you're increasing the number layers。

 you're also going to increase the dimension of the number of attention heads。



![](img/852ad884d0e10a4e3ff4251a6291c576_529.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_530.png)

For GP3 being famously 175 billion parameters， 96 layers， 12，000 embedding dimension。

 96 attention heads。

![](img/852ad884d0e10a4e3ff4251a6291c576_532.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_533.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_534.png)

And another thing to think about is like。Those 175 billion parameters。



![](img/852ad884d0e10a4e3ff4251a6291c576_536.png)

How how are they distributed between the types of operations。



![](img/852ad884d0e10a4e3ff4251a6291c576_538.png)

And if it's that large， it's mostly the feed forward layer that takes up the weights。

 but for a small network like this GPPT3 small， a large part of the weights is also the embedding and the attention itself。



![](img/852ad884d0e10a4e3ff4251a6291c576_540.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_541.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_542.png)

So why does this work so well？So Andrea has a great tweet that says the transformformers magnificent neural network architecture。



![](img/852ad884d0e10a4e3ff4251a6291c576_544.png)

Because it's a general purpose differentiable computer， it is expressive in the forward pass。

 it's optimizable via back， and it's efficient because everything is happening in parallel。



![](img/852ad884d0e10a4e3ff4251a6291c576_546.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_547.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_548.png)

There's some lines of work try to figure out exactly how expressive the transformer is。

 a cool result is this ra。

![](img/852ad884d0e10a4e3ff4251a6291c576_550.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_551.png)

Brasp paper， which is basically a programming language that should be implementable inside of a transformer。



![](img/852ad884d0e10a4e3ff4251a6291c576_553.png)

So they like the example on the right here。

![](img/852ad884d0e10a4e3ff4251a6291c576_555.png)

Is like a two layer transformer network that reverses strings。



![](img/852ad884d0e10a4e3ff4251a6291c576_557.png)

And they wrote it as this programming language， but it can actually compile down to like transformer weights that'll execute that。



![](img/852ad884d0e10a4e3ff4251a6291c576_559.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_560.png)

Every time and there's the inverse problem is like， well， given the way it's。

 can we decompile it to a program？

![](img/852ad884d0e10a4e3ff4251a6291c576_562.png)

And the answer is no， we don't know how to do that yet。



![](img/852ad884d0e10a4e3ff4251a6291c576_564.png)

And we actually mostly just don't understand what the transformer is doing。



![](img/852ad884d0e10a4e3ff4251a6291c576_566.png)

Some people are trying most notably anthropic and you should check out their grade blog posts if you're interested。

 so like induction heads is an interesting result。

![](img/852ad884d0e10a4e3ff4251a6291c576_568.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_569.png)

Where like one thing they observed is as you add multiple layers of attention or sorry。

 multiple heads of attention。

![](img/852ad884d0e10a4e3ff4251a6291c576_571.png)

You can notice this thing where' like。

![](img/852ad884d0e10a4e3ff4251a6291c576_573.png)

You know， like the。The model basically figures out how to use the second head。



![](img/852ad884d0e10a4e3ff4251a6291c576_575.png)

And。And。

![](img/852ad884d0e10a4e3ff4251a6291c576_577.png)

There's other interesting blog posts。So， you know， you might have a question like， okay。

 should I be able to code this up？

![](img/852ad884d0e10a4e3ff4251a6291c576_579.png)

I don't think it's necessary， right， especially if it's just building kind of AI power products。



![](img/852ad884d0e10a4e3ff4251a6291c576_581.png)

But it's fun， it's not that difficult， it's probably worth doing the reason I say it's not that difficult is because of this beautiful man who recorded a bunch of YouTube videos that really walk you through it。



![](img/852ad884d0e10a4e3ff4251a6291c576_583.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_584.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_585.png)

And the final， you know， G2 reimation is like less than 400 lines of code， including。



![](img/852ad884d0e10a4e3ff4251a6291c576_587.png)

His own attention block， his own MLP block and so on。



![](img/852ad884d0e10a4e3ff4251a6291c576_589.png)

And there's more resources， I want to get through some notable large language models。

So let's start with three easy pieces。There's Bt。There's t 5。And there's GP。

And these kind of cover the gamut of。Large transformer models。Bert was the first one to be。



![](img/852ad884d0e10a4e3ff4251a6291c576_591.png)

To be popularized， it stands for bidirectional andr representation from transformers。



![](img/852ad884d0e10a4e3ff4251a6291c576_593.png)

So this is actually taking just the encoder part of the transformer。

 which is the same as what we covered， except the attention is not masked。

 which means that in order to produce the output。

![](img/852ad884d0e10a4e3ff4251a6291c576_595.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_596.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_597.png)

The transformer is actually allowed to look at the entire sequence。

 not just the sequence that precedes the output。

![](img/852ad884d0e10a4e3ff4251a6291c576_599.png)

It's large for the times， but not large by current standards， but is 100 million parameters。



![](img/852ad884d0e10a4e3ff4251a6291c576_601.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_602.png)

And what they did is they took some corpus of text。

 they masked out about 15% of all words just randomly。



![](img/852ad884d0e10a4e3ff4251a6291c576_604.png)

And then they trained it on this task of like。

![](img/852ad884d0e10a4e3ff4251a6291c576_606.png)

You know， predict the mask words correctly。

![](img/852ad884d0e10a4e3ff4251a6291c576_608.png)

And this was great and you now it's stated， but at the time was very useful and it kind of became a building block that you could build other NLP applications on top of。



![](img/852ad884d0e10a4e3ff4251a6291c576_610.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_611.png)

Thats the first step。T5 is the first or T5。

![](img/852ad884d0e10a4e3ff4251a6291c576_613.png)

Took that transformer architecture from the original 2017 paper。



![](img/852ad884d0e10a4e3ff4251a6291c576_615.png)

And applied it to a somewhat new task， which is。

![](img/852ad884d0e10a4e3ff4251a6291c576_617.png)

The text， the text transfer。So that means that both the input and the output are text strings and the text string actually encodes the task to be done in the string。

 so if you look at the bottom here， it says like translate EN to DE， so English to German。



![](img/852ad884d0e10a4e3ff4251a6291c576_619.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_620.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_621.png)

This is good， and then the output would be like Du' Coth。



![](img/852ad884d0e10a4e3ff4251a6291c576_623.png)

Or the task might be summarized and then a paragraph to summarize。



![](img/852ad884d0e10a4e3ff4251a6291c576_625.png)

And so on， so this innovation of just like encoding the task in the actual input string and then just thinking of everything as just translation essentially。

 but you don't have to be limited to translating languages。

 you can just translate input strings to output strings in all kinds of ways。



![](img/852ad884d0e10a4e3ff4251a6291c576_627.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_628.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_629.png)

And they tested a bunch of architectures， they founded that the encoder decoder actually was the best for them。

 it was large 11 billion parameters， and this's actually still a contender like there's you know more updated T5s released and it's a great choice for fine tuning potentially。



![](img/852ad884d0e10a4e3ff4251a6291c576_631.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_632.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_633.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_634.png)

What it was trained on is something called the colossal Queen crawled corpus， sea4。



![](img/852ad884d0e10a4e3ff4251a6291c576_636.png)

They started with Common crawl， which is like a nonprofit that just crawls the internet。

 makes it available。

![](img/852ad884d0e10a4e3ff4251a6291c576_638.png)

10 billion web pages。

![](img/852ad884d0e10a4e3ff4251a6291c576_640.png)

But they filtered it down to like around 160 billion tokens， which is a line。



![](img/852ad884d0e10a4e3ff4251a6291c576_642.png)

By discarding short pages， removing offensive wars and pages。



![](img/852ad884d0e10a4e3ff4251a6291c576_644.png)

Interestingly， removing things that had。

![](img/852ad884d0e10a4e3ff4251a6291c576_646.png)

codeode。So if they had any code on the page， they would remove the whole page。

And then they deuplicated it because they don't want the same data more than once。



![](img/852ad884d0e10a4e3ff4251a6291c576_648.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_649.png)

And then they fine tuned it or like trained it later on some academic supervised tasks。



![](img/852ad884d0e10a4e3ff4251a6291c576_651.png)

For a bunch of NLP tasks。GPT is the third easy piece， which is the generative pretrain transformer。

 and this one is decoder only， so Bt was encodeder only， this ones decoder only。

 so it uses a mass attention and because it's predicting the next token， it's what we covered。



![](img/852ad884d0e10a4e3ff4251a6291c576_653.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_654.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_655.png)

The largest GPT2 model was 1。5 billion。

![](img/852ad884d0e10a4e3ff4251a6291c576_657.png)

And it was trained on。

![](img/852ad884d0e10a4e3ff4251a6291c576_659.png)

Not common crawl because they thought it was just too noisy。

 so they formed their own data called webtex。

![](img/852ad884d0e10a4e3ff4251a6291c576_661.png)

Where they scraped links from Reddit that had at least three phharma。

 which was like probably a useful link。

![](img/852ad884d0e10a4e3ff4251a6291c576_663.png)

And then you duplicated it， some heuristic filtering， but it was 8 million documents or so。



![](img/852ad884d0e10a4e3ff4251a6291c576_665.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_666.png)

And I want to talk about the encoding， so how does the GPT tokenize so this is how it actually does it。

 there's like a tokenizer on the openAI website。

![](img/852ad884d0e10a4e3ff4251a6291c576_668.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_669.png)

So one things you might notice is like some words map to one token， but some don't。



![](img/852ad884d0e10a4e3ff4251a6291c576_671.png)

And then a Uniicode character is representable， but it's like a lot of tokens for some reason。



![](img/852ad884d0e10a4e3ff4251a6291c576_673.png)

And the numbers are interestingly tokenized at the bottom where it's like one，2。

3 is it's actually its own token， and then 45 is its own token。



![](img/852ad884d0e10a4e3ff4251a6291c576_675.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_676.png)

So。This is a middle ground called by pair andcoing。

 it's a middle ground between old school tokenization where you would take each ward and tokenize it and throw out wards that like weren't frequent enough。

 replace them with a special like out of vocabulary token。



![](img/852ad884d0e10a4e3ff4251a6291c576_678.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_679.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_680.png)

And。the goal tokenization would be just to use UTF aid bytes。

 which just doesn't work empirically you know wasn't found to work。

 so the middle ground is you merge some frequently occurring things and you set tokens for them。

 but you're able to fall back to like bytes if you need to。



![](img/852ad884d0e10a4e3ff4251a6291c576_682.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_683.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_684.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_685.png)

UGPT3 came out in 2020 and it was just like GPT2， like the architecture is exactly the same。

 but it was 100 times larger。

![](img/852ad884d0e10a4e3ff4251a6291c576_687.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_688.png)

And because it was so much larger， it started exhibiting these abilities of like fu shot learning。

 which was。

![](img/852ad884d0e10a4e3ff4251a6291c576_690.png)

Not that surprising， but also zeroroshot learning where you could just describe the task and then it would be able to do a really good job doing it。



![](img/852ad884d0e10a4e3ff4251a6291c576_692.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_693.png)

And it seemed like it was just getting better and better， the more parameters you added。



![](img/852ad884d0e10a4e3ff4251a6291c576_695.png)

And。And it definitely is better the more examples if you give it。

 but it's also pretty good with just zero shot examples。



![](img/852ad884d0e10a4e3ff4251a6291c576_697.png)

It was trained on。

![](img/852ad884d0e10a4e3ff4251a6291c576_699.png)

The original web text corpus， but also just the raw common Cr filtered down and also a selection of books from some。



![](img/852ad884d0e10a4e3ff4251a6291c576_701.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_702.png)

Sketchy sources and then all of Wikipedia。

![](img/852ad884d0e10a4e3ff4251a6291c576_704.png)

And it's interesting to look at what the top page is。

In the web text and the Common crawl data sets are。



![](img/852ad884d0e10a4e3ff4251a6291c576_706.png)

So for the web text， it's a bunch of new sites， it's like Huffington Post， New York Times， BBC。

 Twitter， the Guardian。

![](img/852ad884d0e10a4e3ff4251a6291c576_708.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_709.png)

And then for Common C， it's a lot of patents for some reason， then a bunch of news。

 but also some papers like science papers。

![](img/852ad884d0e10a4e3ff4251a6291c576_711.png)

Okay， in total 500 billion tokens， they only trained on 300 billion tokens so they actually didn't even see this whole corpus in training。

 so that's another counterintuitive thing about those LLM training is actually only see each data point once。



![](img/852ad884d0e10a4e3ff4251a6291c576_713.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_714.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_715.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_716.png)

That's not quite true if it's kind of sampled， but like。

The the mindset is like you're only seeing something once， you get one shot to predict on it。



![](img/852ad884d0e10a4e3ff4251a6291c576_718.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_719.png)

And for GPG4， we don't really know what's going on because given both the competitive landscape and the safety implications。

 there are no further details about the architecture chair。



![](img/852ad884d0e10a4e3ff4251a6291c576_721.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_722.png)

or the data set construction or the training method or anything like that。

 but it's safe to assume that it's pretty large because that's the trend like the more computation you use to train these AI systems。

 the better they get。

![](img/852ad884d0e10a4e3ff4251a6291c576_724.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_725.png)

And people keep training larger and larger ones。

![](img/852ad884d0e10a4e3ff4251a6291c576_727.png)

And that points to the bitter lesson of Rich Sutton， who's a reinforcement learning professor。



![](img/852ad884d0e10a4e3ff4251a6291c576_729.png)

Which is basically like no matter how hard you try to come up with like cool math and algorithms and stuff。

 you're going to get beat by so much just stacking more layers。



![](img/852ad884d0e10a4e3ff4251a6291c576_731.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_732.png)

And。And you know that。

![](img/852ad884d0e10a4e3ff4251a6291c576_734.png)

That is bitter。But we can still do some science so like what exactly is the relationship between increasing the model size and the amount of compute and increasing the data set size？

So scientists at Deep Mind set out to answer this with a paper called trainingining Compute Optimal LLMs。



![](img/852ad884d0e10a4e3ff4251a6291c576_736.png)

Wwhich is commonly known as Chinchilla， because that's the name of the model that they eventually trained。

 but what they did is they came up with formulas for like answering the question if I had a fixed compute budget。



![](img/852ad884d0e10a4e3ff4251a6291c576_738.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_739.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_740.png)

How should I distribute it， should I add more parameters to my model。

 or should I train a smaller model on more data or just go through the data more at times。



![](img/852ad884d0e10a4e3ff4251a6291c576_742.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_743.png)

And what they found is that like most LLMs in literature had too many parameters for the amount of data that they saw。



![](img/852ad884d0e10a4e3ff4251a6291c576_745.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_746.png)

And so to capitalize on this， they trained this Chinchilla model， which was only 70 billion。

 and they showed that it actually beat the performance of a model four times the size called Gopher。

 but what happened is that it was four times smaller but it saw four times more data。

 it was trained on like 1。4 trillion tokens。

![](img/852ad884d0e10a4e3ff4251a6291c576_748.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_749.png)

Whereas all the other models were only chain on 300 billion。



![](img/852ad884d0e10a4e3ff4251a6291c576_751.png)

Why 300 billion because that was the GPT3 paper and everyone else just just started， you know。

 they just wanted to replicate GPT3 so they only did 300 billion。



![](img/852ad884d0e10a4e3ff4251a6291c576_753.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_754.png)

I'm not sure。But note that this is still actually not even going through all the data that we have。

 you could keep training it and having the model see the data over and over again。



![](img/852ad884d0e10a4e3ff4251a6291c576_756.png)

It might help， I think that's kind of an open question right now。



![](img/852ad884d0e10a4e3ff4251a6291c576_758.png)

So Lama came out recently as an open source， Chinchilla Optimal LLM from meta Research。



![](img/852ad884d0e10a4e3ff4251a6291c576_760.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_761.png)

They released。Several sizes。From 7 billion to 65 billion， and all of them saw at least1ill tokens。



![](img/852ad884d0e10a4e3ff4251a6291c576_763.png)

And the benchmark competitively against GPT3 and other state of the art LLMs。



![](img/852ad884d0e10a4e3ff4251a6291c576_765.png)

It is open source， but it's non commercial license for the weights。For the pretrain weights。



![](img/852ad884d0e10a4e3ff4251a6291c576_767.png)

What was it trained on， it was trained on。

![](img/852ad884d0e10a4e3ff4251a6291c576_769.png)

You know， like a custom common crawl filtering， C4。



![](img/852ad884d0e10a4e3ff4251a6291c576_771.png)

GitHub。Wikipedia， some books， some scientific papers。



![](img/852ad884d0e10a4e3ff4251a6291c576_773.png)

And recently was replicated this data set was replicated by an effort called Retajama。

 which is also training models to replicate Lama。

![](img/852ad884d0e10a4e3ff4251a6291c576_775.png)

But what's interesting here is like GitHub， why is GitthHub in here？



![](img/852ad884d0e10a4e3ff4251a6291c576_777.png)

So why would we include code in the training data because remember like T5 paper actually removed code from the training data。

 but now we're adding it again like 5% of the total training data。



![](img/852ad884d0e10a4e3ff4251a6291c576_779.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_780.png)

So I think the answer is just empirically， people found that when you include code。

 it actually improves。

![](img/852ad884d0e10a4e3ff4251a6291c576_782.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_783.png)

Performance on non code tasks。 I think open AI found this with their codex model。

 which is the first model where they trained it on some code。 but then they。



![](img/852ad884d0e10a4e3ff4251a6291c576_785.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_786.png)

They actually started with GPT3， so they trained GPT3， then they fine tune it on code。

 and they saw that it was good on code， but it was actually better on like reasoning tasks than GPT3 was。



![](img/852ad884d0e10a4e3ff4251a6291c576_788.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_789.png)

And so since then， people have been adding code， there's an open source data set called the stack。



![](img/852ad884d0e10a4e3ff4251a6291c576_791.png)

And it's all from GitHub basically， but they try to respect licenses。

So check it out if you interested， and then there's another important part to this LLM story。

 which is instruction tuning。

![](img/852ad884d0e10a4e3ff4251a6291c576_793.png)

so。The when GPT3 was published， people were kind of their minds were blown just by few shots。

 like the fact that you can produce。

![](img/852ad884d0e10a4e3ff4251a6291c576_795.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_796.png)

Or provide some examples of what you want， and then the model just kind of gets it and starts doing it that is cool。

 it's also sometimes called in context learning。But the mindset is really like text completion。

 right it's like you're completing what I've already started。



![](img/852ad884d0e10a4e3ff4251a6291c576_798.png)

But by now and by the time a Chad GPT release， the mindset is that things should be zero shot。

 so it's like I shouldn't have to provide examples。

 I should just say what I want the model to do and then I should figure out how to do it。



![](img/852ad884d0e10a4e3ff4251a6291c576_800.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_801.png)

And so that's the instruction following mindset。

![](img/852ad884d0e10a4e3ff4251a6291c576_803.png)

And the way we got from text completion to instruction following is with supervised fine tuning。

 so if we want the model to do a good job on stuff like this like zeroshot tasks。

 then we need that in the data， but there's very little text on the internet that's like of this form。



![](img/852ad884d0e10a4e3ff4251a6291c576_805.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_806.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_807.png)

So what we can do is we can gather our own data of zeroshot inputs and like great outputs。



![](img/852ad884d0e10a4e3ff4251a6291c576_809.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_810.png)

And。And then fine tune the prechain model on the data。



![](img/852ad884d0e10a4e3ff4251a6291c576_812.png)

And profit， and that's exactly what OpenI started doing。

They hired thousands of contractors to gather this data。



![](img/852ad884d0e10a4e3ff4251a6291c576_814.png)

They published the paper about。

![](img/852ad884d0e10a4e3ff4251a6291c576_816.png)

Doing that and also doing it even more advancedly with reinforcement learning。



![](img/852ad884d0e10a4e3ff4251a6291c576_818.png)

I don't think we need the details， not very important。

 but basically like once you train the model with this reinforcement learning from human feedback。

 it becomes much better at following instructions than the base GPT model。



![](img/852ad884d0e10a4e3ff4251a6291c576_820.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_821.png)

And so they released that as text Da Vincis years02。



![](img/852ad884d0e10a4e3ff4251a6291c576_823.png)

Chad GT was like further reinforcement learning trained on not even just zeroshot task。

 but like whole conversations。

![](img/852ad884d0e10a4e3ff4251a6291c576_825.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_826.png)

And introduces this chatl format where you have like user and assistant messages and special system message。



![](img/852ad884d0e10a4e3ff4251a6291c576_828.png)

And kind of interesting to think about the GT lineage， so like GT3 came out of 2020。

 it's called Da Vinci。

![](img/852ad884d0e10a4e3ff4251a6291c576_830.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_831.png)

And then open， I experimented trained it on code that became the codeX models。



![](img/852ad884d0e10a4e3ff4251a6291c576_833.png)

Like the Code Da Vinci 001。

![](img/852ad884d0e10a4e3ff4251a6291c576_835.png)

And they also experimented with instruction tuning。

 so that became instructive Vinci beta and text of Vinci001。



![](img/852ad884d0e10a4e3ff4251a6291c576_837.png)

And then they kind of realized that like they really need to see a lot of code even in the pre training。

 and so they trained code Da Vinci002， this is all congesure by the way， it's not like for sure。



![](img/852ad884d0e10a4e3ff4251a6291c576_839.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_840.png)

But it's both language model abilities and code generation abilities， venue you instruction tu。

 and then you can further find tune for kind of。

![](img/852ad884d0e10a4e3ff4251a6291c576_842.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_843.png)

Like standard GPT applications or specifically for Cha GT applications。



![](img/852ad884d0e10a4e3ff4251a6291c576_845.png)

But fine chain is not free， it's really great， but it imposes what's called an alignment tax。



![](img/852ad884d0e10a4e3ff4251a6291c576_847.png)

Which is that the zero shot ability increases， but the fu shot learning ability probably decreases。



![](img/852ad884d0e10a4e3ff4251a6291c576_849.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_850.png)

And the model's confidence and its answers also becomes less well calibrated。

 So you can kind of think of it as like。

![](img/852ad884d0e10a4e3ff4251a6291c576_852.png)

The base model。

![](img/852ad884d0e10a4e3ff4251a6291c576_854.png)

Before fine tuning。Is。

![](img/852ad884d0e10a4e3ff4251a6291c576_856.png)

Kind of knows what it knows。And it'll complete text for you in like the way that it knows how to do。

 but then you teach it to complete text in different ways and because you're like teaching it this different thing。

 it kind of gets confused about what it actually knows。



![](img/852ad884d0e10a4e3ff4251a6291c576_858.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_859.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_860.png)

Interestingly， it's possible to steal this leg。Fine tuning， That's what。



![](img/852ad884d0e10a4e3ff4251a6291c576_862.png)

You know， steal， but the Lama model that we saw was quickly fine tuned by Stanford team on。



![](img/852ad884d0e10a4e3ff4251a6291c576_864.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_865.png)

Some fine tuned， some some instruction instructions。

 but the instructions they actually didn't pay contractors to get they just。



![](img/852ad884d0e10a4e3ff4251a6291c576_867.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_868.png)

As GPT3 certain， they gave GPT3 instructions， and then GPT3 would like do it and then they would take that as an example for allma。



![](img/852ad884d0e10a4e3ff4251a6291c576_870.png)

So it's only cost them $600 to reproduce you know。

![](img/852ad884d0e10a4e3ff4251a6291c576_872.png)

I mean， it's not as good as GPT3 instruction following， but it's pretty good。



![](img/852ad884d0e10a4e3ff4251a6291c576_874.png)

There is a data set for instructions tuning， specifically in the chat。



![](img/852ad884d0e10a4e3ff4251a6291c576_876.png)

In the chat， a paradigm called open Assistant。

![](img/852ad884d0e10a4e3ff4251a6291c576_878.png)

And there's one last day I want to share， which is retrieval enhancing。

So this is a model called Re from Deep Mind， and basically it's like we have these large models because they have to learn a lot of facts。



![](img/852ad884d0e10a4e3ff4251a6291c576_880.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_881.png)

About the world， and also they have to be good at reasoning and like writing code and stuff like that。



![](img/852ad884d0e10a4e3ff4251a6291c576_883.png)

But can we train a smaller model that's like only good at reasoning and writing code。

 but then if it needs to like say facts about the world。

 it just kind of looks them up from some database。

![](img/852ad884d0e10a4e3ff4251a6291c576_885.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_886.png)

So what they did is they burden coded a bunch of sentences and stored them in like a trillion token database。



![](img/852ad884d0e10a4e3ff4251a6291c576_888.png)

And then had a small model train where it would be able to fetch things from the database and kind of have them in the context。



![](img/852ad884d0e10a4e3ff4251a6291c576_890.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_891.png)

They haven't been able to get it to work as well as just like large language models。

 but I think that's a matter of time， like I think this approach kind of points to the future of LLMs。



![](img/852ad884d0e10a4e3ff4251a6291c576_893.png)

![](img/852ad884d0e10a4e3ff4251a6291c576_894.png)

🎼，🎼。🎼，🎼，🎼，🎼。