# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p18 P18 CS-E4740 Lecture 24-Feb-2025 -BV1cojRzDEfQ_p18-

あ？To our course。走咧。And welcome to our course on federated learning。Which is offered。

I think you have your。你把消。Yeah。Sorry for the little glitch。 We offer this course as fully online。

 but I'm sitting here in the lecture hall with a few students， which is nice。 But yeah。

 you should be able， or you can complete this course fully， fully remote， itself paced。

 We have no mandatory assignments。 Yeah， at a glance， This course is worth。



![](img/d08c36f5ee750aa354781025ca74b9f5_1.png)

5 credits。It's fully online， no mandatory attendance。 It consists of。6 modelss。

 Each model has a lecture。Which happens on Monday in this in this very time slot in the same zoom lecture hall。

 but yeah， as I mentioned， we also have reserved a real lecture hall。

 a very nice lecture hall here at Alto Campos。 So if you want。

 you can spend or follow the lecture also here in the lecture hall。Whatever you prefer。And yeah。

What else， yeah this year， one of the changes in this edition based on the student feedback is that we offer additional activities。

 so one of these activity will be a paper review so for those of you who are more advanced so which have already some basic knowledge in federated learning instead of the assignments which I will talk about more in a second。

 you can do paper you can review papers like current recent research papers。Yeah。

 another change in this year is that we have the student project as a mandatory part of the basic version。

 So the student project involves a peer review。 So each one of you has to review three to five other project reports。

 this is meant also as a training of the basic or maybe the most important tool in academia。

 which is peer review。So you will practice basically a paper submission， like， like for a conference。

 you could use this also as a A a test for some conference submission that you are working on and get feedback from up to five other students。

Yes， I will tell more about the student project in a second。 Yeah finally。

 last year we had the student project as the extension to 10 credits and this year the student project is part of the five credits version but on a case by case basis so if you if you did well in the basic version in the five credits version I'm willing to discuss potential extension to 10 credits。

 but the details are to be are to be determined so this could be for example extending your student project。

More。Any questions at this point， please ask questions in the chat or here。Okay， so fast good。Yeah。

 just the outline for today's intellectual lecture。 First， I talk about the prerequisites。

 So what do I expect from you， What， what is the starting point。

 the launching point regarding mathematics。En codingding， what are the learning goals。

 What do I want you to learn after this course or to know after this course。

 Then I will talk about related courses。 So I will position this course within broader machine learning curricula。

Then I will talk about the course logistics in particular， the schedule。

 and the final part is then actually getting down to business。

 So we talk about federated learning and how it evolves from basic machine learning techniques in particular。

 from regularization ideas。

![](img/d08c36f5ee750aa354781025ca74b9f5_3.png)

Okay， so the prerequisites for this course， I expect you to be familiar with objects like vectors。

 Euclidean vectors， matrices or norms。 So if， if this looks very strange to you， then either you。

 you try to， to refresh your linear algebra skills or you might consider another taking this course。

 maybe next year。 So this is really the the bare necessity， you。

 you should have one course on or the first course on linear algebra。



![](img/d08c36f5ee750aa354781025ca74b9f5_5.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_6.png)

Then we will use calculus。 So you should be somewhat familiar with the notion of smooth or differentiable functions and the gradient as a generalization of。

 of the differentiation。Okay， we also use or we assume that you are familiar with basic machine learning techniques like this expression here。

 empirical risk minimization should be not too strange to you。

 So you should have had some course already where you train machine learning models and validate them。



![](img/d08c36f5ee750aa354781025ca74b9f5_8.png)

Yeah， and in the exercises， which you will hear more about in the Wednesday session。

 we will ask you or require you to implement these theoretical concepts that I talk about in the lectures。

 I talk mainly about mathematical models， abstract concepts。

 but you will see how to implement them or you will implement them using Python in the assignments。



![](img/d08c36f5ee750aa354781025ca74b9f5_10.png)

Okay， so the learning goes。 What， what do I want you to get out of this course after completing。

 after completing this course， you can model federated learning applications using networks。

 So maybe some of you have had courses on network models， complex networks。

 And we use those models to formulate federated learning applications。And in particular。

 we use those network models to formulate federated learning as an optimization problem。

 So after this course， you should be comfortable with translating a federated learning applications of a real worldor federated learning application into an optimization problem and as soon as you have formulated it as an optimization problem。

 you can try out or you can try any any of the optimization methods you have heard about to obtain federated learning algorithm。

 So this is a very， very clean， very principled approach to design federated learning algorithms。

 We formulate federated learning as an optimization problem and we apply distributed optimization methods to this problem。

And finally， a core component of this course will be key requirements for trustworth federated learning you will hear about explainability。

 you will hear about privacy protection or how to measure privacy。

 leakage using differential privacy。So you will also get some very basic skills for designing federated learning systems that are somewhat transparent or explainable and privacy preserving。

 which which is one of the key features or characteristics of federated learning。

 so how to do how to distributed machine learning by still protecting to some degree the privacy of user or user data。

Are there any questions at this point？So how， how many of you just let me ask how many of you have learned about optimization methods or hadcur on optimization。

 Very good。 How many of you have heard about gradient descent。Very good。

 How many of you have have heard that gradient descent is a fixed point iteration。Very good。

It guess in one of my courses。Now， so just as an outlook。

 we will basically use gradient methods and we will see how to generalize gradient decent methods by interpreting them as fixed point iterations。

 this is useful because gradient methods can only be used for parametric models but you will learn in this course optimization methods that don't require parameters。

 model parameters， any kind of model， a decision tree which doesn't have a natural parameterization。

 you can use or can you can use for the federated learning algorithms that we discuss in this course。



![](img/d08c36f5ee750aa354781025ca74b9f5_12.png)

Okay， so regarding the， the positioning。Yeah， as I mentioned。

 the bare necessities a course on matrix algebra in for some reason。

 for some reason this linear algebra course in Alto is called matrix algebra so this such a course that covers what are vectors。

 what is a linear vector space， what are norms， and all these kinds of very useful concepts。

So we expect that you have taken such a course。 Then you should have had a course like a machine learning Bchelor course at Alto。

 where you learn how to train machine learning models to validate them and to regularize them。

 And in some way， this， this course really takes this one step further。

 So instead of of training one single model on one single data set。

 you will learn how to to train a coupled network of models。 And this network of models could be。

 for example， all smartphones that run a certain app。 So a federated learning app。



![](img/d08c36f5ee750aa354781025ca74b9f5_14.png)

For example。Okay， then you should be familiar with Python， the Python programming language。

 in particular， how to read in data， how to work with numeric data。

 and there I found a nice online course data analysis with Python。 so we we start very slow。

 so you will have the opportunity to refresh your knowledge， but as I mentioned。

 I consider these courses and the content of these courses is really the be necessities for this course。



![](img/d08c36f5ee750aa354781025ca74b9f5_16.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_17.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_18.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_19.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_20.png)

Then what is nice to have， as I said， we use a lot of optimization。

 or we we discuss optimization methods， but I will build it up very slow。

 And maybe from a bit of a different perspective， as you hear in in this introduction to optimization course。

 So from， from my perspective， optimization algorithms are just instances of fixed point。

 fixed point iterations。 And as soon as you understand the fixed point iteration， you understand the。

😊，The optimization method。Okay， yeah。 and then there's also one more advanced course on comics optimization。

 If you really want to look into want to do a careful analysis of， of convergence rates。

 then I recommend this more advanced course on comics optimization。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_22.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_23.png)

Yeah， and as a follow up。 So once you happily finish this course。

 what I found is a course on wireless systems because in this course。

 we mainly talk about mathematical models。 So as I like to say， pen and paper is patient。

 But when you have to implement these federated learning algorithms in real hardware。

 and really on the physical level， you， you must， at some point。

 use some form of of wireless communication link or you must establish a wireless communication link。

 And if you really want to dig into the details of this。

 then there's also an excellent course at alto called wireless systems。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_25.png)

And I also found this course， distributed and intelligent automation systems。

 which covers a very important application domain of federated learning。

 which is the Internet of things。 So a machine learning task or each machine learning problem corresponds to one sensing device。

 And you want to train the machine learning models for each sensing for sensing devices in a collaborative fashion by exploiting similarities between the data sets。



![](img/d08c36f5ee750aa354781025ca74b9f5_27.png)

Okay， any questions at this point？😡，六点。Here on the chat。Okay， here's a question。

 What is the difference between five credits and 10 credits。 Yeah， as I mentioned。

 this potential extension to 10 credits is， is decided case by case。

 So I would suspect that we offer this 10 credit extension only to students which do really well in the in the basic course a variant in the five credits variant。

 And then it's up to， to negotiation what， what you want to do， if you want to expand， for example。

 your paper review， you want to review another paper and write a report about it to get 10 credits or you want to extend your your student project into a journal paper or something。

Okay， then another question， if the course is self paced。

 how do we ensure that all are doing the project， Yeah。

Talk more about this in a second when we come to the course Kittle。 So there are some。

 there are some deadlines。 So it's， it's self paced respecting the， the submission deadlines。

 of course。So regarding the schedule， we have。6 modelss。 So the。

 the core content is divided into six modelss。 The first model is a machine learning refresher。

 which we will cover today。And there will be an assignment for this， for each module。

 So the first assignment will be introduced on Wednesday again。

 here in this Zoom lecture hall by teaching assistant。



![](img/d08c36f5ee750aa354781025ca74b9f5_29.png)

And yeah， then we have a second model， which then starts next week。

 which is about using networks or graphs to model federated learning applications。

Then we will have a third model on a federated learning design principle where you will learn how to formulate federated learning as an optimization problem。

 in particular as an optimization over a graph or a network。

Then the fourth model then build on this by applying distributed optimization methods to this optimization problem。

 which then results in federated learning algorithms。

Then we will talk about some main flavors of federated learning， which you might have heard about。

 So we will talk about classed federated learning， vertical federated learning。

 horizontal federated learning， for example， and we will see how these are just special cases or special specific design choices for this optimization problem that we will learn in model 3 and the final model would say maybe the most important one regarding my my preference。

 it's about trustworthiness。 So there we talk about explainability。

 So we want to build federated learning systems that are transparent to the user to some degree that are robust。

 So if some some node in the network fail， the whole system should not break down。



![](img/d08c36f5ee750aa354781025ca74b9f5_31.png)

Or if some of the of the， of the participants in a federated learning system are malicious。

 Let's say cyber criminals from Austria， then we still want the whole system to work well。

So this is related to robustness。 And， of course， this is actually one of the of the key promises of federated learning or why it became so popular。

 in my opinion， is this promise of of privacy protection。

 So we will see that federated learning algorithms don't share raw data。

 but only derived quantities like model parameter updates。 Of course， there's a tradeoff。

 Some information must be shared， because this is a simple a trivial observation。

 if there would if if there would be perfectly information protection。

 So there would be no information spreading out of of a client in a federated learning system。

 then why， why should you use it at all， should it be included in the federated learning system。

 So some information must be shared between the nodes。 But the question is which information。

 And this is sensitive information。

![](img/d08c36f5ee750aa354781025ca74b9f5_33.png)

Okay， then the content of these models is evaluated in graded activities because I guess some of you or most of you want the grade for this course。

 So the graded activities include assignments where you will implement all these mathematical ideas and concepts in Python using auto graded Python notebooks。

😊。

![](img/d08c36f5ee750aa354781025ca74b9f5_35.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_36.png)

You will hear more about this on Wednesday in the exercise session。And yeah， we will also release。

 We will release the， the Python notebooks around Wednesday。 So you will then on Wednesday。

 you can start to work on this， on these notebooks。

They are small student tasks which require you to complete code snippets， basically。Okay。

 then the second core component of this course is a student project。

 And there I want you to practice the modeling。 The modeling is is really the art here。

 How do you formulate a federated learning application。

 Any application of your wish as an optimization problem。 So this is。

 this is your task and in the project。 you must formulate a federated learning application using the concepts that you learn in this course。

 So in some sense， this course teaches you some instruments or language that you will then apply in the in the project。

 So you will you will use the language to formulate a federated learning application such that your colleagues who peer review it。

 understand it。Yes。Very good。 Yeah， So there was a question。 If the project is individual， Yes。

 every student has to submit independent personal project report。 There is no group work allowed。

Okay， yeah， and then one change that I implemented based on the student feedback of last year。

 where some students were a bit， let's say bored。 So they were more advanced and they wanted to really read and understand the cutting edge or bleeding edge Feerated learning techniques。

 And for those students， I have now introduce a paper review activity。 So instead of the assignments。

 If these assignments are boring to you， you can look up a list of papers that I have linked here with a Q R code。

 you find those list also on the on the federated learning website that I have shared。With you。

 why are my courses？And yeah， the deliverable。Or the task of this paper review will be to interpret this。

 this paper that you pick using the， the instruments and the language of this course。

 So in this course， you will hear about G TVV miniization。

 So that's the name of this optimization problem。 And I want them to， to hear from you in your。

 in your paper review。 What type of G TVV minimization does the paper use。

 or is it completely different from T TVV minimization。

 You must somehow interpret or analyze this paper using the instruments or concepts that you learn in this course。

That's the， the name of the game。 And you have to present your review as a slide talk and the deliverable will be the the slides and a recorded talk。

 This is like a little conference talk。 Should also let you practice conference presentations。

 And this should be maximum 10 minutes。 This is also a bit of a challenge。

 You must stay within 10 minutes in your talk。

![](img/d08c36f5ee750aa354781025ca74b9f5_38.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_39.png)

Okay， then so these are the graded activities。 You can collect points in this graded activities。

 The point distribution is as follows。😊。

![](img/d08c36f5ee750aa354781025ca74b9f5_41.png)

Okay， there's one question。 Yes， please ask the questions on the chat。Have a look。

There's one question。 I there any intersection between graph learning and federated learning。 Yes。

 we will。 So this is already quite detailed question。

 We will talk about graph learning in the second model about when we talk about federated learning networks we can use or we。

 we sometimes should use graph learning methods to learn the optimal collaboration pattern between federated learning node。

Then another question， does the project need to be something new or just an implementation is fine。

 Well， it it， it cannot be， you cannot use， reuse a student project from another course。So。

 but you don't have to invent， actually， we， we require in the student project that you use some of the methods from this course。

 So you don't have to invent a new federated learning algorithm。



![](img/d08c36f5ee750aa354781025ca74b9f5_43.png)

You just， yes， another question。诶呀。Yes。😊，嗯哼。😊，Yes， so the question is。

 how does the points combine that you collect from the paper review with the points that you get from the assignments。

 And for this， we have here this formula。 So we use the maximum of the points that you get from the assignments and from the paper review。



![](img/d08c36f5ee750aa354781025ca74b9f5_45.png)

So you can do both。 You can do assignments and the paper review。

 and we will take the higher number of points。

![](img/d08c36f5ee750aa354781025ca74b9f5_47.png)

Yes， you can。 you can only improve。啊，是。是。So maybe this answers your question。

 when I go over the point distribution。 So for each of the assignments， you can get up to7 points。

So in total， we have 6 assignments， which makes 47，47 points， if I'm not wrong。呃。



![](img/d08c36f5ee750aa354781025ca74b9f5_49.png)

So for the peer grading， you get 7 points from the project，51 points。 And for the paper review。

 you get up to 49 points。So， yeah， you can， you can improve using the paper review if you get full points。

 you get more than if you would do all the assignments。Slightly more。

 I'm not sure what put the intention there。But， yeah， so， but the idea is to， to allow students who。

 who， for， for which this for whom these assignments are underwhelming。

 that they just focus on the paper review。 They don't have to do the assignments。

But it seems we are final。上。Well， penalized if you。

So the paper review will for sure not be the easy option。Yeah。Yeah。Yeah， so the， the attention。

 the intention is that you can replace the assignments with the paper review。 but if you want。

 you can also do both。 but I'm not sure if this is type of hit is 49 points。

 and we should have here actually 42 points。 but yeah， it's not a two big of a difference。



![](img/d08c36f5ee750aa354781025ca74b9f5_51.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_52.png)

呃。No worries， if you， if you're really interested in work hard on the course。

 you will get a good grade。 I'm confident。

![](img/d08c36f5ee750aa354781025ca74b9f5_54.png)

But， of course， we also don't make it too easy because we want to make， keep you motivated。



![](img/d08c36f5ee750aa354781025ca74b9f5_56.png)

So， yeah， how do we translate the points into the grade。So for 50， when you。

 you need to get at least 50 points to get a positive grade or to pass the course with grade 1。

50 to 59 points。 then starting at 60 points， you get a grade 2， starting at 70 points。

 you get a grade 3，80 points for grade 4 and at least 90 points for the top grade 5。



![](img/d08c36f5ee750aa354781025ca74b9f5_58.png)

对。I this okay， doesn it， Yeah， I think it's pretty， pretty straightforward but pretty regular。嗯。Okay。

 about the assignments。 So as I said， for each model， we have one assignments。

6 models make six assignments。 First assignment is about using Python to implement model training。

 validation and regularization。 Second model。 you will use network models using network X library to。

 to make a whole network of machine learning tasks。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_60.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_61.png)

Then you will see in assignment 3， how to， how to solve federated learning as an optimization problem。

 As 4 is about implementing federated learning algorithms as message passing over networks。

Assignment 5， you will look at two specific flavors of federated learning， in particular。

 clustered and vertical federated learning。

![](img/d08c36f5ee750aa354781025ca74b9f5_63.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_64.png)

And in the assignment 6， you will study privacy attacks。

 think this is about inferring the location of somebody from whom you only know whether predictions。



![](img/d08c36f5ee750aa354781025ca74b9f5_66.png)

And you will learn how to ensure subjective explainability of a federated learning system。



![](img/d08c36f5ee750aa354781025ca74b9f5_68.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_69.png)

Okay， then about the student project， as I already mentioned， you can choose。

 You are free to choose any a federated learning application of your choice。 There's no limitation。

 no restriction。 You only have to use the tools or instruments from this course。

 So you have to design and study the federated learning algorithms that we talk about in this course in model。



![](img/d08c36f5ee750aa354781025ca74b9f5_71.png)

4， I think， yeah， Model4 and Model three。Then you have to write a project report。

 which is similar to a conference paper。 And we will also provide a template for this。 So the。

 the structure is pretty much fixed。 You will get a lottte。Template for this。 Yeah， I think we。

 we would stick to late tech as the， the document。Preparation tool。

 I hope everybody is familiar with latete or willing to learn it。 It's， I think it's still the。

 the standard type setting tool in， in academia。As far as I know。Okay， then yeah。

 we'll have a bit of time。 The project only starts after these boot camps。 In the beginning。

 we have these six models， which are kind of a boot camp。

 You learn the basic techniques and instruments， And then you can focus on your， on your project。

 and you have to submit the first version of your report by the end of April。

Then we have a two weeks peer review phase。 So till mid of May。

 you have to peer review others reports， and we will still need to decide how many reports you have to review between 3 and 5。

 I think， would be a good。Good number。 Yeah， and the final deliverable is revised report。

 So you have to revise your report based on the peer reviews and you have to prepare response letter。

 So we will also provide you a template for the response letter where you explain how you revised your report based on the peer reviews。

 So this， this should。Let you practice this basic workflow of paper submission in academia。 This is。

 this is how it works。 So you get reviews， you get feedback。

 You try to address this feedback and submit the revised version。 And then the associate editor。

 for example， me， decides if you sufficiently address the the reviewer comments。

 and it can be accepted。 In this case， we don't have acceptance or rejections， but the grading。

So the， the number of points that you get depend on on how well you took into account the。

 the peer reviews。Yeah， just want to point out that we often get the feedback that students don't like this peer grading activity and we have deemphased this peer grading activity to  seven points。

 but just to point out we take your peer grading performance into account so you must do a reasonable job not just giving best grades as a peer review and no justification。

 So each each aspect of this peer review， we have some 10 to 15 aspects for example。

 does the report clearly explain the network structure used or something like this and you must then justify your peer review No the paper didn't explain or didn't describe the network structure or yes。

 the network structure was described in section b so it must be reasonable comments that you should give as a peer reviewer and we will look at those so if if you do trivial response。

For the peer peer review， you might not get the seven points。



![](img/d08c36f5ee750aa354781025ca74b9f5_73.png)

Okay， the schedule， what about the schedule we have the lectures each Monday。

 so six lectures for the six models starting today in Zoom。

 if possible I will try to be also present in the lecture hall like today。

 but by default there in Zoom in this zoom meeting which you are now currently。Then on。

 on the following Wednesday， we will have an exercise session where a teaching assistant introduces the assignment for the。

 for the model。

![](img/d08c36f5ee750aa354781025ca74b9f5_75.png)

So for example on the first two assignments。 So assignment 1 and assignment 2 must be submitted by the 17th of March。

 So we have the same deadline for the first two assignments。

 which gives you more time for the first assignment and less time for the second one。呃。

In order to get into speed， to get used to， to this sufficient system。 So we use a Jupyter hub。

 which we will hear more about on Wednesday。And yeah。

 we then have the next deadline end of March for assignment 3 and assignment 4。

 and the final deadline submission deadline for the assignments is 14 April for assignment 5 and assignment 6。

Yeah， and this is before then the first project report submission， which is end of April。

 So this project， you should focus then after the module after the assignments。Okay。

 peer grading until 15th of May already mentioned。 and the final project submission is end of May。



![](img/d08c36f5ee750aa354781025ca74b9f5_77.png)

Which is also the official end date of the course。 I think， yeah， this course is。Until end of May。

 running until end of May。Okay， let's see here we have questions。Then one question。

 what if someone wants to do more than one project， will they be graded， So， well。

 if you want to do more， then we could discuss this extension to 10 credits。 But by default。

 everybody does one project。Next question， does Chet GP T use federated learning in its implementation。

 or only if it requires multiple inputs that federated learning is used， I don't know。

 I don't know how and if and how Che GPT uses federated learning。嗯。

Regarding then another question regarding paper review。Is the list of papers exhaustive， No。

 so I'm also open to， also open to suggestions from you。

 So if you have a cool new paper at Nips that appeared on Nips and you want to do a paper review。

 please let me know。 We can discuss it that you can use。 Also papers beyond the list that I provide。

Yes， any other questions at this point。A good point。 So the question was。

 if there will be exercise sessions for the project work。 So when you worked then on the project。

 we might set up some。 Yeah， it's not planned yet， but it's a good point。 I might set up some。

 some garages。Yeah。

![](img/d08c36f5ee750aa354781025ca74b9f5_79.png)

No。也一次一次。Yes， yes。 that's a good point。 So we might set up up some two or three project garages where I will be present in some lecture。

They a good point。对。But we have the。对。啊。I hope till next week I'm I'm working on it soon， soonish。

 Yes， but yeah， in in general。 So the question was。

 when will the the the project report templates be available。

 I'm working on it publishing them and hope to publish it by next week， but yeah， as I said now。

 I would say for the next four weeks， the the focus should be more on the。

 on the lectures and assignments， But， of course， you are free to start already now thinking about some interesting and exciting Feerated learning applications。

😊，For your project。Okay， so。Theres one one more question。

 If I have doubts regarding assignments after the exercise session， can we ask through S， Yes。

 please make heavy use of our slack discussion forum to ask about exercises or lectures。

 Anything about the course。Okay， so yeah， for， for this course。

 I really want to emphasize the two main ground rules that I have in my courses and that I。

 I started to， to explicitly articulate in the first lectures。 So， first of all。

 as a student as a participant of this course， you must act according to the auto university code of conduct。

 How many of you have have read the code of conduct。No， I have read， I， I have glanced over it。

 So it's something， something we all commit to like code of conduct for research integrity and b。

 but it's good to sometimes actually read it。 but I have， I have summarized it， basically。

 So the two two main ground rules are as in general， in academia， be honest。

 So this course involves a lot of independent work， completing assignments。

 I will not sit next to you and check when you submit your assignments using your Python notebook It's up to you。

 I trust you that you do your assignments yourself。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_81.png)

What is important is you should not steal work of others， ideasas of other solutions of others。

 Be honest to yourself also， and in particular， indicate or cite any source that you used。So this。

 this is rule number one。 be honest。 And， of course， trust is trust is good and control doesn't hurt。

 Or how is the saying， So we will randomly select students。 this I I do in all my courses。

 which require a lot of independent work。 We will use a fair a lottery wheel and select randomly select students。

 which I invited to one on one meeting with me and have to explain their solutions。

 which should be no problem if you did your your assignments yourself。

 you just have to explain them to me。And of course， I expect that you have no problems in explaining。

 but if I get the impression and I really， I'm a very kind person。

 but when I feel my kindness is exploited or abused。

 it turns So I will not hesitate to report to to the study admission officers because I want to ensure that when you get a grade。

 it's really deserved in this course and I want to combat any gaming。



![](img/d08c36f5ee750aa354781025ca74b9f5_83.png)

As much as I can。Okay， so rule number one， be honest。 Rule number two， be respectful。

 will not tolerate any disrespectful behavior in this course。 And again。

 if I observe this and there's really a confirmed case of disrespectful behavior bullying or inappropriate comments also in the discussion forum。

 I will report this。

![](img/d08c36f5ee750aa354781025ca74b9f5_85.png)

So be honest and be respectful， and then we have no problem。O。Any questions at this point？Good。

 then for the yeah。 just wanted to ask， do you prefer having now a little break or now finishing the material。

 And we， we stop earlier， So who wants a break。Who wants to continue and finish earlier。另一个。

Some are still indecessive， but the majority ones。To continue， O。

So it seems to be not overwhelming so far。In general， I， I tend to， to speed up when I talk。

 And the best way to slow me down is to ask questions。



![](img/d08c36f5ee750aa354781025ca74b9f5_87.png)

Let's see if we have a few here on the chat。Will so one question here is。

 will edge machine learning deployment be discussed in this course。

 I'm not sure what you mean by edge machine learning deployment。 But yeah， as I mentioned before。

 we will mainly discuss mathematical models。 So we will not talk about。A low level implementations。

Of federated learning algorithms。Another question， are there any predefined projects or we should define a project for ourselves at the moment。

 I'm not leaning towards preparing a list of topic ideas。

 I I want to make it also a bit of a challenge for you to come up with a good choice。

 a useful choice。 So there will be no predefined。 Most likely。

 there will be no predefined project list of project topics。



![](img/d08c36f5ee750aa354781025ca74b9f5_89.png)

Okay， so let's jump into the fray of the actual course content。

 So this course is called federated learning。 Then it might be good to first talk about what is federated learning。



![](img/d08c36f5ee750aa354781025ca74b9f5_91.png)

And my， my one sentence definition of federated learning， which I hope you will。

 you will fully grasp after this course is as follows。

 Feerated learning trains machine learning models in a distributed fashion over a network of devices。



![](img/d08c36f5ee750aa354781025ca74b9f5_93.png)

So we have here in this sentence machine learning， machine learning models。

 So it's a special type of machine learning。 or you could view it as an upgrade of machine learning。

😊，Which uses networks。 So it's， it's bringing in communication networks。

It's binding together communication networks or networking ideas and machine learning。

 training of machine learning。呃。In a sense， it's distributed optimization of。

 of machine learning models。

![](img/d08c36f5ee750aa354781025ca74b9f5_95.png)

And I have shown here one， one prototype， one prototype or one。

 one example for a federated learning application， which was popular or which was very hip two years ago or so when we had something called the COVID pandemic。

 maybe some of you remember。Those nice days sitting alone at home。And following Zoom lectures。

So we had several apps。 So researchers then felt， of course。

 obliged to contribute and develop apps like Covid trackcker apps。

 And these apps could be seen as a simple form of federated learning。 So you。

 you train your own model。Which is to predict， are you very likely to have Covid or contracted CoviId or not。

 So we want to predict something。 And these predictions are based on， on local observations。

 So there has been， maybe some of you have heard this cough detector app。 Was it from Cambridge。

 They developed a machine learning system that analyzed cuff cuffing。 when you cuff。

And the recording of it was analyzed if you have Covid or not。



![](img/d08c36f5ee750aa354781025ca74b9f5_97.png)

I don't know if it took off。 I I have not followed it further。

 but this is111 machine learning problem， but to improve it。

 you could couple these cuff detectors over a network of a million people。 and this。

 this kind of scaling up this using collaboration between many， many， many machine learning models。

 This is one of the key aspects of federated learning。

 So we want to collaboratively train personalized models by exploiting similarities between many small chunks of data。



![](img/d08c36f5ee750aa354781025ca74b9f5_99.png)

Yeah， some key characteristics of federated learning are that we we have no centralized data collection。

 So this gives some form of， of robustness because if you have a server based system。

 if you kill the server， the system doesn't work anymore in this course。

 you will hear about fully distributed peer to peer， federated learning algorithms。

 So if you take on one of the peers。The network will still continue。With other peers。

 So it's like a self healing property of these federated learning systems。Yeah。

 another key characteristic is this personalization of models。

 So each model or each device in a federated learning network。

 in a federated learning system trains a personalized model。

 So this means I can train a model that is really tailored to me， gives me the optimal prediction。

 How long does it take me to get too campy when I start now。When I take a bike。

 I don't want to have the average prediction。 How much does it take for an average person cycling from here to camppi。

 I want to have the tailor prediction。 How long does does it take me given my current fitness condition。

 My bike， the road conditions currently I really want a tailored prediction。

 And this is something that federated learning can do， if you have suitable if。

 if you have the federated learning system designed accordingly。

 So there's a personalization aspect in federated learning， And then there's the scalability。

 So instead of only using my history or my， my cycling history。

 I can use the information contained in in the cycling logs of millions of users。

 So how many of you have a fitness tracker or use the fitness tracker。

There's a company called Paular， I think， in， in Finland。I'mlock paid by them。

 I just remember their name。And I assume if I remember correctly， they have also apps。 And in。

 in via these apps， they collect all kinds of fitness traces whenever you run。

 polarlar gets a bit more data that it can use to train a better predictor for how long it takes me to get to camp。



![](img/d08c36f5ee750aa354781025ca74b9f5_101.png)

Okay， and it's the maybe the most widely non characteristicacteristic of federated learning is the privacy。

 So no raw raw data is shared only model parameter updates or some other derived quantity。

 doesn't need to be model pameter updates can also be something else because in this course。

 you will you will learn how to do federated learning with nonparmetric models。

 And for nonparmetric models， you don't have model pa。 So you don't exchange model pa updates。

 You will exchange something else。 And this you will see in a later model。 what we exchange。Okay。

 here's another question。We had the。Covin E in India， which had this distance thing。 Okay。

 this's just a comment。 Thanks for， for mentioning this。 Co V E。 I didn't hear about this before。



![](img/d08c36f5ee750aa354781025ca74b9f5_103.png)

Then another question， if the model is being trained on data from various users。

 How is it personalized to one user or each user on their device。 Very good question。

 So this is a bit of contradiction。 So we， we share the information。



![](img/d08c36f5ee750aa354781025ca74b9f5_105.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_106.png)

We share the information among devices。 but at the same time， we train a personalized model。

 And this is something that that federated learning can can trade off。

 So we you will hear about federated learning systems that know how to combine the information from other users。

 So which other users have similar characteristics to me， for example。

 have the same body mass index as me or the same cycling training level。

 So this federated learning algorithm。 they know which other information to pick to optimally train your own personalized model。

Very good question。Okay， another question。There's a question， what does it mean non I IT？Data。

 where is this non ID data。 I didn't mention it here。 I guess the question refers to another module。

 I will talk about more about non I ID in in a later model， but not not in this introduction。



![](img/d08c36f5ee750aa354781025ca74b9f5_108.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_109.png)

Okay， so federated learning applications， a quick overview Feerated learning is is one of the of the hot topics or or buzzwords in in machine learning。

 gaining more and more traction in applications beside healthcare。

 So I would say maybe healthcare was the first main application。

 really federated learning took off some eight years ago， but now you find it in in mobile networks。

 So you can use federated learning to optimally steer base stations to optimally allocate resources in in mobile networks。

 you can use federated learning for cybersecur。 So each server each server or each node in the Internet trains machine learning model to detect cyberat。

In autonomous vehicles。 So each， each car， electric car， I don't say any brands， each car。

Can train its own machine learning model for obstacle detection。 And this。

 this individual models could help each other。 So if there's one well trained model and I pass by this car with my own car。

 why not exchanging this information。 So my model， all of a sudden becomes better in obstacle detection。



![](img/d08c36f5ee750aa354781025ca74b9f5_111.png)

Yeah， yeah， I have put here more more examples， but I really would like look forward already to the。

 the project where I see all your federated learning applications。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_113.png)

So I will skip those here。 Maybe。 yeah， for the， for the lecture parts to illustrate some of the concepts。

 our running example will be the weather。 I really like the weather It's such an innocent topic and a good data source So we will use the federated learning application of the Finn Meteorological institute。

 So here we have we have weather stations。

![](img/d08c36f5ee750aa354781025ca74b9f5_115.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_116.png)

And you will， you will learn how to down how to analyze this weather data in the assignments to read in this weather data。

 This is only a subset。 I think in total， there are some 200 weather stations all across Finland。

 and you could then try to train a forecasting model for each weather station or for the neighborhood of of each weather station。



![](img/d08c36f5ee750aa354781025ca74b9f5_118.png)

嗯。Story。Just a technical glitch。Whi is good to slow me down。 so I can check the。Questions。you hear。

Okay， so we can train a different。

![](img/d08c36f5ee750aa354781025ca74b9f5_120.png)

Or a separate forecasting model， for example， for the Kzau area， Another model for the innerry area。

 Yeah， another model for Inon Takeu。And this might make sense because the， the。

 the dynamics of weather in inery might be very different from the dynamics of weather near Toku。

So you will you will learn how to use federated learning to to optimally combine the information in all these weather recordings。

 And this is nice about the FMI。 It really has a nice data interface so you can read in this weather data using Python scripts。



![](img/d08c36f5ee750aa354781025ca74b9f5_122.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_123.png)

And all this information in this local weather data can be combined to train optimal weather forecasting systems for each of these locations。



![](img/d08c36f5ee750aa354781025ca74b9f5_125.png)

Not a nice example of open date， yes。Hi， Steve Justin， say all。



![](img/d08c36f5ee750aa354781025ca74b9f5_127.png)

I probably instead of bringing out of mu。对。Yes。Yes， so the。

 the question was the standard machine learning approach would be to。

 to just define more features for the， for the weather stations。 So to include the。

 the location of the of the weather station， the latitude and longitude as features of a data point。

 And then you just scrape， you download all the data from all FMI stations and use one single deep neural network that also uses the。

 the latitude and longitude as features， yes。😊。

![](img/d08c36f5ee750aa354781025ca74b9f5_129.png)

Okay， then another example of distributed data。And distributed machine learning problems finished road safety。

 So I also found out that you can download the current or the most recent snapshots of。

 of road cameras， weather cameras operated by thin traffic。 And you could say the the weather。

 the snapshots of the weather cameras over the last 10 hours is the local data set for one node in a federated learning network。

 And you would like to predict， for example， what's the risk of having a congestion here during the next hour。

And， of course， these data sets are interconnected somehow because there is a road underlying road network。

 So if you have a congestion here in in Raa。

![](img/d08c36f5ee750aa354781025ca74b9f5_131.png)

You might have then a bit later congestion here， also nearby in Orulu， somewhere near Orulu。

So there are some， some intrinsic similarities between the statistical distributions of the data sets。

 and we， we will see federated learning algorithms that exploit these similarities in the in the statistics。



![](img/d08c36f5ee750aa354781025ca74b9f5_133.png)

There's one question in the FMI example。 we can train separated models， Cant we。

 What are the advantages of federated learning？ Yeah， so very good question。 Why not。

 why not training a separate model for each weather station。



![](img/d08c36f5ee750aa354781025ca74b9f5_135.png)

It could be it could be the best， so it could be that we have enough weather observation in in Xa。

 for example， and the weather distribution is so different from all other weather stations that it does make any sense to collaborate So it might be that for some applications。

 the best thing you can do is independently train a separate machine learning model for each local data。

 There might be applications where this is the best way to do it。However， if。

 if you have very small data sets and in particular。

Small relative to to a model that you want to train for weather forecasting。

 we now use deep neural networks with billions of parameters。

 So this means that a data set with a million data points is small。

 So for small local dataset sets relative to the the dimension of the local model that you want to train。

 you don't have enough data on， on one client。 So you need to pull somehow the the information from several local data sets。

 but you must pull them in in the right way。 you should not pull for example， data from。

 from the coastal weather stations， which have a very different statistical distribution as I。

 as I understand。

![](img/d08c36f5ee750aa354781025ca74b9f5_137.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_138.png)

Okay， just one， one final example for an application is the Internet of things。

 and this is growing fast。 So I I found here some， some numbers from， from Erickson。

 which is the the Swedish Nokia。So we have around billions of of interconnected IoT or IoT connections。

 And you could think of each each device in an IoT network as running one simple machine learning algorithm。

 So how， how do we coordinate or how do we make them collaboratively train their models。



![](img/d08c36f5ee750aa354781025ca74b9f5_140.png)

嗯。Okay。Any questions at this point？No。Let's look at the chat。ちょっとか。



![](img/d08c36f5ee750aa354781025ca74b9f5_142.png)

Okay， so how， how do we get from machine learning to federated learning。

 So basic machine learning is to train a single model by minimizing the average loss on a single data set。

 So how how many of you have implemented machine learning training in in Python。



![](img/d08c36f5ee750aa354781025ca74b9f5_144.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_145.png)

Yes， so， but no worries， if you didn't do it， we will have a short refresher in the first assignment。

 So this just to bring you onto onto speed onto the same that we are on the same page。



![](img/d08c36f5ee750aa354781025ca74b9f5_147.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_148.png)

And the difference now between machine learning and federated learning is。

 you train a separate model for each device。

![](img/d08c36f5ee750aa354781025ca74b9f5_150.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_151.png)

So all of a sudden you， you're not having So this is the。

 the prototype of a Python implementation of a machine learning method。 So you， you read in data。

 store them in an Empireary， X and Y。

![](img/d08c36f5ee750aa354781025ca74b9f5_153.png)

呃，You choose a model哦。By some from some library and you hit the dot fit。

 but the you on the dot fit function。That's basic machine learning。

So what's difference in federated learning， We now do very similar， looks very similar。Actually。

 it looks exactly the same in each node。 So where do you think is the coupling here between these machine learning models。

So when you implement the federated learning algorithms in this course。

 the code looks pretty much like this。So where do you think we， we do the coupling。

So we could do it in model dot fit。We could bring it in somewhere here， yes。

 so it's a tough question， I admit。But the， the idea will be to bring it it here in read data。

 So we will， we will。 instead of reading in just the N features X and Y， the features in the label。

 we will also read in data from other devices， which， for example， have an I address。

 So all you need is an I address and then set up an I socket to it。 but forget about this details。

 We will not discuss this I socket programming in any detail in this course， but。



![](img/d08c36f5ee750aa354781025ca74b9f5_155.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_156.png)

Just one one idea how to implement this coupling。 And this read data function gets some summary statistic from the other node。

So they exchange some summary statistic and one form of a summary statistic could be a model parameter update。

 but that's only one form。 you will see other statistics that we can exchange。

 The important thing is we will never share the raw data。

 We will never share this X and y that we get in here with this note。

 we rather share some model parameter update in this in this read data function。🤧。Okay。

 there are some questions。So there's one question we we could use federated learning for air quality analysis as well。

 Yes， that's one possible application for a project。

 So instead of one big machine for each subdistrict or one big machine learning model。

 we could use one for each junction does that counted federated learning if we are trying to build a model for that。

 Yes， so this would be a very cool federated learning application。

 air quality prediction or air quality forecasting。Next question。

 how hard it gonna be to secure the global model in federated learning as a malicious node might trigger data from local node no to global model。

 So we will talk about robustness against data poisoning in the last model in Model 6。

 So I will briefly touch methods to make federated learning robust against some malicious node who。

Who intentionally perturbate the。Then another question， I have heard that infeerated learning。

 the model is initialized at the central server and then distributed to the clients。

 Can different models。Be distributed to the clients。 So in this course。

 we will mainly talk about fully distributed decentralized algorithms where each node starts with。

 with its own initialization。 So theres no initialization needed from a server。Next question。

 how federated learning can handle participants instability， for example， in vehicles， vehicles。

 I mean， in some cases， we have various participants in this case， will the result be reliable。

 Very good question。 So this is related to robustness。

 So we need to make our federated learning systems robust to to devices that don't behave as expected。

 for example， because they are run by an Austrian cyber criminal or something is wrong with the device。

 It just doesn't work and spits out random numbers。 So we we should develop。

 so trustworthy federated learning systems must be robust against to some extent and against such such failing node。

 so to say。Next question。 Very good question。 iss federated learning similar to transfer learning。

 Yes， so in a sense， these federated learning methods are trans form of transfer learning。

 We transfer the knowledge from different devices to other devices。 So it's a special case of。

 of transfer learning or a specific form of transfer learning。😊，We are good question。 next question。

 Do we choose our models in each device based on each client data？ Yes， so the。

 the model that we use， for example， here。 in this example。

 if we use S T D regression or here decision tree， this is a design choice。 And in principle。

 or in general， this design choice is based on the local data statistics。 So you must somehow know。

 if you want a decision tree or somebody requires you to， to use a decision tree， for example。

 because decision tree are transparent or easy to understand。 So this is a design choice。

 each client can choose its own local model。Next question。

 how do we average the model weights while models are not the same。 Very good， very good point。

 So in this course， you will learn methods where you federated learning methods that can cope with completely different types of model。

 So you can have one node， which runs a decision tree and another node。

 which runs a deep neural network or linear regression。

 and you will see how to combine those models not by model parameter updates。

 but by something that is similar to knowledge distillation。

 So you will see how to couple those models by forcing them to have similar predictions on a common test set。

 but you will hear more more details about this in model。4our or three and four。Next question。

 can a node help another node to train its model because of computational power？Yes， so it might be。

That one node has so much computational power that it can train the model much faster than others and get better predictions on a test set。

 which is then shared。 This knowledge is then shared with other nodes， which run slower。

 which have less computational power。 So in a sense。

 this federated learning algorithms allow also to leverage computational power of neighboring nodes。

 not only not only data or not only the information in the data。

 but also the computational advantages of other nodes。😊，Very good questions。 Next question。

 if the models are introduced。

![](img/d08c36f5ee750aa354781025ca74b9f5_158.png)

At clients， how can we ensure the consistency in aggregation of model parameter update model。

Update parameters because different clients can initialize different models。 Yeah， as I said。

 we will discuss this in Model 4。 We do this by a form of of knowledge distillation。 So we。

 we never compare or we don't compare model parameters。 We only compare predictions of models on our。

 on a curated test set。 So the the different models should somehow agree on a carefully chosen set of data points。

 That's how we couple the models。

![](img/d08c36f5ee750aa354781025ca74b9f5_160.png)

Next question， how is federated learning different from decentralized machine learning， I。

 I don't know what exactly is meant by decentralized machine learning。

 I would say federated learning is， is one form of decentralized machine learning。🤧。Next question。

 is it possible to reverse engineer or infer private data from shared model parameters such as gradients or weights？

Yes， yes， that's possible。 That's known as a model inversion attacks。 So model inversion attacks。

 they， they just observe， for example， what， what was the。

 the model parameter update shared of this node here with that node。

 And just from knowing the model parameter update or a gradient might be a gradient。



![](img/d08c36f5ee750aa354781025ca74b9f5_162.png)

This note can find out a bit about the， the local data here。To some extent， this is possible。 yes。

 and we will have one，1 assignment。 think assignment 6。

 you will try out a method that allows to infer some properties of the local dataset set just from the model parametergameter updates。

Next question， can data specific aggregates be shared across devices in this setup？

I'm not sure what is meant by data specific aggregates here。 So I need to skip this question。 Sorry。

 Next question。 how the federated learning model would provide compatibility。

 like backward compatibility is different nodes might have different resources。



![](img/d08c36f5ee750aa354781025ca74b9f5_164.png)

Good question。 So I don't know how to I answer that。 As I said， in this course， we。

 we mainly ignore implementation details。 So as as long as we can compare the model predictions on a test set。

 we can use this， this device or the machine learning algorithm running on that device。

Next question is federated learning used only in the training or also in inference。

 So in this course， we focus on the training phase。

 We focus on federated learning algorithms that are used to train machine learning models。

 And once you have trained a machine learning model， For example， for this node here。

 you just use it on this node for make for making local predictions。 So these predictions。

 the prediction step is then fully decoupled。 We only use the coupling for their model training。Okay。

 so just to， to finish my last few slides， from a mathematical perspective。

 we can think of federated learning as a tensor product。

 I like this tensor product concept of of machine learning。

 So instead of having one single machine learning problem， which is to fit a curve to data points。

 we have now a whole collection of machine learning problems。

 So a whole collection of data sets and a different curves， which might come from different models。

 So here we have a linear model here we have a polynomial model。



![](img/d08c36f5ee750aa354781025ca74b9f5_166.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_167.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_168.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_169.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_170.png)

Yes， but more details about how we couple these individual machine learning tasks will be provided in the next lecture next Monday。

 I just want to finish this lecture。 let's say with five minutes of machine learning refresher so that we are all on the same page so I apologize for those for for those who have seen this already a thousand times。

 So what what is machine learning， machinech learning is about learning a hypothesisesis map。

 It's learning about it's about learning a function。



![](img/d08c36f5ee750aa354781025ca74b9f5_172.png)

For example， I want to know for a certain user， give them a certain mood and daytime。

 what is the best song that I should recommend to the user。



![](img/d08c36f5ee750aa354781025ca74b9f5_174.png)

To up uplift his mood。 And this might， might seem like a toy application。

 but I have found actually a recent work on how to choose the right songs or how to use music to treat depressions。

 So we might train a model。 And if we， if we solve this problem well enough。

 we might get rid of of medical treatment， of depressive disorders。



![](img/d08c36f5ee750aa354781025ca74b9f5_176.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_177.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_178.png)

Which might be， of course， a loss for Orion company in Finland。



![](img/d08c36f5ee750aa354781025ca74b9f5_180.png)

And mathematically， as I said， so machine learning is about fitting a curve to a bunch of data。

 which we we call training data。 So we want to to fit a curve to to these blue data points。

 which we call the training set。 We want to minimize this average loss。



![](img/d08c36f5ee750aa354781025ca74b9f5_182.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_183.png)

And after we train a model， this is very important。 We always need to validate the model。 never。

 ever stop after training a model， because with modern models， powerful deep neural networks。

 you will get a small training error。 Then you might think， wow。

 I have now trained a super good model， you run to your boss or colleague and breakg about your cool model。

 And then the colleague asks you and what is the validation error。😡。



![](img/d08c36f5ee750aa354781025ca74b9f5_185.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_186.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_187.png)

So how is the model doing outside the training set on which you have optimized your model。



![](img/d08c36f5ee750aa354781025ca74b9f5_189.png)

And this is then， the hard truth。So you might get a very small training error。

Just because you have such a big set of possible hypothesisthees maps that by accident。

 just fit your training set， but they do very poorly outside the training set。



![](img/d08c36f5ee750aa354781025ca74b9f5_191.png)

Okay。😊，So this might sound trivial。 but in the end， this。

 I would say it's still the the day to day job of an applied machine learning engineer。

 So train a model， evaluate， compute the validation error and compare it against some baseline or benchmark。



![](img/d08c36f5ee750aa354781025ca74b9f5_193.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_194.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_195.png)

So does anyone of you know about a principled way to compute the baseline or benchmark So when do you know that the validation error that you have obtained is close to optimal。

 Theres no point in in pushing this further。Yeses。是的。关。都。Yeah， so， so in general， the。

 the validation error will be higher in the training error。 So what do you do then。

 you do some regularization techniques to bring it down on the same level。 So let's say we have。

 let's say we have the training error and validation error on the same level。How do you know if this。

 if this level is good， close to optimum or not。When do you know that you are done， basically。

 you cannot get better performance。This is related to the question of having a baseline or benchmark。

What what， what is the ultimate baseline or benchmark for the performance of a machine learning model。

Does any of you work as a machine learning scientist or researcher？So when when you work。

 let's say you， you， you come up with a cool new network architecture， call it transformer networks。

And you apply it to some data set and you train it， and you get a good performance。

 like validation error， small， like training error。 When do you know that this is really good now。

 This is something you should share with others in the community。 Subub the paper to nearips。😊。

Comparare to state of the art。 and how how do you compare to the state of the art。You read papers。

 Yeah， so that's， that's， maybe the main， the main source for a baseline is state of the art。

 reading papers or do you know， other sources for， for baselines for the state of the art。

 than reading papers。

![](img/d08c36f5ee750aa354781025ca74b9f5_197.png)

Leadder boards， do you know a platform where there are leader boards for。Papers with code。 or。

 do you know Kegel， is this still thing。Maybe I'm too old already。 I， I， I was。

 I was amazed about this cable。 And this， I， I would say is one of the key drivers for the machine learning explosion or the machine learning research explosion。

 because we have this leader boards。 We have well defined benchmark levels or benchmark data sets where you can compare your。

 your， your proposal for a new transformer network architecture with others。 And if you beat it。

 you submit a paper。😊，Okay， do you know any other way to get a baseline or benchmark besides comparing with what others did previously。



![](img/d08c36f5ee750aa354781025ca74b9f5_199.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_200.png)

嗯，Yeses。Could you repeat？Compared to a human， yeah， human performance。

 So you might just say you might set the performance target or you might have regular regulation。

 Like， I hope that this autonomous vehicles， they have a regulation。That requires if you。

 if you have one accident in hundred0000 hours of driving or so。 So this this defines a baseline。

 how， how much errors， How much wrong predictions can you tolerate。



![](img/d08c36f5ee750aa354781025ca74b9f5_202.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_203.png)

Yeah， I I also mentioned another one， which I like because my background is in in applied statistics。

 which is the base risk。 So if you know a probability distribution of your data。

 you can compute the optimal error level， which is called the base risk。 But the， the。

 the drawback here is you need to know the distribution of the data， which we really know。



![](img/d08c36f5ee750aa354781025ca74b9f5_205.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_206.png)

🤧P。Okay， so。What can we do instead of making this cycle， So come up with a machine learning model。

 train it， compute the validation error。 And if it's not good， retrain it。Well， in practice。

 we could。 We could do regularization， so。

![](img/d08c36f5ee750aa354781025ca74b9f5_208.png)

This this picture here， when the validation error is larger than the training error is a typical situation when you train a powerful model because this highly or high dimensionmenal models。

 they allowed to achieve a small training error， but you will overfit and you will overfit typically when the training set is not large enough is smaller than the dimension of the model So what you can do is you either increase the data set size。

 or you decrease the model size。 and this is what you do when you regularize a model。

 So there are three different perspectives on regularization。

 The first perspective is you increase the data set using data augmentation。

 And the idea is you typically know some intrinsic symmetries or invariances in your data like when you when you have a feature that is measured by a sensing device。

 Then it's typically subject to noise。

![](img/d08c36f5ee750aa354781025ca74b9f5_210.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_211.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_212.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_213.png)

Maybe some of you have have sometimes looked into data sheets for a temperature sensor。

 and this temperature sensor data sheet tells you this is accurate。

 this measurement is only accurate up to plus minus-1% error。

 So in everything you measure there are typically an uncertainty， a measurement error。

 So why not saying then okay， instead of this blue data point could have equally well observed this perturbed red data points。

 So you add a bit of noise to the features of the data point。



![](img/d08c36f5ee750aa354781025ca74b9f5_215.png)

And all of a sudden you have three data points instead of one。

 and then you you not clone it two times， but you clone it 1 billion times each time adding a random realization of a random variable。

 so you can arbitarily arbitrarily increase your training set using data augmentation So this is one approach。

 and it turns out that this approach is actually equivalent。



![](img/d08c36f5ee750aa354781025ca74b9f5_217.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_218.png)

To adding a penalty term。

![](img/d08c36f5ee750aa354781025ca74b9f5_220.png)

To the loss function， Because this augmented。Augmented data points。

 the effect of these augmented data points is to add terms to the loss function to the training error。

 and you can collect， you can collect those additional terms as a regularization term。

 And this is just a penalty。 and you can show， for example。

 that this rich penalty is exactly what you obtain when you perturb each data point by a Gaussian random variable infinitely many times。



![](img/d08c36f5ee750aa354781025ca74b9f5_222.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_223.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_224.png)

And you will actually， in the first assignment， you will have to implement this。

 So I find this acute trick to implement such a penalty term。

 a rich penalty using a data augmentation。How many of you have ever implemented a rich penalty or rich regression？

Very good。 How many of you have implemented rich regression or rich penalty for decision trees。



![](img/d08c36f5ee750aa354781025ca74b9f5_226.png)

Yes。Now you crushed my choke， how？So is there， is there an option in in ski learn for decision trees to implement this type of。

 of rich term。Because in， in decision trees， you don't have a model parameter。Vectctor。

 so it's not obvious how to implement what is the analog of this rich term that you can use for linear regression or anything that has a parameter vector。

 But what is this， How do you implement this for a decision tree。

 and in the in the in the first assignment， you will learn how to do this。

 How to implement an an analog or how to generalize this rich penalty term to decision trees。

And the idea is， this rich penalty is exactly what you would get if you add in a detaministic way。

 new data points to the training set so you can obtain this this rich penalty term。



![](img/d08c36f5ee750aa354781025ca74b9f5_228.png)

By adding。Specific data data points with a specific label。In particular， you set the label to 0。

And when you work out the additional loss on this augmented data。

 this additional loss is exactly this penalty term。

And I find this trick cute because it will also allow us to implement federated learning algorithms because。

 I mean， this is maybe the summary of the whole course or the idea of the whole course。

Confderated learning， we construct this penalty term。Using the predictions of other models。



![](img/d08c36f5ee750aa354781025ca74b9f5_230.png)

So instead of perturbing the local dataset， we use the predictions that we would get from a neighbor node from from another device on our data as as augmentation。

 That's how we couple the models。 And the nice thing is that this does not rely at all on model parameters。

 So you can do this with any kind of model as long as it delivers predictions in the same label space。

 So if you have regression models， then you can couple any regression models that you like decision trees。

 deep neural networks， linear models。

![](img/d08c36f5ee750aa354781025ca74b9f5_232.png)

![](img/d08c36f5ee750aa354781025ca74b9f5_233.png)

Okay， and that's it actually it was a nice conclusion of today's lecture。

 so today we talked about the course。

![](img/d08c36f5ee750aa354781025ca74b9f5_235.png)

Logistics and schedule all the all the activities。 And finally。

 we started to talk about how to do machine learning， how to regularize machine learning。

 And in the next model， we will see how to。S up this machine learning setting to networks of machine learning problems。

 I call this federated learning networks。 This is a mathematical object。

 It's basically a network model with， with some machine learning on top of it。

And in the so this will be the next model next week and in the later models。

 we then use this this federated learning network to formulate optimization problems。

 which like federated learning problems， and then we solve this federated learning optimization problems using optimization methods。

 which gives us a very clean and principled approach to to design and crank out all kinds of different or federated learning algorithms。

Okay， any questions at this point。Very good。 So on the chat， one final question I will answer。

 when we can we access this lecture on YouTube， I would say within the next 10 hours。

 So I will translate this。 well transfer this recording onto the YouTube playlist。😊，这个。A some person。

I have it already Okay， okay， thanks a lot and have a nice evening。😊。



![](img/d08c36f5ee750aa354781025ca74b9f5_237.png)