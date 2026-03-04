# 【人工智能访谈会 2023】斯坦福大学—中英字幕 p15 p14 AI and Robotics - Chelsea Finn & Andrew Ng -BV14XB8YYEb1_p15-

![](img/91fe84832ca5079fd23e5da4b1c122b8_0.png)

Thanks to joining me here at Stanford University with Professor Chelsea Finn who's with both the computer science and the electrical engineering departments。

 Chelsea's leads a research lab that does cutting edge work applying machine learning。

 especially reinforcement learning to a range of robotics applications so I'm really glad to have you here Chelsea happy to be here so I know that before you settled into working on computer science and machine learning。

 you actually considered a lot of career options ranging from biology to aerospace to you know computer science and electrical engineering so what made you make this choice。

😊，Yeah， so I was always drawn to engineering because I really like solving puzzles and solving problems。

And when I arrived at MIT for my undergraduate， I was considering different engineering majors。

 And what really drew me first to computer science was that it gives you a lot of flexibility in terms of。

The different paths that you can do essentially， computer science empowers you to build lots of different things with software with code。

 And with that， I could eventually go into biology if I wanted to， I could go into robotics。

 There's all sorts of really exciting things you can do with computer science。

 So that landed me in computer science。 And then once once I decided on that。

 I I really enjoyed a lot of the math that goes behind AI like probability and statistics。

 And I was also really drawn to this challenge of how can we build a computer that can see like humans do that can perceive things and images and can take actions in the world。

😊，So it was almost as if your choice was if you do computer science you could do you know anything and so that makes it。

 I guess what Mark and Gesson said software is eating the world and I think Jenssen Huang said AI is eating software and it feels like when you work in machine learning you get to poke your nose in all corners of the world and do fun things and Abolly I think machine learning is a really exciting place to be and I mentioned that computer science is very flexible and open lotss of doors and I think that machine learning。

Is very similar to that。 There's so many different things you can do with machine learning and so many different applications。

 I'm really excited about applications in robotics。

 but theres we've seen lots of different applications in language processing in biology and in other fields。

😊，So your specialization， you know the many things you do。

 a large fraction of your work is in robotics and when you know people look at popular media or social media you see these videos of for example。

 humanoid robots jumping up and down and doing Pod Co and incredible things how should one think about what robots really can and cannot do today because there these amazing demo videos it looks like and do almost anything but how should one decide what is actually doable Yeah the videos that we see online from Boston dynamicsys。

 for example， of robots doing back flips or doing parkco and of course are really impressive because they look really complicated and。

You it's， it's really easy to， in some ways， anthropomorphify as the robot and think that if you saw a person doing that。

 that would be very impressive， and they would probably be able to do lots of other really impressive things。

And the catch is that in robotics， in those videos and in many impressive demonstrations of robotics。

 the robot was set up for that particular environment， and it was tuned to do well with that setup。

 and if you change something about the environment about the setup about what it's supposed to do。

 then the demo no longer works it， the robot will fall flat。

So really the big challenge with robotics is getting robots to generalize。

 to be able to handle lots of different scenarios， with lots of different objects。

 with lots of different environments。And。Right now。

 robots can do things in very controlled environments like in factories and they are very useful in factories and what I'm really excited about and what's really hard in robotics is giving them the flexibility and generality of the skills that humans can do。

Just to dig a little bit more into the specific one off one environment thing before going into generoity when someone sees a Ns Co robotics demo。

How should they think about it or what the questions they should ask themselves？Yeah。

 so I think that the first question that someone can ask is what will happen if something changes in the environment。

 what will happen if you move a block or if you put the robot in a slightly different position when it starts oftentimes you don't see those kinds of tests of the system's robustness or resilience to those variations and if you do start seeing those demos where actually you kind of poke the robot or you change the environment a little bit and it still works。

 that's when I think we can be really impressed Co so a lot of your work has specifically've been on making robots robust to generalize or apply the loss of different environments tell me more about that work and how you approach this problem。

Definitely， so in other areas of machine learning， we've seen huge successes where。

We take a very large data set， like you take all of Wikipedia and you train a neural network to be able to model the data in that very large and broad data set。

And in robotics， one thing that I'm excited about is if we can somewhat replicate that sort of success。

 if we can collect a similarly diverse data set and allow robots to learn from that data。😊。

Now this is challenging for a couple reasons， one is that we don't already have an existing data set we don't have Wikipedia for robot motor control。

 there isn't data lying on the internet of how exactly to move a robot's fingers to tie shoes。

 for example， so you don't have tons of diverse data already but fortunately robots in principle should be able to collect data themselves and。

That is an opportunity because it means that we might be able to collect a large amount of diverse data。

By allowing the robots to collect their own data， but it's also a challenge because it means that we need to figure out how to allow robots to collect data that's useful and diverse。

And so there's lots of different things that we explore in terms of approaching this problem。

 some is allowing robots to collect their own data and lots of different environments， some is。😊。

Showing demonstrations to a robot of how to perform a task。

 We've also explored a little bit of how to use data from the Internet。

 like videos of humans to show a robot how to do a task and incorporating all of these different data sources to allow robots to。

Well， once they've hopefully seen very diverse data sets like this。

 they might be able to generalize not just to the one scenario that they saw in a lab environment。

 but possibly the real world in the long term。One of the things we've seen is machine learning。

 reinforcement learning algorithms are great at playing video games because you can get you know essentially infinite data playing a video game with yourself。

 what do you think of the role of simulation？Yeah， so we've definitely seen lots of successes of AI systems。

Doing very well at video games and simulation is somewhat similar because we can collect lots of data in simulation as well。

One challenge with simulation is that the physics in the simulation engine are not exactly the same as the real world。

 We know generally the laws of physics， but the friction on a table， for example。

 may not be exactly known or the friction between the grooves on a cap and a water bottle if you try to screw a water bottle modeling that is very difficult。

 and it's prone to errors and then when you try to train a policy in that simulator to close a water bottle。

 for example， and then deploy in the real world， it actually doesn't work because of those errors in the simulation。

 So I think it's a promising data source but because of these inaccuracies and this challenge of transferring something that was learned in simulation to the real world。

 I don't think it's the only approach that we should bet on。

 I think that we should try to leverage lots of real data。And is it。

 I wonder it be surprising to someone Washingtonism why is it so hot to simulate the real world is's just a water of bottle those you two pieces of plastic and somehow we can't seem to figure out what's going on with two pieces of plastic。

Yeah， so I think that there's there's lots of challenges。 I mean。

 first is just modeling the low levelvel physics。 a lot of simulation engines out there。

 they will model time at a certain discretization， and in reality。

 time is much more fluid than operating at like 100 Htz or something like that。

 and to actually accurately model these things， you may need to actually model at a very fine time discretization and that gets very expensive and then your simulator may actually be slower than actually running things in the real world。

 and then it's no longer no longer useful in comparison to collecting data in the real world。😊。

And then the second thing is the real world is super diverse and so actually creating the content of all of the kind of objects that you encounter。

 even in everyday life when you're eating lunch or when you're kind of cleaning up a table。

 creating all of that content is actually a really manual effort and usually in machine learning systems。

 you want to kind of do away with the things that require a lot of manual effort and try to and automate things so that they can be scaled up。

Yeah。AndIn fact， in terms of the diversity of environments。

 today factories work great in robots where the environment is relatively controlled。

 relatively few know unexpected things happening on average。

 I know some of your work has been looking to send robots into people's homes and do things in people's kitchens that's one of the most uncontrolled environments in the world you can say a bit more about that Yeah absolutely。

😊，I think that the controlled environments are the ones where we've seen a lot of success。

 and in the long term， I would love to see robots that could go into any environment like a home or an office and be useful to people。

 and to do that， we want to actually start collecting data in those environments oftentime in robotics research。

 we collect the data once in a lab environment and learn based on that data。

 but if we only collect real data in a lab， we're never going to actually get the robots out into real world。

 So we're trying to start data collection efforts actually putting robots into the real world so that they see the diversity of all these different homes。

Rather than kind of the narrow data that you see in a lab。So I want to get your gut about one thing。

 which is you talked about wanting to get a robot to go into brand new home and makebo cereal right challenging tasks。

 liquids， cereal fridge what's your gut about how many different homes。

 how many different kitchens a robot will need to see so how many training examples you think a robot will need in order to have you know a good chance of doing on the N plus first on the next kitchen。

😊，Yeah， so I think it really depends on how hard the task is if the task is as simple as like。

 I don't know， maybe。Pressing a button on the microwave。

 Then I think that you may not need quite as much data for that。 but I think even for a new kitchen。

 you probably need still quite a large number of kitchens in order to。

 to generalize to a new one maybe。Maybe 20， maybe 100。

 if it's a test that's more complex like making a bowl of cereal。

 it's something that's super simple to people， but it's actually really hard for robots because there's lots of different steps involved for that。

 I think you'd need more data and probably also more kitchens as well maybe maybe in the thousands and I also think that even if we had thousands of kitchens of data or tens of thousands。

My guess is that the problem still wouldn't be solved fully。

 we've seen applications like autonomous driving where there's tons of data and the problem isn't quite yet solved。

 so I think we also need to try to go beyond the data distribution and also allow robots to adapt on the fly in a new environment。

 Well， thousands that's higher than myca， but that's interesting interesting see how it plays out。😊。

And so on the theme of making robots more robust， I know a lot of your research work was also on meta learning or you learning how to learn rather than。

U telling computer this is a learning algorithm to how they get a computer even get better at learning Can you say a bit about that Yeah absolutely。

😊，Part of the motivation is that if， if a robot encounters a new kitchen， we don't want it to just。

Run what it learned in that new kitchen it may actually need to adapt and learn on the fly it may need to。

 for example， if it's trying to open the door to a pantry and the door is a little bit different。

 it may need to take a little bit of experience and trial and error on that door in order to figure out how to open it and we don't we want to allow systems to do this sort of learning process on the fly at test time in new scenarios。

And unfortunately。If you just run machine learning from scratch at test time on a very small amount of data that won't work very well。

 you need large amounts of data in order to learn something。

 so what metal learningning tries to do is it tries to take experience in previous kitchens or previous tasks and optimize for the ability to learn new things。

 the ability to learn new things based on having learned lots of previous things。Yeah so for example。

 you know， what's the best learning rate which wish to adapt to new kitchen setting and lots of other things one could Yeah absolutely so the simplest setting is if you're only optimizing for one parameter like the learning rate in a new situation and in more complex meta learning algorithms you can sort of optimize for the entire learning algorithm So I think of it as one of the world expert in meta learning In fact。

 if remember this is a big part of your PhD thesis which you did way back with a P who was my PhD citizen standard and so just you say more about how meta learning works。

😊，Yeah， so there's a few different approaches to me learning。

 but the approach that was in my PhD thesis was essentially。

Putting a learning problem inside another learning problem。

 so it's actually forms this bilevel optimization， this twolel learning problem where you are actually trying to optimize for all of the parameters in this inner learning problem such that you could achieve faster learning or more efficient learning Yep I remember reading some early papers and very impressive。

😊，So lots of software algorithms， machine learning algorithms， reinforcement learning algorithms。

One part of your work is you also run a robotics lab with robots running around robot arms。

 I'm curious for someone that has not yet spent a lot of time in a robotics lab。

 can you tell us what it like if a student were to join your lab。

 what it like to shrug and work in the morning and work in a robotics lab？Yeah， so in the lab。

 it's not all that different from running machine learning experiments where you run code。

 you try to train a model and then evaluate that model。 but in addition to those everyday things。

 there's also interfacing with the real robot so。Oftentimes。

 a lot of projects might start with a simulation and start iterating on algorithms using a physics engine that might involve actually kind of designing aspects of the simulation to test the hypotheses you want to test。

And。Also sometimes projects won't involve that simulation step or maybe you've already itated in simulation。

 and on the real robot， there is everything from setting up the control stack such that you can actually command the robot to move to a certain position。

 to setting up the cameras to collecting data with the robot that data might be you might be collecting data by using like a VR controller。

 for example， to tell the robot to move to certain positions。And then also actually。

 when it comes time to evaluate a model， it involves actually running that on the robot and seeing what the robot does in real life。

 It's a pretty fun process， at least for me， I think it's very rewarding to actually see the robot do something。

 rather than just see some numbers or some accuracy of your model。

 but it' also requires a little bit of persistence because robots can break down。

 You might have a motor that breaks。 You might。😊，may not have set up the camera correctly it might be giving you all zeros for example。

 there's all sorts of there's many more bugs that can come up than in a system without a robot So you know a number of people have had experience debugging software and then there's debugging machine learning algorithms which has different practices and ideas and then can you say a bit about what debugging hardware in a robotics lab is like？

😊，Definitely， so I think that the。I mean， in general， with debugging。

 you want to rule out possible sources of errors， possible sources of bugs。

 And oftentimes you might have a guess that it is from the software or the hardware。 and from there。

 I think that。I mean， I think that many of the machine learning things will apply。

 You want to look at your data。 And because a lot of the data is actually。Collected in the lab。

 It may not be from a data set。 Then there may be something that is wrong about it。

 And you may want to actually look at the images that the robot is seeing。

 maybe visualize some of the features that your model has learned。You could also。

 I guess one thing that we did recently is we wanted to actually deploy policy on multiple different robots。

 and so we would actually replay actions on a robot and make sure that the robot was reproducing a certain motion that we wanted it to reproduce。

U。So I guess it's， I don't know if it's really， I I think how you Dbu depends a lot on the problem。

 I don't know if there's any one way or any kind of single bug that comes up the most because there's all sorts of sources of bugs。

 But yeah， that gives us a little bit of a sense for what it looks like。

And I thought one of the lovely and frustrating things about robotics。

 as opposed to software is in software， if you make a mistake。

 you can always revert back to an early version of software。

 but that time that you do something and your robot breaks and then you go boy。

 that's another two months of work or something to rebuild that。

 there's a unique experience in hardware。😊，Definitely and because we're doing a lot of work on the software side of things。

 we typically try to get robots that won't break by very like nice high end robot so that we can worry more about the software and less about the hardware but if there are cases where a robot might break we try to get robots where you can pretty easily swap out parts where if one motor breaks you could just swap in a new motor rather than having to repurpose the whole thing。

 but certainly there's lots of challenges that come up you know I used to fly autonomous helicopter so every time a helicopter trash fortunately we manage to keep it safe and away from people then is frankly destroy helicopter that we have to just go build a new one but it's nice when you it to do that too often fortunately arms do not crash too much maybe actually have chosen working on that。

So in your robotics lab， one tool of choice that you've often use is reinforcement learning。

Can you say a bit about the practical lessons， tips and tricks for how to apply reinforcement learning。

 amazing algorithms to yourha by robots Yeah， so reinforcement learning is a really appealing framework for robotics because in principle。

 it would allow a robot to learn something completely on its own through trial and error from data that it collected itself。

😊，And so it's something that we're really excited about for that reason。

 but it's also really challenging for a number of reasons。 So first。

 reinforcement learning typically assumes that you're given some reward signal。

 some feedback and if you're trying to learn how to play a game like like play a pong or an Atari another Atari game you can just use the score as the reward function and just try to maximize your score。

 but the real world doesn't give you a score it doesn't give the robot a score when it tries to learn something and instead the robot might need to learn its own reward function it might need to learn what it means to accomplish a task at the same time of as also trying to learn how to accomplish that task in the physical world。

 So that's one big challenge and and one way that we approach it。😊。

Another challenge is typically in this trial and error and so how do you learn the reward from a demonstration how do you learn the reward Yeah so we learn it in a few different ways。

 we often give it at least give it some examples of what success looks like and we also sometimes give it a full demonstration of this is an example of what we want you to do and then you can get into techniques like inverse reinforcement learning which you worked on a long time ago as well and actually try to kind of invert the reinforcement learning process and try to figure out what reward function underlies this behavior So beyond learning reward functions another challenge is autonomy in the process of reinforcement learning So typically you think of it as a trial and error process where you try to solve the task and then you then want to kind of try it again and in between trying the task and trying again。

You need to somehow get back to some starting point。And maybe for example。

 if you're trying to learn how to do a back fliplip。

 trying it again will involve standing up after you fall down。

But actually sometimes learning that resetting behavior is also quite challenging and there's this challenging interplay between learning how to do the task and also learning how to recover from all the ways that you failed at the task in the entire process of doing that It's really automating the research process so that you run repeated experiments without having to lug a robot around every single time to put it back exactlyact。

😊，And in fact， in your application of reinforcement learning。

 I think you are one of the earliest researchers， you're among the earliest researchers to do you more or less or completely end to end robotics end to end reinforcement learning can you can you say a bit about what that was like in the early days and why you went that route Yeah。

 so at the start of my PhD deep learning was just starting to become popular after AlexNet was showing that you can do very well with deep neural networks trained to end to end for computer vision？

And I had just arrived at Berkeley for my PhD and there were some people that were working on reinforcement learning with neural networks。

 and I was pretty excited about that work and I wanted to see in the past work， it was all blind。

 The robot wasn't using cameras in any way。 and I wanted to see if we could learn a neural network that directly maps from the images taken by the robot's camera to the torque applied into the robot's joints。

 and in that first project it was a lot of work to try to actually get that initial result。

 but we were excited to see that we actually could get a single neural network that could learn something like screen a cap on a bottle or putting a coat hanger on a coat rack。

😊，With a single neural network mapping directly from pixels to torques。

 and it was a pretty exciting result， it was definitely very different from what the rest of the robotics community was working on。

 And I think the paper that we we worked on was actually rejected twice because people didn't like deep learning。

 They didn't like robototicists didn't like that these neural networks were very black box and you couldn't understand them。

 but eventually got published and was accepted。😊，And now it's actually become a much more prominent paradigm in robotics。

 where a lot more people are now trading neural networks to represent the policy。

 to represent how the robot chooses actions based on the camera images。

I think that early work you did was quite visionary and said an important。

 you hope said an important new direction for the field。

 what's your prediction for where this will go， do you think the percentage of practical robotics work that is train end to end。

 how much do you think that will continue to go up or not？😊，Yeah。

 I certainly think that it will continue to grow quite a bit。

 I still not all of the robotics research community is looking at these kinds of approaches。

 in part because there are useful techniques in control theory that are useful。

 especially in controlled scenarios like we talked about。But I think that it will certainly grow。

 I think that especially with as the machine learning field continues to make really impressive advances。

 I hope that that will convince more people that this sort of paradigm is really promising for robotics as well。

 especially in terms of handling the vast degree of variety in objects and environments in the world。

In terms of looking forward， in terms of like understanding what might happen in the next 10 or 20 years in robotics。

One thing that I'm really excited about that we touched on a little bit is trying to train robots on broader data sets a lot of the field of robot learning is still collecting a data for a project in a lab and then training on that small data it's small because it has to be because you collected it for that project。

And I think if we imagine that if computer vision researchers had to collect Inet for every single project that they did。

 they probably wouldn't be making that much progress。 And so I think that my prediction。

 at least for the coming years， is to move towards a paradigm where we reuse data sets a lot and we use much larger data sets and ideally。

 our kind of sharing data sets across institutions across robot platforms。😊。

And scaling up the data that these systems are trained on。

 such that they can generalize more broadly。That's an exciting vision and how do we get there for images everyone uses you know PG files and G files and JP files so the data is highly postpon and highly shareable if different research labs just have different pieces of hardware how do you make that happen for robotics Yeah so it's definitely challenging the place that we're starting that I'm quite excited about is。

😊，First， trying to actually have a little bit of consensus， bring the community together to say。

 okay， let's start with this robot platform with this roughly this setup so that we can at least standardize on some of it and then try to collect lots and lots of diverse data on that fairly standardized platform start from there and then if we're able to get some signs of life and some positive。

Success from collecting a broad data set with those standardized choices。

 then starting to standardize less and less and move not maybe the same robot but with a different control stack and then maybe starting to move towards different versions of that robot。

 different grippers and ultimately lots of different robots and lots of environments cool right。

 this is exciting vision。And in fact。So this is one of the things you're doing in robotics。

Just looking more broadly。With all the work you're doing in reinforcement learning。

 some not even apply to robotics， but to other other applications， where。

 Where do you hopement learning and robotics will go in the next many years。 Yeah。

 so I think that the， I mean， I'm hoping that it will move towards these reusable data sets and very broad data sets。

I also think that even beyond robotics I think that there's lots of other applications of reinforcement learning as well so for example in some of our recent work we applied reinforcement learning and actually meta reinforcement learning a combination of meta learning and reinforcement learning to education to give feedback on student work where students would program a game like breakout and then the system would actually play the game and find the bugs that the students made and give them feedback on how to improve their program and how to continue to learn how to code No this is very cool in fact。

😊，Robots are so visual， sometimes it's easy to forget that reinforcement learning is a general technique for decision making with delayed rewards that's useful for many things other than robots。

Like frankly， when I was the more advice where I used to。

 I used to try to get all my patients to learn to solve。 I don't know if that was a。

I learned how to solder an undergradal， although I don't think I actually ever used that in my robotics work Oh wow。

 I see。Maybe things have moved on， but I had to。Yeah I think we would just buy robots that didn't need some soldering。

 so your journey has led you to do cutting edge work in reinforcement learning and robotics。

I'm curious what advice you would have for someone looking to break into reinforcement learning or roboticings。

 Not everyone。 Yeah owns a cool robot。 that an easy program。 but how should someone get started。Yeah。

 my main advice would just be to try to get your feet wet and just try to build something。

 try to program and code something up there's lots of different things that you can do and I think that learning by trying to build something by trying to do something is one of the coolest ways to learn because you have a certain goal in mind but would you build something using a similulator robot or do you think you should just you know build a little robot？

I think that starting with a simulated robot is probably the easiest and there's less of a learning curve and less。

Less things that you have to do。 you don't have to go out and buy hardware。 That said。

 I think that also trying to work a little bit with hardware right off the bat is is great。

 And there is it it definitely teaches you about how hard robotics is robotics is really hard。

 but also by kind of。😊，Struggling to get the robot to do something。

 it makes it all that much more rewarding when it actually does something cool when it does something that you wanted it to do。

 and I don't know some of the robots that we use are fairly expensive。

 but nowadays there's actually lots of robots that are fairly inexpensive that people can buy or you can kind of build your own robot by connecting wheels and a camera or maybe even a smartphone together to build something I actually got started with Lego robotics and middle school and you could also build robots out of Legos and get started that way。

 Yeah yes， I remember I went to Lego robotics competitions when I was in middle school or something and that was those interesting set of experiences So to someone taking the machine learning specialization。

😊，If their goal is to work in reinforcement learning and robotics。

 what else would you recommend they look at， whether are the other resources you think would be helpful？

Definitely， so there are resources in terms of like just learning about reinforcement learning and there are kind of courses online theres for not there's also kind of course videos。

 there's textbooks like Sutton Barto。And so those are lots of resources I also think that there are lots of I don't know videos online tutorials。

 code bases you can actually check out a physics engine like the Mojoko Ph engine which is freely available and try to kind of explore with that So yeah those are a few resources there's also one thing that we use a lot to interface with robots is called the robot operating system or Ross and so learning about that can also be useful that came out of my research lab way back working with a little garage yeah。

Yes good good times sorry to yeah so I think that those are some of the resources and yeah not too much more than that Co yeah very cool it feels like you know with the world moving forward and evolving feels like the number of paths for someone wanting to get involved in this is even growing and probably gets a little bit easier every year for someone to enter this view so this is an exciting time to be in definitely thanks for joining me here at Stanford University with Professor Chelsea Finnn who's with both the computer science and the electrical engineering departments and leads a research group that does cuttingish work on applying reinforcement learning and machine learning to robotics and other applications thanks for joining us Chelsea Yeah happy to be here。

😊。

![](img/91fe84832ca5079fd23e5da4b1c122b8_2.png)

![](img/91fe84832ca5079fd23e5da4b1c122b8_3.png)