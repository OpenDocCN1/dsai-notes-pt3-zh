# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P41：2_Python面向对象与类的应用（第二部分）.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/dafd4a623b7cae339ab51b1c7c69c71d_0.png)

Welcome back。So what we first want to do is we want to go and start looking at the structure of a method。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_2.png)

And then from there， we're going to go and break this down even further。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_4.png)

So here what we use to identify a method。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_6.png)

Is we have the key word deaf， which it means define。

 so we want to make sure that we're defining the method within the class。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_8.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_9.png)

And then what we want to give it is a name。That name in this case is multiply。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_11.png)

And if there are any variables that we want to include， we can go and put in x comma Y， in this case。

 we're going to pass in those two variables。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_13.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_14.png)

Then here I'm going to print multiply blank and blank。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_16.png)

Dot format， and I'm going to put a pass into the values of X and Y。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_18.png)

And then I'm going to go and put the results， and then here I'm returning。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_20.png)

Those results back to the method that actually called it。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_22.png)

So to create an object， the first thing we want to do is we need to give it a variable name。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_24.png)

As you see here， I said Ford is equal to car。 Ford is my variable。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_26.png)

And then car is what's going to call the constructor of a method。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_28.png)

And we'll kind of get into this in a little bit as we' get going。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_30.png)

So as you can see here， objects are handled a little bit different than variables because when we cut a variable For equaled Sam before。

 basically it pointed an address to in memory where the Samm was being stored。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_32.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_33.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_34.png)

And that's what Ford would hold。 In this case here， we've got an actual object。

 that object may contain multiple pieces of data， and those multiple pieces of data are going to be stored in a block of memory instead of just one memory location。

 And so here we're going to show where the first piece of memory data is being stored。

 and that address is going to be stored in the word forwardd。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_36.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_37.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_38.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_39.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_40.png)

For that variable。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_42.png)

Let's go ahead and zoom in and take a look。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_44.png)

So。Here we've got a special class of we're going to call it car。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_46.png)

Now I'm going to call this death。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_48.png)

Now there's two underscores here。And this is IN IT and then double underscores。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_50.png)

This right here will represent that you're creating a constructor in your class。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_52.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_53.png)

This constructor is a very useful process。 it's kind of like a map that outlines how an object is going to work。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_55.png)

And here we've got two variables that we're going to pass in year and speed。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_57.png)

Now， this thing called self is the object itself。 We're going to pass that object in。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_59.png)

And then from there we're going to be able to call that object and then look at the specific items for that object。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_61.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_62.png)

As you can see here， I said， self do year equals year。

 so the object that I pass in and I will show that here in a second。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_64.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_65.png)

Dot year。Is going to equal to the year that I am passing in。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_67.png)

Then self dot speed is equal to speed， again， grabbing the speed value from here。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_69.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_70.png)

Now， as I mentioned earlier， we have getters and setters because if we use default settings and let's say that the we needed to change a year on a vehicle or something like that would be a little bit difficult。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_72.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_73.png)

So we want to be able to go in and modify or change values if needed。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_75.png)

So we do de， get speed， passing south， and anytime you use the word get。

 it's always going to mean you're passing something in。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_77.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_78.png)

Okay。Here I'm going to print speed， and it's going to give me that speed。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_80.png)

If I want to set the speed。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_82.png)

Here I'm doing set。Set speed， notice Im passing the object in again。

 and then the variable value that I want for that speed。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_84.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_85.png)

And then I set that object dot speed to equal that value。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_87.png)

If I want to get year。I can go and print year， and then I'm going to print the year of that object。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_89.png)

We're going to go and do depth set year past the object back end。

 we're going to set the value of the year that we want。

 and then we're going to assign it to that object。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_91.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_92.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_93.png)

As you can see here， Ford equals car。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_95.png)

2021。And then 130 is the max speed。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_97.png)

As soon as I do this， what happens is this method card or class card gets called。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_99.png)

So it goes all the way up here， it says， okay， now I'm up here。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_101.png)

I'm looking for a constructor in this class。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_103.png)

Then I can go and pass in the parameters of two values and it looks down and says， okay， oh。

 there it is， there's year， there's speed， I'm going to put the year and speed in。

 now this object that I'm creating called For is going to be store that value。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_105.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_106.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_107.png)

I created another object called Chevy。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_109.png)

Car， I pass in or 2019 and 110。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_111.png)

Again。It goes up here， look for the constructor， creates it， and sets it up。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_113.png)

Now， if I do。F dot get speed。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_115.png)

The function here will return the value of 130。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_117.png)

Shay dog get speed。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_119.png)

Now its speed is 110。As I look here， I do four dots set speed and I'm changing the speed from the original speed of 130 to 120。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_121.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_122.png)

As soon as I do that， what that does is it passes the object in for set speed。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_124.png)

And it passes in the new value that I've inserted。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_126.png)

And now it reassigns that value， too。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_128.png)

The Ford object。Now when I come down here to get speed， it prints out this current speed is 120。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_130.png)

So at this point， what I want to do is I want to go ahead and break down this a little bit more for you guys。

 So a nonmet data stored basically by an object is called an attribute。

 We have two different types of attributes。 We have basically a data to attribute which basically is a variable owned by a particular instance of a class Each instances has its own value for it and then therefore these are the most common kinds of attributes。

 Then we have what they refer to as a class attribute which is owned by the class as a whole。

 So therefore all class instances share the same value for it and these are called static variables。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_132.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_133.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_134.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_135.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_136.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_137.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_138.png)

And so as you can see here in the previous example that we looked at。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_140.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_141.png)

I did not declare。Any variables up here underneath the class car？



![](img/dafd4a623b7cae339ab51b1c7c69c71d_143.png)

But here， I have。To find class attributes of name， account number and balance。

 and this allows me to use these variables anywhere within this class。

 and that's the difference between them。 And what I'm going do is I'm going to go and go to the next program and we'll break this down a little bit more and give you some good example。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_145.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_146.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_147.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_148.png)

This is a bank account example of a program。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_150.png)

And so here what I've done is。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_152.png)

I have a name， an account number， and a balance。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_154.png)

Now。One of the things that you'll find in programming is that， as I said earlier。

 is that you may want to overload a method， and I said that Python really does not have a way to directly overload a method。

 but there is a workaround for that process。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_156.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_157.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_158.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_159.png)

And the way to do this is this。Here I have a method。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_161.png)

That I want to pass in no parameters。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_163.png)

And so if I did it this way by doing death， underscore， underscore， I N IT， underscore。

 underscore self， meaning I'm passing the object。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_165.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_166.png)

And then just did self dot name， unknown， self dot account number1，2，34， and self dot balance zero。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_168.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_169.png)

This is a common practice in other languages， and they you have a second method of or a second constructor。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_171.png)

As the example here， de， underscore underscore IN IT underscore underscore here now I'm passing in the variable name。

 account number， and also balance。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_173.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_174.png)

And then assigning those values to each one of those。 This is a very known process。

 and unfortunately， or fortunate， would opinion how you want to look at it。

 Python does not allow this to occur。 So to get around this。

 what I do or what the most common practices is that you would do de， underscore。

 underscore I and IT， underscore， underscore self。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_176.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_177.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_178.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_179.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_180.png)

And then this asterisk args。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_182.png)

And you can name it something else， it doesn't have to necessarily be the wordRs。

 but I refer to as arguments。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_184.png)

It's basically an array that you're setting up of objects being passed in。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_186.png)

So here what I'm saying is if the length of my arguments is less than three。

 meaning that I'm looking for three different elements。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_188.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_189.png)

If I don't get those three， then I'm going to set the default values of name is unknown。

 account number is 1，2，3，4 and the balance is 0。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_191.png)

Otherwise， I'm going to set the name to the argument starting to index 0。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_193.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_194.png)

Account number is my index 1 and then balances index 2。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_196.png)

And then again， we create our setters and getters， you can see get name， get account number。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_198.png)

Get balance， each one of these are returning self dot name， self dot account number， self do balance。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_200.png)

Then we also have our setters so if we need to change or modify something。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_202.png)

We do self underscore or I'm sorry self comma name。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_204.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_205.png)

Self comma balance。 self comma account number。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_207.png)

And then here I've got deposit。This is another method that I want to keep track of the deposit that's being put into the account。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_209.png)

So therefore， it's going to behave the balance。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_211.png)

So self do ballot， and I do the plus minus because if I'm doing a deposit。

 I'm going to add money to it， if I'm doing a withdrawal I'm going to take money out。

 and so therefore you see the plus equals and the minus equals。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_213.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_214.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_215.png)

And then last。I want to print this out so I can do a two string self。

 pass the object in and then print out each one of the different elements。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_217.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_218.png)

And so。First thing Im want to do is I'm going to create Bob new account number。

 I'm just going to do the default settings。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_220.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_221.png)

And then we create another object called T。Pass in Tm's name。

 the account number and the current balance。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_223.png)

As I print out to the string， I'm going to get the name， which in this case was unknown。For Bob。

I'm going to get the default setting for。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_225.png)

The account number， which is 1，2，3，4。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_227.png)

And then I'm going to get the balance， which is zero。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_229.png)

When I do the two string41。

![](img/dafd4a623b7cae339ab51b1c7c69c71d_231.png)

Notice I'm getting Tim's name here， I'm also getting his account number and the current balance。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_233.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_234.png)

So what I'd like to do here is go and stop and then I'm going to go and go right into a demo of creating a live version of an example and the example we're going to look at is creating an employee。



![](img/dafd4a623b7cae339ab51b1c7c69c71d_236.png)

![](img/dafd4a623b7cae339ab51b1c7c69c71d_237.png)