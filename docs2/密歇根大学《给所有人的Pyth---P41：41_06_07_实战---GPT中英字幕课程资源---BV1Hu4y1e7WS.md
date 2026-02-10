# 密歇根大学《给所有人的Python课》课程3：《使用Python访问Web数据》｜python-network-data｜ - P41：41_06_07_实战示例_OpenStreetMap_API.zh_en - GPT中英字幕课程资源 - BV1Hu4y1e7WS

Hello and welcome to yet another code walkthrough for Python for everybody in this walkthrough。

 we're going to play with geocoding， which is really taking a text version of an address and turning it into a well known to a location。

 And we see this all the time on map applications。 This map applications that I'm using is called opentet map。

 It's an open source， openly maintained。 It's a wonderful organization that gives us an alternative to the commercial map companies like Google map who。

😊，Play games with all of us， so I'm a big fan of open source， big fan of open data resources。

And so I'm going to search for a place。 one of my favorite restaurants in the whole world。

 And so I'm using a text address。 I'm like， where is this thing。😊。

And so it found to me and found all their sad and we see things like the the GPS coordinates or the coordinates of latitude longitude coordinates here。

 and there is one of my favorite restaurants in the world。 And so the act of going from a text。

Address to a location is called geocoding。 It's a super common kind of thing。

 So we've got a bit of sample code here， and I am going to edit this code。 this。

 you can get it from ww Wp free dot com slash code 3， Open Geo dot P Y and save it to some location。

 so you can edit and play with this bit of code。 So I've got it right here。

 I'm actually editing the master copy。 It's in Github。 So I will be able to fix it。

 So don't worry about that。

![](img/19396e8d60b639907705d687efa06b79_1.png)

![](img/19396e8d60b639907705d687efa06b79_2.png)

![](img/19396e8d60b639907705d687efa06b79_3.png)

![](img/19396e8d60b639907705d687efa06b79_4.png)

![](img/19396e8d60b639907705d687efa06b79_5.png)

So let's let's do a bit of walk through the API that we're going to be doing is a thing called geo APIpi。

 and it's a company。 and they take that openstreet map data and they make it available to us in this geocoding API。

 for example， This is the thing that we're going to be doing。

 And so you can see that the idea of geocoding is you take a text， like I've said， a text address。

 can theres there's all kinds of stuff you can play with it。

 you can play they give these free playgrounds。 And so if you look at this。

 this is not not exactly free， there is a free level of it right。

 And so you still have to go get an API key。 And if you start using it more and more。

 you got to pay money and it gets pretty high。 So this is 250000。



![](img/19396e8d60b639907705d687efa06b79_7.png)

![](img/19396e8d60b639907705d687efa06b79_8.png)

Whatevers 600 bucks a month。So that's where the real API is， but if you take a look at the code。

 were not going to hit that API because otherwise you'd have to sign up for account。

 although it'd be good exercise， you could definitely use their their official API endpoint if you signed up for an account。

 but I have given you what I call a heavily rate limited proxy of that。

And it means that I've got a copy of it， I've got a database where I cache the most commonly used things。

 and I use Cloudflare and we talked about that in the lecture。

And it's also super heavily rate limited， which means it slows you down to a crawl if you overuse it。

 the rate limit is designed to allow you to get what you need done for this class。

 but not more okay so the prefix for this is Hpy free data Drchuck。

net Opengequest mark and then afterwards you put a Q equals query parameter and so I've got this and you see the Q equals this is just you know URLs and HttP。



![](img/19396e8d60b639907705d687efa06b79_10.png)

![](img/19396e8d60b639907705d687efa06b79_11.png)

The plus in that is the space， this is called URL encoding and the percent2 C is URL encoded comma because you can't just put a comma there。

 you actually have to take the comma and encode it。 But if we click on this click， you will get。



![](img/19396e8d60b639907705d687efa06b79_13.png)

![](img/19396e8d60b639907705d687efa06b79_14.png)

![](img/19396e8d60b639907705d687efa06b79_15.png)

Some Python some some JSson right and just like we talked about in the lecture and so in there is all kinds of stuff right it's a feature collection which means it's an array named features and then you got the country we've got the latitude longitude which we're going to go after and then we're going to look at this formatted address Okay so that's you can test this in the browser without a key。



![](img/19396e8d60b639907705d687efa06b79_17.png)

![](img/19396e8d60b639907705d687efa06b79_18.png)

![](img/19396e8d60b639907705d687efa06b79_19.png)

![](img/19396e8d60b639907705d687efa06b79_20.png)

![](img/19396e8d60b639907705d687efa06b79_21.png)

And so we're going to retrieve this。 Now there's this little bit of stuff that we've got to do。

 just don't worry too much about this。 and that is。



![](img/19396e8d60b639907705d687efa06b79_23.png)

![](img/19396e8d60b639907705d687efa06b79_24.png)

![](img/19396e8d60b639907705d687efa06b79_25.png)

This URL open wants to check sometimes the certificates of the HTPS and we want to tell it that we're going to take data even though the certificate may not be well known by Python。



![](img/19396e8d60b639907705d687efa06b79_27.png)

![](img/19396e8d60b639907705d687efa06b79_28.png)

![](img/19396e8d60b639907705d687efa06b79_29.png)

And that's because Python last eye checked doesn't ship with a ton of well known certificates。

 had do， it's a long story。

![](img/19396e8d60b639907705d687efa06b79_31.png)

![](img/19396e8d60b639907705d687efa06b79_32.png)

So just here's some code for you。 This is basically saying we're not going to verify the certificate。

 Now if we look at the certificate of this， you can actually see that this is a secure verified and and it's a cloudflare certificate and and here's some more information about it blah。

 blah， blah blah， blah， blah， and so。

![](img/19396e8d60b639907705d687efa06b79_34.png)

![](img/19396e8d60b639907705d687efa06b79_35.png)

![](img/19396e8d60b639907705d687efa06b79_36.png)

What we're saying is we're telling Python not to look too closely at this stuff。

And because we're just reading it， I mean。

![](img/19396e8d60b639907705d687efa06b79_38.png)

You probably would want to solve this if you were doing production。 but for us。

 this is just the quick way we do it。 Okay， so I make a big while loop， and I ask for a location。

 if I just press enter， it's going to break and I strip it。



![](img/19396e8d60b639907705d687efa06b79_40.png)

![](img/19396e8d60b639907705d687efa06b79_41.png)

![](img/19396e8d60b639907705d687efa06b79_42.png)

And then I created a dictionary in order to do this Q equals thing， right。

 this little Q equals thing。 Now I could sort of change the space to a plus。

 I could change the comma to a percent2 C， or I could call a library called URL parsy or and code Farms。

 which takes a key value pair in a dictionary， So Q equals address。

 and that does all the fancy stuff， So I print it。

![](img/19396e8d60b639907705d687efa06b79_44.png)

![](img/19396e8d60b639907705d687efa06b79_45.png)

![](img/19396e8d60b639907705d687efa06b79_46.png)

![](img/19396e8d60b639907705d687efa06b79_47.png)

And then I use URL of request open with that URL context equals CTX， ignore any certificate problems。



![](img/19396e8d60b639907705d687efa06b79_49.png)

![](img/19396e8d60b639907705d687efa06b79_50.png)

And then read the data from the URL。 Now， if we look at the raw data。 only retrieve this again。

 if you look at the raw data， this is actually what it looks like。 Okay， it's very compact and dense。

 doesn't have a lot of spaces。 Pre printing， as we well know， says， oh， let's throw some spaces in。

 so at least we can figure out what's going on。 And then there's this Json viewer。

 which is not really what's coming back， but you can show and hide things in this Json viewer。



![](img/19396e8d60b639907705d687efa06b79_52.png)

![](img/19396e8d60b639907705d687efa06b79_53.png)

![](img/19396e8d60b639907705d687efa06b79_54.png)

![](img/19396e8d60b639907705d687efa06b79_55.png)

![](img/19396e8d60b639907705d687efa06b79_56.png)

![](img/19396e8d60b639907705d687efa06b79_57.png)

That's okay， I guess， but。I like to。

![](img/19396e8d60b639907705d687efa06b79_59.png)

I like to see the raw data。 I do like it pretty printed。 So in this particular browser。

 which I'm using as Firefox， there's a when it sees Json。

 it gives you some options as to what is supposed to work now。



![](img/19396e8d60b639907705d687efa06b79_61.png)

![](img/19396e8d60b639907705d687efa06b79_62.png)

![](img/19396e8d60b639907705d687efa06b79_63.png)

This decode we've talked about this before， the data on the web that we just got。

 this data is in UTF8。

![](img/19396e8d60b639907705d687efa06b79_65.png)

And that's because， you know， there there could be all kinds of characters in here that are not simple ASI characters。

 So the web pretty much uses UTF8。 So when we get a read。



![](img/19396e8d60b639907705d687efa06b79_67.png)

That is UTF 8， right， We've read data from the Internet， and it's a UTF 8 data decode。



![](img/19396e8d60b639907705d687efa06b79_69.png)

Says， okay， look at it。 make sure it's UTFA and then give it back to me in the form of a Python string data。

 which is Uniode。 And so Unicode is not the same as UTFA。

 Unicode is how we manipulate things inside Python。 So by making everything Python。

 Everything Uniode in Python。 It all works inside Python。

 You can encode it and decode it when you move it out and back in。 so。



![](img/19396e8d60b639907705d687efa06b79_71.png)

![](img/19396e8d60b639907705d687efa06b79_72.png)

Then we say how many characters we got and then we parse it， so JO Lodes is a parse and might fail。

 and then we look for sort of a sanity check to make sure if features the features thing is and there's that looking for this thing。

 like just checking if it exists。

![](img/19396e8d60b639907705d687efa06b79_74.png)

![](img/19396e8d60b639907705d687efa06b79_75.png)

![](img/19396e8d60b639907705d687efa06b79_76.png)

And if there's if you look at features， features is an array， and so for sanity， we also say， hey。



![](img/19396e8d60b639907705d687efa06b79_78.png)

![](img/19396e8d60b639907705d687efa06b79_79.png)

We only got one back。 Now， in this I Arbor example， it's going to work。 But if you put something in。

 you might want it。 this sanity checking may or may not sort of work。



![](img/19396e8d60b639907705d687efa06b79_81.png)

![](img/19396e8d60b639907705d687efa06b79_82.png)

So what I'm going to do。

![](img/19396e8d60b639907705d687efa06b79_84.png)

Is well， let's just run it。

![](img/19396e8d60b639907705d687efa06b79_86.png)

I'm not I'll just run it without uncommenting anything， so let's come back here。



![](img/19396e8d60b639907705d687efa06b79_88.png)

And I'm going to say Python Open geo dot pi。

![](img/19396e8d60b639907705d687efa06b79_90.png)

And I'm going to type an aor。

![](img/19396e8d60b639907705d687efa06b79_92.png)

Michigan。So it's retrieving it。

![](img/19396e8d60b639907705d687efa06b79_94.png)

Oh， I mistypeped it， so you seem you see the。

![](img/19396e8d60b639907705d687efa06b79_96.png)

You see the。Rate limiting in in action。 So it figured out that I had typo and it went and found Ann Arbor。

 Michigan and found the real place， right， And that's part of what you do。 This。

 this geocoding is kind of a search engine。 I made a mistake。 Now。

 you'll notice it's a lot quicker if I type it， right。



![](img/19396e8d60b639907705d687efa06b79_98.png)

![](img/19396e8d60b639907705d687efa06b79_99.png)

Cause it already has it。 And so it rate limits things see how fast that was。

 that the proxy's working。 So in that first one， when I typed it wrong。

 the proxy was actively slowing you down and I'm like， my code's broken。

 but it was actively slowing me down because it was mad at me because I was asking for too many things。



![](img/19396e8d60b639907705d687efa06b79_101.png)

![](img/19396e8d60b639907705d687efa06b79_102.png)

![](img/19396e8d60b639907705d687efa06b79_103.png)

![](img/19396e8d60b639907705d687efa06b79_104.png)

And but then it doesn't rate limit you on things that it already has。

 which are cheap for it because it's all very well proxy， but we retrieve the data。

 we got 1319 characters。 we figured out parse the latitude and the longitude。

 see we print that out and then we got the location right And so and so now let's。



![](img/19396e8d60b639907705d687efa06b79_106.png)

![](img/19396e8d60b639907705d687efa06b79_107.png)

![](img/19396e8d60b639907705d687efa06b79_108.png)

![](img/19396e8d60b639907705d687efa06b79_109.png)

![](img/19396e8d60b639907705d687efa06b79_110.png)

I can't think of a better way to describescribe it。 We're just going to delete a bunch of work code。



![](img/19396e8d60b639907705d687efa06b79_112.png)

I'm going to delete this。 I'm going to delete this。



![](img/19396e8d60b639907705d687efa06b79_114.png)

And I'm going to say。Lat equals 42。 Law equals 42， and location。



![](img/19396e8d60b639907705d687efa06b79_116.png)

Equals。

![](img/19396e8d60b639907705d687efa06b79_118.png)

Jerk pit。So now what I did is I had all that code that was looked really cool is gone now。

 So if I run it again。

![](img/19396e8d60b639907705d687efa06b79_120.png)

![](img/19396e8d60b639907705d687efa06b79_121.png)

I can say Ann Arbor。

![](img/19396e8d60b639907705d687efa06b79_123.png)

Michigan。Oops。Oh， see， you got a download error。 I It was like， I don't know what that is。

 So it was unhappy， but you'll notice this download error code checked because I was typing in cursors and keys and weird things and it was not happy。

So let's do it again。

![](img/19396e8d60b639907705d687efa06b79_125.png)

I wondered what would trigger that in this。So now you see we're running。



![](img/19396e8d60b639907705d687efa06b79_127.png)

But we are not looking at the latitude and the longitude， so let me show you how I build this code。

 So the first thing I'm going to do is I'm just going to print this stuff。



![](img/19396e8d60b639907705d687efa06b79_129.png)

![](img/19396e8d60b639907705d687efa06b79_130.png)

And so we're going to see it。

![](img/19396e8d60b639907705d687efa06b79_132.png)

And so now this is that same data that we saw in the browser， right？

And so what I want out of this data， and it takes a while to figure it out is I want this la and this lawn value。

 okay？And I can kind of guess what this is， but I'll show you how I work through it。

 So I look at this and I say， okay， the outer thing that I want is features so that this is an outer object。

 a outer dictionary basically。Features。 and so I'm going to that's in this variable JS。 that's a。

 that's object。 that's a dictionary variable。 So if I say print。



![](img/19396e8d60b639907705d687efa06b79_134.png)

![](img/19396e8d60b639907705d687efa06b79_135.png)

![](img/19396e8d60b639907705d687efa06b79_136.png)

JS sub。Features。

![](img/19396e8d60b639907705d687efa06b79_138.png)

So what I'm doing is I I'm tom。

![](img/19396e8d60b639907705d687efa06b79_140.png)

Comment this part out。And we're going to indent that。



![](img/19396e8d60b639907705d687efa06b79_142.png)

I got a bit close curly brace there， comm indent。

![](img/19396e8d60b639907705d687efa06b79_144.png)

Equals 4。So what I'm going to do is I'm going to work out in， so originally I'm going to dumping JS。

 and I'm going to dump JS so features， and so I'm going to save that。



![](img/19396e8d60b639907705d687efa06b79_146.png)

![](img/19396e8d60b639907705d687efa06b79_147.png)

And I'm going to。

![](img/19396e8d60b639907705d687efa06b79_149.png)

I got to keep running it。Oh yeah， because I。I didn't type it correct。



![](img/19396e8d60b639907705d687efa06b79_151.png)

Do be do， be do。Go an extra parenthesesis。

![](img/19396e8d60b639907705d687efa06b79_153.png)

And I put a semicon in because I've written too much Java and JavaScript in my life and I can't help it。



![](img/19396e8d60b639907705d687efa06b79_155.png)

![](img/19396e8d60b639907705d687efa06b79_156.png)

![](img/19396e8d60b639907705d687efa06b79_157.png)

Oh， I' got to add the Json D bass， here we go。

![](img/19396e8d60b639907705d687efa06b79_159.png)

![](img/19396e8d60b639907705d687efa06b79_160.png)

I should just copy that previous line。

![](img/19396e8d60b639907705d687efa06b79_162.png)

So now I got to dig in one level， and then I just got a pretty printed。

 So that's Json Dumpest with index with an indent of4。



![](img/19396e8d60b639907705d687efa06b79_164.png)

![](img/19396e8d60b639907705d687efa06b79_165.png)

![](img/19396e8d60b639907705d687efa06b79_166.png)

Okay， so now what you see， it seems subtle， but I win in and now the only thing I'm seeing is the array。

Okay， so in this array。Okay。

![](img/19396e8d60b639907705d687efa06b79_168.png)

There's the0 with object or the 0 with dictionary in this array。

 So now what I'm going to do is I'm going to make a tiny change here because the thing that came back from J S sub features is an array。

 And I'm going to grab the first item in that array。

 So what you're going to notice next time is we're going this is going to be the outer bit because we went into this array。

 sub 0。

![](img/19396e8d60b639907705d687efa06b79_170.png)

![](img/19396e8d60b639907705d687efa06b79_171.png)

![](img/19396e8d60b639907705d687efa06b79_172.png)

Okay， so you see the outer thing is now a dictionary。And it is of type feature。 I mean。

 one of the keys is type and one of the keys is properties。 Now we want the stuff inside properties。

 So what we're printing here。

![](img/19396e8d60b639907705d687efa06b79_174.png)

That we want to go into the key within that dictionary， so we have a dictionary。



![](img/19396e8d60b639907705d687efa06b79_176.png)

But we have an array， sub 0， which returns a dictionary。

 and now we're going to get the sub propertiesties。 And this seemed kind of slow。



![](img/19396e8d60b639907705d687efa06b79_178.png)

But it is。

![](img/19396e8d60b639907705d687efa06b79_180.png)

Going to finish。Okay， so now what we have is we have。A dictionary。

The La lung string now is a dictionary， let me move this over。That long string is a dictionary。

 and within that dictionary， there is a lawn。And a la。 So now just for testing， I'm going to say。



![](img/19396e8d60b639907705d687efa06b79_182.png)

Look up in that dictionary。

![](img/19396e8d60b639907705d687efa06b79_184.png)

Alan。So I'm going to run it again now。

![](img/19396e8d60b639907705d687efa06b79_186.png)

So now we see that the actual thing we retrieved using this。



![](img/19396e8d60b639907705d687efa06b79_188.png)

Whole thing was the number that is the longitude。 and so now what I'm going to do。

 I've gotten this far。

![](img/19396e8d60b639907705d687efa06b79_190.png)

And now what I'm going to do is instead of the longitude being 42。

That's what the lawn is going to look up， right， And， you know， we can pretty much。

Say that the la is going to be the la。

![](img/19396e8d60b639907705d687efa06b79_192.png)

So we're going to now， I think， be able to look up lawn and la。



![](img/19396e8d60b639907705d687efa06b79_194.png)

![](img/19396e8d60b639907705d687efa06b79_195.png)

So now the Latin long are correct。

![](img/19396e8d60b639907705d687efa06b79_197.png)

UmOh， now I kind of forgot。So I'm going to take this off the print statement。



![](img/19396e8d60b639907705d687efa06b79_199.png)

The debug print。And run it again。Okay， so we found the la in the lawn。 now I went up now。

 so I'm not printing long and la。Okay， that's easy。 It's just formatted。

 The key inside the properties is formatted。 So now what I can do is I can find the location。



![](img/19396e8d60b639907705d687efa06b79_201.png)

By grabbing this。

![](img/19396e8d60b639907705d687efa06b79_203.png)

And just look up format it。

![](img/19396e8d60b639907705d687efa06b79_205.png)

So I'll just comment this a little bit out temporarily。



![](img/19396e8d60b639907705d687efa06b79_207.png)

And。Oops。I just hit control C。And Arbor。

![](img/19396e8d60b639907705d687efa06b79_209.png)

Michigan。So now I'm getting the formatted address， I'm getting the latitude。

 and I'm getting the longitude。

![](img/19396e8d60b639907705d687efa06b79_211.png)

And so when we started， I had code that pretty much looked like this。

 It was a little bit different order， and you saw me sort of successively dig hierarchically into this。



![](img/19396e8d60b639907705d687efa06b79_213.png)

![](img/19396e8d60b639907705d687efa06b79_214.png)

Now if you know， it's like， okay， here we go， it's an outer dictionary sub features， it's an array。

 sub zero features sub zero， and then sub propertiesties， subla。 Now you might just figure that out。



![](img/19396e8d60b639907705d687efa06b79_216.png)

And immediately derive this long thing。

![](img/19396e8d60b639907705d687efa06b79_218.png)

I'll just say that every time I try to do that， I miss it up one tiny little mistake。

 And let's just say let's just say you missed on this。 I'll just make a mistake here。

 So you just said， oh， I got that first entry and features。 and I'm just going to go into that。



![](img/19396e8d60b639907705d687efa06b79_220.png)

![](img/19396e8d60b639907705d687efa06b79_221.png)

![](img/19396e8d60b639907705d687efa06b79_222.png)

So that means that you're going to go straight into La and you're going to see what happens then。



![](img/19396e8d60b639907705d687efa06b79_224.png)

![](img/19396e8d60b639907705d687efa06b79_225.png)

Boom， so what's saying is there is no key lat， and that's because you're in Js feature sub0 subla。



![](img/19396e8d60b639907705d687efa06b79_227.png)

![](img/19396e8d60b639907705d687efa06b79_228.png)

And again， it's easy because I made the mistake I knew it So the zero， this is the sub0。

 and I thought that La was in this object， but it's not you have to go in into one more dictionary deep in the properties dictionary than you can go to La。

 And that's why this one works because I kind of dive into the properties Now I think I can get that back to save me some time。



![](img/19396e8d60b639907705d687efa06b79_230.png)

![](img/19396e8d60b639907705d687efa06b79_231.png)

![](img/19396e8d60b639907705d687efa06b79_232.png)

![](img/19396e8d60b639907705d687efa06b79_233.png)

And now it should work again。

![](img/19396e8d60b639907705d687efa06b79_235.png)

![](img/19396e8d60b639907705d687efa06b79_236.png)

Okay， so we're working so。I hope you found this interesting geocoding is just fun later in the course we will make a map and do kind of a batch geocoding。

 use a database， etc， and then make a map and that's kind of cool and you can place yourself on the map or a place you know on the map。

 so I hope you enjoyed this cheers。

![](img/19396e8d60b639907705d687efa06b79_238.png)

🎼。