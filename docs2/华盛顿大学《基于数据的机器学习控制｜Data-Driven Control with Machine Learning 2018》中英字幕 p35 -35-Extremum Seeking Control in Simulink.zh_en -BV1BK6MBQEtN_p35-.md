# 华盛顿大学《基于数据的机器学习控制｜Data-Driven Control with Machine Learning 2018》中英字幕 p35 -35-Extremum Seeking Control in Simulink.zh_en -BV1BK6MBQEtN_p35-

![](img/826eff8663e22102965578208d02af6a_0.png)

Hi everyone， welcome back。So we've been talking about extremetrem seeking control。

 and I thought it would be fun to try an actual live demo where in real time。

 I'm going to show you how easy it is to cook up an extrem seeking controller in Matlab simullink。

 Okay， so for those of you who don't know， I'm going to just click go on simullink and generate this。

😊，Blank simullink canvas。 What simullink is is essentially a realtime environment in Matlab where you can simulate physical systems。

 You can simulate dynamical systems。 You can design control laws kind of with point and click block diagrams。

 So we've been drawing all of these block diagrams for control。

 You can directly implement those in simullink。 It's an extremely powerful environment。😊。



![](img/826eff8663e22102965578208d02af6a_2.png)

![](img/826eff8663e22102965578208d02af6a_3.png)

![](img/826eff8663e22102965578208d02af6a_4.png)

You can even simulate， you know PDdeEs or ODs and control those in here。

 You can use simullink to interact with real hardware。

 You can use these simulant controllers to control a real physical system in real time。

 and you can watch the output using virtual oscilloscopes。

 So simullink is an awesome environment very， very powerful。

 fun to kind of sandbox and play around in。

![](img/826eff8663e22102965578208d02af6a_6.png)

![](img/826eff8663e22102965578208d02af6a_7.png)

![](img/826eff8663e22102965578208d02af6a_8.png)

![](img/826eff8663e22102965578208d02af6a_9.png)

And this is a little dangerous， but I really want to try a live demo right now of just dropping in all of this kind of extreme seeking control architecture and showing you how easy it is in real time to design one of these things。

 so we fire up simullink。 I'm going click on this button here。

 which is gonna give me my library of stuff。 So if I click on that。

 I get my browser of all of my sim blocks that I get to play with。

 and you can see here that there's a ton of stuff。 Okay so here's all the common simullink stuff。

 But then there's you know aerospace block set。 there's like a neural network toolbox。

 There's all this stuff that you can drag and drop into here。

 and build these pretty sophisticated interactive。

![](img/826eff8663e22102965578208d02af6a_11.png)

![](img/826eff8663e22102965578208d02af6a_12.png)

![](img/826eff8663e22102965578208d02af6a_13.png)

![](img/826eff8663e22102965578208d02af6a_14.png)

![](img/826eff8663e22102965578208d02af6a_15.png)

Interactive systems。 And one of the things that's great about simlink is that Matlab kind of abstracts all of the time integration and time stepping and error tolerances for stiff systems and and so on。

 So you can kind of drag and drop and connect all this up。

 And it will figure out the best way to simulate it to give you good results。 Okay。

 so the way I'm going start this is I'm just going to drop in all of the blocks I'm going to need。

 And then I'm going to connect them up and we're going to tune the extreme I seeking controller。

 Okay， so what are we going to need， I'm going to need an integrator gain。😊，Again。

 I'm going to need I'm going to have to inject a sine wave and add it to my best estimate。

 I'm also going to inject that sine wave and multiply it by my high pass filtered output。

 so I'm going to need this multiplication block right here。And this addition block。

 okay I'm going to need my multiplier and addition。

 I'm going to change the colors in a minute to make this look a little cooler。



![](img/826eff8663e22102965578208d02af6a_17.png)

Okay， I'll need some sinusoidal inputs， so those are in the sources。



![](img/826eff8663e22102965578208d02af6a_19.png)

So I'm going to go down here and get my sinusoidal input block。



![](img/826eff8663e22102965578208d02af6a_21.png)

I'm going to need some virtual oscilloscope so I can plot the output。

 so let's take one of these virtual oscilloscopes here。Okay。

 that will be for my objective function that I'm trying to maximize。 Maybe I want another one。



![](img/826eff8663e22102965578208d02af6a_23.png)

For the input， so I'm going to have two oscilloscopes， one for the output， one for the inputs。



![](img/826eff8663e22102965578208d02af6a_25.png)

Okay， so what do I have， I have my seusoidal input， my addition， my multiplication。

 I have my oscilloscopes， Okay， I need an integrator， a high pass filter， and my objective function。



![](img/826eff8663e22102965578208d02af6a_27.png)

Integrator high pass filter objective function。

![](img/826eff8663e22102965578208d02af6a_29.png)

Okay， for the continuous in the continuous block， I'm going to pull this integrator1 over S。

 I'm going to use an integrator block。

![](img/826eff8663e22102965578208d02af6a_31.png)

I'm also going to make my high pass filter out of this transfer function block。



![](img/826eff8663e22102965578208d02af6a_33.png)

Okay， good transfer function block。 And the last thing I have to do is design my objective function。

 And I think that is in user defined functions。

![](img/826eff8663e22102965578208d02af6a_35.png)

![](img/826eff8663e22102965578208d02af6a_36.png)

This F of U is going to work just fine for us， okay。

 so this is my output as a function of my input U。F of U。Okay。

 and I think that's actually all the building blocks I'm going to need。 I have everything I need。

 So now what I'm going to do is I'm just going to make this look a little bit cooler so that you can see it better。

😊。

![](img/826eff8663e22102965578208d02af6a_38.png)

![](img/826eff8663e22102965578208d02af6a_39.png)

At home， I'm going to make my foreground color white。

 and I'm going to make my background color black。

![](img/826eff8663e22102965578208d02af6a_41.png)

So that it pops Okay， and now I'm going to start actually arranging these things and connecting things up in the right topology。

 Okay， so let's do that's let's just get the course ordering here so I'm going to have some oscilloscopes。



![](img/826eff8663e22102965578208d02af6a_43.png)

To measure stuff。I'm going to have my objective function here。 I have my sign input down here。

 I have a。High passs filter。Integrator gain matrix。 I'm going to want to multiply some stuff I guess。

 and I'm going to want to add some stuff。

![](img/826eff8663e22102965578208d02af6a_45.png)

And now notice that everything， all these arrows are pointing in this direction。

 but my feedback control is going to go this way， I'm just going to flip some stuff。



![](img/826eff8663e22102965578208d02af6a_47.png)

So I'm just going to do that really quickly， rotate and flip， control I apparently flips it。

 so I'm going to do that here。Here。😔，Hhir。

![](img/826eff8663e22102965578208d02af6a_49.png)

AndHere。And I delete that one because I don't want that there。



![](img/826eff8663e22102965578208d02af6a_51.png)

诶。And I'm going to flip this one too。Okay， so we're pretty much ready to build our。



![](img/826eff8663e22102965578208d02af6a_53.png)

Our control topology， our extrems seeking control loop。



![](img/826eff8663e22102965578208d02af6a_55.png)

And so this F of U is kind of given to us。 I don't， you know。

 we're not going we're going to define what it is， but but this is just。

 we have some measured output of our objective。 We have some input that we can use to change the system and we're going to wrap our controller around。



![](img/826eff8663e22102965578208d02af6a_57.png)

![](img/826eff8663e22102965578208d02af6a_58.png)

![](img/826eff8663e22102965578208d02af6a_59.png)

So let's start with that， let's map from here。And I think in simulant。

 it's about as easy as just clicking on these arrows。And then dragging to where you want them to be。

 Okay， so now I've connected up the output to my high pass filter。



![](img/826eff8663e22102965578208d02af6a_61.png)

I'm also going to connect up my oscilloscope。 so I want to essentially measure。



![](img/826eff8663e22102965578208d02af6a_63.png)

![](img/826eff8663e22102965578208d02af6a_64.png)

I'm going to measure the output of F in my oscilloscope。 Okay， my highpas filter。

 I'm going to multiply that by my sine wave， so I need to connect up my high passs filter to this multiplication block。

 I'm also going to connect up my sine wave to that multiplication block。

 So here my sine wave gets multiplied by my highpa filtered outputs。



![](img/826eff8663e22102965578208d02af6a_66.png)

![](img/826eff8663e22102965578208d02af6a_67.png)

![](img/826eff8663e22102965578208d02af6a_68.png)

I want to bring everything a little bit closer。Yeah。

 I want everything a little bit closer so I don't have to reach so far。



![](img/826eff8663e22102965578208d02af6a_70.png)

Okay。This is my demomodulated signal。 so I take my highpas filtered output。 I high passs filter it。

 I multiply it by my sine wave， and I get that signal that's mostly positive when I'm to the left of the optimum。

 mostly negative， when I'm to the right of the optimum。

 And I'm going to integrate that into my best estimate of U。 So here's my integrator block here。

 And let's connect those up。😊。

![](img/826eff8663e22102965578208d02af6a_72.png)

![](img/826eff8663e22102965578208d02af6a_73.png)

![](img/826eff8663e22102965578208d02af6a_74.png)

Now， this integrator block， normally I would have some K over S， some K constants and gain。

 I'm just to make it easier to code up in the simullink。 I have this little triangle here。

 which is kind of the universal block diagram for a gain。 So this is going to be my integrator gain。



![](img/826eff8663e22102965578208d02af6a_76.png)

![](img/826eff8663e22102965578208d02af6a_77.png)

![](img/826eff8663e22102965578208d02af6a_78.png)

And then I'm going to add。

![](img/826eff8663e22102965578208d02af6a_80.png)

My， so that's this right here。 Let's see if I can write， hopefully on top of here。

 So this right here。Is U hat？This is my best estimate of my optimizing controller。

 I've integrated up the demomodulated signal。 I've multiplied it by some gain。 this is my U hat。

 and I'm going to add to that U hat， my sinusoidal perturbation from this sign block。Okay。

 so that's kind of one of the last steps here is I'm going to。



![](img/826eff8663e22102965578208d02af6a_82.png)

Connect back guy up。Not as easy as it looks on a touch screen。 Come on。 Come on， Come on， Come on。



![](img/826eff8663e22102965578208d02af6a_84.png)

What's。Just connect this guy up to here， good。

![](img/826eff8663e22102965578208d02af6a_86.png)

Okay， so now my sinusoidal ripple is adding to the best estimate you had。And then that ripple。

 when I add the ripple， that's actually what's going to go into my system F。



![](img/826eff8663e22102965578208d02af6a_88.png)

![](img/826eff8663e22102965578208d02af6a_89.png)

Okay， this is not the prettiest control diagram in the world。 I have to be honest。

 if I was doing this at home and not on a touch screen。

 I'd make all these lines straight and I'd bring it all together， but it's fine。



![](img/826eff8663e22102965578208d02af6a_91.png)

![](img/826eff8663e22102965578208d02af6a_92.png)

Okay， I also probably want my second oscilloscope。

![](img/826eff8663e22102965578208d02af6a_94.png)

To measure。The input， Okay， so I've got one oslloscope on the output，1 oslloscope on the input。

 so I can kind of simultaneously watch what's happening with U and what's happening with J。

 the objective function。

![](img/826eff8663e22102965578208d02af6a_96.png)

![](img/826eff8663e22102965578208d02af6a_97.png)

![](img/826eff8663e22102965578208d02af6a_98.png)

Okay， so that is basically it。 That's how you build an extreme room seeking controller in simlink。

 It is super simple。 Now we're going to actually populate this with some values。



![](img/826eff8663e22102965578208d02af6a_100.png)

![](img/826eff8663e22102965578208d02af6a_101.png)

And I'm going to walk you through my logic of how you actually tune one of these things and what variables you get to play with okay。



![](img/826eff8663e22102965578208d02af6a_103.png)

Okay， so my function， my objective function， I'm going to try to use the same value that's in the book。

 And it's also in in the other videos where we coded this up as a script。

 And I think that was 25 minus。

![](img/826eff8663e22102965578208d02af6a_105.png)

![](img/826eff8663e22102965578208d02af6a_106.png)

![](img/826eff8663e22102965578208d02af6a_107.png)

5 minus u squared。So this thing has a peak when u equals 5。

And that peak is at J my objective function is 25。 So at U equals 5， I have j equals 25。

 And then when I go to the left or right， this thing drops off like a parabola。

 So it's a very simple static cost function。

![](img/826eff8663e22102965578208d02af6a_109.png)

![](img/826eff8663e22102965578208d02af6a_110.png)

![](img/826eff8663e22102965578208d02af6a_111.png)

Okay， in general， you can put a real O D E， a dynamical system differential equation in here。

 Some x dot equals A X plus B U or some x dot equals F of x。 This can be a dynamical system。 Again。

 I'm just showing you the simplest case with a static objective function。



![](img/826eff8663e22102965578208d02af6a_113.png)

![](img/826eff8663e22102965578208d02af6a_114.png)

![](img/826eff8663e22102965578208d02af6a_115.png)

If this had dynamics， you'd have to consider what the time scales of those dynamics are when you design all of these other blocks。

 Okay， that would be very important。 but here we have a static objective。

 so it's a little bit easier to design everything。

![](img/826eff8663e22102965578208d02af6a_117.png)

Okay， let's hope I can do this。Trying to just move everything over a little。So I don't have so much。

Space to walk。

![](img/826eff8663e22102965578208d02af6a_119.png)

Okay。Good， so we have our objective function。 So now what are the actual parameters we get to start with。

 So I have to have an initial condition for you hat。

 I have to have some initial guess for what my best optimizing controller is。😊。



![](img/826eff8663e22102965578208d02af6a_121.png)

![](img/826eff8663e22102965578208d02af6a_122.png)

![](img/826eff8663e22102965578208d02af6a_123.png)

And so what I'm going to do is I'm going to。

![](img/826eff8663e22102965578208d02af6a_125.png)

I'm going to use this initial condition of my integrator block。

 So basically U hat comes out of the integrator and in simlink。

 that's where I get to choose an initial condition for U hat。

 And I'm going to start with U hat equals 0 because that'll be sufficiently subopmal that will be able to see it converge to the optimum。



![](img/826eff8663e22102965578208d02af6a_127.png)

![](img/826eff8663e22102965578208d02af6a_128.png)

![](img/826eff8663e22102965578208d02af6a_129.png)

Okay， good。嗯。What else do I get to do， So I get to change my， let's say I have a sinusoidal ripple。

 So let's play around with this。

![](img/826eff8663e22102965578208d02af6a_131.png)

![](img/826eff8663e22102965578208d02af6a_132.png)

In many physical systems， this ripple is actually a side effect of how you're building your system。

 And so in the case of in one case， we tried to use extremere seeking control to optimize solar array performance and our DC to AC converter gave us a ripple that we couldn't really control。

 and so oftentimes the parameters of the sinusoidal ripple are things that are just given to you。

 So I'm going to say that our amplitude is 02。

![](img/826eff8663e22102965578208d02af6a_134.png)

![](img/826eff8663e22102965578208d02af6a_135.png)

![](img/826eff8663e22102965578208d02af6a_136.png)

And that our frequency is 10 Hz，10 times 21 pi。In some cases。

 you actually would get to increase or decrease this amplitude and you might get to change this frequency。

 but I'm just going to kind of lock these in。In some cases， you can change the amplitude。

 for example， by putting on a bigger or smaller capacitor， things like that。

 So that actually was one of the trade offs in the solar array design。But for now。

 we're assuming the system is given to us and we have a fixed ripple at a fixed frequency and amplitude。



![](img/826eff8663e22102965578208d02af6a_138.png)

And so the actual knobs that we get to turn are this gain matrix and our high pass filter frequency。

 So those are kind of the things that we get to play around with。 In some cases。

 you could also play around with the amplitude and frequency of this。 But for now。

 let's say those are locked。

![](img/826eff8663e22102965578208d02af6a_140.png)

![](img/826eff8663e22102965578208d02af6a_141.png)

Okay。I think we're ready to go。 Let's try， let's try running this。

 It's always a little dangerous to do a live demo， but I wanna。

 I want to be as kind of transparent as possible about how easy or difficult this is。



![](img/826eff8663e22102965578208d02af6a_143.png)

， I ran it， it did some compiling， it simulated it， and now it's ready to go。

 so that means it's finished。

![](img/826eff8663e22102965578208d02af6a_145.png)

So I can double click my objective function，ooh， that's terrible。I wonder。



![](img/826eff8663e22102965578208d02af6a_147.png)

It's so bad that I don't think， I think there must be something wrong here。 What did I do wrong。



![](img/826eff8663e22102965578208d02af6a_149.png)

诶。Oh， my high pass filter is actually a low pass filter。 I didn't design my filter at all。



![](img/826eff8663e22102965578208d02af6a_151.png)

Okay， my high pass filter is supposed to be s over S plus omega n。



![](img/826eff8663e22102965578208d02af6a_153.png)

![](img/826eff8663e22102965578208d02af6a_154.png)

omega H， my high pass filter frequency。And in MATLAb。

 the way you can see that this is a1 over S plus 1， that's not an S in the numerator。



![](img/826eff8663e22102965578208d02af6a_156.png)

So in MATLb， the way that you define these transfer function blocks are with numerator polynomial coefficients and denominator polynomial coefficients。

 and so if my polynomial only has one coefficient， then it just corresponds to the constant term one。



![](img/826eff8663e22102965578208d02af6a_158.png)

So if I want to make this S plus 0， I do one space 0。



![](img/826eff8663e22102965578208d02af6a_160.png)

And then my denominator is 1 s plus 1， so this would be S plus1。



![](img/826eff8663e22102965578208d02af6a_162.png)

I hope that was clear。 So now I have a proper transfer function S over s plus 1。

 So I'm choosing my high passs filter cut off it at a frequency of1。

 and we might change that later depending on the performance。 So let's just for now。

 let's try to run this。 Okay， good。 So you saw at least one bug really， really quickly。

 I didn't design my high pass filter transfer function。 So you always have to do that。



![](img/826eff8663e22102965578208d02af6a_164.png)

![](img/826eff8663e22102965578208d02af6a_165.png)

![](img/826eff8663e22102965578208d02af6a_166.png)

T it again super fast。

![](img/826eff8663e22102965578208d02af6a_168.png)

Double click is now I get something much more reasonable。

 My objective function J starts at 0 because it was 25。



![](img/826eff8663e22102965578208d02af6a_170.png)

![](img/826eff8663e22102965578208d02af6a_171.png)

Minus， it was。J was equal to 25 minus。5 minus u squared。 and I started at U equals 0。

 So this J at that point was 25 minus-25。 So I started 0 down here。



![](img/826eff8663e22102965578208d02af6a_173.png)

![](img/826eff8663e22102965578208d02af6a_174.png)

And you can see that my extreme seeking controller， this block diagram is actually working。

 I am increasing my J， but I'm doing it a little slowly。 This is not as fast as I want， right。

 This is pretty a pretty slow rise， and I'd like it to be much more aggressive rise up to the up to the peak。

😊。

![](img/826eff8663e22102965578208d02af6a_176.png)

![](img/826eff8663e22102965578208d02af6a_177.png)

![](img/826eff8663e22102965578208d02af6a_178.png)

![](img/826eff8663e22102965578208d02af6a_179.png)

Okay， so what do I actually get to change？In this system to play around with。

 to get this to converge faster。 Well， one thing I get to do is I get to increase this integrator gain here。

 So let' let's bump this from  one to5。

![](img/826eff8663e22102965578208d02af6a_181.png)

![](img/826eff8663e22102965578208d02af6a_182.png)

Hope that's not too aggressive， okay？Let's run that。



![](img/826eff8663e22102965578208d02af6a_184.png)

I got a ding。 Hopefully that means it worked。 Okay， cool。 This actually looks pretty good。

 So now my J function is rising at a pretty good clip when it's far away。

 and then it slowly tapers off to nearly the optimum value of 25 with a little ripple on top。

 So this is already doing much much better just by bumping that gain K。

 which is kind of my first line of attack is I'm going to get a rough order of magnitude of what my gain K should be so that I get kind of the right behavior。

😊。

![](img/826eff8663e22102965578208d02af6a_186.png)

Maybe we should also look at the U signal， So this is my U。



![](img/826eff8663e22102965578208d02af6a_188.png)

It's increasing， but notice that it's actually it's kind of slowing down before it gets to five。

 so it's going to take a long time to get all the way up to that optimal value。



![](img/826eff8663e22102965578208d02af6a_190.png)

![](img/826eff8663e22102965578208d02af6a_191.png)

Of U equals 5。But because this is a quadratic cost function。

 the output is still pretty darn close to 25。 So it's still pretty good。



![](img/826eff8663e22102965578208d02af6a_193.png)

![](img/826eff8663e22102965578208d02af6a_194.png)

But it's not good enough。 I want better performance。 Okay， so what could I do。

 I could try to bump my gain up higher。 I could try K equals 10 or K equals 20。



![](img/826eff8663e22102965578208d02af6a_196.png)

Let's try that。 Let's see what happens at K equals 20。



![](img/826eff8663e22102965578208d02af6a_198.png)

Okay。Runs。Okay， now I actually get like ridiculously fast rise and almost zero steady state error here because it gets up to the peak value。

 And then when when U is at that optimizing value， if it swings to the left and the right。

 essentially， my slope is flat in my objective function。

 So the objective function doesn't dip at all。 So just bumping up that gain did a great job and gave me very。

 very fast performance。 Let's look at what the U does。

 and I get this really fast performance up to U equals 5， which is the optimal value。😊。



![](img/826eff8663e22102965578208d02af6a_200.png)

![](img/826eff8663e22102965578208d02af6a_201.png)

![](img/826eff8663e22102965578208d02af6a_202.png)

![](img/826eff8663e22102965578208d02af6a_203.png)

![](img/826eff8663e22102965578208d02af6a_204.png)

Now， a couple of things that you know I've done a lot of extremetrem seeking control。

 so I've seen these kinds of curves all the time。

![](img/826eff8663e22102965578208d02af6a_206.png)

![](img/826eff8663e22102965578208d02af6a_207.png)

There's some things that concern me about this really big gain K equals 20。

 One is you can see that this this is pretty fat here and it's。Kind of this inconsistent。

 It gets really fat。 And then it gets really， really skinny。

 Something about this tells me that this might be kind of getting towards the edge of instability。

 And maybe if I add a noise to my system or a tiny little time delay or you know。

 this might be getting right on that margin of instability。 So in a simulation， it looks awesome。

 But I'm a little worried about the way that this looks。 So you might also in this block diagram。

 add a little bit of noise， disturbance， teeny， tiny time delay just to simulate what's more realistic and a physical system。

 so that you don't tune this thing to be amazing in a noisefree， clean simulation。

 but then break in the real world。😊。

![](img/826eff8663e22102965578208d02af6a_209.png)

![](img/826eff8663e22102965578208d02af6a_210.png)

![](img/826eff8663e22102965578208d02af6a_211.png)

Okay， let me make this more extreme。 If I make this 50， it's probably going to look pretty bad。

 So let's， let's see what that looks like。

![](img/826eff8663e22102965578208d02af6a_213.png)

Yeah， so now you can see how like jaggedy and horrible this is。

 You don't want your extreme seeking controller to look like this。 This is bad。

 even though it kind of works in simulation， I would never trust this in the real world。 Okay。

 so we're not going to use that one。 We're going go back down。

 I think a gain of 10 is actually pretty reasonable here。



![](img/826eff8663e22102965578208d02af6a_215.png)

![](img/826eff8663e22102965578208d02af6a_216.png)

![](img/826eff8663e22102965578208d02af6a_217.png)

One thing I'm going to do is I'm actually going to change my high pass filter a little bit。

 I'm going to make my denominator coefficients， I hope this doesn't break。



![](img/826eff8663e22102965578208d02af6a_219.png)

I'm going to increase the frequency of my high pass filter from one to five。

 I'm going to make it a little bit more of an aggressive filter。



![](img/826eff8663e22102965578208d02af6a_221.png)

And I'll tell you why， in a minute。I hope I don't mess anything up here。



![](img/826eff8663e22102965578208d02af6a_223.png)

And now this is kind of exactly what I want。 this is what I want my system to look like。

 I have a pretty consistent small perturbation， I don't have those fat you know oscillations in the cost function。

 I have a pretty small band of oscillations tapering off to nearly perfect performance in the asymptote。



![](img/826eff8663e22102965578208d02af6a_225.png)

![](img/826eff8663e22102965578208d02af6a_226.png)

![](img/826eff8663e22102965578208d02af6a_227.png)

![](img/826eff8663e22102965578208d02af6a_228.png)

And then if I look at what my control signal does， my control signal is basically going right to u equals five and then hanging out there。



![](img/826eff8663e22102965578208d02af6a_230.png)

Okay， so。

![](img/826eff8663e22102965578208d02af6a_232.png)

What did we do， We had a system given to us。 We had a ripple given to us。

 We didn't have that much control over it。 but what we did have control over was this gain matrix。

 and my highpas filter。 So when I'm designing an extreme seeking control。

 If I don't have access to this ripple。 if I can't change it。

 the first line of attack is I just run it， and I see what happens。

 then I modify my gain to get close。 and we kind of realized pretty quickly that the 5 to 20 range was was kind of a good range。

5 was a little under aggressive 20 was a little over aggressivegress。 So I bumped it down to 10。



![](img/826eff8663e22102965578208d02af6a_234.png)

![](img/826eff8663e22102965578208d02af6a_235.png)

![](img/826eff8663e22102965578208d02af6a_236.png)

![](img/826eff8663e22102965578208d02af6a_237.png)

And then I tweaked my high pass filter gain to get just the right performance， the right performance。

 And so the high pass filter gain is probably the most subtle part of this， this。

 this high pass filter， not not gain， but the cutoff frequency。



![](img/826eff8663e22102965578208d02af6a_239.png)

![](img/826eff8663e22102965578208d02af6a_240.png)

![](img/826eff8663e22102965578208d02af6a_241.png)

Is the most subtle part of this。So this high pass filter frequency in this case， five。

 and it's probably five radians per second， I always get a little confused about the units here。



![](img/826eff8663e22102965578208d02af6a_243.png)

嗯。But that frequency of that transfer function block is supposed to be designed to be lower than the ripple frequency。

 because I want all of my ripple to pass through。 I don't if if I。

 if if my high pass frequency was too high， then I would actually start to attenuate。



![](img/826eff8663e22102965578208d02af6a_245.png)

The output ripple。 So this output ripple is happening at 10 Hz。 And if I made this 20 Hz。

 that output ripple would start to get attenuated。 It would start to get diminished by this high pass filter。

 and it would be like having an effectively smaller gain here。

 So it would kind of defeat my gain here by overly aggressively filtering out my output ripple。



![](img/826eff8663e22102965578208d02af6a_247.png)

![](img/826eff8663e22102965578208d02af6a_248.png)

![](img/826eff8663e22102965578208d02af6a_249.png)

So that makes me want to have my high pass filter lower than my ripple frequency。



![](img/826eff8663e22102965578208d02af6a_251.png)

But I don't want it to be arbitrarily low。 I don't want it to be ridiculously low。

 because if my high pass filter frequency is too low。

 that it's actually going to let some of this fast rise through the signal。 So this fast slope here。



![](img/826eff8663e22102965578208d02af6a_253.png)

IfIf my high pass frequency cutoff is too low， then this fast rise will actually pass through。



![](img/826eff8663e22102965578208d02af6a_255.png)

That high pass filter block， and that can actually cause stability issues。

 it can cause this thing to like ramp up into a runaway if enough of this gets through。

Then that can cause the system to go unstable。 So that makes me want to make my highpa cutoff frequency closer to the ripple。

 And that's kind of this tension you have in designing this。

 That's why I actually think designing this is sometimes pretty challenging is you want it to be lower than the ripple frequency。

 So you pass the ripple but you want it to be higher than other frequencies that occur in the system so that you don't get these weird instabilities occurring。



![](img/826eff8663e22102965578208d02af6a_257.png)

![](img/826eff8663e22102965578208d02af6a_258.png)

![](img/826eff8663e22102965578208d02af6a_259.png)

![](img/826eff8663e22102965578208d02af6a_260.png)

And so if you're actually designing one of these systems and you're going for peak performance and the system actually has dynamics and time scales。

 so this is a little bit more complicated， I highly recommend you go back to the original papers and books by Christtiitch at all。



![](img/826eff8663e22102965578208d02af6a_262.png)

![](img/826eff8663e22102965578208d02af6a_263.png)

Because there's great kind of analytical guarantees on when this will and will not converge along with guidelines for how to design these things。



![](img/826eff8663e22102965578208d02af6a_265.png)

Okay， but you can see right away how easy it is to design a really。

 really good extreme seeking controller in simullink。 So a few takeaways I want you to take away。

 the first main one is it's super easy and you should try it。 It's fun。 You know。

 I like just kind of these these plug and play blocks。 You can build really complicated。

 interesting control laws， very quickly and easily。😊。

And it takes a lot of the simulation burden off of you。 You just click go and it runs。

 So that's the first takeaway。 easyasy to build an extreme seeking and control law in simlink。

The second takeaway is that this。This architecture is very amenable to analog control design。

 So this is supposed to be kind of simulating an analog setup。

 You can also simulate digital setups and siming。 But the way I've drawn it here。

 this is all continuous time。 And you could actually build all of these blocks in analog circuitry。

 so you could you could get a sign generator and an integrator and a high pass filter。



![](img/826eff8663e22102965578208d02af6a_267.png)

![](img/826eff8663e22102965578208d02af6a_268.png)

And you could build this entire extreme seeking control in an analog circuit that you could then kind of wrap around your system。

 you could kind of build this and clip it onto your system。



![](img/826eff8663e22102965578208d02af6a_270.png)

![](img/826eff8663e22102965578208d02af6a_271.png)

![](img/826eff8663e22102965578208d02af6a_272.png)

And it would measure the output and in continuous time in analog circuitry。

 it would feed back this this extreme of seeking control input U and and control your system。

 So that's a big appeal of extreme seeking control。

 Also is it's very amenable to both analog and digital control design。

 So this is kind of supposed to be the analog version。

So that's why I have these oscilloscopes up here， I also have a script where we show how to implement this in digital or in discrete time。

 and in that case I actually have to write kind of a for loop for every delta T of my digital controller and then this high passs filter becomes a little bit more complicated but。



![](img/826eff8663e22102965578208d02af6a_274.png)

![](img/826eff8663e22102965578208d02af6a_275.png)

![](img/826eff8663e22102965578208d02af6a_276.png)

![](img/826eff8663e22102965578208d02af6a_277.png)

Basically the takeaway is it's easy to implement in analog okay and the third takeaway。

 which I think is kind of interesting doing this live。

 So I'm glad everything worked out and we have a converging extrem seeking control。

 I'm pretty happy with this this output。 actually， I think this is exactly what I want my extremist seeking control output to look like。

😊。

![](img/826eff8663e22102965578208d02af6a_279.png)

![](img/826eff8663e22102965578208d02af6a_280.png)

![](img/826eff8663e22102965578208d02af6a_281.png)

![](img/826eff8663e22102965578208d02af6a_282.png)

No， no wonder， I mean， this was a very simple objective function。



![](img/826eff8663e22102965578208d02af6a_284.png)

But I guess the other thing the third takeaway is just the thought process of how you actually build and tune these things。

 so this is given to you and you may or may not know what its time scales are。

 you may or may not know a lot about your system so you might have a lot of tuning to do because this might have some time scales that you have to kind of figure out。



![](img/826eff8663e22102965578208d02af6a_286.png)

The the ripple may or may not be given to you， but basically if this is given to you。

 then the only knobs you really have are this integrator gain and the high pass frequency filter cut off and I always start with the gain and then save the frequency for last so I get this close you know I might take the input frequency divided by 10 for this and start there and then work on my gain once I have the gain in a good place。

 then I'll work on my high pass frequency。

![](img/826eff8663e22102965578208d02af6a_288.png)

![](img/826eff8663e22102965578208d02af6a_289.png)

![](img/826eff8663e22102965578208d02af6a_290.png)

![](img/826eff8663e22102965578208d02af6a_291.png)

![](img/826eff8663e22102965578208d02af6a_292.png)

If you actually have access to your ripple then you have a lot more knobs to turn。

 you can change the frequency， you can change the amplitude and all of those things will give you faster or slower convergence with bigger or smaller error and more or less stability so there's a lot of knobs to play with which is why in this demo I've kind of kept it simple and we've only played with K and mega。

Okay， so I hope you have the tools you need now to just try this out on your own system。

 I encourage you to try some dynamical systems。 That would be fun。 You know。

 try your own physical system。 You could even try this。

 You could build a little experiment that you want to control， you know。

 a little solar array or something like that。😊。

![](img/826eff8663e22102965578208d02af6a_294.png)

And you could get a you know， some kind of a digital analog converter or A to D converter。

 and you could actually wrap this around a physical system in simullink。

 So there's a ton of powerful stuff you can do here。

 and I hope you actually play around with with this simple extreme seeking control loop。 Okay。

 thank you。

![](img/826eff8663e22102965578208d02af6a_296.png)

![](img/826eff8663e22102965578208d02af6a_297.png)