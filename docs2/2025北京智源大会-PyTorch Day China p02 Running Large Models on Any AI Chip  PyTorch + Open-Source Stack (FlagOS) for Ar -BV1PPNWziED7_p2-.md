# 2025北京智源大会-PyTorch Day China p02 Running Large Models on Any AI Chip  PyTorch + Open-Source Stack (FlagOS) for Ar -BV1PPNWziED7_p2-

So our very first speaker is someone that you know very well。Ms。 L Yanghua。

 Vice President chief engineer of Beijing Academy of Artificial Intelligence。

 and she'll be speaking to us today about running large models on diverse AI chips using Pytorrch and the open source stack flagOS for architecture free deployment。

So please welcome Yang Hua to the stage。🎼Okay， actually， before I start my speech。

 I want to spend two minutes to talk about Py。 first， I I I think let's thanks Matt and Debbie。

 they come from P from US to here to bring us the first the， the formal the P event here。Yeah。

 I still remember last year I a participant Py conference in San Francisco and that's my first time to meet Matt。

 and we discuss how about we bring the formal Py event into China because I really impressed by the P conference in San Francisco。

 that is the two day conference a lot of experts from global and also those top companies start companies they bring in a lot of different technology actually。

 when they share the technology iss not only the Py itself。

 it really related to each key piece related to the AI right So that's why I impressed by that and I think I really want to bring that kinds of event into China。

 So that's why we have this first Py event。 and we also appreciate the Py Foundation support。

 you know， if we want to get this Py logo here， we need to get the。😊。

From P Foundation and P Foundation， they have a multiple stakeholder。 We get the。

They help us to to get the approval to， to get this event here。 So， so that means two things。

 One is actually， as Matt mentioned， we will have conference will have the global conference in in in September。

 So if you any of you have interest please try to join that。

 you will feel the the whole week I think it will be exciting。

 the second is I think this day China is will be the first time。

 and I think we will get it next year。 and hope we can work together。 I mean。

 not only P Foundation only B AI。 and you also want to invite any companies organization here today to work with to make this day China even bigger and have larger impact next year。

 okay。😊，Okay， then I will start my talk。 And since since I already written in English So I want to change back into Chinese to to。

 to introduce， okay。😊，那呃今天其实其实今天介绍的题目哈呃是关于fOS。但是我想还是想先说，为什么我们希望构建一个uniified和统一和开源的这样一个系统软件站啊。

那实际上我们再看哈从整一个AI的invation来看，今天已经走到了大模型。那大模型我们看到其实有三个最重要的challege。第一个是说所有任何大模型的创新都是high cost。

任何我们的算法的创新。如果是放到这个基础模型的创新，那可能动辄都是几千万的一个投入。呃，所以这是为什么我们开源很重要。就是说我们一我们可以al站在前人的基膀肩膀上往往后迭代。

大家想想ep如果没有前面去证明了MOE的可行性。那ep也不会堵到MOE上，正因为dep r一出来了，所以才有今年的很多的一些呃大模型，它推出了reing的版本。😊。



![](img/cbf2b2179519bd940cf11cc929194938_1.png)

![](img/cbf2b2179519bd940cf11cc929194938_2.png)

![](img/cbf2b2179519bd940cf11cc929194938_3.png)

![](img/cbf2b2179519bd940cf11cc929194938_4.png)

![](img/cbf2b2179519bd940cf11cc929194938_5.png)

![](img/cbf2b2179519bd940cf11cc929194938_6.png)

那这是第一。第二个也不会可能有任何一个organization可以把所有大模型训练所需要的resource可以能够呃完成。那最重要的一个就是data，没有任何一个企业单独自己不靠不依赖别人的数据。

可以构建自己完整的整一个数据集。所以这也是为什么包括智源，包括拍to，也包括很多企业，我们一起做了很多呃data set open source。但是最后一个我觉得其实是今天很重要的一点。

就是说今天来看，任何跟大模型相关的训练和推理的co还是太高了。所以在这一块上面，我们依然一直需要去在基础架构上不断的创新，包括芯片架构的一个创新。



![](img/cbf2b2179519bd940cf11cc929194938_8.png)

![](img/cbf2b2179519bd940cf11cc929194938_9.png)

![](img/cbf2b2179519bd940cf11cc929194938_10.png)

![](img/cbf2b2179519bd940cf11cc929194938_11.png)

![](img/cbf2b2179519bd940cf11cc929194938_12.png)

但是在当我们在做很多的芯片架构的创新的时候，实际上对所有的厂商任何一个芯片它的研从创新到研发到落地，实际上是需要很昂贵的资金。所以其实肯定不会是只是以research为 purposepose。

肯定是以in落地为 purposese。但当我们希望某任何一个新的一个架构可以大范围落地的时候，他必须要考虑怎么样让广大的上层用户很容易的用得起来。如果不解决这个问题。

任何创新的那个架构都很难大范围落地。最终我们还是要回答用户怎么样很方便的去用。所以但是呢在过去的这些年，我们看到哈这个如果有呃在座的有参加昨天的那个workshop也听到我们很panel的讨论。

就是说呃在这么些年，其实呃我们看到其实整一个全球在AI的acccelerator这样子各种各样架构上面，其实他们的这个eys。他们的stem software都是分裂的。

都是分裂的那所有的都是烟囱式的那这里头带来什么问题呢？带来的问题是说，除非我们这些芯片企业或硬件架构企业，它足以强大到他自己会以有一个相当庞大的团队。否则的话对我们很多尤其初创企业。

很多innovation的企业，甚至是研究团队，它不可能有能力从底到上构建出所有的系统软件，尤其是发展自己的生态，这个是一个很大的一个投入。

那第二个呢呃随之而来的肯定就是说我们的上层的软件的开发者和用户也很头疼。就是说随时可能是说因为missing某一个算子的支持，missing里头某一个版本的不支持，你就tuck在那。

但是不可能是说我们永远都能够拿到芯片企业，这个嗯很快的一个支持。那同时的确就是因为这些各个都是烟囱式的，使得是说我们希望从今天从一种芯片或一种系统架构转到另外一种系统架构的时候，整一个迁移。

又要重新开始。所以。好。对，所以这是我们做这个事情的一个很重要的一个出发点。就是说我们是否有能力去构建一个统一的一个中间这一层，向上支撑好现在的拍套，支撑好现在上面的算法，向下可以辅助呃这些芯片的创新。

否则如果我们很多大家可以倒过来想，如果我们今天看到有很多的芯片的创新。它依然受制于这样子哦，没有任何大范围落地的可能，还会有人愿意投入到呃这些硬件的创新吗？不会的。所以但是呢如果我们当我们想哈。

如果我们要构建这样这么一个开源且统一大家都可以享用的这样1个AI系统软件层。我们要做的考虑的是什么。那首先我们会从语言考虑。但那个chon是我们目前呃大家都关注的一个。

因为的确大家在gi up上面可以看到，目前以ton相关的这些呃开源项目或大或小，已经跟ku达比起来已经有10%的这样一个一个。



![](img/cbf2b2179519bd940cf11cc929194938_14.png)

![](img/cbf2b2179519bd940cf11cc929194938_15.png)

![](img/cbf2b2179519bd940cf11cc929194938_16.png)

项目的数量。当然，项目的成熟度是千差万别了哈。😊。

![](img/cbf2b2179519bd940cf11cc929194938_18.png)

但是呢我们有chon的语言就已经解决问题吗？根本不是这个我我们要知道咱们的上层的这些算法，它要很容易的去编织去实现一个模型，去调用咱们的pyto。其实很重要是直接要调用到各种各样的librry。

没有这些library的话，算法工程师不可能每个library重新从chon来去手写。所以我们要让一个语言能够真正能支撑起来我们庞大的用户群，必须要有稳定高效且覆盖广的一个算子库。这个library。



![](img/cbf2b2179519bd940cf11cc929194938_20.png)

![](img/cbf2b2179519bd940cf11cc929194938_21.png)

![](img/cbf2b2179519bd940cf11cc929194938_22.png)

![](img/cbf2b2179519bd940cf11cc929194938_23.png)

但是有library也呃也解决问题吗？不是，因为我们在过去的这么长时间呃，智源研究院我们跟很多的那个嗯很很多的团队讨论哈，呃呃呃共建在过去一年多之后，我们发现是说虽然我们都选择了用chton。

我们构建了整一个庞大的一个刚才说了f jam这样的librry库，发现正因为各个芯片企业，他们的他们自己去弄那个tton的ton的那个compilr。

自己去去去去hack里头去customize里头的东西，版本不一样，使得在在compilr这一层又开始分裂分裂出不同的chton的comp。

其实大家今天看在那个包括intel他自己也不得不需要有一个自己的fo出来自己的一个tton的compr。虽以我们希望是说能不能给我们上面的用户在部署的时候，他不需要去wo是说虽然我算。😊。



![](img/cbf2b2179519bd940cf11cc929194938_25.png)

![](img/cbf2b2179519bd940cf11cc929194938_26.png)

![](img/cbf2b2179519bd940cf11cc929194938_27.png)

![](img/cbf2b2179519bd940cf11cc929194938_28.png)

![](img/cbf2b2179519bd940cf11cc929194938_29.png)

![](img/cbf2b2179519bd940cf11cc929194938_30.png)

![](img/cbf2b2179519bd940cf11cc929194938_31.png)

![](img/cbf2b2179519bd940cf11cc929194938_32.png)

不统一了。但是我发现下面的comppier又各式各样的。当这些complir，它更新的tton的版本不一样的时候，也会带来很多的问题啊，但这一块我就今天先不深入介绍下午这个我们呃这一块的负责人门春内哈。

他下午会专门在这个compiler上面给大家做更多的分享。

![](img/cbf2b2179519bd940cf11cc929194938_34.png)

![](img/cbf2b2179519bd940cf11cc929194938_35.png)

好，但是我们又看哈解决了算子库这一层和和和那个编译器这一层是不是解决了？不是，因为咱们现在知道AI已经到了大模型解时代，它已经不是单一的一个芯片来deliver我们的per。

其实它deliver performance，是一个class，是一个系统。所以我们不能说只解决了芯片问题，但不去看系统性的问题。所以在这里头。

其实我们是不得不也摄入到是说是否我们可以构建出一个并行优化的这样的并并行呃推理训练，都优化的一个框架来面对不同的芯片和不同的AI系统。😊。



![](img/cbf2b2179519bd940cf11cc929194938_37.png)

![](img/cbf2b2179519bd940cf11cc929194938_38.png)

![](img/cbf2b2179519bd940cf11cc929194938_39.png)

![](img/cbf2b2179519bd940cf11cc929194938_40.png)

![](img/cbf2b2179519bd940cf11cc929194938_41.png)

但当我们构建这个东西的时候，又发现另外一个问题。今天我们所有的这些芯片，他们的通讯库又不一样啊，那个英美达有呃 ni，但其他的芯片企业又有自己各自的通讯库。那这里头带来了两个问题。

一个是说当然昨天哈如果大家有听昨天包括智源研究院，包括上海AI都谈到了异购混训，甚至异构推理。那首先我们如何让不同的芯片。

它的workload可以t to each other那这里头肯定要解决互通的问题。目前呃没有统一的protocol可以互通。那因此我们需要有统一的通讯库。另外还有一个哪怕我们在一个同构的一个环境里头。

当我们要做一个class level的一个优化的时候，也需要也需要利用到下层的这些通讯库。但如果各自的通讯库是不一样的话，我们的优化是得一遍一遍的重来。所以这也是出发。

我们需要有一个unified的这样子的。😊。

![](img/cbf2b2179519bd940cf11cc929194938_43.png)

![](img/cbf2b2179519bd940cf11cc929194938_44.png)

![](img/cbf2b2179519bd940cf11cc929194938_45.png)

![](img/cbf2b2179519bd940cf11cc929194938_46.png)

一个统一的通讯库。那。最后在上面是说，最终我们还是要解决的是用户的问题。我们在底层解决了包括硬件厂商、芯片厂商等等的问题之后，是就解决了所有问题吗？其实不是最终整个生态要做起来。

最终还是要满足我们用户怎么用的更好的问题。是否和他可以有一个一站式的地方，直接甚至连迁移都不需要，他直接就可以拿到他想用的东西。那这里头也是为什么我们提到了这种自动的迁移，甚至release啊。

这个等会我也会谈到。那最后下面我我列了三个图，其实都有生意。第一个是代表了我们的芯片。第二个代表了我们的数据中心，从classlast的角度去考虑上层的这些问题。最后我看放了机器人。

这是因为我们现在看到从机器人的角度，它也是一个需要云端协同，需要多机通讯。实际上大家可能也到也也也在我们智源的研究院也以及其他的机器人公司，看他们的demo。为什。

他很多时候的demo要进行一个两倍3倍的一个快放。因为今天来说，端到端的完成一个任务，尤其实现云端协同的时候太慢了太慢了。所以这里头也是对我们整一个无论是跨平台啊。

我们把这样子的一个呃大模型放到我们的呃呃边缘侧需要有这样子的生态的支持。还有就是说端到端的优化。这里头其实又会回到我们整个系统软件的很多的research上面来。

所以在这个呃呃呃整个过程中哈出于这样的一个驱动，我们在呃智源研究院，我们连同了呃国内呃其实也有一些全球的团队。呃，在过去的两年多，我们打造了整个f o。

那今天呢这个大家可以看到flash o实际上包括了两个重要的大的模块。呃，在大家可以看到这个那个框框框住的哈ca modules就核心部件有包括4个一个是flash drive算子库呃。

还有flash tree就是今天下午我们春雷呃呃会给大家介绍的我们的统一的编译器。然后呢呃另外就是flash scale和flash c分别是我们的呃训练并行训练和推理的框架以及统一通讯库。

这一块是我们的热门的核心部件。那另外还有重要的工具。那重要的工具，一个是说f release等会我会介绍一下。另外还有flash其实是面向多种AI芯片AI系统的一个 mark开源的它。😊。

对标的是MLPf，但是比MLPf更加接近目前当下大模型的讯推的需要。但更重要的说，这样一个perf工具完全是开源呃，由各个厂商共建的嗯。

那我们的目标就是说通过这样一个统一的一个系统软件站向下支持不同的芯片和不同的系统的部署架构。大家可以看到我们看到的系统部署以经包括在数据中心呃，支持大模型的训练和推理，包括在端侧支持在边缘侧的推理。

因为大家可以看到，随着大模型进入到机器人领域，肯定会触发在机器人领域，在边缘侧的更多的大模型的推理的需求。啊，然后呢，在在在合在一起，就是说面对这个机器人的话，我们肯定要考虑如何云云端协同。

那向上我们已经支持了不同类型的大模型。那呃另外呢我们也是很欣慰哈，这样一个呃系统的一个生态技术生态呢其实已经获得了越来越多呃呃架构的支持。那包括GPGPU架构DSA架构。

也包括re five呃AI这样这个新的指令级的支持，还有arm等。😊。

![](img/cbf2b2179519bd940cf11cc929194938_48.png)

好，那往下再说哈，虽然我们有很好的愿景，也布局了这样子的一个呃整整一个是我们呃呃产学研一起来做的这么一件事情。但是更重要说我们到底我们deliver什么样子的value，可以给到我们的产业。

所以在这里头呢，我就放一些highlight的点，有一些呢呃关于这个呃就选了一些highlight的点哈。首先第一个是说我们认为始终我们是还是要提提供更好的这个性能。

那这里头我讲呃稍微说一下这f jam，那可能更多的信息呃，春内下午会给大家也会提到，但我想highlight哈。

既然刚才这个mat也说了f jam被入选新入选为这个to echo ecosystem的重要的项目。为什么他会被入选。原因就是说我觉得无非是几点，第一个提供足够多的算子，已经目前已经超过200个的算子。

那这个算子呃其实。😊。

![](img/cbf2b2179519bd940cf11cc929194938_50.png)

![](img/cbf2b2179519bd940cf11cc929194938_51.png)

![](img/cbf2b2179519bd940cf11cc929194938_52.png)

也也可以给大家说，前阵子出现很很好玩的一个事情是说open AI的tton team。实际上他们当时在看全球的这些呃用tton来写的这些呃项目。但当时他们找到了我们的这个项目。

他们发现我们这个项目是全球用tton来写这些算子最大的一个。所以他们现在反而是说希望用这样子的一个项目来反向去测他们的tton的编译器啊。呃，所以足够大。然后第二个是说，我们不断的通过不断的优化。

甚至优化到底层来提供呃在某些算子上面，甚至比ku达更好的性能。大家可以看中间这个图，中间这个图，我们现在已经有76%以上的算子是比ku达的算子，原生算子的性能还要好啊。

当然我们是在同样都是在英伟达的硬件上去测量。另外还有就是说面向刚才说了，因为triton它是一个开源的语言和开源的编译器结构。所以它已经可以很容易被各个厂商支持。那支持了chton的这些硬件厂商。

有有有有多个是跟我们合作的硬件厂商，跟他们自己原生的自己厂商的原生的专用算子比，它的性能已经已经很凸显了啊。那另外呢所以所以已经今天为止已经有18个18种不同的芯片来追11个厂商支持。

那另外呃也是很方便使用啊，所以我们这也是我们。觉得很有幸，可以就是说已加入到了pyytoch echo ecosystemt这样一个可以更好的去支撑大家。

那另外呢是呃我我想说是说自自动化自动化是另外一个很重要的一个feature。那我们是希望呃看到哈今天因为大模型有不同的架构，下面的数据中心也有百卡千卡甚至万卡的架构。

那数据中心里头使用的芯片又可能是不同的芯片。所以这实际上是一个三维的一个相当复杂的问题。我们今天很难用人类专家的经验来去做所有的优化。所以我呃这也是我们通过这个fsscale这个平台框架。

这个并情框架来做自动的这样子的优化。那这样自动的优化，我们希望是说能够就开箱即用，让我们的所有在集群上面的用户都可以开箱即用，直接就是针对它的模型，通过我们fsscale的自动的优化策略达到更好的性能。

右下方大家可以看到一些明显的例子。😊，还有另外一个我我也想这个再一下在f还有另外一个很有特色的。就是说今天来看我们也有很多的创新。包括今天下午大家可以看到，包括呃SM呃。

还有拉P还有昨天那个翟老师介绍的度，这些其实都是很优秀的这个在推理测的呃优化的引擎。所以呢呃也是支持了多种的后端的引擎，可以让用户在一站式的一个框架的接口入口，可以调用不同的引擎。

但我们也看到哈其实这些不同的后端引擎，他们实际上是各自有他自己的强项。所以当我们一个用户，他针对他的用户，他的他的场景的时候，到底他是呃呃优先，还是是说端到端的实验优先，还是是就不同的优先策略。

可能是合不同的后端。那所以这也是我们给到用户的一些自动的一些优化的一些。😊。

![](img/cbf2b2179519bd940cf11cc929194938_54.png)

![](img/cbf2b2179519bd940cf11cc929194938_55.png)

![](img/cbf2b2179519bd940cf11cc929194938_56.png)

![](img/cbf2b2179519bd940cf11cc929194938_57.png)

![](img/cbf2b2179519bd940cf11cc929194938_58.png)

![](img/cbf2b2179519bd940cf11cc929194938_59.png)

![](img/cbf2b2179519bd940cf11cc929194938_60.png)

呃，方法。那的确在这个上面，我们是呃也。也也达到了一些在在上面同比哈不同的通过这个优化，实际上的确在不同的后端引擎上，同一个模型和在同一个硬件上面可能会出现不同的一些优化的一个结结果嗯。呃。

因为时间关系啊，有一些我我我就sip掉哈，这这些先sip掉。那我我最后说一下这个就是说。😊，我们怎么样子把我们的这里头，因为咱们通常做的都是系统软件，系统软件实际上是挺下面的。其实跟用户是有一段距离。

那我们怎么样子真的把这些价值直接给到我们的最终用户。

![](img/cbf2b2179519bd940cf11cc929194938_62.png)

![](img/cbf2b2179519bd940cf11cc929194938_63.png)

那在这里头我想给大家分享一个，就是说在CPU领域它是怎么解决这个问题。在CPU领域其实在过去的四五十年，CPU的发展已经发展出来了80个，真的是80多种不同的体系结构。

但他们是怎么解决在这么多的开源软件里头去去支撑这些不同的体系结构呢。那实际上这里头给大家一个例子。就是说其实在呃美国的俄亥俄租力大学，在过去的这么多年，他们维护了一个CICD的环境。

他们所做的就是说通过这样一个环境来支持像linux基金会，还有阿帕奇基金会上百个这样开源的项目。那意味着当这些开源项目release的时候，可以通过这样一个平台来在不同的硬件上面进行自动的集成和适配。

还有它的测试嗯，pass了这些测试之后就发版。所以这时候大家可以看到，当我们要下载一个买西口或者是阿帕奇的一些嗯。的一些开源库的时候。

很多时候大家都可以可以看到它可以杠叉86或杠PPC或杠 up这些东西是怎么来。实际上就是因为有这些。而通过通常做这些的，很多时候，他们都是会依赖于有这些不同硬件环境。

且依赖这些不同硬件环境builup的整一个CICD环境。否则的话，全球这么多的开源软件。每一个开源软件公司都要考虑多多个种CPU的这种真的是很难。所以在CPU领域一直已经形成了这样一种成熟的方法。

所以在这时候我们就反思，在我们现在的AI领域，现在也已经全球包括中国已经有几十种的呃甚至上百种的这种不同的 architectureit。那我们是否也有机会去做这么一个事情啊。

尤其是我们可以先选择大模型来做。所以这个基于这个想法，我们在去年就开始这样一个工作叫。我们的梦想是说希望能够构建一个端到端的。😊。

我们的起点是从kenface或是modelco去下载最新的刚开源的这些主流大模型。然后通过我们的这个整个去自动的去分析它的dependency自动的去执行我们底层的这些替换啊，包括框架。

包括算子库等等的这些替换。然后自动的分发到我们这个class上面，不同的AI芯片的硬件架构的芯片集群上面呃呃，然后执行这个测试买后执行这个测试。

测试完了之后很重要的是说我们自动的进行这样一个呃验证这个验证因为我们最终是需要保证我们的呃结果是对齐呃从英伟达发就是呃在face上发布的基于英伟达的这样一个模型的，一定要做到结果对齐。那对齐之后。

我们在自动的发版回去呃kenface和摩达。那这样做的好处是什么呢？是说我们的最终用户，如果他今天拿到一个新的硬件，是某个厂商的新的硬件，他不需要自己去做迁移。

他直接就在fly release的这个官方网站上去找这个模型。对应的那个硬件型号有，那他就可以下载模型，下载代码以及下载docker镜像就谈搞定了。当然这里头有很多的系统系统架构的挑战真的很多啊。

但这也是我们做system research很大的一个研究的机会。今天来说，我们只做到了部分的自动。但我们尤其是面对很多的这些挑战的时候，我们相信我们用很多stem research的工作。

是可以逐步的提升我们的这个制动的水平的嗯。😊，那这个是我们so发已经deliver到呃，通过这样一套流程。呃，在过去的3个月发版到这个hkenface和摩哒的，包括9个模型多种的AI芯片啊。

但实际上它某种程度也是对拍 touch整一个echo ecosystem的一个很好的集成嗯。呃，时间关系我就呃不放这个了哈，不放这个这这个video了啊。😊，那最后呢说一下，就说实际上我们做这个事情。

整一个还是跟产学研相关。上面念的所有的企业名字、团队名字都是在过去的呃2年2到3年跟我们紧密合作。那我们也呼吁是说，希望有更多的团队，可以跟我们一起来做这样一件开源生态的很有意义的事情。谢谢大家。

