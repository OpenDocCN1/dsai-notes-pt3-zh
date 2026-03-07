# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p26 P26 Lec 26-Deep Learning -BV1Lcnhz1E7P_p26-

Great， so I guess because we are about， we are close to the end semester。

 Tom and Di for today rather than being very specific about the topic We be give a bit of a bigger picture about current interesting research in machine learning。

😊，And of course， since you are taking this class， but I already know that machine learning is this amazing research field。

 but it's not only intellectually stimulating， but also has changed the world and had amazing impact in many application areas ranging from say speech recognition to information retrieval to。

😊，Computation biology and so on。 I mean， basically all areas of science and computer science have benefited and significantly because of machine learning。

 right， And this is something that people widely recognize today， know。

 like in industry and academia。 Okay， so machine learning has changed the world。 But I also think。

 and I guess don't think so。 And many of us think so。 so machine learning has changed the world。

 But the world is changing machine learning too Okay， and in particular。

 the wide variety of new types of applications。 and the explosion of data have really forced machine learning to very quickly evolve and significantly expand its basic set of tools and approaches。

 Okay so some of the tools that we've talked about in our class or very basic tools。

 But there is a lot of exciting activity in machine learning that goes beyond those basic tools。😊。

And this is what the current of research is and what's needed for the next generation。 Okay。

 and just to give a couple of concrete examples。 So， I mean。

 this is something we've implicitly talked about about the course。So for example。

 I mean most of the techniques we talked about in the course assume that humans can label or annotate all the data available for training right but most motor machine learning applications have such massive amounts of data that is hopeless to have humans anannotated all right like for example。

 there is brain imaging data， massive amounts of data， like coming from surveillance data。

 lots of data for information extraction and computational biology and so on so it's hopeless to have humans anannot all and I think one of the cool directions in machine learning these days and really talked about it is to design learning techniques。

 but somehow most effective utilize the available data。

 but mini it for expert or human intervention and we've seen in the course some techniques related to semiupervised learning and active learning。

 but these are just very stylized approaches and very result exciting activity on doing this even better。

😊，あ。So it's one new key challenge or a modern challenge to design techniques that most effectively utilize the available data。

😊，Huge amount of data while minimizing it for expert intervention。 Okay， It's a real issue today。

 It wasn't such an issue 20 years ago。Now， it's a different example of a modern challenge。

 So in again some of the modern machine learning applications。

 we have massive amounts of data distributed across multiple sites or locations。 So， for example。

 we have we could have large amounts of scientific data or large collections of video or image data。

 right， and in such cases， in order to do learning over the combined data sets。😊。

The whole does must communicate， right。 And so， for example， in this context。

 communication becomes a new resource。 So in addition to human labeling effort and computation。

 which are the two key resources we've been talking about about the course。 Now。

 we also have communication as a key new resource。Okay。

 and this just interactive learning or learning algorithm that most effectively utilize available data and also distributed learning are just examples of modern machine learning approaches that are widely research these days。

 But are many more。 And for example， Tom talked about some of them。

 like never ending learning and deep learning， There are other issues like multitask。

 Trans learning or somehow we want to learn to leverage data from many like tasks to learn more efficiently new tasks and so on。

 I think Tom we'll talk about at a little bit。😊，Right。

 so there are many exciting new approaches that go beyond the classic programs we've been talking throughout the course。

 And one thing that I find particularly interesting is that each of these approaches brings up a new set of challenges and resource constraints。

😊，A new set of resource constraints。But we have to worry about resources and constraints that we have to worry about right so classically the two constraints we would think about are computation and the amount of data。

 potentially label data， right and now suddenly， we have to think about many more resources and constraints。

 for example， we have to minimize human labeling effort。 when do interactive learning。

 we have to take into account communication efficiency， when do distributed learning。😊，Or actually。

 we have to also think about privacy when the data belongs to someone。 So most。Of the data。

 most of the， some of the machine learningning applications involve sensitive data， right。

 like medical data， or genomic sequence data and privacy becomes a key a key constraint or resource that we have to really worry about。

Okay， or even so privacy， but even incentives， in cases what the data actually belongs to someone。

 some like some research groups or say， Google or Microsoft， right。

 So what incentive would they have to share with data。And what type of data。 Okay， so suddenly。

 we have a lot more resources and constraints that we have to think about compared to the classic machine learning。

😊，That was 10 years ago。 Okay， so it's very exciting。啊。And this is， I think， what happens currently。

 Okay， so this is kind of a current picture。 And of course， there are issues of scalability， right。

 I mean， even for the classic constraints， like， say computation。

 there are many issues regarding scalability and so on。But I mean， this is， I think。

 a picture of the current machine learning。 And I guess at the end lecture。

 will'll talk about more about the future machine learning。

 But even the current machine learning was very different from machine learning 10 years ago。

 So lots of exciting topics。😊，Okay， and I think Tom will touch on so he already started last time to touch on deep networks。

 He will continue two lectures ago。 He'll continue deep networks。

 When I'll talk a little bit about privacy。 And then each of us will talk a little bit about the future of machine learning。

😊，Yeah。So if you have more comments about this， though。啊。I you agree。Good， excellent。

 So what we're trying to do here is we。'sSure， we're trying to do here。

Discussion about some themes that we see as being increasingly important in machine learning over time。

And we agreed that we would each pick one and talk about it for。10 or 15 minutes。

 But then we would open it up to。Discussion among the collection of experts。We haven't arrived yet。

 but we'll be this。And。It's kind of a brainstorming discussion。About what are some of the directions？

这不是。无意见。Will be increasingly important and good research topics now and important applications。

In time， so。Given that we both got to choose one to talk about for 10 or 15 minutes， I chose。

This one。It seems to me the whole theme of deep learning is one of the most important current。

Developments in in the machine in the field。So already， it's having applications。

In commercial enterprises。Many types。And so I want to take my1 to。那么这。嗯。2 points。

 We talked about neural nets last week。And I want to make two additional points。Here today。

So last time we talked about。We pointed out that one of the key things in detail。

You feel he have many stages。That they go through to compute their results。

And we also talked about the idea that a lot of the training and what makes state networks valuable。

I that。P。It output the same thing you give them a input。ideaear that this is the way。Wth thing。

The network could come up。でも目ロ。A very interesting and intricate code to capture the distribution。

Inputs that you give us。And learning that representation is actually。あ。Reasons why being network。

So and we talked about this is a slide after lecture， we touched back and we can train these。

 for example， by in this paper。By training just one stage at a time and then。声ing。

We didn't get to look at。就是。Example of how。Those learned representations can look。

So here's an example in one slide of a deep network that's trained to do image。啊。

Representation and also image classification later。呃。Its this is。

