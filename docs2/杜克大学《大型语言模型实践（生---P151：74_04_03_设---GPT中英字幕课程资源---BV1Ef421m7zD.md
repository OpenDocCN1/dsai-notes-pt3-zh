# 杜克大学《大型语言模型实践（生成式AI简介、Azure的LLMs（1、2课，共6课）｜Large Language Model Operations》 - P151：74_04_03_设置Azure组件.zh_en - GPT中英字幕课程资源 - BV1Ef421m7zD

![](img/07a6bd468883e2bab6f141462223f391_0.png)

Let's start creating the services that we're going to need in order to get started with our application or launching our application to the cloud。

 so we're in the Azure portal once again and what we're going to do is we're going to go into container apps and we're to create a container app but before we do that there's one very important detail that we need to keep in mind when we do this our automation is already in place but one key aspect of it and we'm going to switch over to the repository here I'm going to go to that Github slash workflows and go and take a look at the Github action I've already premade these there's an important detail do you see the group name and the container app name those are crucial so and I need to get them correctly input it into the creation so it doesn't matter the order like in my case these exists before creating the service but。

If you don't just make sure that these match when you're creating the container so in the application I'm going go into container apps into a portal I already have one previously created and I create one from scratch so I'm going to create one and in this process I'm going to select a right description and the resource group is what I was still on you before so I'm going to say let's just verify and it's demo dash container and the container app name is going to be the same so let's create that a new resource resource group demo container。

And it seems that I already have one so perfect I can I can just use a dropdown and do search for demo container there we go and name my application the same so by doing that I'm going to ensure that things are going to actually work correct Australia is is not the region that I want I prefer East US and that seems okay to me once I do that I can just review and create this will go through the verification and then I can just click create at the very end。

Perfect， this is going to take a second and once it's in place I will be able to to start using my automation。

 so these are all the resources that I need because I'm going to go back to the Github action here because what this Github action is going to be using is using the Github container registry by using the Github container registry。

 anything that I produce the container that I produce is going to be stored in Github itself。

 so it is sort of like like a type of architectural components or ordering that allows me to put the container in specific portion it doesn't mean that you have to use the Github container registry in this case GHCR that Io it could very well go into Azure but what we're going to do here is we are going to make use of。

These very easy， very straightforward container registry offered by GiHub so once you'll see that this will start making progress here by having some of these go through the deployment progress and once it completes everything again will be ready for us to continue make progress in trying to deploy these and automate the deployment of our application that will connect to Azure Open AI service。



![](img/07a6bd468883e2bab6f141462223f391_2.png)