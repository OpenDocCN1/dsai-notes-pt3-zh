# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P7：6-作业 Training Transformer - Ai人工智能工程师 - BV1QdzCB3Eu2

那我要来讲作业四，那我们作业室的内容是training transformer，然后在line一样是三个礼拜后这样，那我会先讲这次作业的online，那这我会先讲这次作业的task。

还有这次作业会用到会用到的assets，然后我们这次作业是要打榜的，所以会讲一下这次作业的备赛，然后会讲一下这次作业的角交跟评分规定，然后跟一些appendix好，那先讲这次作业的task。

那我们这次作业的task呢要用呃transformer，Decoder，only的model去做next token prediction。

那我们会拿宝可梦的图片做next token prediction，那我们的目标呢，就是要用现在的LM的architecture。



![](img/46e93621760e69645276f41a8da3c3ea_1.png)

做next token prediction，那先来讲一下next token prediction，那我们知道文字的LM可以用next token prediction，来做training。

而是给前面的文字，然后你就要去predict说下一个文字是什么。

![](img/46e93621760e69645276f41a8da3c3ea_3.png)

那其实在其实图片也可以做一样的事情，我们可以把图片看成是一串pixel，然后我们就可以由第一个pixel去predict，第二个pixel，然后前面两个pixel去predict，第三个pixel。

然后前面三个pixel去predict，第四个pixel，以此类推去做到啊，Next token prediction，那这是training的部分。



![](img/46e93621760e69645276f41a8da3c3ea_5.png)

那testing呢我们会拿呃，前60%percent的图片的pixel，然后要同学去predict，后面40%的图片的pixel。



![](img/46e93621760e69645276f41a8da3c3ea_7.png)

好那我们这次作业用到matrix会有两个，第一个是FID，那FID呢，就是我们会把你的图片跟，真实的宝可梦的图片呃，输入进这个inception net里面，然后去抽各自的feature。

然后去得到各自的呃平均跟标准差，那我们会算他们两个之间的呃distance，那这个距离呢就是代表说啊你生成出来的啊，宝可梦图片跟真实的宝可梦图片的distribution，之间的距离这样。

所以这个距离应该要越小越好，表示两个distribution越相近。

![](img/46e93621760e69645276f41a8da3c3ea_9.png)

那第二个BATTRIC呢是这个PDR，就是ppocameo detection rates，就是我们会把啊，你生成的这些宝可梦图片，输入进一个classifier里面。

然后这个classifier呢就会去分类你的图片，把像宝可梦的这些图片的label设成一呃，Prediction1，然后呃不像宝可梦那些图片分类成零，所以这个分数应该是越高越好。



![](img/46e93621760e69645276f41a8da3c3ea_11.png)

好那再讲一下这次作业的dr sets。

![](img/46e93621760e69645276f41a8da3c3ea_13.png)

那我们这次作业的dr sex呢，会拿额792张的宝可梦图片，然后每个图片是的大小是20×20，所以每张图片会有400个数字，然后每个数字就代表一个颜色，像是呃这个左边这个DATASET呢。

就是啊就是有啊很多张图片，然后每张图片就是会有400个数字，然后再看啊右边这个DATASET的话，就是每个数字会对应到一个颜色，那其实这份作业你只要用到呃，左边这个data set就足够了。

那我们这次总共会有792张图片，然后training size呢会有632张，对dation test会有80张，然后testing size也会有80张，然后每张图片的大小就是20×20。

所以总共会有400个pixel，然后总共会有167种颜色。

![](img/46e93621760e69645276f41a8da3c3ea_15.png)

那再讲一下这次作业的备赛。

![](img/46e93621760e69645276f41a8da3c3ea_17.png)

首先是simple杯赛，那simple bassn的话就是你去建一个transformer，Decoder，Onemodel，做next token prediction。

那这部分你只要跑一下simple code，应该就能过simple杯赛，那大概预计的training时间，就是在口袋上面跑10分钟，就能完成这次的simple备赛，那再来的话是medium备赛。

那medium备赛的话，你可以做两件事情，第一件事情就是你可以去改model的configuration，去改里面的heaven parameters，那第二件事情的话就是你可以去改sil code。

里面的train的AIRPODS跟learning rates，那如果你调到一个合适的数值的话，你应该就可以过这次的迷迭杯赛，那大概预计的training时间是呃，在口袋上面跑20分钟。

那第三个的话是双倍赛，那STR杯赛的话有两种做法，那我们比较推荐第一种，应该理论上你做第一种就能过这次的双杯赛，那第一种就是我们在sample code用的model architecture。

其实是GBT2，但其实你可以换成不一样的model architecture，比如说你可以换成la miro或是前文，他们虽然都是transformer decoder on only的model。

但是其实里面的架构还是有点有一些不一样，那你换成这个lama mr。或前吻的话，那应该就能帮助你过双北赛，那第二个话就是劝一个class bar去看，说你生成出来的影像到底像不像一只宝可梦。

大原因是这样，就是我们在simple code里面，我们存checkpoint的方式是我们去看啊，最小的那个train lost的那个APOK，然后把那个check point把它存下来。

那这个这样做的理由是，因为如果你拿vacation sets的reconstruction accuracy，其实它不能真正代表说这这个model生成呃，图片的能力，那有一个更好的做法。

其实就是你去呃创造一个classifier，去classify说啊，你这现在这个checkpoint生成的这些图片，到底像不像一个一只宝可梦这样，那如果你做完呃这个算备赛这些hits的话。

你大概在口袋上面跑30分钟就能劝完，那来仔细讲一下这次作业的啊，这这这这次作业双杯赛的两个H，那第一个hint的话，其实你只要去改啊，sample code里面的呃，CONFIG的那个dog。

那你就可以把里面的CONFIG换成是拉马尔的CONFIG，或者mix的CONFIG，或者千万的CONFIG，那这边的话你就要去看，说这些CONFIG里面的那些hyper parameters。

各自代表什么样的意思，然后你要去调出一个合适的数字，你才会过这次的双备赛，那你你要调调到一个合适的数值，还有另外原因，就是如果你完全不调的话，你有可能会out of memories。

那这样你可能会劝不下去。

![](img/46e93621760e69645276f41a8da3c3ea_19.png)

那第二个话就是嗯这是一个option的做法，就是你去劝一个classifier，那training的方式，就是你把那些不像宝可梦图片的，不要不像宝可梦的图片的label设成零。

然后像宝可梦的图片label设成一，然后去造一个bbinary classification的DATASETS，去创一个CNN的classifier，这样你就可以拿这个classifier去选择。

你最终要用哪个trap point，但理论上如果你做完上一个HS的话，你应该就可以过双飞赛，所以这个这个HS其实是可做可不做的。



![](img/46e93621760e69645276f41a8da3c3ea_21.png)

![](img/46e93621760e69645276f41a8da3c3ea_22.png)

那再讲一下角交跟评分规定，那这次作业的话，我们我们就要缴交到judge boy去看啊，你生成出来的图片的品质好不好，那我们这次作业只会呃拿那个点TXT的file，那每天就是只能缴交五次，然后晚上11：

59分会重置那个qua。

![](img/46e93621760e69645276f41a8da3c3ea_24.png)

![](img/46e93621760e69645276f41a8da3c3ea_25.png)

那你的撒submission file呢就是要包含80行，因为你的testing set就是80张图片。



![](img/46e93621760e69645276f41a8da3c3ea_27.png)

那每一行呢就要包含400个数字，原一张图片就是20×20的的大小，这样。

![](img/46e93621760e69645276f41a8da3c3ea_29.png)

那也要记得把你的扣缴交到NT5pro上，那我们只会看到你最后的submission，那请不要缴交你的model check point或者data sets。

然后你的code也必须要是reproducible的，然后你的扣子，你的扣子要包成就是下面的格式，就是啊你的学学号，然后底线HW4点。



![](img/46e93621760e69645276f41a8da3c3ea_31.png)

这，那再讲一下评分方式，那我们这次呢就是有三种杯赛，就是simple media跟strong，然后又有分public se跟private se，那要然后每一个杯赛的话就是一分。

然后cos Mission就是四分，那要注意的是，就是啊每个杯赛你都要同时过FID跟PDR，你才会是你才是真正过那个杯赛，那deadline的话就是呃，四月11的11。59分。

不管是judge co或NT5pro都是一样，那再讲一下规定，就是不能抄袭，然后不要手动去改你的prediction file，然后不要不要分享你的co或是prediction file。

然后也不要用任何方式，就是让你可以每天缴交超过五次，然后去不要请不要去找额外的training data，或是用任何的pretrain model。

因为我们这次的我们这次是transform scratch的，然后这次这次作业的生成的一些图片，只能用在这次作业，不要拿去让他有额外的用途，这样然后如果违反上面的规定的话，就是分数乘以0。9或是。

然后呃你要学习分数乘以0。9，然后这次作业的分数是零分，然后如果违反多次的话。

![](img/46e93621760e69645276f41a8da3c3ea_33.png)

就是会被当掉这样，然后最后是一些appendix啊。

![](img/46e93621760e69645276f41a8da3c3ea_35.png)

这是做这次作业会用到的DX，然后如果有问题的话，就是要推荐，先要推荐先同学先去NT5pro上面发问，然后如果有其他问题的话，就可以寄掉这个助教信箱，那你的title必须要包含这个HW4。

然后TL2的话就一样是啊，每周五的呃，01：30到2。20，或是课堂结束后到六点截止，啊这是做这次作业的size的讲解。



![](img/46e93621760e69645276f41a8da3c3ea_37.png)

好诶，大家有问题想要问的吗，如果没有的话，那我就要开始讲code。

![](img/46e93621760e69645276f41a8da3c3ea_39.png)

好诶，等一下好。

![](img/46e93621760e69645276f41a8da3c3ea_41.png)

那我来讲一下这次作业的扣，那首首先前面呢就是呃去下载一些package。

![](img/46e93621760e69645276f41a8da3c3ea_43.png)

然后跟呃import需要用到的package。

![](img/46e93621760e69645276f41a8da3c3ea_45.png)

然后去检查说你这次的code有没有真的用到GPU。

![](img/46e93621760e69645276f41a8da3c3ea_47.png)

然后会先设render seit，就是让同学扣可以reproduce。

![](img/46e93621760e69645276f41a8da3c3ea_49.png)

那再的话就是准备data a部分。

![](img/46e93621760e69645276f41a8da3c3ea_51.png)

那我们这边就是会建一个data set的class，那要注意的部分是。

![](img/46e93621760e69645276f41a8da3c3ea_53.png)

这边这边的话每个sequence的话，每个sequence都是代表啊一张图片，就是一串pixel这样，那如果是在training的这个mod的话。

就是你的input会是除了最后一个token的sequence，那你的label呢就是除了第一个token的sequence，那在北diation size的话，就是前面60%的图片的sequence。

然后label的话就是呃，后面40%的图片的sequence，那testing set的话就是只有input。



![](img/46e93621760e69645276f41a8da3c3ea_55.png)

那接下来的话这边就是啊download data sets。

![](img/46e93621760e69645276f41a8da3c3ea_57.png)

跟准备好那些data loader的部分。

![](img/46e93621760e69645276f41a8da3c3ea_59.png)

那这边的话我有帮你们写好。

![](img/46e93621760e69645276f41a8da3c3ea_61.png)

那个visualization的部分，就是呃你可以去看说training sets里面的图片，大概长什么样子，跟testing set上面长什么样子，那可以看到说testing size的话。

我们只会给你呃，那个那张图片前面60%的的东西，那再来的话就是准备model的部分。

![](img/46e93621760e69645276f41a8da3c3ea_63.png)

那我们这边的话就会先set这个model configuration。

![](img/46e93621760e69645276f41a8da3c3ea_65.png)

那这边会有两个hints。

![](img/46e93621760e69645276f41a8da3c3ea_67.png)

第一个hints就是你去改这边的啊，这个CONFIG里面的hyper parameters，那第二个hints就是那个双杯赛的hits，就是你可以改这边把这边的改。



![](img/46e93621760e69645276f41a8da3c3ea_69.png)

把这边的CONFIG改成是其他model的CONFIG，这样。

![](img/46e93621760e69645276f41a8da3c3ea_71.png)

那呃你把CONFIG这边改完之后。

![](img/46e93621760e69645276f41a8da3c3ea_73.png)

接下来就是low model部分，就是我会呃，这个model就是from config，这样就是因为我们不需要他的PRETRAIN的位置，我们是要transform scratch的。



![](img/46e93621760e69645276f41a8da3c3ea_75.png)

那这边会pr出你的model的这个architecture，然后然后也会print出呃。

![](img/46e93621760e69645276f41a8da3c3ea_77.png)

你现在有多少个trainable的parameters。

![](img/46e93621760e69645276f41a8da3c3ea_79.png)

那再就是training和inference的部分，那这边的话就是会可以设一些，training的arguments，那这边就是会有第三个hints，就是medium bas赛的hints。

就是你可以去改啊。

![](img/46e93621760e69645276f41a8da3c3ea_81.png)

这个training的AIRPODS跟training的learning rate。

![](img/46e93621760e69645276f41a8da3c3ea_83.png)

那这边会有safe model的function，那再的话就是啊training的code这样。

![](img/46e93621760e69645276f41a8da3c3ea_85.png)

那trainer code的话上半部分是training。

![](img/46e93621760e69645276f41a8da3c3ea_87.png)

然后下半部分的话是呃呃伪vacation的那个部分。

![](img/46e93621760e69645276f41a8da3c3ea_89.png)

那可以看到说我们在这边是拿额最低的training。

![](img/46e93621760e69645276f41a8da3c3ea_91.png)

loss当做train checkpoints的标准。

![](img/46e93621760e69645276f41a8da3c3ea_93.png)

所以这边会有第四个hits就去改。

![](img/46e93621760e69645276f41a8da3c3ea_95.png)

说我们把呃从checkpoints的标准，换成是用一个test fer去看，说你生成的有的你生成的有多少图片。



![](img/46e93621760e69645276f41a8da3c3ea_97.png)

像一只宝可梦这样，那再次提醒这个是option的部分。

![](img/46e93621760e69645276f41a8da3c3ea_99.png)

是可做可不做。

![](img/46e93621760e69645276f41a8da3c3ea_101.png)

那你劝完之后呢，应该会长这个样子。

![](img/46e93621760e69645276f41a8da3c3ea_103.png)

然后这边的话就是inference code，就是我们会把你的model漏进来。

![](img/46e93621760e69645276f41a8da3c3ea_105.png)

然后做evaluate，然后生成prediction的FB，然后最后一个visualization部分就是看啊，也你的这个track point啊，生成出来这个prediction file。

生成出来的图片到底长什么样子，对啊。

![](img/46e93621760e69645276f41a8da3c3ea_107.png)