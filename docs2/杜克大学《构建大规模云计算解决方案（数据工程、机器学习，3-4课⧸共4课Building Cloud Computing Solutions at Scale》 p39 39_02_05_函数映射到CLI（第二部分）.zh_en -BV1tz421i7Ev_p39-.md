# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p39 39_02_05_函数映射到CLI（第二部分）.zh_en -BV1tz421i7Ev_p39-

![](img/71c264a6710141840aa067974a03005d_0.png)

Now what else can we build that would be you know more useful well let's try to build some more command tools so let's look at this one here。

 which is another one I've gotten here， which is called Comp vision CLI。

So what this one does is allows us to pass in the name of a bucket in Amazon S3 and actually do computer vision based on what's in that bucket and in particular it has a。

A labels function that will allow us to detect labels。In order to test this。

 I'm going to switch environments， I'm going to swap over to AWS here。

 and I'm going to go to something called Cloud9， I'll make this a little bit bigger。

So let's go to Cloud9 and Cloud9 is really the Amazon equivalent to this。

 and I can go ahead and just open up any environment。



![](img/71c264a6710141840aa067974a03005d_2.png)

Instead of here。And what this will do is allow me to natively connect to。Amazon。

 so that when I'm doing API calls， things are a lot simpler。Now， if I went to。Amazon recognition。

And I think I have a picture somewhere here。

![](img/71c264a6710141840aa067974a03005d_4.png)

On my desktop， if I don't， I can just download it。 so I'm going to go through and say like Google image search。



![](img/71c264a6710141840aa067974a03005d_6.png)

Here， and I'll just type in like a lion， right， so we'll just go through here say a lion。



![](img/71c264a6710141840aa067974a03005d_8.png)

Great， there's a picture of a lion， I don't know， this one looks good。

 I'll just go ahead and save that。We'll call this lion。And then maybe like a tiger next。Get a tiger。

Here， great， and here's a tiger。We'll go ahead and save those， so I'm going to grab these two images。



![](img/71c264a6710141840aa067974a03005d_10.png)

And then I'm going to go not only to this cloud9 environment， which we'll get into in a second。

 but first I'll show what you can do with the services in AWS。

 so they have something called recognition， which allows us to search and analyze things。

And in particular， we've got object and scene detection， so if I go ahead and I throw in。

Here I would just throw this。Into drag and drop this lion。

 you'll notice that it finds that it's a mammal， it does wildlife， is another label。

 animal is a label， lion as a label if I throw in a tiger。It goes through here， same thing。

 really similar。That's really the use case here is that we have a pretrained computer vision model that does labels。

 and so I want to maybe operationalize this and use this well how could I do this well what we could do is build out something that will allow us to do this programmatically。

And so in order to do that， I'm going to check out this project。

 this function bike ridder inside of this cloud9 environment and start to build this out。

 so I'm going to click on code here。And I'm going to go to this repo and copy it and then go back into this environment。

And I'm going to say get clone。Like this。And clone this。

 notice that you will have to set up SSH keys if you haven't set that up and I have， you know。

 basically in a nutshell， we'll just briefly say what that is is for SSH keys。

You would just need to type in SSH keygen， T RSA， go through， generate the key。

 take the public key and put it into GitHub I've already done this previously so I won't need to do it All I need to do is do Git clone。

Once I do that， it puts it into this environment， which has also got great Python support and now I can look at this CLI tool here。

 right？Now， what I'm going to do here is actually restructure this a little bit。Because the logic。

Is in this labels function。And I want to test out the labels function independently。And。

I guess you know， basically it's already kind of pre embedded into this Ka tool， so what we could do。

Is we could just take this function here and we could just put this into another file real quick。

 So let's see the into here。I'm going to create a virtual environment。

We'll do this function bike rider。And let's source it。Okay， now that I've got this。

 we can see that it's we're using this virtual environment。Python 36， okay。

And what I can do here is make another file and we'll just call this label。labelbel or。

How about that？We'll just labels。 labelbels sounds good。 labelbels up UI。

And if I double click on this thing， we can paste this in。

And this says this takes an S3 bucket and an image name。

 so this is the bucket name and this is the image name so in order to get this thing working。

 I will have to。Import Bodo3， so go through here。And we'll say import Bo3。Like this。

 And I also will need to do something with this code。

 So I'm going to need a bucket and then a name of an image。 So in order to do that。

 let's go over to Amazon S3 here。And let's。Create a bucket。If I don't have one handy， let's go to。

I probably have one that I could use， but let's see if。

Let's see if I can create another bucket if they'll let me， we'll call this。Function， bike rider。

And go ahead and create this。Oh I've created too many buckets。

 I knew I was going to get trouble with that， so I'll just delete some bucket。And I'll do that。 Okay。

 doesn't like that one， let's delete。Census demo， if it doesn't， I'll just reuse a different bucket。

Yeah， I got too many buckets in my my project， I can just put it into。Here we go， Alfredo Noah。

 this is a good one， I don't think there's anything in here or I'll delete these。

 we'll just delete those things。And I can just permanently delete this。Okay。

So we'll use this Alfredo NoA bucket。In our code， and what I'm going to do is I'm going to drop in。

A picture of the lion inside of here， just like that。There we go， so we've got this picture inside。

 it's called lion。 JPg。Now， how do I now get my code working with this？

What I would need to do is my opinion， the best way to do this would be to use i Python again to play around with this so if I go。

Here。I can actually。Say from labels。Import labels。We didn't install Bo 3 so that's easy enough to fix What I can do is I can go back to my requirements file here and notice that I didn't do a make install So that's one problem so let's go ahead and do a make install。

And this should put everything inside my project。Oh。Command exit。Not sure。Oh。

 I know what the problem is。This one doesn't， I think it doesn't like this library。

 which we can get rid of。The black library。I believe might be the issue。Let's try it again。Yeah。

 that's a formatting library that likes the newest versions of Python。

 so what I'm going to do is go to my make file here as well and maybe just get rid of the format step。

Here， we can just get rid of this step。 We don't need it。 it's a nice to have。

 and then I also can go to Gitthub actions here and we can change that out right So this is common too is like these are these are things where you can nothing's precious。

 whatever it is you're doing， you can tweak it and change it because we have all this protection and tests and everything it's easy to verify everything works。

 So if I say make tests， for example， everything works now。

 make links right so I have a good safety mechanism here to make these kind of changes。

 So what I'm going to do again is I'm going to test that out。

So we'll go through here and we'll say I Python。And I will say。From labels， import labels。

And I believe that there's an issue here。In that， it's using the wrong。

Not sure why it's not recognizing Bodo 3 here。There could just be a sometimes I Python has weird issues。

In in these environments。And so what I can do。Is just use the regular Python shell， which is fine。

 And I can just say from labels， import labels。And then I can just test this out so we know it is going to take a bucket and it's going to take a name and so I can just say bucket is equal to and we know that'll be Alfredo NoA was the name of the bucket。

And then the name would be equal to lion， let's go double check here， it would be lion。 JPg， so lion。

 JPg。Okay， and then I just need to pass in this function。 So we'll say results is equal to labels。

And bucket and name。And let's see what happens。There we go。It looks like。

There is some kind of an issue。Here， maybe I misspelled the name of the bucket。Potentially。😔。

Not sure why that。It has got an issue。Let's， let's go ahead and tryread this out actually。

 to make it even simpler， what I can do is。Is just run this as a script。Right， again。

 this is probably the easiest way to do it， which would be labels。And put in Alfredo N NoAA。

And then put in lion， got JPg， there we go， and if I run this， we can get these labels。So。

 there could be some。Weird issue here。That there's some kind of a bug here。

And I'm not sure if it's that I need to put in。Is it that？I don't think you needed to do that。

But yeah， I thought you just needed to put in this。This particular name。

itUnable to get object metadata from S3 or access permissions。Yes。

 something's weird about this in particular。Not sure， oh， because I never uploaded it。

 there we go that that's like something doesn't seem right here， so here we go。

That now it's able to detect it in it in a， this is the image。

 and so what I could do is I could just say。Print labels here。And run this。There we go。

 so in this case it doesn't， it doesn't seem。Like。It found any labels which， which is kind of weird。

 actually。嗯。And so what we could do is just tweak。Tweak this a little bit and let's look at the original script and see what it does。

In this case， it says for label and labels。It looks like this should work though。

So what I'm going to do is I've tested out the majority of this function here。

 let's go ahead and convert over to the Kalan tool version。

 so if I go through here and I say let's do the same thing I did before is we have this shang line。

So I can test out this thing， which is CV CLI。It lookss like it works。

 so it's going to ask me for the bucket and we'll say Alfredo Noah。

 and then the name of the image again is lion JPg。And it was able to give me these labels。

 so it needed to iterate over that object here so we can see that it found the name of the lion。

 the name was lion， the animal was mammal。 Now， let me show you how else we could use something like this as well。

 one of the things that we could do。Is one of the cool things about。

This particular cloud9 environment is you can copy things into an S3 bucket。 So let's say that I。

 I want to take this ti picture。

![](img/71c264a6710141840aa067974a03005d_12.png)

And let's just say that I put it into here， I can just drop it。um。



![](img/71c264a6710141840aa067974a03005d_14.png)

I can actually just throw this here like this。Right into this machine， notice that it's up there。

 so if I just go up one level。You should see this tiger。

 So what I can do is I can just copy into that directory this image so I can say AWS S3。Cp。

And copy this。Into this bucket。Alfredo NoA like this right so copy this in there so then I can run my community tool to detect it and this I think would be a very common。

Workflow that that you would probably do if you were building command line tools for doing computer vision。

There we go。 We uploaded it。 Let's go back。 let's double check that it exists。 If I refresh here。

 there should be a tiger as well。And there is， I believe， let's see。There we go。

 there's a lion and tiger。 So now lets let's run this code again。

 the one that goes through it it finds the bucket and then it does our click command line tool here。

And we'll say。Let's go into function by gridder。And let's do。Let's run it。 remember again。

 it says it accepts a bucket and a name so we can just pass it in this time so I can say bucket。

Is equal to Alfredo NoAah。And then the name is equal to， in this case， ti。Daad Jpeg。There we go。

 and now this one， let's look at the results of it。

And we can see that it found the label tiger with 99% confidence。

 Also it's confident that it's an animal animal， it's a mammal wildlife。

 So we use the same pattern again， the same pattern here is that you build out。

 kind of test out the function， get it working。Then put it into a Kamean tool and then start to build more complex things。

And in particular here。I can actually just get rid of that。The labels file here。

 I was just using that temporarily and we can say get status， we can add in these changes。

 which really didn't change anything in a material way。

 but let's go ahead and do these this just remove the black function， get add requirements。

So why would we care about this， what is the real problem that this is solving？

Adding changes is that a lot of times a Cammelan tool is the start of building something more complex and in particular the more complex piece could be not only do I want to build a chamean tool for this。

 but maybe I also want to do a trigger where I automatically detect things based on a trigger that I use with AWS Lambda。

So。In particular。One of the things that we can do is if I go， let's open up another terminal here。

Is I could keep going down this road。And go to AWS Lada。And what AW Lada does。

Which is very related to the kind of things we do is it allows me to build these kind of functions as well。

 So let's go ahead and say， you know， Marco。土威。And we'll change this to Python。3，8。And for yeah。

 let's make this real quick。So the the core concept is very similar to what we were just doing again。

 is as a function， It has some input， It does some stuff and it returns back。

 So I could actually just copy here the other file that I had。Which is。This one， hello。

 we could basically。We could basically build something like this， right？And so if I go back here。

 I can go to Lambda。And I can go to the code itself。

And I can just get rid of this and don't need this and I can just go through here and just process the event。

 the event is what gets passed into this function。And the way this works is I can say if events。

Is equal to if event name， let's just pass in a name here。Is equal to Marco。Return back， polo。

Or just return back no。Like this， so literally the same thing that that other command tool did would deploy it。

 I test it。I can do the same thing， I can just say。You know， name。Is Marco。And we'll do Marco here。

Invoke it。There we go。And look， we see that it was able to successfully。

Execute polo right so same kind of concept。 So why why did I bring this up is that we could do the same thing we did now with the computer vision technique as well。

 So let's go ahead and build one of those out real quick。

 If I say create function I can build out a computer vision function。

 So we'll just call this computer vision。呃。To为。And go through here and just say Python 38 sure that works and then for permissions I will need to have a role that will let me do privileged API calls and so I'm going to use one that I've had earlier here we go there's an admin role。

And really the only thing I need to do now is just kind of wire together enough code so that I can do the same thing that I did previously。

And what I can do here is I have an example of this in a computer vision repo that I believe I can just copy。

And。Grab， so I think it is。This。Not this one。Lambda S3 trigger， I believe。

 is the one I'm looking for。 Yeah， this is what I want。

 So basically what this code does and I'll check it into this repo is it has a label function that does。

 you know goes through finds the labels and then it has a handler。

Which again processes this event and what I do is I say for every record in the event。

 So every time something you know happens there's some kind of a trigger in S3。

 it'll go through and it'll run those labels for me。

 So this is a very common workflow that someone was set up with something like AW Lada。

 So to do that， and I'm going to go here， and I'm just going to copy this in。

And we'll put this into our repo。 so go back to this cloud project first to just。

Make sure that it's in here。 We'll just say touch。S3。呃， trigger。Lambda and all this。

 I'm not going to directly use it this way。 I'm just going to put it in in here， so that。

We have access to it。We'll say get status， get add。S3。There we go and commit this。

Adding S 3 Lambda trigger。So again， the advantage of building that came tool first is I got at working and it's pretty simple to test out that it works and it reduces a whole bunch of like cognitive load for me that to now build this lambda to build the Lada now much。

 much simpler， we just go here and I paste this in here and notice again。

 this is the part that grabs that does what I was doing before。

And then this is the particular piece that this is the Lambda handler right that goes through in it and it all it does is print out the labels。

 it could do more complex things if necessary， so if I go through here and I，Do this。

 we can say deploy。Now to run it， we'll need to do a couple things first。

 let's clean out the bucket so that。We can verify that what we're doing is actually working。

 so first let's just delete these things inside of here so we got this bucket done。

And then the next thing that I'm going to do。Is I'm going to go back to this code section here and I'm going to。

Do a trigger。Set up， so how do I set up a trigger？Well。

 the way you do this is I'm going to say latest configuration and go to triggers。And under trigger。

 I'll say add trigger。And all the trigger does is it's who gets to call it or who gets to invoke this function and if I go down here I can find an S3 event there it is S3 event and then I just need to tell it where to accept the trigger in this case the trigger will be this bucket called Alfredo NoA and I'll say every time I put something in there。

 go ahead and grab it out and do something with that event。And then we'll go ahead and say。Add this。

There we go perfect so we've got this thing enabled there we go this looks like it it's ready to go so really we're ready to test this thing out so how do I test that out it's actually that simple。

If I go here， I can just grab this tiger。And I'm going to upload it。There we go and we'll say upload。

This should immediately trigger this function， and so if we go back here and I say monitor。

I can see the logs。Here。And this will show me all of the logs that this thing does。

 There's a couple of ways to look at this。 I'm going to look at it in CloudWch logs。

And once it's working， we should see a print statement there we go， we can say this is my bucket。

 Alredonovaa， this is my key which is a tiger and it went through and it found out all that information so now we've got actually a event that just sits there and it waits for us to tell to do work which。

Is even more useful in some cases than that command line tool。And in particular。

 if we know that it's only doing the tiger， but let's add the lion， let's add this lion in here。

Which is。X， let's go back to this bucket and let's upload another， let's add the lion。Here we go。

We'll say upload ands it should be instantaneous。 if I go back to this cloudWch logs here。

 we should see that。Here's the lion。So refresh。

![](img/71c264a6710141840aa067974a03005d_16.png)

Or here here's a lion。 There we go。 There's a lion and I found on these labels。

 So this is now generically going to work with any kind of thing that I put in there it'll detect whatever label that I've got set up。

 So this this is really almost production ready for some maybe a company that wanted to do build a computer vision pipeline that labels the data before it goes into。

 let's say another part of a machine learning system。



![](img/71c264a6710141840aa067974a03005d_18.png)