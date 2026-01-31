# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P23：22-作业：HW10 - Diffusion - Ai人工智能工程师 - BV1QdzCB3Eu2

各位同学大家好啊，我们这个影片是要来讲解啊，作业时那主题是defusion model，那这边是一些同学在做作业时，可能会需要用到的link，然后这是今天讲解时的online。

好那因为defusion model在今年的课程还没讲到，所以这边就先放上几个之前老师讲解的影片，那如果不太了解的。



![](img/c8b37866b5adabcafc7bd9f11ed28987_1.png)

可以先来看这边的影片，好那你我先从这次作业有的task开始讲，那我们这次作业的task主题是customization of，Text to image diffusion model。

那这边先快速讲解一下什么是text to image，Diffusion model，那他可以做到的事情，其实就是左下面左下角这张图所所画的这样子，那我们使用者会给呃model一个句子。

比如说这边是a dog in a bad man suit，那它就会生成上面这张图片给我们，那另外一个例子是a dog in a bucket，那他可能可以伸出这张图片给我们对。

那但是这种普通的text to image model有一个问题，就是说嗯它每次生出来的狗都会是不同只狗啊，这可能跟是跟user想象的不一样，user可能会希望说它可以固定生成，某一只特别的狗。

例如说我自己的宠物，那我想要把嗯customize生成不一样的情境，下面的或者宠物的图片，所以嗯这个task它主要的目标就是说，我给一张诶给几张特定object的reference的image。

那我们希望嗯这个depression model，可以根据我们所给的text pro，然后伸出特定嗯情境的图片，但是里面的object要是我们给定的这个reference。

那做到的事情就是右下角这边画的，就是我给一个reference image，我希望他可以生出这只狗，然后再给他一个prompt，比如说a dog和bad man su，那它就可以生出下面这只狗。

但是他是嗯依照这个test prot去condition的的图片，这样子看这边有其他例子，一个bucket，那他也是同一只狗，然后真是八，但是在bucket里面这样子。



![](img/c8b37866b5adabcafc7bd9f11ed28987_3.png)

好那更详细的来讲的话，就是同学在做这个task，你们拿到的是几张preference image，然后还有一个test pro，那以例子来讲就是reference in image，就是这张图片。

那text point就是a dog in a bad man should have play jumping，这些text prop对，那你的目标，你要做到的事情就是把上面这些图片伸出来。

OK那我们会拿到拿到大家嗯，上传的图片之后，我们会EVBEUIT，就是说第一个就是希望这个图片里面的object，他的主角要跟reference里面长得像。

然后第二个就是你的图片要遵照text pr去生成，对，那这这两个就是我们主要会evaluate，大家做的好坏的标准，好，那我先来讲我们是如何160这两个标准的，那刚才说我们第一个标准是说。

我们希望这个生成出来的图片里面的object，它跟reference image啊一样，那我们这边使使用的就是用一个叫dino score的，呃的matrix，那他的做法很简单。

就是拿一个image coder，然后这边是DINO，然后就把嗯reference image，那这个这个同学是拿不到的，然后再再把同学上传上来的，generated的image丢进去。

然后抽出feature之后算这两个比确的cos simelity啊，这个cos smearity就是dinos score，那它它代表的就是说这两个object，它在视觉上是不是是不是像的这样子。

所以说越高就代表越像，就是越好这样子好，那这边就是刚才的第二个标准，就是说我们希望生出来的图片，是遵照tax prod的对，那这边做哎，这边的matrix就是用一个叫clip提的matrix好。

那这个clip t跟刚才的算法其实蛮像的，只是说我们就不是看reference image的feature，我们就是把tech pr丢进呃一个clip的text coder里面。

然后把它抽出feature，然后同学生成的图片，这边也是就进一个以B9encoder去生成图片，然后算这两个呃feature的啊，Similarity。

那这个similarity也就就代表说这个tx from，跟这个image它是不是想的，那也所以哎他也是cos simacity嗯，Cos simacity。



![](img/c8b37866b5adabcafc7bd9f11ed28987_5.png)

所以也是越想越好，那接下来我会讲一下，我们这次作业会用到的方法，就是大家如何做到customization，那在这之前我就稍微recap一下，就是text to image model，它的一些限制。

就是说为什么他没办法直接达到，我们想要的目标，是因为仔细想的话，他其实嗯text to image model，它其实是可以遵照text pro的。

那这一定程度上其实已经是一种customization，比如说我想要它生成呃柴犬的图片，想要是它生成科技的图片。



![](img/c8b37866b5adabcafc7bd9f11ed28987_7.png)

他其实都可以遵照test pro式出来，但为什么他办不到，说我我要哎生成这个长得跟reference image一样的，这种效果呢，有一个有有一个可能性是你给的text pro嗯，太笼统了，不够细节。

所以有其中一个方法，就是你把所有的呃reference image里面，所有的细节跟这些图片的特征，都把它描用文字描述清楚，那这个可能有一定的帮助，就是他可能会比这张做的更好一点。

但有一些细节其实是没有，那那么容易使用text pn去描述的，所以我们想要做的事情可能比较像说，我们希望呃这个model他去学会一个特别的字，就是它是一只spatial的特别的狗，对那这个特别的狗。

这个特别的这个字，就希望他可以知道说，他代表着这reference image里面的所有特征，这样子，OK所以说从这个直觉就会有哎，衍生出第一个解决custom alization的方法。

就是它叫CUSMDEFUSION，那是从上上面这篇paper呃提出来的，那他的做法其实很简单，就是透过反应tin去让text to image model去学会，我刚才说的这个spatial。

那这边就是用一个new one的token来代替对，那这个FIGHTIN其实大家都已经读过，就是作业五，作业六应该都是跟fighting in相关的，对那他这边的啊。

主要的流程就是说我有一个reference image，那random model是左边这样，然后中间经过一个FIGHTIN过程，那FIGHTIN主要的目标。

就是希望说模型看到tanew one这个token，他就知道说new one代表的是呃这张图片，reference image图片的所有特征，所以说如果FTONE他学会这件事，就是new one。

就是嗯reference image的特征，那它在实际在使用的时候，就是说我们给他a new one dog，那他就看到new man，所以知道说我要生成一个跟REFENSE页面。

具有同样特征的呃图片出来，这样子对，那中间这步就是透过FTIN，去让模型学到这个新的token，那这是同学，这是作业第一个会用到的方法。



![](img/c8b37866b5adabcafc7bd9f11ed28987_9.png)

那接下来是第二个，那嗯第二个方法它主要就是想要改善，第一个方法，一个很大的缺点，就是说呃同学在做作业，五作业的应该就知道就是翻al in其实挺麻烦的，那如果用上面这个CUNDEUTION的方法。

你就必须要你有一个reference image，那你就要翻译成一次，那这是这是很浪费时间，而且很不方便的这样子，所以说嗯这篇新的方法lady fusion。

那是这边这边哎这上面这篇paper去propose的，他的核心思想就是说我们嗯可以直接学一个model，那这个model可以直接把这种new one token，给predict出来。

那地址就是下面这样，就是我有两种不同的reference image，那我有一个特别的model，那他是就是它可以特别拿来predict，这个new one token。

那所以说你给定不同的reverse image，它就有生成不同的new one token，那我这边是用不同颜色来代表，所以说难道这些嗯代表对于你reference image的new。

换token之后，我们再拿去给tt to image model，那我拿这个红色的new one token给text to image model。

他就知道我要生成的特征是这个reference image，那如果是绿色的话，他就知道我要生成的特征是这个，第二个REFERENCMGE，这样子，那这个方法的好处就是说我就不需要去嗯。

FIGHTIN的的这个步骤，那这个COSMEDITATION就可以很快的完成，对啊，这边是要介绍的第二个方法。



![](img/c8b37866b5adabcafc7bd9f11ed28987_11.png)

那同学嗯，同学在这次作业就是我们的在线播课，已经帮大家实做了这两个方法，那就是请大家去用用看这两个方法，然后挑挑一些关键的参数，然后就把生成好的图片呃，伞兵上来，那这次做的作业就算结束。



![](img/c8b37866b5adabcafc7bd9f11ed28987_13.png)

这样子好，那这边介绍一下这次作业会用到的data set，那嗯这次作业的data usage也就是只有六个object，那每个object它会有一张或者多张图片。

那还有它对应的tt form那六个object就是下面这六个，然后我们会希望比如说这只猫像on the graves啊，比如说这只狗with some glasses的这种。

那同学只要把对应的图片各自生成15张，然后嗯呃SAM到trash boy，那就可以进行一备备选。

![](img/c8b37866b5adabcafc7bd9f11ed28987_15.png)

那评分的部分呢就是嗯我们有六个object嘛，所以一个object就是一分对，那嗯依照难度来看的话，会有两个object是simple的，然后两个object是MEDI电。

然后两个object是strong的对，那各自需要的时间是大概是这样，就是用COLAB跑的时间，然后各自需要达到的呃，所需要做的hint是右边这边，那等等会再详细讲一下这个HT的部分。

对他这边说的就是成功，customize的话，它的定义是下面这一页，就是说我们刚才有介绍两种match，一个是长得像，一个是跟tech p是一样的，对那每个阿觉他都有各自的标准啊。

只要要就是一个object的两个matrix都达到了，才算成功，所以说如果你object1DIOSCORE高18618，然后take clip提高于八，那这个就算完成一个，那你就拿到一分。

这样那六个都完成的话，就能拿到六分，OK那接下来是讲同学该怎么达到这些啊，备赛啊，怎么拿到这些分数，OK那一样先从这个DISCER开始，就是就是，那就是同学就是依照这些这些hint。

也不一定可以不保证一定可以超过BESI，那我们后面会有一些嗯建议的范围，但也不保证你在这个范围里面就已经是最好的，那你是有可能在这个范围之外找到更好的，Hyper parameter。

然后第三个DISCRIMIN就是呃，我们这边算介绍了两个就是matrix，那这两个matrix可能跟同学格物嗯，自己用肉眼看的感觉可能有一些些不一样。

对意思就是说你可能会观察到这两个mattress很高，但是你自己觉得好像没有那么好，对或者是反过来，但也对，那通常通常这类型的customer类选，都会做human evalation。

但是因为我们这堂课人数太多，助教没有这个BANDWAGE去做这些事，所以我们就只能用这个自动化的，这些里面取出来，帮大家评分，这样子，好那再是int部分，那int首先就是因为跟刚刚介绍的嘛。

就是blade fusion，他是不需要嗯fine tuning的，所以他其实比hasten deution还要快，所以说基本上就是先试试看这个play deution。

那他可以把大部分的case都可以customize的很好，那这边我自己列出来，我自己觉得比较重要，可以先先调调看的HYPERFORM去，那第一个是这个number of influence steps。

然后再次改正skill，那这两个参数在simple空里面就是叫这个名字，所以大家可以直接搜寻这两个，这这两串字就可以找到这两个type perform。

那他们代表的意思分别就是啊number of inference steps，就是说在底NO型的用的次数，那就是下面有一张图，就是DEPENSIONMANO，在生成图片的时候。

它其实是一步一步的去DNOSE出来的，那如果你把这个次数调高，就代表这个步数会增加，代表说它可以DNOISE的更精细，所以通常来说啊这个step越高，那它的quality就越好，但是就会生成的就会越慢。

这样子，然后下面这个HYPERPARAMETER是呃guidance scale，它是主要用来控制我们的呃，Depression model，他要读more，准准找tech pro。

那通常嗯通常这个值越高的话，它就生出来的图片会跟你text pr越相关，但是通常会降低image quality这样子，OK所以我只这边是我自己的建议，就是上面这个influence state。

Number of influence state，通常诶你在目前在sample code的值，可能是相对偏低的，那大家可以慢慢把它调高了，看看看，然后看就是image quality有没有逐渐提升。

那提升到一个程度，那可能就没有没有提升那么明显，这样子对，那这边也是给一个呃推荐的范围，然后第二个第二个跟那个hyper parameter的话，也是目前simple code值也是相对偏低。

那你可以看看它慢慢调高之后，有没有更align你的tag pro对，然后这个这个hyper parameter你调的太高的话，你就会看到下面这种呃颜色比较奇怪。

然后或者有奇怪纹路的这种artifacts，那如果你看到的是类似这种东西的话，那就代表你这个纸条太高，你要把它降低一点点对，那这边也是有一个推荐的范围。

好那再来是关于custom diffusion的hit，那嗯CUNDEBUTION基本上就只要拿来解，只是比较困难的cash，那以我们这次作业的话，其实就是object5干嘛跟阿卷六。

那其他object你用blady fusion基本上都可以，就是成功的CUSMASH，那以下也是列出了几个我自己觉得比较重要的，Hyper paramar，那额底下底下四个其实就是FTIN会用到诶。

对了是这两个，第三个跟第四个是FTIN会用到的参数，那第五个跟第六个就是刚才介绍的那两个对啊，所以我这边就是介绍前面两个啊，第一个instance n pn，它其实就是说你在翻译成你就是教模型。

看懂这个new one token的时候，它所用的training data，就是它你给它一个嗯train data的tech from，那里面会有new one这个字，那他他看到这tae brown。

他就会去生成reference image，他的这个在这个翻ta过程这样子，然后第二个的话就是primeter to train，就是我们去调呃，劝你的时候要劝多少。

或者是劝劝哪些啊parameters，OK那现在也是我自己的建议这样子，那关于第一个嗯，instance problem嗯，最重要的就是你因为这个是在教模型。

这个new one token这个值的时候的training data，所以你啊这个句子里面就一定要有new one token的，这个这一串字在里面，这样子。

OK然后再来是你希望你在text run之类，在instance pn里面，你会希望尽量的去嗯，用文字，先把一些相关的information都直接include在里面啊。

例如说你已经知道你要customize，是一只黑色的狗，那你就可以嗯把黑色的狗就直接放在里面，而不是直接放new one dog这样子，这样子的我们画模型，就是就是从text就已经知道他是一只黑色的狗。

那就不需要把黑色这个feature也学在这个里面，然后会让群领更更容易一点点，那第三个就是第三个就是在你inference的时候，一定要把这些呃new one token也放在你的test pro里面。

你的模型才才会知道，你要生产的是reference image的那那个object，那接下来的话呃就是parameter to train的话，就是大家在FTIN的时候大概也知道。

就是嗯越多parameter他就可以越容易去学习，对那这就代表说它可以啊，最后在inference的时候，它会生成更接近reference image的图片，但你会失去模型，用taxi去搞错的能力对。

所以说是tenno scores比较容易会增加，然后会体会下降子，然后这个training step match matching steps也是同样意思，就是你train越久。

那模型就会伸出越像的image，但是他会越来越不去呃，遵照你的tt form这样子，那再来是额角胶的部分啊，嗯第一个是跟之前之前作业都一样，就是大家必须要把你的扣缴交到嗯额NTU库，那这个会占四分对。

那你以下就是这个缴交出来档案的一些规定，就是啊，那么只会有你最后一个是最后一次SAMMISSION，然后你必须要把你的口compass进去一个zip档，那他的档名是有规定的对。

那大小写就是大家要注意这样子对，然后再就是你这个zip里面是助教，在unzip完之后，你会看到一个directory，那它的名字要是这个，那这个底下。

这个directory底下就一定要有你的remain，跟你的code这样子，那不要去找掉你的model checkpoint啊，data set或者是其他不相关的档案对。

那这都可能会就是让你拿不到这个十分这样子，所以大家要小心一点好，那这边就是给一个呃例子，就是这个zip档要长成下面这个格式啊，有一个实际的例子让大家看这样子，好啊，这边是加大加大还呃瑞密的内容要怎么写。

这样子，那这些也跟之前的作业都是一样的，好那再来是judge boy的的部分，那judge judge boy，就是让大家去以value生成出来的图片，这样子啊，这个这部分会占六分。

OK那嗯这些图片会怎么被EBAY率，或者是怎么给分的话，就是看前面几个投影片，那啊一样会有每天五次的这个扩大，然后再就是你生成的图片，必须要压成一个zip档去上传，对那呃日语当解压缩之后。

它你会有六个六个的directories，那就是分别对应六个不同OBJE，那每个object你要生成15张图片对，所以这个六个directory各自底下就会有15张image，这样子。

那每个image的resolution是512512，对那实际上就是角角的话就会长成这样子，就是你的zip档的档名，然后底下会有六个directory，那每个directory底下又有15张图片。

这样子，好那再来的话就是一些额规定的部分，那这都跟之前一样，就是大家要仔细看，就是不要用额外的data，然后不要作弊般的嗯，档案啊，扣的分享给别人啊，对那惩罚的话就也都跟之前一样，所以就大家要小心。

不要违反了，这样子对，那再一次如果有问题的话，就是可以先去NTL库上面问，或者是寄寄email到助教形象，然后嗯我们也会有这个ta hour，但因为后面就没有实体上课，所以TL后会改成online的。

那时间是一样的，这样子，对啊，这就是啊作业时的讲解。

![](img/c8b37866b5adabcafc7bd9f11ed28987_17.png)

好那我们接下来讲解先破口的部分，先破口的部分，大家可以在size最前面。

![](img/c8b37866b5adabcafc7bd9f11ed28987_19.png)

link这边可以找到。

![](img/c8b37866b5adabcafc7bd9f11ed28987_21.png)

好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_23.png)

那前面的步骤就跟之前大家做之前的作业，不一样，所以就先复制一个一个copy。

![](img/c8b37866b5adabcafc7bd9f11ed28987_25.png)

我记得要改到使用GP5。

![](img/c8b37866b5adabcafc7bd9f11ed28987_27.png)

就可以放那一到R台上面，然后这份额sample code主要就是implement，同一篇里面讲的BLEDEFUSION跟custard deution，这样子。

那他们分别是从下面两个reference的call改过来的好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_29.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_30.png)

那我们这边就确认一下有用到GP5好，我下载嗯。

![](img/c8b37866b5adabcafc7bd9f11ed28987_32.png)

我的DNA set，然后poor package跟啊固定这个VENENCY这样子好，那DA的话就是旁边它会长这样子，然后这边会有一个meta data。



![](img/c8b37866b5adabcafc7bd9f11ed28987_34.png)

那这里面主要就是放说呃每个object它是它是什么，就是他是奥瓦，是SUNGLASS对，然后还有我们的text condition，就是我们要customize的text pro。

然后还有他的要通过的对，show是他备赛的标准，这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_36.png)

打图片的话就会，大概长这个样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_38.png)

就是大家可以从旁边这边看到的。

![](img/c8b37866b5adabcafc7bd9f11ed28987_40.png)

好那对。

![](img/c8b37866b5adabcafc7bd9f11ed28987_42.png)

那这份投影片就是由两个部分，lady fusion跟CARSONDEFUSION，那我自己的建议的话，就是同一个wrong time，就是同他那一次就是同一个RUNTIME里面就跑。

其中一个方法就好标接着跑，就是我跑完这堆DEPENSION，然后又直接跑卡成DIATION，因为这样可能会让呃collab run out of memory。



![](img/c8b37866b5adabcafc7bd9f11ed28987_44.png)

那就可能会出ERROLL，这样子好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_46.png)

我这边就先demo blady fusion的部分。

![](img/c8b37866b5adabcafc7bd9f11ed28987_48.png)

那BLADYPRESSION这边就嗯扣比较短，比较简单，就是我把帮大家把inference的防选写好对。



![](img/c8b37866b5adabcafc7bd9f11ed28987_50.png)

那里面有一些参数，就是我直接把它固定起来这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_52.png)

然后这边这行就是会把BLADYBUTION下载下来。

![](img/c8b37866b5adabcafc7bd9f11ed28987_54.png)

然后load到GU上面好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_56.png)

那接下来这边就是大家主要需要改的部分啊。

![](img/c8b37866b5adabcafc7bd9f11ed28987_58.png)

同一篇里面我讲过，讲到有两个比较重要的HYPERFM，就是把它写在这边，那大家就可以在这边改这样子，那如果想要改其他更细节的HYPERPARAMETER的话。



![](img/c8b37866b5adabcafc7bd9f11ed28987_60.png)

就可以去呃inference function里面找对，那就是这个blade哎，BRIEDY不选择，pipeline里面就会有很多参数可以改这样子。



![](img/c8b37866b5adabcafc7bd9f11ed28987_62.png)

那下面这个呃这个number of images的话，就是我要每个object我要生成几张图片，对，那这边要注意的就是，你如果是要拿来交交作业的话，那就一定得要写书，这样对你不乱改的话。

你可能一辈都学会出问题啊，但是在调参数的时候，就可以不用生成这么多张图片，就可以看结果，所以我这边比如说我这边只叫demo。



![](img/c8b37866b5adabcafc7bd9f11ed28987_64.png)

我就这是这样就好，然后再来的话就是下面这是default的话。

![](img/c8b37866b5adabcafc7bd9f11ed28987_66.png)

我是六个up主都会帮大家一次生成出来对，但如果你想要一个OBJE，一个阿卷来，或者是你只想要生成其中某几个up卷的话，你就可以把这一行on con没掉，就把前面的井字号拿掉。

然后把你要的嗯object留下来，例如说我这边只想要生成object，然后就把其他的就把呃删掉。

![](img/c8b37866b5adabcafc7bd9f11ed28987_68.png)

那这样他就会直接设置拉距离。

![](img/c8b37866b5adabcafc7bd9f11ed28987_70.png)

这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_72.png)

对那他这边就会开始开始啊生成图片。

![](img/c8b37866b5adabcafc7bd9f11ed28987_74.png)

那生成的图片就可以在旁边，它会在就是这个output directory底下，这里有一个resource。



![](img/c8b37866b5adabcafc7bd9f11ed28987_76.png)

他就可以生成一张图片，这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_78.png)

然后。

![](img/c8b37866b5adabcafc7bd9f11ed28987_80.png)

OK然后哎生成完之后就可以把，这边就会帮你把RZ补起来，那基本上就是这边的structure，就是我们规定的structure，所以如果你这边是六个object，然后每一个都生成15张。

那你直接呃zip下来的这个东西就可以下载下来，就可以直接上传。

![](img/c8b37866b5adabcafc7bd9f11ed28987_82.png)

就是它的格式就会是正确的这样子，但如果你像我这样子，就是我只生了某一个object，然后每其实不是每一个都是数张的话，你就必须要自己手动把它改成正确的格式。

这样子就是这边要有object1到object6，然后会有零点JPG到四点JPG。

![](img/c8b37866b5adabcafc7bd9f11ed28987_84.png)

这样子好，那这部分就是lady自选的部分。

![](img/c8b37866b5adabcafc7bd9f11ed28987_86.png)

就是非常容易，这边就对。

![](img/c8b37866b5adabcafc7bd9f11ed28987_88.png)

那我们接下来得某CARSONDEVISION，但就跟我刚才说的，就是我现在直接跑的话，应该会out of memory，所以我这边就是DISCENT掉，然后再重新开一个新的。



![](img/c8b37866b5adabcafc7bd9f11ed28987_90.png)

好那前面的步骤就是要这把改成用GPU对。

![](img/c8b37866b5adabcafc7bd9f11ed28987_92.png)

那前面的部分就是呃，不管你用play debution还是卡申defection。

![](img/c8b37866b5adabcafc7bd9f11ed28987_94.png)

都会需要跑前面的这部分，这样子对。

![](img/c8b37866b5adabcafc7bd9f11ed28987_96.png)

那VIDEFUSION部分我们就关起来，然后就感叹第二个部分就是他成底部选。

![](img/c8b37866b5adabcafc7bd9f11ed28987_98.png)

那他森DEPENSION这边就比较复杂一点。

![](img/c8b37866b5adabcafc7bd9f11ed28987_100.png)

因为会需要fighting，所以我们会先呃定义一个training data的的clash。

![](img/c8b37866b5adabcafc7bd9f11ed28987_102.png)

那他这这边就会把你的，就是投影片里面讲的那个instance part。

![](img/c8b37866b5adabcafc7bd9f11ed28987_104.png)

然后跟reference image配合起来，然后喂给model去做权利。

![](img/c8b37866b5adabcafc7bd9f11ed28987_106.png)

这样子，这部分就是帮大家写好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_108.png)

就不太需要修改。

![](img/c8b37866b5adabcafc7bd9f11ed28987_110.png)

那这边就是一些UT的地方，全是嗯data loader会用到的，然后还有sap嗯，把大的券号这东西存下来的时候会用到的防线。



![](img/c8b37866b5adabcafc7bd9f11ed28987_112.png)

然后再就是全脸防选。

![](img/c8b37866b5adabcafc7bd9f11ed28987_114.png)

那这个方选会很长，就是他会做是吧，下载的definition model的里面的卡扣呢都甩出来。

![](img/c8b37866b5adabcafc7bd9f11ed28987_116.png)

然后把该圈的地方啊，把它瑞典打开。

![](img/c8b37866b5adabcafc7bd9f11ed28987_118.png)

然后，对。

![](img/c8b37866b5adabcafc7bd9f11ed28987_120.png)

然后把嗯optimizer设定好，确定data哦，那你rise guler在九华就是会呃，ITERRAY那个training data。



![](img/c8b37866b5adabcafc7bd9f11ed28987_122.png)

然后就开始去some output snals，然后DEPAGATION去update这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_124.png)

然后最后就把就是选好的东西存下来。

![](img/c8b37866b5adabcafc7bd9f11ed28987_126.png)

这样子好。

![](img/c8b37866b5adabcafc7bd9f11ed28987_128.png)

那接下来的话就是这边，就是我同影片里面提到的，比较重要的hyper para对，所以如果也就是可以只改这些对。



![](img/c8b37866b5adabcafc7bd9f11ed28987_130.png)

那但如果你想要改更多细节的话。

![](img/c8b37866b5adabcafc7bd9f11ed28987_132.png)

就是可以到上面的training function里面去改，就是那些learning reschedular啊之类的都都可以改好，那这边instance prt的话就是找投影片面。

投影片里面讲的就是在training的时候，model就是看这句话，然后去生成reference里面去对，所以说你你是一定要把这个new one token放在里面，然后才可以去才可以去交。

MOL说你要看到这个new one token，那就是要生成这个up ject5的图片这样子，所以说好嗯对，那如果你要对，你要去，就是这边这边demo是object，但如果你想要改成object6的话。

就直接把这边改成object6，然后对，那下面的话就是premature主权，那这边有两个选项给大家选，就是可以只劝cross attention里面的K跟B，或者是你可以把Q也一起去圈下去。

那这样的话后面这个选项就是圈里的parameter，数会变多，这样子，那再就是learning rain，然后training state，然后bech size这些的。

就是在大家如果翻译清国model的话，就会知道，那这边我要因为demo，所以我就把train steps改小一点。



![](img/c8b37866b5adabcafc7bd9f11ed28987_134.png)

这样。

![](img/c8b37866b5adabcafc7bd9f11ed28987_136.png)

OK那这边就会开始train。

![](img/c8b37866b5adabcafc7bd9f11ed28987_138.png)

然后对那大家要注意的话，就是如果你想要改其他object的话，上面的这个pk就是要修改。

![](img/c8b37866b5adabcafc7bd9f11ed28987_140.png)

就是修改成对应的啊，就这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_142.png)

然后另外一个嗯嗯好，那我们这边等他群。

![](img/c8b37866b5adabcafc7bd9f11ed28987_144.png)

然后这边的话就是把就是这边翻译听完的模型。

![](img/c8b37866b5adabcafc7bd9f11ed28987_146.png)

把它load起来，那下面的话就是inference，那这边你要注意的最重要的地方，就是这个是你应认识时所需所给的TEXPL，对，那这边最重要的是new one，这个token一定要在。

然后再就是后面这个in the snow的这个condition。

![](img/c8b37866b5adabcafc7bd9f11ed28987_148.png)

就会是在这边这个metadata里面的the taste contection u。

![](img/c8b37866b5adabcafc7bd9f11ed28987_150.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_151.png)

如果他是这边是demo，说要生成object，所以他是赢得什么，那假设你想要生成object6的话，那你就是要记得要改成on the play went，然会它也会生成你的store的图片。

那我们在啊100UA是用on the，on the play去EVELLIA的话。

![](img/c8b37866b5adabcafc7bd9f11ed28987_153.png)

那你的结果就会是错的这样子。

![](img/c8b37866b5adabcafc7bd9f11ed28987_155.png)

啊这边两个APPROPRIMETER。

![](img/c8b37866b5adabcafc7bd9f11ed28987_157.png)

也就是呃图片里面讲到的这两个加起停在。

![](img/c8b37866b5adabcafc7bd9f11ed28987_159.png)

啊对这边也是一样，就是这个15的话就是要生成图片的数目对，所以如果你要交作业的话，就一定要是实物。

![](img/c8b37866b5adabcafc7bd9f11ed28987_161.png)

就不要乱改这样子，啊结果的话就会，结果的话就会在这边那一样的。

![](img/c8b37866b5adabcafc7bd9f11ed28987_163.png)

就是这边的structure，如果你是都是15张的话，那他的就是数目跟director。

![](img/c8b37866b5adabcafc7bd9f11ed28987_165.png)

就是structure或者是对的这样子，所以如果就这样会直接帮你自己起来，那假设你这边的档案都是有六个object，然后每个OBJE又有15个话，那他就会是正确的zb down这样子。



![](img/c8b37866b5adabcafc7bd9f11ed28987_167.png)

![](img/c8b37866b5adabcafc7bd9f11ed28987_168.png)