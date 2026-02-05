# 吴恩达《生成对抗网络（Generative Adversarial Networks，GAN）》中英字幕 - P1：01_01_01_欢迎来到专项课程.zh_en - GPT中英字幕课程资源 - BV1JC4y1T7vZ

Welcome to this specialization on Generative adversarial networks or GAS for short。

Gans are an emergent class of deep learning algorithms that are generating incredibly realistic images。

 The specialization will teach you how to build and apply cutting imagegans。 For example。

 you learn how to build a G to generate pictures of people that had never existed or make someone maybe yourself look younger or older。

 you can also use a G to take a lowres video and turn it into a greatlook highres video。

 or on the supervised learning side。 If you are trying to classify scratched objects or classify medical X- ray images。

 but you don't have enough pictures， don't have enough examples。

 you can also use a again to synthesize more data to feed to your learning algorithm。

 I think GNs are on a path to transform image editing and more broadly media and entertainment。😊。

I'm here today with Sharon Joe， who will be your instructor for the series of courses。

 welcomelcome Sharon。 Thanks， Andrew， pleasure to be here。

 One of the things about Gs is that they seem a bit complex or mysterious。

 but I don't think they necessarily have to be。 It doesn't take a lot to actually implement agan into the learners watching this you actually get to implement again in your very first week So Sharon to demystify Gs I've heard you when you teaching sometimes use the art forger and the art inspector analogy to explain Gs Can you say more about that。

 Yes， I love this analogy because it strippeds away kind of the neural network components and the details the math。

 everything and it really leaves us with two different networks that are one is the art forger who's trying to mimic pieces of art or realistic artworks。

 maybe the Mona Lisa maybe storyry night。 And then there's an art inspect。😊。

Who's looking at a pile of real famous art and also this fake art that's forged by this art forger and trying to figure out which ones are real and which ones are fake and giving that feedback back to that art forger to improve over time and that's how you get a really great G that generates really realistic images So as a G implementer what one is doing is really implement two neural networks the art forger that's trying to paint these amazing looking pictures and the art inspector neural network thats trying to give feedback to the art forger so that the art forger neural network can become better and better generating these images Exact one of the really fun things about working with Gs is I've seen a lot of G researchers take a lot of pride in their creation because as someone working on Gs is that you created is your artwork So I'm actually excited about。

Specialization， helping a lot of learners create their own artwork and feel that pride of creation as well。

 I would definitely agree with that。 and I actually think of this as the Ikea effect because with Ikea furniture you get to build it yourself and people actually have seen that you like your furniture more if you build it yourself and just like your artwork if you build your G yourself you'll like that output that artwork。

 those masterpieces you create with your G much more and to the learner。

 I think one of the things that might be really fun would be if in this specialization you implement your owngan and generate some really coollook pictures that you feel proud of and want to share your friends and family or with us get creative Finally Gs are relatively advanced deep learning topic So let's also go over the background that dis specialization assumes you have so for the background of this specialization for you to get the most out of the specialization you should know what a neural network。

including a convolutional neural network and be able to code up models in Python and also know how to use a deep learning framework such as Tensorflowlow。

 Kas or Pytororch and if you've completed deeplening。AI's deep learningning specialization。

 you'll be all set and it's okay if you're a little rusty on these topics。

 you'll get to review them in the first couple of weeks。

So to those of you that had done the deep learning specialization。

 I hope that this specialization on GNs will be a good mix step to learn about a very advanced sets of deep learning algorithms。

 I'm excited about the specialization helping many learners helping many of you get started in this cutting edge field And with that let's get started with course1 where you get to build a base again in your very first week。

 which is awesome second， you get to build upon that G add some convolutional neural network aspects to it to build a more powerfulgan and you keep improving on it such that your G can train stably in your third week and finally in your fourth week you get to actually tell your G what to generate So if yourgan is generating types of dogs you can tell your G to generate a golden retriever for example and you'll also get to control the outputs of your G a little bit more So if yourgan is generating faces you can make this face look younger or older sounds like it be an exciting few weeks let's jump into it。

And let's get started， let's get started， I'll see you in the classroom soon。

