# 密歇根大学《Python3编程（课程3、4、5）》｜Python 3 Programming（Python for everyone进阶）（中英字幕） - P113：05_01_02_转换类图.zh_en - GPT中英字幕课程资源 - BV1gj41177yd

![](img/eadbec09f012758db16ea3bff71c7331_0.png)

Now that we have some basic classes， we can begin to actually write the Python code behind them。 Now。

 you've done this before， but here we're going to go sequentially and create each class based on the name it's been given in our diagram and initialize attributes to have some default values。

As I go through and do this， I'm going to document my code following the Google Python style guide。

 Now， you don't have to use this format， but it's pretty commonly used and it makes for nice clean code。

It also enables development environments like Jupiter to help you a bit by reminding you what a class attribute or function might mean。

The main form of the documentation in this style guide is a triple quoted string。

 here's an example with the adventurer。So note that by convention classes start with a capital letter in Python。

 then we follow that with a triple quoted string， the first sentence of the string describes the class concisely and that's this one here represents the user in our game a fearless adventure。

Then we add any more details that we might want， and this can be as many paragraphs as you want it to be。

Finally， we end with a section called attributes， and this lists the name and details of each data attribute that we expect to be in the class。

 So here Im saying name， the display name for the character。

 dexterity here I've just decided that it's going to be on a scale of1 to 18 and so forth。

We do not put anything about the functions or methods in this documentation block All right。

 let's execute that。Now we've created an adventure class。

 and this means that we can instantiate this class to create adventure objects。

But the objects don't have anything in them， except documentation。

 So let's create the init function for the adventurer。

 which sets the default values for those different attributes。Remember that in Python。

 you don't have to declare your object level attributes ahead of time if you don't want to。

 but it's pretty common practice to initialize them in the init function。

 as well as to document them in the class doc string， just as I did。In this specific case。

 I'm going to require that a name be provided to be initialized for an adventure。

 everything else is going to come up with sensible defaults。In this specific case。

 I'm going to require that a name be provided to initialize an adventurer， but for everything else。

 I'm just going to come up with some sensible defaults。 So for those defaults。

 I'm actually going to import random。 I'm going to use some random numbers here。

You'll see that the definition of the adventurer class starts just as it did before。

 and I've pulled in all of the documentation from before。Just like our class definition。

 each method or function associated with a class should have a triple quoted strain that describes it and the arguments it takes。

For methods， the first argument is always self。 that's a reference to the object being called。

 and we don't include that in the Args list。 So here I've said the constructor and that's our double underscore。

 so our Dunder in it Dunder is going to take self so it's a constructor method object and then is also going to take a name which is string and then this dash arrow remember is just type painting indicating what's being returned from this and the return is none。

Here， I've just indicated that this is going to initialize the adventure with a name and some random stats。

 And then just like with the class， I've indicated what the arguments here are。

 So it's a name and some friendly text description。

 Then maybe another developer would like to see the name of the adventurer。Now， in my actual code。

 I want to set the name to whatever the color is passed in。 Remember。

 our field and our argument can actually be the exact same as is this case。 They're both called name。

 So we distinguish between these by using self dot name to refer to the object attribute field。

 And this is pretty common。 So get used to seeing it。 So here I'm saying self dot name。

 which is of type string， is going to be equal to the argument that's passed in called name。

I'm also going to create some default values for constitution and strength。

 I'm just going to make these random integers between3 and 18。

And then here I'm actually going to set our hit points of the character to beat our Constitution plus some random offset。

 so that's just me deciding on that， and then I'm going to create a bag for the adventurer too。

 and it's a list of items okay， let's execute that。Okay， we've created our adventure class now。

 as you can see， the process of taking the UML class diagram that we created in the previous lecture and converting it into a class in Python is relatively straightforward。

I personally really liked diagramming and drawing out my ideas on a whiteboard before writing any code。

 It helps me quickly iterate on the main concepts I want to include in my software。

 and it helps me find hidden relationships that I initially didn't expect。😊。

But something is kind of odd about this adventurer class。 We don't have an item defined yet。

 but I was able to execute that cell in Jupiter。 So let me ask you。

 why didn't I get an error when I executed that last cell。Okay， well。

 remember that when we execute a cell in Jupiter， the contents of that cell are sent to the Python interpreter。

 Since this is done within a class definition， nothing inside of the class has actually been instantiated yet。

That is， we have an adventure or class， but we don't have any adventure objects。

 If we tried to create a new adventure， That's when Python would actually execute the code that we've written。

Okay， so let's actually test this。 let's actually instantiate a new adventure。

 So here I'm just going to say adventure is equal to adventure and I have to pass in a name。

 so I'm going to call this adventure， of course， Sir Christopher。Okay。

 now we've actually created an adventure object， but we still didn't get an error thrown。Why。

In this case， we just referred to the item class in a type annotation。

 We're telling the Python development environment that this bag associated with Sir Christopher is going to be a list of item objects。

 but the list is empty。 We haven't actually created any item objects。

This is how Python is very different than many other programming languages。

 The type annotations are often called type hints， and they're really just there for development tools and are ignored by the Python interpreter itself。

If you've forgotten some of these concepts， type hints， objects。

 classes and initialization functions， please don't hesitate to go back to the previous courses to review those videos。

All right， let's get to it， let's create the item class。Okay， so I create the class the same way。

 triple quoted string here， class item， I give it one sentence at the top。

 an item which is going to be held by an adventurer。

 and then I can have any number of paragraphs here that describe this。I also set the attributes。

 remember of our class and this is just documentation。

 it doesn't enforce anything but it's telling developers which includes yourself in the future what you're expecting to see for this object。

 so an item should have a name， a min damage and a max damage。

I create the constructor here I'm going to pass in the name， the min damage， the max damage。

 and I'm going to return none。And for the adventure class。

 we didn't actually do any input error checking， but frankly we probably should。

 so I'm going to do a little bit of that here for items。

 if the user passes in an item without a name， I'm going to set it to unknown。

 So that's just a quick， simple little check， but you really should have these for all of the different parameters that come in。

Then I'm going to assume the minimum and maximum damage here are being passed correctly and remember。

 you don't have to return at the end of a function or a method if it's nothing to return if you just return none。

 that can be done automatically by Python Let's execute this。

We now have a class for the adventure and any item objects we want them to hold。Now。

 we have a few more classes that need to be created。

 one for the monster that an adventurer might run into and then one for the cave system which contains a list of room objects which each have monsters and items in them。

I think you probably have enough knowledge now to create these yourself。 So here's my recommendation。

 Open up a new Jupiter notebook book and try and create these three classes。

 You can then compare them to my solution towards the end of this module。In the next lecture though。

 I want to show you how to capture the interactions between classes through diagraming techniques。

 I'll see you there。

![](img/eadbec09f012758db16ea3bff71c7331_2.png)