# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p35 35_02_07_凯撒密码CLI.zh_en -BV1tz421i7Ev_p35-

![](img/882b02226b7882cd0621710bc90efb20_0.png)

Let's take a look here at a Caesar cipher， which is a simple cipher that shifts values by some numerical constant。

 for example，2， three different letters in the alphabet over and in this scenario here we can see this in crypt function。

 which does all of the heavy lifting and then the decrypt which turns it out the other way now in terms of what I'm going to do in this particular example。

 is to build out a comment that allows me to show how you can actually use this in a more sophisticated way so。

A lot of times when you're building a utility， a command line tool is one of the best possible ways to play with it。

 iterate through the different concepts。 So in this particular example here。

 we can see here that I have cargo run and I put in dash message off to the bunker every person for themselves。

 and then I can encrypt it and then shift it by some numerical constant。 and to decrypt it。

 I would actually just do the opposite scenario here， which is do cargo run dash message。

 put in the encrypted message and then decrypt it and then shift it。

 So this is a great way to try a different idea out。

 especially things like encryption cipher's klan tool is an amazing you know utility to actually leverage how to get the most out of the code you wrote。

 So in this particular example here， I just import the decrypt and encrypt。 Next step。

 I use the clap parser here to do all the heavy lifting。😊，And this example here。

 I say CI tool to encrypt and decrypt messages。 and this is mostly boilerplay code。

 but I do have an encrypt message。 I have a decrypt message and I also have the message itself right So those are really the main items and then the shift is really important as well。

 I do a default value of three。 but obviously you're going to need to shift in and also unshift whenever you're decrypting or unenrypting a message。

 Finally to pull it all together pretty straightforward。

 you just pull in those arguments by using let args and then you just iterate through。

 So you say if encryption is set， do this。 otherwise do this。

 and you you navigate through what's happening。 So let's go ahead and run this。

 So let's type in cargo run。And now， if we look and we say message。We can say， for example。Hello。

And just try something really simple。And it says， oh。

 we need to actually change how we're doing things。

 I noticed that it didn't work because I didn't put in the first double hyphen here。

 So this is an easy make mistake to make because when you're using it from a non binaryary release。

' you're using the chameleion tool from essentially the project。

 you're going have to pass in those messages inside。 And that's what the double hyphen does。

 So if we run it again， there we go， please specify either encrypt or decrypt。 Okay， great。

 So now I can start to play with us and I can just say I want to do the binary。

Toggle here of of encrypt。 So there we go。 We see that it encrypted with a shift of three。 Now。

 if I wanted to change the shift to， for example， one。There's a shift of one。

 and we can also see obviously H， the next letter is I E， the next letters is F right。

 so you can intuitively kind of figure that out and then to decrypt it。

 we can actually go through here and do a decrypt。Derypt。And then put in the message。

Which is this message。And then go to the end。 I did a control E to get me to the very end again。

And now it can actually decrypt it。 So in my opinion。

 building little tools that help you out to do things is one of the advantages of Rus。

 I would say it has a strong advantage over scripting languages because of the fact that it has binary-based deployment and then it's very。

 very safe so I would say in many ways a rust-based kmean tool has a superior experience to other scripting languages because that binary once it's built you can just give it to somebody and then they can actually run through the tool。



![](img/882b02226b7882cd0621710bc90efb20_2.png)