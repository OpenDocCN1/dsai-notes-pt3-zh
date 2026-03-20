# 宾夕法尼亚大学【中英⚡GPU编程｜CIS5650 2024 GPU Programming】 p03 P3 2024-09-04 - Lecture 2 CUDA Introduction 2 -BV1JeMnzFEWv_p3-

は。

![](img/579514094183b68005aa86f6f500062f_1.png)

H everyone hope everybody had a great Labor day break I know it's always weird to have the first class and then have a Labor day break so let let's get started here。

😊。

![](img/579514094183b68005aa86f6f500062f_3.png)

![](img/579514094183b68005aa86f6f500062f_4.png)

I want to get started with maybe before we even do this a quick show of hands because I know a bunch of people missed last Wednesday so just to show of hands to see if anybody missed all right we have one two。

😊。

![](img/579514094183b68005aa86f6f500062f_6.png)

![](img/579514094183b68005aa86f6f500062f_7.png)

![](img/579514094183b68005aa86f6f500062f_8.png)

3 and you guys were able to watch the recording to catch up okay。

 any comments on the recording was the audio clear and stuff because again we try to use we try to improve every year but any feedback would be good so that we can act on it this semester itself。



![](img/579514094183b68005aa86f6f500062f_10.png)

![](img/579514094183b68005aa86f6f500062f_11.png)

![](img/579514094183b68005aa86f6f500062f_12.png)

Yeah， the south。Sound is a bit low， okay。Oh oh so the Monday one is actually prered from a few years ago but but thank you for that feedback was the Wednesday class good Okay Wednesday class good。

😊。

![](img/579514094183b68005aa86f6f500062f_14.png)

![](img/579514094183b68005aa86f6f500062f_15.png)

![](img/579514094183b68005aa86f6f500062f_16.png)

So it's optional， and that's my next question。

![](img/579514094183b68005aa86f6f500062f_18.png)

We， we'll get to it。 Allright， so wna do a quick round of introductions。

 I don't do it last class because everybody's new。 Everybody's like why wided。

 So maybe a quick round of intro with with this。 Let's start with you。

 and then we'll go around like a snake。 Yeah hi， I'm Nick。

 I'm a senior I'm gonna graduate from undergrad like in spring in 2025。

 but I just applied for another semester for CGTT。 So I'm assist undergrad。

 And I interned at Samsung for the past couple summers one doing like bulk an internal deathols and another doing compilers compiler stuff in the same place as。

😊。

![](img/579514094183b68005aa86f6f500062f_20.png)

![](img/579514094183b68005aa86f6f500062f_21.png)

![](img/579514094183b68005aa86f6f500062f_22.png)

![](img/579514094183b68005aa86f6f500062f_23.png)

![](img/579514094183b68005aa86f6f500062f_24.png)

![](img/579514094183b68005aa86f6f500062f_25.png)

![](img/579514094183b68005aa86f6f500062f_26.png)

![](img/579514094183b68005aa86f6f500062f_27.png)

这什语吗。呵呵系呀。What。Hello， everyone I'm Matt。 I am a CGGT student。



![](img/579514094183b68005aa86f6f500062f_29.png)

Two semesters now full time。I haven't interned anywhere in the games industry。

 but I have been in software for a while at Amazon。



![](img/579514094183b68005aa86f6f500062f_31.png)

![](img/579514094183b68005aa86f6f500062f_32.png)

He fair for that。So yeah， I'm just doing a little bit of a careership and I'm excited to take this box and meet everyone。



![](img/579514094183b68005aa86f6f500062f_34.png)

And Matthew met me last year， right， for attending the class。



![](img/579514094183b68005aa86f6f500062f_36.png)

How about you。Hello， my name is Allen。I am also a C teacher student。 I plan to graduate next summer。



![](img/579514094183b68005aa86f6f500062f_38.png)

And as for my previous internship， I entered Samung this summer。 I worked on the project Mohan。

 the Xer device theyre making to talk ofco。

![](img/579514094183b68005aa86f6f500062f_40.png)

And在行里。

![](img/579514094183b68005aa86f6f500062f_42.png)

S。Next it， all。

![](img/579514094183b68005aa86f6f500062f_44.png)

My early leg intership would be it。結婚的个。

![](img/579514094183b68005aa86f6f500062f_46.png)

Hi I'm Kevin， I'm a first year Max student the ZIS program。

 while I did an internship last summer the NCSA， which is a super confidence intern in UIDC。



![](img/579514094183b68005aa86f6f500062f_48.png)

![](img/579514094183b68005aa86f6f500062f_49.png)

D요。

![](img/579514094183b68005aa86f6f500062f_51.png)

嗯。Over summer， I was at Eri doing some graphics program。Its like you' having the same set。你个。



![](img/579514094183b68005aa86f6f500062f_53.png)

I'm Denette， I'm a senior in DMD graduating spring， and in the past for this past summer I worked。



![](img/579514094183b68005aa86f6f500062f_55.png)

Respond E on ApX Legens as a technical。

![](img/579514094183b68005aa86f6f500062f_57.png)

A cool。

![](img/579514094183b68005aa86f6f500062f_59.png)

Hi， my name is Cchelle and it's my first year at CBGBC。



![](img/579514094183b68005aa86f6f500062f_61.png)

I expect to graduate。Spring party on somes and。呃。Last year I was working as a game player。嗯。



![](img/579514094183b68005aa86f6f500062f_63.png)

Oh。Yeah I'm too too。 I'm I'm also a second year T student and have。



![](img/579514094183b68005aa86f6f500062f_65.png)

Dened at in games。And mainly develop some QG5 engine development。

 and also I have internal turn Apple to some activity。



![](img/579514094183b68005aa86f6f500062f_67.png)

![](img/579514094183b68005aa86f6f500062f_68.png)

呃，对。3呢。

![](img/579514094183b68005aa86f6f500062f_70.png)

And technically， a third year。ね I love all kinds of。内裤。でく。



![](img/579514094183b68005aa86f6f500062f_72.png)

Hi， I'm Joanna， I was a DD undergrad graduate。

![](img/579514094183b68005aa86f6f500062f_74.png)

Last year that this year for。

![](img/579514094183b68005aa86f6f500062f_76.png)

。

![](img/579514094183b68005aa86f6f500062f_78.png)

Okay。嗯，行，那是。I'm also a senior in BMT。 this past summer month， I'm the research at CU。

 and before that， I worked in。

![](img/579514094183b68005aa86f6f500062f_80.png)

![](img/579514094183b68005aa86f6f500062f_81.png)

我。

![](img/579514094183b68005aa86f6f500062f_83.png)

![](img/579514094183b68005aa86f6f500062f_84.png)

Aers。あそで。And before。

![](img/579514094183b68005aa86f6f500062f_86.png)

Hi everyone， I'm Jordan， I'm a senior majoring in computer science and mathth。

 haven't interned anything related graphics before， but last summer of the CASCAI。好。

I am Kyle for my second year E student。If they graduate in spring。能会家那我们你就发。I think Mike。

 I'm a part time C Houston expect graduate May。Let it go for a lot of art full time background later。



![](img/579514094183b68005aa86f6f500062f_88.png)

Yeah。Sorry， we。

![](img/579514094183b68005aa86f6f500062f_90.png)

Now let's use your GT I was respond again。

![](img/579514094183b68005aa86f6f500062f_92.png)

I miss the first in the classes， I explained I was entertaining video。



![](img/579514094183b68005aa86f6f500062f_94.png)

第个。It have very close experience on role level。

![](img/579514094183b68005aa86f6f500062f_96.png)

So。

![](img/579514094183b68005aa86f6f500062f_98.png)

Good。他们些人。那什呢？W minus7。I second years agoです。Inmread it。あ？Summer are。In terms of guidance working。Hi。

 everyone。呃，然后姨现在。

![](img/579514094183b68005aa86f6f500062f_100.png)

应。I不能再对一。最全。嗯，他人。In the past summer， I was。personalal dynamics working。



![](img/579514094183b68005aa86f6f500062f_102.png)

Hi， my name is David。 I'm。在哪位。And那呃。

![](img/579514094183b68005aa86f6f500062f_104.png)

Carbons。Thank you to the students a year library room。はと。那有不能。This so much。I am Michaelcha。

Bian MCC B。For year and。

![](img/579514094183b68005aa86f6f500062f_106.png)

Sp。Before I was studying， I was animation TV at Animal Lo。



![](img/579514094183b68005aa86f6f500062f_108.png)

I go movie and stuff， so that was fine。

![](img/579514094183b68005aa86f6f500062f_110.png)

And I'm from Australia。Yeah。My name is Arrey。How many ZS MCG students are inter in De people。

啊年可个西个嘅都这个。たかの大か。あ。还是。Sorry， didn't catch your name did you say Billy？Okay， thank you。お父さ？

And I will just that。按那个2。他收到这个个上了。Co。I am Dominic。 in confusion。 I don't have any previous sector。

认真不然。啊，我看了这个什问。最しで。And I。And this summer I was doing。当し。我之前。好的。哎，我是。of。没。啊嗯。All right。

 we'll skip Han and Kristen。I。ます。

![](img/579514094183b68005aa86f6f500062f_112.png)

Everyone a fun and。