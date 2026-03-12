# 【全集】斯坦福大学-并行计算导论-CME213-中英字幕-1080P-p05-Lecture-5---OpenMP-2--BV1f8ijBYEjR_p5-

都给出的。Let's start。Okay， so we're going to continue be open the lecture today， so sort of trying to。

Today， maybe it is。Long lecture we may go into Friday。

 and then on Friday I will give some sort of examples on how to use these techniques on various products。

So essentially， you know the。Open and is。You know at least the basic concepts。

 you know are fairly straightforward， so essentially you have two main concepts， first one is just a。

The loop， okay， so is the full loop， although as I pointed out， there's no magic here， the idea is。

 well， is you have the full loop？Where in which each iteration is independent。

Then you can just paralyze it with spread by way people around four。

And if you have dependencies in your follow loop， essentially if youwrite your follow loop or do things slightly differently so that each iteration becomes independent。

Okay， so sometimes you know， it's really just more than adding this one line。

 it can be changing the algorithm。But okay， this is the basic thing。And then， the。

Next idea is because of does， so obviously not everything is in a for loop。

 I mean that covers the vast majority of cases， but let's look at situations where。You do have。

A lot of foul work， a lot of concurrent work， but it's not in the form of a loop。Okay。

 so this is a little bit similar to the C+ thread concept of Y。

A certain block of code you want execute and you're going to sign it to a threat。Okay。

 so there are you know a number of sort of classical examples。Of using tasks。

So essentially you unit need to of a。A process。In which you know。

A lot of independent tasks are going to be generatedrated。

 of course you could create just a handful of tasks， maybe one，2， three， four。

 but then you're going to be limited in the concurrency you can express in this process。

 but you have situations where。You know， you can actually， through tasks， still you know。

 provide a lot of concurrernce in case of for example， T traveral。

So it's sort of a recursive process。嗯。You could you can generate a large amount of concurrent work and then use the Open P test for this process。

So classical example of tree search is if you try to play a game， so a game of go here。

 and in trying to build a tree。Of all the possible moves from the current。

Infiegration on the board so each move is basically adding a new stone so say it's black stone so you're getting to add a black stone here on the right or the top right and so on and then next one is the white stone so maybe you add a white stone here or middle right here and so on and so forth and so you you go down to a couple of steps and to enumerate you know。

All the possible combinations and try to figure out what is the move that needs to has the highest probability of winning。

Okay，Essentially， there's two process in this。knowIn this calculation。

 one is the actual traveral of the tree， essentially each node know looking at the children nodes and then each child node looking its own children's so on and just traversing this。

 and then presumably there is some sort of calculation or evaluation that needs to be done。

At every stage， or for example， maybe you could have an algorithm that suggests the next top five moves that you could try from here。

 and then you would try these as five children， five different options here at the bottom just to bring this。

Okay。So this is the problem of tree traversal， so for certain types of tree it is possible to write a full loop。

 for example if you have a completely regular tree where each known has a fixed number of children。

 then you you can actually write for loops to kind of traverse what's happening at each step and so on。

 but if it's a very adaptive tree where the structure is sort of not really known or is not very simple。

 then you need something a little bit more sophisticated right so the full loop is not going to work to work well in that case so I'm going to show you you know an example。

 so if you you can open up this code on。On on on Github。

 So I'm just going to show you the snippet of code。 But if you go to to Github， you know。

 on the code lecture 5。Then you're going to have the code samples I'm using for for today。Okay。

No this actually works。Works。So this is an example of a routine that would traverse a tree。

So it's a binary tree， you those two children， but the two children knows not the still exist。

So the way this works is， first of all， this is sort of a recursive process， okay？

So you are sitting on a certain node， you're going to start the root node。

 then there is dysfunction visit。Basically this means perform some operation on the current node or some calculation of some type。

 so you do this before visiting the children node it scope free order traversal。

Visit the node and then traverse the children。 And then you ask， well。So it's a binary。

 so you have a left and a right child node， so does the left node exist？If so。

 then you traverse it and then does the right don exist if so then traverse it okay。

 so here we are assuming that all these visits。A independent of each other can be done concurrently。

 so you can see that you can generate a lot of visits at every node of the tree。

 okay run this concurrently。And so this is what happens to each so traverse might be a task here when you start and then going to generate one or two other tasks。

 and then just keep point so if you you will do this a couple of times then you generate large tasks and pretty soon all the process or course。

You know， have work to do， okay， well all your thread and f pool have a task assigned to it。Okay。

 so now this task is similar to the C++ thread， in the sense that when openmp encounters traverses。呃。

What they' saying is， okay， well， here is a piece of work that needs to be done。

It's independent on everything else， but you're not specifying you know how this is going to be like who' is going to run this and when and so different scenarios are possible。

The main thread， if everybody's busy， the main thread that might actually execute Traverse itself。

Or it may be a deferred execution， which is sort of perhaps what you would expect。

 so in sense that it records that there a task to do and then continues on。

 the main thread just continues on with the rest of the code and then either that thread comes back and execute traverse or some other thread you starts executing traverse so it's deferred execution。

嗯。So presumably initially， you have one set that sounds。三 good。Then execute two set tasksasks。

 so after that maybe you have three threads working。

 then each thread perhaps generate two other tasks and so on。

 so you just keep doing this until essentially all threads or all cores are busy at which point the execution sort of becomes sequential again。

 instead of sort of setting aside the task or giving it to another thread。

 then once you have enough task in flight， then the thread would simply start executing this as if it was a sequential。

Okay， so this is basically the process here and so now。

So you cannot call the function traverse just sort of just like that。 Okay。

 you need to put something around it。 Okay， and you need to do things。

 The first one is this needs to exist。Inside the parallel region。Because remember。

 essentially the program is split into a sequential part and the parallel part。

 so in the sequential part there's only one thread working and if you write open task in that region。

 probably nothing happens because there's only one thread burning。It looking。

So you've got to be inside a parallel region， okay where like all threads are now active and potentially could do the work。

 okay， so pra that one p parallel and then you traverse traverse root。

So next thing is next thing is a little weird and it sort of goes back a little bit。To呃。

I guess the way Open and came about and sort of a historical baggage。

 which is that when you encounter Prama empty perll。Well Loia， you declaring， okay， well。

 now I have multiple threads。And they can execute the code concurrently and so on， but in fact。

 in principle， if you remember what we said last week。Inside a parallel region。

 all threads are expected to execute the code。 So if I don't say parama only be single。

 then actually all threads will do traverse， which is not what you want。 Okay， what you want here。

 if you want to create a pool of threads， multiple threads that are sort of available to do the work。

 but the code traverse itself，He's only executed by a single friend， okay， so it's a little deal。

Maybe be telling to treat them or whatever。Only one thread actually needs to execute this code。 Okay。

 and the logic behind this is， for example， that's going in traverse。 again， when you encounter this。

 you know， only one thread should do the root。 and then essentially one thread is going to create this task and one thread is going to create this task。

 once you have these two tasks。 those can run in parallel。

 but the process of creating the tasks is done by only one thread in some sense。

 the task created only one right without the one single， you'd have like and you say four threads。

 you know， you'd have a task and you know， four of them would just be repeat。

 this is not what you want。So always remember， when you use tasks。

 essentially you have to be in a bra region for the obvious， but you must include or be single。

So this is sort of a common error and without the single SG， you traverse the three four times。

 which doesn't make a whole nonsense。呃。Okay， so basically this is just kind of a summary of this。

So either the site execute immediately task or deferreder the execution。

 and then in terms of who is executing the task while it's anybody in the federal。

Do any questions about this to ask？So it's basically a simple first thread。

 but instead of having to write an actual function。

 it's just a block of code So start of meat in terms of you know。The seat tax is a lot。先啲费。Although。

 to be honest， you know， with the new secret 11， you know， you have。Then the functions。

So it is possible because7 to create a thread。And sort of right there。😔。

You know write the body of the function that needs to be executeded within the function。

 so it look actually quite good。But regardless， this is this is a bit more flexible。 And again。

 one thing that。You know， it's quite different is that simple a thread where when you see a thread。

 you know a new thread is actually created， whereas when you see tasks。

You may have a pause thread that's already li and running and just sort of waiting for things to be done and just to hand a new piece of work。

 so in some sense this can be done much more efficiently。Okay， so let's look at another problem now。

 so we did the preor traversal， meaning that you visit。And then you know， you traverse。

The children notes， okay， so the way I wrote the code， you know， it was。You know。

It was very too the main thread enters traverse。Runs to function visits。Once it finishes。

 then it encounters that the task constructs and just goes up and this is sequential。

 the task must exist after visit。But how about another situation in which you visit？Okay。

 and then you have execute something。Okay。So actually sorry didn't show this correctly so for this note。

 it would be more like。Traverse the left child。Then traverse the right child。

Then visit okay business morning， well， it's a funny going。It means you visit left， visit right。

And then do are big， okay， so for example， if you want to do some sort of reduction。

where maybe some sc quantity is attached to each node and you want to just sum up all these numbers so you would say。

 okay， well， I need a number for A， I need the number for D and maybe the entire sub。

Once you have these numbers， you return them。Add them， add the number for B。

 and then you continue okay。And so this process of adding and sort of returning。呃。

needs to wait for the counting of A and D to be complete cannot do this you cannot just say oh。

 visit A， visit D and then return you obviously you need to result with counting A。

 counting the subject D and then you can add then return。So that's you， again， another common。

problem in multiple computing which is synchronizations。

 which be this so called synchronization point， by synchronization。

 I mean that you declared that there is work to be done sub for A。

 there is work to be done for sub D， okay so some thread to do some work。

Don concurrently is a different execution， okay you need to wait for this to be over before it can continue okay so it's called synchronization point to basically wait for the other thread to be done before you yourself can continue your work。

And so so there' is a。Special。Pragma in Open and B that will do that。

So you have to wait for the children to be complete before continuing。

 so this is so called tree post order online。Once you code。

 but this is sort of the bit that matters here。So it's called post order Traverse。

 so it's basically the same as before you have pragma andP。Pro well it be single， okay。

 so now you traing the tree。And what this is doing is it's counting the number so the kilo quantity on the left。

 So here just the number of nodes。 So just you know just counting the nodes。

 So how many nodes you have on the left subre， how many nodes on the right subre。

 Okay so it's the same as before。But there's a couple of differences。First of all。

So similar to sea dust spread and so on。All variables that。Appear inside the。The task。You呃R。Private。

 so in fact， specifically first private。Okay， so this is saying that for example， the well。

 you may have。But here the block is just single line， so it's very simple。

 but if you have a block of code， you know you may have local variables and so on。

 those are obviously private， but let's say what about left here because left。

Is defined before the construct， okay。So。Usually， left should be shared。

if you just have a prama or bearel。Before the B region。These are shared drivers， okay。

 so you'd expect left to be shared。But。Tuss are a little different right。

 because what's happening is when you have pragma or MP per。You have a parallel block that begins。

 okay？And then you know this block ends and there's a synchronization point at the end。

 so it's kind of clear where the parallel region starts where it ends。

And you know it's kind of logical that you， if you had variables previously defined。

 they would be shared， but for task， this is a little bit more involved。

Because you don't know when the task is going to be executed。

 okay it gets shipped off and executed whatever， in fact。

 it's very possible that past order traverse returns。Okay， while the task is still not executed。

And so for example， if you look at left。And so， okay。And so as a result。For a。我当。

It makes more sense sense that things should be private， like everything should be private。

 you seen that are shared。Obviously treat here because again。

 you don't know when the task is being in， so you have to be very careful that for example。

 if there's a shared variable in the task， that the task is complete。

Say before you delete it this shared variable or the ways it would be memory corruption。Okay。

 the default is to be private。Okay and so for example left。

 default fourth attribute for task is it should be first private okay and first private means that it's private and then it's initialized with the value before the constant so basically zero okay so left start with left equal zero well the initialization here doesn't matter。

 but whatever is' first private。And then it becomes private inside of the task。

 but in this particular instance， that is not the correct choice because。

You need left to be a data here。 If left is private， then that the task is going to cap it left。

But then right here， it's going to be zero。Okay， because your private copy。

So actually left by default， it's first private。But what share we had to specify share okay so share left。

And children。So again有一些关关的问题 pair扰。Be variable for default or shared， but for tasks。

The variables by default are first private。Okay， so this is a very important difference and again。

 you know if you're not really paying attention and you have these different choices。

It could lead to some error。Okay here the errors is that' and right would be always equal to zero without share。

Okay， so I be scared about that yet。All right， so that's the first point shared and then you you have Prama OMP task weight。

 meaning that the code is going to stop here and will not execute this line until both these tasks are complete okay so whatever tasks you were detailed prior task weight you know in this function right here you' going be waiting on that okay and so now you know that once you execute this line。

 you know that less than right or to date and you can just sort of。O。Yeah。

 I would say no it's those two tasks waiting on is it like a scoping thing Well yeah。

 yeah basically there's some complicated rule that I can never remember， but yeah basically right。

 there is a definition of what are the tasks。ThatSo essentially， right。

 So I don't sure the definition is， it's actually over complicated。的。One of the points？Is that。

 for example。Well， something I know for sure is that。Let's see that this dust right here。

It declarelars other tasks。You're not going to be waiting on that。Right。So for example。

 so here it post。So if this guy was doing other tasks， but then just returning。

Then you would just wait for the return， not the completion of all these。Like children dust whatever。

嗯。So yeah， there's a complicated way to understand which task you're talking about。

And the potential source of errors， so for sure the children tasks are not included。

 but tell you they might be tasks that are called prior traverse。Okay。Not 100% sure about that。

 most likely you're not waiting on that。嗯。But呀哋 some你 compiler。

That the convention as to what you're supposed to be waiting for because it does weight means you need to。

The compiler needs to register。Like what does he supposed to be weighing on of this？

So there's a little bit of work as to when you encounter a big task weight。

 you need to register what you're supposed to be waiting on， and so for example。

 if the other tasks outside of post order traverse that least becomes sort of arbitrarily complicated。

So my sense is that they may be excludedd， for example。So yeah， there's a little bit of complexity。

 I mean， I can double check on this but。Yeah， I remember looking to this and the answer was。

Something which at the time I understood that forgot。But yeah。

 there's a little there's actually a lot of things of that type， like scooping things that are。

Very ill。嗯。You know， aaque and you can expect。呃。Okay。So yeah， but， but good question。 Yeah。

 and good question。So then you have first private。So we talked about this and then task weight。Okay。

So let's look at so here you know the process of generatinging tasks is basically a recursive calls。

 so so case number one。Case number two is basically a w， a case of value。

 is also something that would be difficult to paralyize so a night。So the four。

 although the photo loop， you know， in some sense， could be。Time of white loop， I mean。

 the determination condition could be again of complicated。

 but what's happening is when you say why people are out four，Then呃。

The API specifies that the following loop should be simple。

 but this essentially in the case of follow loop， everything。

 you should be able to reason about the loop， like you know when it sounds。

 you know when it depends and exactly how its it have。

So everything is sort of known ahead of time so the Ko can do some optimizations。

 so here we're looking at basically an intuitive process or while loop。

 but where you cross list yout know how many elements you have in your list in that case the Prama or MP4 does does not apply and this is another example where tasks work extremely well okay so again。

 very similar construct Prama or PL。Prama would be single。Okay， and。

So you just traverse your list so here it's just， I did the list throw it by hand。啊啊有。

You can use it SCL and so on better so essentially at the end current node is now it's going to stop and every time you visit a node you have Pragmat1MP task okay。

And then just visit the next building one。So in this code， for example， well it's a very simple code。

 but still it is possible to have bugs。In particular， you can see that current node。Keeps changing。喂。

你几。Keeps moving in the list， right？And so when you say pra O MP task， you say visits。

 but the argument is the value of current node okay but current node keeps changing。

 so what value is that okay so this is where you this default choice of first pilot works as it should okay so what's happening is。

Your current note。Defined prior to Taskk。So the default choice is first private。

 meaning that this block of code here will have a private copy of current node and the value will be initialized by the value of current node prior to entering the construct which is exactly what you want here so actually in this case without doing anything you get the current code but the correct code。

 but you see that there is actually a some point in the middle。Okay， so I guess this is it。All right。

 so any questions about this？If they're with execute a particular task。

 if you are to wait for a particular task， can you spawn a whole bunch of tasks。

 and then you want to wait。One themOkay， alright， so good segue in in the next。Next bit。 So now。

So I guess until recently， so I haven't tried exactly the specifications， whatever。

But you until recently， there was only that weight， I mean actually。

know there was some timeable when there were no tasks but that was sort of recent addition and there was sort of limited support and so initially that's right。

 the only thing you can do is this task wait which you wait on everybody。

But there are situations in which you want more fine grain dependencies and the reason for that is so that each time you do a dust weight。

It's a synchronization point， okay， meaning you got to wait right like no additional work is going to be produced until everything that comes before is done。

 but maybe the kids that actually have tasks coming after that are ready to be run right and you're just waiting for no good reason。

Okay， so it's very important that。When you declare task you sort of specify the minimum number of so-called dependencies okay so that you start essentially as soon as possible。

 as soon as essentially the input variables for task and ready。

 you should go and so how does this work so this is rather。You know。

 this is more complicated than definitely back prone， but。In the recent maybe4 or5 version of Openmp。

 you have now this fine grain control over dust and actually I'm not going to go over everything。But。

 you know， just least some the features so first thing is priority， Okay。

 so priority is something actually a little tricky。But。So actually， let me just little aside here。

Your side， which is so called so called critical path。Okay， so critical path is basically a。

 situation like this。Where， you know， you have a sequence of。Of no like this。

 and so here this is a path and what this diagram means is that。

You cannot execute the next tasks until you're done with the previous。

SoNow let's assume that you had a situation like this where you had at the top。家。So at the top。

 you have many。Many， many tasks so of course it is a little you know。け。呃。Exaggerated， but okay。

 let's it's good。Okay， so essentially， as soon as this task is done。

 then you can execute all these tasks。Okay。Now， the question is， so what about this priority？

At some level， all these tasks you can do and you can solve with whatever and so on。

 what difference is make？Well， so there's this concept of critical path and the critical path is basically in your graph。

It's the longest， essentially sequential path， okay？And so by sequential path。

 I mean that you have an exact sequence。And so， for example。You may have a million cores。

But if the only thing you have to do is this guy， only one core is ever going to have any work to do。

So critical pass is basically saying that let you have an infinite number of courses。

That's pretty much the fastest you can go。Or that's the lower bound on execution cut which can go faster than that。

And so the best you can do is therefore。To do this as quickly as possible。

 know in a sense you start here， as soon as you're done， you move to this guy， then that guy。

 that guy and that guy okay now you have you know an infinite number of process of course。

 so while this is happening，You know， you can assign one core to this， okay？

And then let's say that all these circles take about the same time to execute。

 essentially once you're done with this one， then actually everybody's done。And you go here， okay。

 and indeed， your subscription time is minimum。Now the wrong thing to do。

Would be to not start this task right away， but for example， spend a lot of time。😡。

Doing all these tasks。 Okay， and once all these are done， then you start working on。

This path here and the reason why this will work is because then at the end of your code。

 you'd have one thread doing work and everybody else is being idle。Okay。

 so this leads to the concept of priority， it means that it is much more important to make progress on this critical path as soon as possible。

Whereas these can be done just whatever a fed is idle， you can go work there。

But it would be very bad that， for example， a task here has to wait。We want these guys to finish。

 okay， that's suboptimal。So you want these guys to have high priority。Okay。

 and these guys do have low priority。嗯。So there are different， you know。

Prairie is kind of a complicated business， actually。

So that' sort of theory that of course in practice， yeah。all the parts have equal prayer。And的。

哦 you你 all all the people先。When you cook means basically a reader is the same。

Because there's no one that's shorter than the other aware。hoper。Okay， so the。Right。

 so what this is saying is。Right， so when you're。Deciding on which task you want to execute。

So let's say you finish this one， so then you you have one of these seven tasks to choose from right so you have four tasks that are ready to execute。

And yeah， you a scheduler or something that's going to decide， you know。

 say you have 7 w if only two courses， we've got to decide which one is next。

 and so if you don't have any priority， typically it's random。我。

But you want this to have a higher priority， so let's say priority is zero here。

 priority is one alone here。So if you have a choice to pick one， okay。

 and then the next thread would be zero， as soon as this one is finished。Next high will be one for。

So so in your out with him。The critical path should have a high priority。

 whereas the sort of side branches， if you wish， should have a lower priority。Okay， so that's the。

But you can see that it comes on a attorney coffee。いす。

They don' if you have an infinite number of processors。呃。You。

 that is really the only thing you care about， but the。You may have a certain critical path here。

 but then on the side， you may have another path that might be shorter， but it's still kind of wrong。

And it would be the second highest priority and so on。时后 it was taking call complicated so。

So the bottom line is， you know。This is something that can be used。

 but it's very hard in practice to figure out。What should be the。How to assign these priorities？

Sometimes it's going of semi obvious but it can be something to play around with and it's for complicated could。

 it's very hard。To figure out， you know。What。What priorities should but there are cases where you know。

嗯。诶一是。Well。There are cases that are semi objects， for example。

 if you have a task that runs for a very short time。

And then needs integration creation or one or many tasks that are much longer than you probably want to give it the high priority。

 essentially runs very fast and it unlocks a other of work。

 so this would get a tricky case you want a high priority on task like even I think this example。

 you can pretty easily see that。You start traversing the longest path。First， if you assign one court。

 you， you have two cores and you assign one court to that。嗯。Yeah， I mean。

 you can see that you can do like let's say each circle is like unit of time。

 you can do it in six units of time， you start outside and go， then I think it should take like8。So。

Right， but although for example， here you can also realize that。呃。RightOf course。

 if you were to do the sixth first。And then finish here， it would be six plus whatever ten。Well。

 would be it would be four like let's say you have two cores and let's say oh。

 you have two cores you have one， three， four。And then eight， right feet。So in this example you have。

 of course， you can see that。This takes four years of time， but this takes six units。

 so it would be actually okay for core one。To do the wrong priority。个ざす。

But because this the personally process。So。There's some meetings。W anyway， I mean。

 it's kind of complicated thing I don't to。Plus， you know， this is just。Right。

 the priority also is just。It's just a， right， because what's happening is。So in this example。

 maybe this is too simple but。You know if you jar it， yeah， well okay。

 I don't want to turn to a shell on this， but this is just a hint。

 so meaning that know you want attached to a high priority will tend to run sooner。

 but there's no guarantee that you this will happen， it's just sort of a hint。

 you're giving the system that if there's a choice between two tasks you will pick the one with a highest priority。

Okay， so now let's go back to the other question， which is these dependencies。So essentially。

 for dependencies， there are two things。There's a lot of stuff around phones。

 which are actually now to cover。Where you have many loops， many cases of full loops。

 where there is actually dependency between I and I plus1。

 you need to wait in the previous iteration。Before doing the next one。

 but there's still the last time that can be done in parallel。

So there's a way to kind of describe in more fine grain way what is dependent in the photo and what is parallelil so that you can extract some parallels in。

 even if there is something that seemingly，Is sequential to only some parts are sequential。

Other parts are should grab， so I'm going to skip that because it gets really complicated。

 but I wanted to cover this because this might be a little bit more。More straightforward。

 And so essentially you have a clause it's called depend。 So let me just show you an example。

Where when you declare a task， you can include dependencies okay。

And the way dependencies work is you specify variables， Okay so it's actually memory locations。

 in case of this。A pointer or a location memory that's going to sort of be used to region about the dependency and the dependencies so you go like this。

 Pra be task。If you shared X。As otherwise， it's first private。And then you have this depending。

Okay and the depend has the name of the variables， it could be you know arbitrary variables。

 you know where have you？Then you have out and in， okay actually the list of keywords was shown here in out this。

Vly reflect， okay， in means that。第议。就家去。You order to start。The dust。你。

The value of x would be up to date， but there were previous modifications。ToX， need to be compete。

 essentially there was another task。That was modifying X， then that has going to be done。

Before the in dust stops。And then out means that the task is going to modify。The variable。Okay。

 in and out is sort of doing both， and then there is on top of that new text。

 which is similar from you know。What result saw basically mutual exclusion。

 so it cannot run the two pieces of code at the same time。所 that就说了个 you know呃。

Mmoage or the sort of youll be the meaning of this in out。But specifically。

 so I'm going to show you then now how how how this was， There's actually a table。

That defines exactly how this works。So for example， the in keyword。

Means that if previously you had a task that had the same variable， but without。

Then there's a dependency， Okay， this one needs to wait on the completion of that one。

If you have out， then you need to wait on everything else。😡，O。呃。

So essentially this saying you're going to overwrite x with a new value， but a previous discussed。

requiresquires a value of x， so it needs to have use that value and after it's been used。

 you're allowed to overwrite it。A little bit less obvious to me is out also depends on out。

So for example， if a thread writes Xco 1， another thread writes Xco2。

 there's actually supposedly a dependence。It's so weird because， you know， you' going to overwride。

 like what's the dependence， but okay。The specificationsency that that is the。Okay。

 and then the new text is actually so it depends on in and out。 So for example you know。So this is。

So the previous case actually， so this is terminology。

 I didn't write it down because it's not super important， but this is a more。

 this is what's called a dependence， produce， this guy is going to produce X and this guy is going to use X。

And x is always equal to2 because of the out and in， it iss called dependence。

And then there is the reverse， which is called antidependence， which is the in and the out case。

 so antidependence means that this task needs x， the value of x or x equal1。

And this task here is going to modify x， so hes has to run after so that this guy sees the correct value of one。

 so it's called antidependence this in out case。Okay， and then you have the case of Mut。

 which basically defines that the task can be run in any order。But not at the same time。

So it's basically just that you got a indexex。Only one task， so basically here， you have mutex on C。

 muttex on C， so same。Mmification is comparable variable。

 so there's an exclusion between these two terms。Okay， so now we're going to do the little game。

Going to do game okay， so I need to set this up。So you need your phone。To pay his game。

Let's see if I can do that。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_1.png)

Okay， you need to go to this website， so actually I need to start it so hold on。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_3.png)

Let me just bring it here。嗯。So you need to go to this website， Kahoot。And with your phone and。Create。

 actually， I'm trying to create an account。 So let me just start this。

And there's going to be funny music and stuff。嗯。Okay， so let me just start。呃O。です。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_5.png)

Okay， so can show you。 So it's a little complicated because I need to show you the game and the code at the same time。

 because you basically the code too。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_7.png)

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_8.png)

And so the game， so hopefully this kind of works out。Oops， sorry。Mistake。Where was I。Okay。

 so hopefully this is。Yeah， I I don't think it can zoom in。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_10.png)

Okay， but hopefully you guys can see the。B earth。Okay， so all right。

 so I guess you guys see how it works。So you go to this website， you enter the game pin。

So actually I'm going to track to as well。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_12.png)

And so you can have so you can get some we code with this there even some questions about the code。

That need to answer and since if you have questions ask break now because you have 30 seconds to answer each question。

And' going to get his forward behind。So I think I've already paid this for some of years。で。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_14.png)

Theres no icon bit at the bottom or you enter the pen， I guess。Okay， then you have to pick a name。

Of course， no offensive name。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_16.png)

So it's me。But you don't have to put Jordan over here on the RF that。So okay， 14 pair。

 so I think they' bonus us。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_18.png)

嗯。Okay see how remember。Ne to remember how to。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_20.png)

Let start。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_22.png)

Sorry， I need to little tricky with the window。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_24.png)

So you have 30 seconds to answer each question， it don't be too stressed， but it does go fast。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_26.png)

Okay， so let's start。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_28.png)

So are you ready， okay， six questions？

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_30.png)

And so you press it basically on your。呃 phoneone。So question Mark， it task T2 comes after T1。

 this is this one comes after this one here and you have to take。One of the answers。Okay。

 so this is how many people answer and then you'll have the correct answer and you score。呵呵。😊，对。Okay。

 this is an easy question。We should get it correct。So yeah， sometimes before going on。

So here there is a depend out A and depend out T to these are completely dependent， Okay。

 so A and C different so basically this comes at any time， so basically sort non comminal sometimes。

不。Any questions？so we just have six of those。Okay， so。So actually it's supposed to be some music。

Just get entertaining。I't if maybe's still working。呃O。I let lets get the music。

 The music is kind of fun。It's not。Let's see what the sound is coming out of。

give be a volume slider on the actual cushion itself。Here， I don't know if there's sexual。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_32.png)

W， that's fine。 Yeah， I I' know what to told。Okay， so yeah that's a score board so yeah。

 the score is depends of course's correct also how fast you are。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_34.png)

So I guess Mark was the fastest。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_36.png)

Okay， so number two， T2 comes f to T4。So Ti is here。啊，接过一次。224。TheF is for genius。😀。😊。

They us some great feedback。F。So answer is never， right， so actually I sort of wrote it backward。

 you know T4 has a deep in a。Right whereas T2 as an out a， okay so basically T4 must come after T2。

 so it sort of going backward and so you the correct answer was never so actually still。Number。

 so five wrong answers。 So if。To be more careful。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_38.png)

It's not graded。So Mar is doing well。And number three。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_40.png)

So T5 comes after T1， so T5 is this one here。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_42.png)

And she was that guy。Over there， so。We would be more complicated， so obviously you know。

You can continue do this， so maybe you have to think a little bit about this。Yeah。

 the sound it's more fun than this sounds。这是是一的。Okay， so all right。

 so I guess oh fewer errors so this is guys are getting it so yeah task T5 has so the muttex C depends on you know and it depends with the al C so it has to。

Come after that。 That's a must。Okay， that's correct。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_44.png)

So Mark is still the fastest。And T 4 and T 5 may run concurrenrtly。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_46.png)

嗯。I guess。Make sure how many pairs we have。O。So no right so concurrentency means that they can run at the same time so we concurrent means it can run at the same time so that basically the point of muttex in outset。

 they can run in any order but not at the same time because you're updating the shared variable C so answer is not possible。

Okay， so。Oh yeah， you also have a streak， it got a streak。

 meaning that if you keep answering correctly， sometimes in the road， you get a super bonus。

SoSo they can pay off to be slightly slower if you can get a streak。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_48.png)

But I guess I film them before。All right， and last。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_50.png)

Gestion， I think。F five T5 comes after T1 and T3。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_52.png)

The G5 is right here again。And talking about the one， which is this one and three， which is this one。

We make the one before。Okay， right， so exactly。 So here it's a little tricky。

 You have the in B means that T 5 weights and T 3， but then you have the mutex C。

 between you also wait on T1。 Okay， so after both because of know， the mutex and the in。All right。

 and last question is。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_54.png)

Right， so F L you five correct answers so that I can。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_56.png)

Is on fire。😀Yeah。😊。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_58.png)

Okay， the square prints d equals6。So you have to kind of go for the stepss here。Okay that right。

 so yeah， I could have。Okay， give you the incorrect result of those it was seeking correct。Okay。

 awesome， all right， so we're done。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_60.png)

And so just have the。放北京。で。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_62.png)

I guess it's Ryan。And the mysterious mark。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_64.png)

不。你 like。还是。All right thank you。Oh it's dancing。あ、ねはす。Okay， all right， so we're going that。

 So that was newt in and outet。 All right， thanks for playing。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_66.png)

O。So that's that。嗯。Okay， and so we're just going to wrap things up with just a couple。

A couple more things， so first one is red， which actually is something you need in your。

In your homework。So not super complicated， but just make sure that in your homework。

 you there are a couple of questions about reduction so make sure you use that sometimes students find other ways。

To get the answer， but so this is the most efficient implementation to make sure you use that。

 So basically reduction has to do with the form code。

And so this code is obviously this type of code is very important just going interpret the sum。

 you traverse some array， computer in quantities， and interpret the sum of all these numbers and end up with one result。

 so。So every day you do， for example， they' get the norm。If you do a dot product。

 okay obviously is the sun， you have it the two norm or the one norm or even the max。

 okay all these example of suns， if you do a matrix vector product， you're going to have the sun。

 I mean depending on how you paralyze it。And so the key thing is there are two issues with the sun。

 first of all， well， there is a race condition on sun。

 so if you have all the variables sort of reading and writing the sun。

 that would be wrong okay so there's a race condition on sun。In fact， if you just look at this loop。

 seemingly。There is a sequential dependence because you need to read some。

 add and need to write the result。And so there's sequential dependence in addition。You know。

 different threads。Need to read and write some。 And this is very bad because the sun， for example。

 cannot stay。In Re file， it is refreshed back to memory that another thread can then read it。

 okay so it's extremism。But there is a so there's a problem of correctness in your efficiency。

But there is a much better implementation and this is basically what I explained first day of class。

 which is you can have each thread compute its own local copy of some。Okay。

 do its own edition in its own local copy and then let's say you have two threads。

 then you would end up with two sums， some zero some1。

 and then you need to add those up and that is the final result So there's an obvious path to paraly it to paralyzing the two very。

 very efficiently just local copies of sum and then once you're done with the code you just add all these partial sums together and you get one final result and that's the result in the calculation。

So there is a correct and efficient way to implement this。And actually the beauty of this。

Is the compiler。Needs to know almost nothing。Because the only thing the compiler needs to know。

 it needs to know that there is its variable sum。Okay。

 and so each thread needs to have a private copy your son fine point number one。And then second。

 the operation to be done at the end once you have all the partial results is a submission。

Okay that is the only two things actually here， you could have really very complicated code。

 right there might be several pluses and so on， maybe even minuses or whatever， okay。

But the point is， you you would get a private copy。

 and does the calculation and then all these final results are just sort of added together， okay。

And so this is specify exactly here， what is the operation that you need to do at the very end？And。

You know， what is the variable in question the very？Okay， so here you can have multiply。

You can have sp operation and so on， you can have minus， which is。just basically just a。

You give them。Yeah。Negative at the end， divide and sort with different operations。

 and then whatever variables variable Google want。So typically these are scalar variable。

 these cannot be erased， although maybe in recent version of open pieces can be arraysed。

 but typically this has to be just scalar variables。Okay， so let's basically2， two questions。

 Ra condition and then improved efficiency。Okay， so now so theres just a couple more things I want to do。

 but so now little exercise for you just very briefly。

 so if you want these slides they on GitHub so you can see the syntax，For the power4 reduction。

Plus column sum。Again， I want you to do something similar。For this piece of code。 So I。

Let you download and so you can download this file and so there's a make file in lecture 05。Okay。

 you can go Github code lecture or5。And then says entropy and entropy solution。 And so just open up。

This code here。So， it's， it's not。Terly difficult， but has to compile。

 And then there is a number of loops that I want you to paralyze。Okay， so remember。

 it's alpgma1P PR4。Is how you parallel a photo？But then in the middle。You have。This operation。

 so basically copy the two probabilities， okay then the entropy of each pro。

So first you have to normalize the probability， so it is going to be a sun okay and then you're going to。

Normalize each entry and then commit the entropy of each format distribution so here sum you know there's going to be a reduction so reduction plus and then you can see sum1 comma sum2 okay just list all the variables for which there is a sum。

Okay， another parallel4 to normalize entropy。And then finally， decorcating the entropy。

By just the sum of。You knowP0 times log P0 and P1 times log P。So it's minus P of p。

And then just print。 So this is a result that the entropy difference。Should be yes。

So basically three， four loops。诶 country水。对。So4。4 four roof and。So， hopefully， everybody's okay with。

The compil step。Has he anything with the Google cloud yet？有。可以嘢日嘢。So the the instructions worked。ざす。

It is。部長も。Okay his not computer。So the combining is working。

So I'll give you a couple minutes and then just show you them。Solution。

And just sort of just wrap it up here。So let me know when you've done。Whats。嬉しです。系咧。我我已是。So。Okay。

 so you don here， you can simplify the reduction。好了。我有要见数。Okay， if everything else you done。

The somebody else is。你哋有。So one thing that actually。YeahIf you want to try something。

 the next thing to try is when running this code。You doing呃。So you're doing this reduction。

 and so the order in which the additions were done。

K change right if you have one thread or two threads。

 so the order of submission is going to be different， so as a result， the round of errors。

Round of errorss are going to be different。So you can try to run with just a single thread。

Or run with two threads and look at the results， and you will see that they differ by basically question precision。

Okay， so you can use。OMP non threads， so you can export OMP non threads。

Or you can use the UP command。OMP set non threads to change the number of threads。

 so let's say go from one to two。And then you will see that the results change。

 or you can do that if。Once a more advanced exercise。

 so let me just show you the solution would it possibly get different results？



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_68.png)

Twice。Oh， you well， that even on the scheduling？呃是。咁先用。So in this case， no。ケでご先 study。

So it's scheduling， so it just should be the same。I mean you have run the fer with it。

 obviously if you do the operations in the same order， then it should work。

 but there are definitely cases where to have what you were to do，诶哋咧你。

Well let mean maybe some size variations。就这个事。But studying for the whole just eating education。



![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_70.png)

Okay， so so this was solution， but it's it's so you have pra and P around4 Okay， so first you can。嗯。

Right， so we have 5 million peopleal4。And so a reduction。

 you can so this is just a length continuation， but you can see plus sum1 comma sum 2 with the reduction and then again O around four。

And when people have four reduction， you know， same thing and one。

Here I added this just know because if somehow P equal to zero， obviously you don't take the log。

And that is， that is it。So one common bug， by the way。I'd forgotten about。

If you say Vietnam thread requesting how many threads are running。

 but you have to run this function inside the current region。

 right if you run this function in the sequential region， you always return to one。

Just remember that you want query how many threads are running。

 you got to make sure that you're inside a parallel region and I want to print this only one。

 so point people out be single and then you can print a number of threads assigned to this work。Okay。

 alright。 so basically Z。嗯。So let's go back here。Okay， so just a couple of things to finish up。

 so essentially you know work and going from most efficient。To least efficient。

 okay so this is the so make sure that if you want to intervention venture your code you sort of follow into the thinking about what solution to use followed this disorder。

 so first is is it a reduction， if it's a reduction， you should use that。

But there are cases where you're updating a variable like you're doing this less equal。

But it's not actually a reduction。 Okay， so I'm going to show you a case in which case you want to do atomic。

He wanted to do stomach。Here。So you want to do a tumch。呃。

So I'm going to explain how this works so example I want to give you is antibody body problem so when you have vibration additionalal bodies interacting with vibrationdational force。

 but it could be also you know in a molecular dynamics simulation when you're computing， for example。

 static forces，So basically you have N particles。You have n square interactions with calculate equal all pair。

 calculate the force， and an a。So this is what the code essentially looks like or another picture here。

So you have to loop over all the bodies in the simulation。Okay。

 let's say you get the blue body and then you loop。

 so you double loop loop over all the other bodies， so so you get this yellow。

 then calculate the interaction between M1 and M2。And then you're going to do like a plus equal on this force。

 and then a minus equal on this force， Okay， so the idea is each force happens for prepare pair。

So of course， you could loop over all I。And then loop over O J and calculate the force that J exerts on I that's N square。

But since the first J on I is minus the first i on J。You know。

 you really want to loop only over the pairs rather than n squared。

 so the pairs will be n square over two with the n and minus1， actually。And minus-1 over two。Okay。呃。

Right。So。Okay and so you're going to look over essentially all the pairs and then once you have a force。

 then you want to do plus equal on this guy and minus equal on that guy and so this is really not a reduction sometimes it's plus sometimes it's minus。

 but the problem is each time you do plus equal potentially you may have different threads。

Trying to update the same memory location okay and so again。

 this is a race condition and this needs to be prevented and so use atomic。To declare that。

 the compiler needs to do something special。With the code right。So what's nice about best equal？

Well this can be done either with a new text that's very expensive。

 but very often the hardware allows you to do plus there's some efficient support in the operating system。

Maybe the hardware to do this type of reduction。But the way you need to be careful。

 and so the way this is done。It goes like this。Okay， so you loop over I。 So you do round 4。

 So there's gonna be parallel over I。 and then you loop over all particles J from I plus one to n。

Okay， so basically it's really all pairs。你似要要啊。The other way would be IJ and JI n square。

 so here it's n square of two。Okay then calculate the relative position of I and J。

 calculate the force， and then you want to add to I and subtract to J and so here there is a you know potential conflict okay so there's actually conflict both on I on both I and J so for both of them you need O andP。

Were in phomic， and so whenever you're doing just one memory location update to basically invest equal minus equal。

Starttorical everybody共。Then you want to use atomic。 Okay。

 and this is going to protect the update of F。 But this is so if you're doing a reduction。

 don't do atomic because this is。Quite slow。 Okay， if you have a lot of threads that try to edit exactly the same variable。

 it's actually very， very slow。 Okay， so here it is kind of okay， because you know。The odds。

 the two threads try to update the same F or somewhat small。

So there's going to be some potential collisions， but not too many。

 So return is a good choice for this problem So。Right， so reduction， okay。

 so reduction means that each thread is going to have its make a private copy and then there's going to be a sum。

Okay， so here， the reason why this doesn't work is。Well okay， first of all， it's an array of IO。

Think about this recycling。Well， I don't know， you could try to do this with a reduction on an array rate which you know。

 I don't know if this is supported depending on the compiler。

But there will be some main problem with the reduction here。The fact that it's in a rate。嗯。

But also the first situations in which the final result is if not the sun。Of the fossil results。

 or there is no simple mutation like that reductions。

Duction means that the final result has to be the sum of the partial result。

 so here it is actually correct although you have to work with an arrayF。

But there are situations where this is something just not possible。

But you're correct that I have double take on reduction， whether you can do reduction arrays。

 but there's actually multiple problemss， there's reduction in arrays。呃。But also the fact that。

For example， if you were just updating certain entries in your array。对不对兄有所趋。Well， I mean， okay。

 there are various reasons why sometimes the do is a right choice Okay， and so just to wrap it up。

 the last final choice is critical。So critical means that essentially this is the equivalent of a new text。

 so it means that the line of code。They issued in any order。

 but two threads cannot not execute the deadline at the same time so for example here I wrote program to calculate prime numbers。

Okay， so I have app parallelel photo loop and then I'm testing you know。

 is this a prime number and this is the prime number then I'm going to insert it into a set。

 okay C plus plus set so the insertion。Can not be done charge， okay， so any order but。

You know insertion one at a time。 So you one be critical this in this example here。 Okay。

 so the code is on GithHub critical that CBP， if you want to see what it looks like。Okay。

 and finally， just to kind of wrap up。Great time， so there are a couple of things that I talked about。

 there is affity， these are more advancedoscopic when you want to attach。

The task to a specific core because of memory affinity is no effects。More those。Yes， target。

 so target is。So we is sort of suffering we start right now。I guess it's un working。

 but this is the more recent， well this is sort of the future of programming GPUs。

 essentially you can program GPUs or arbitrary devices， so it's called targetrg。Devicice。

Using OpenM so you can actually write brand your code on NVDA GPUs or N GPPUs using OpenM but this is just OpenM 5。

0 so the support as you know it comes to 4。5， but it's very recent so it's still very hard to get to work。

 but know as compile control and so on， this is most likely to be the。Default solution。

 because it's much easier to program with Open I rather than writing Ka code。

 So right now there's really only Qa that。Its really well supported and so on and works well。

 but the future is really more along the lines of you，And then you have Cindy。

 so I mentioned Cindy and then locks， there's a way to have new taxes and locks。Okay。

 so here you have some examples， specifications， if youre looking at the details。Okay， all right。

 so I wrap it up here， so I'll discuss some applications and exact applications and algorithms on Friday。

 Thank you。

![](img/c2a7cb4c105f1888eeaf9b3be0442a5c_72.png)