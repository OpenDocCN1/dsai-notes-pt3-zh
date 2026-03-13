# 【印度理工学院】知识表示与推理 ｜ Knowledge Representation And Reasoning p66 P66_递归描述 -BV1c4zNBmEyF_p66-

So， welcome back， we have been。Defining family relations。

And we took the approach that we will start with a primitive set of relation。

And define everything else in terms of those primitives， so the primitives that we chose。Was parent。

Relation so x is a parent of y。And we talked about gender whether that x is a male or x is a female。

 so with these three kind of facts we are defining all kinds of relations between which occur in our family so we define brother。

 sister aren。And so on。Now let's talk about。Relations which are arbitrarily far away。 So grandparent。

 you know that there are， you know two generations apart and things like that。

 So you can write them explicitly that， you know a parent's parent is your grandparent。

 but what about their parent and what about their parent you can't write every such relation explicitly your knowledge base would become。

Too huge。Luckily。😊，We can use recursion here， too。Define search relations in logic。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_1.png)

So， having defined grandparents and near cousins， how do we talk about relations that may be over arbitrary distances essentially？

Here is a recursive definition of the ancestrtoral relation。So the base clause。

 we can keep it as a parent is an ancestor。And the recursive cloud would be a parent's ancestor is is also an ancestor。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_3.png)

So， that definition can be expressed in logic like this that there are two things。

 one is the base clause， which is like this。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_5.png)

It says it。When you say that。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_7.png)

Is an ancestor。Of x， then either a must be the parent。

Offfect in this case it will turn out be either， but we don't need to use exclusive wall because。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_9.png)

That situation will never arisese。So we can just use the all there。嗯。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_11.png)

And you can see that a is a parent of x or。😊。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_13.png)

P is the parent of x。And A is ancestor of P is， essentially。So what are we saying here？



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_15.png)

We are talking about an ancestor A here and an individual X here。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_17.png)

And we want to see if they。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_19.png)

All from the same lineage。Which means but there is a parent child relationship all the way from A to x。

And what we are saying here in this definition。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_21.png)

Is that if you want to find out whether ass or ancestor of x look at the parent of x now there are of course two parents so this should involve search but when you find the answer you will see that one of them of course。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_23.png)

Would be the relevant parent parent。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_25.png)

So， an edge here denotes a parent relationship。And。You say， okay。

 look at a parent of x and ask whether that parent is。

A descendant of a or whether a is the ancestor of the parent。

 essentially that is what we are seeing here。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_27.png)

You can see that this will involve certain kind of search here because x will always have two parents。

 so lets say parent 1 and parent 2。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_29.png)

And the ancestor could be connected to either of them。

 so just some amount of search would be necessary。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_31.png)

Which we are not emphasizing on， we are only emphasizing on the definitions here， essentially。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_33.png)

So， the right to left part we can actually break it down into two separate clauses。Which is。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_35.png)

The base clause is that if p is the parent of x， then p is the ancestor of x。

 that is the base clause。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_37.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_38.png)

The recursive clause， we can just copy from here。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_40.png)

It is what we have done here。And then we can move the。

Existential quantifier out of the left hand side and convert it into a universal quantifier。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_42.png)

So， the definition now becomes。For all A X p， if p is a parent of x and a the ancestor of P。

 then a the ancestor of x， this is what we were seeing here。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_44.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_45.png)

Now this is not the only way that you can define ancestors。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_47.png)

Lets look at one or two more definitions。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_49.png)

Because， as I said。Searching for your ancestor is actually going to be a search over your knowledge base and。

The search will follow the definitionlation that you have given。And which of the following？

Definitions， I'll give you three definitions here。Is going to be efficient。 So when we say efficient。

We basically mean。😊，In the number of influences that you make essentially。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_51.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_52.png)

There was a time。In the mid 80s。When the Japanese government embarked upon what they call as a fifth generation computer system program。

And their goal was to。Bill。Machines。Which were essentially built on top of logic， essentially。

So they wanted to take the idea of logic programming to its。Completeness。

And say that everything we do will be in terms of logic。

And they said that they will measure the speed of their machines。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_54.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_55.png)

Not in terms of instructions per second。But in terms of logical instructions per second。

 logical inferences per second， so they use the term lipss。Logical influences per second。

But somehow the idea， like many ideas， did not survive。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_57.png)

But when we talk about complexity of our representations。

 what we mean is how many inferences you are going to make before you arrive with the answer。

Or how many inferences will you try essentially？

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_59.png)

So， the query that we are interested in is of these two kinds we want to find somebody's ancestor。

Or we want to find somebody' is descendant， which is like saying。你。

That person Aa in this case is the ancestor of someone。

 so you know we are asking whether x is a descendant of Aji。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_61.png)

So， just like we had defined parent trial， we can define ancestor descendant relation also。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_63.png)

So， here is the definition we started with， it said。😊。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_65.png)

That you want to connect a and x， A is the ancestor and x is the。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_67.png)

Pent person and start from the parent of x and then see whether that parent is there。

Descendant of a or whether a is as ancestor of that parent P， that is a definition we just saw。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_69.png)

We could do the other way we could start searching from the top essentially we could say。

The first clause is the same in both the cases， the second clause is different。

The second definition which is what we are looking at now。

Says that if you want to check whether a is an ancestor of x。You want to say。That， if a。

Is a parent of x。And x is the ancestor of P。Then a is the anncetor of x， so this definition is right。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_71.png)

But we have started searching from the ancestor essentially。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_73.png)

So， obviously。😊，Which one would be more efficient？Would depend upon what is a query essentially for one query one definition may be better for the other query the other definition may be better。

 so I would like you to think about that and say。That how would you？Take care of efficiency here。

 essentially。Another aspect that may influence the complexity is branching factor essentially。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_75.png)

Now of course everybody has only two parents， but people may have any number of children so it could range from one because we are talking of a relationship here。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_77.png)

From one up to any number essentially， so then an ancestor may have many children。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_79.png)

Whereas descendant will have only two parents。 So the branching factor。

 if you are searching from button put top will be only two。From the top， it depends on what is the。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_81.png)

Number two。Children that people have in general， I think。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_83.png)

What about this definition？The first clause is the same， the base clause is the same。

 the second clause says。That is an ancestor of x if。P is an ancestor of x。And a is the anncetor of P。

 essentially。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_85.png)

So， both。Closes in the left hand side are。Ancesstral closes， will this work？



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_87.png)

So I will leave you to think about this。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_89.png)

Another question that you might want to ask is does the order matter inside the conjunc。

 so should I write the parent first or the ancestor first if I am using a parent in the ancestor definition that is something that you should have pondered over when you are looking at prolo so it depends upon what is the。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_91.png)

Evaluation mechanism that we are using for this。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_93.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_94.png)

呃 것만 error。That people make。When expressing things in logic。Yes so they omit the category。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_96.png)

Of the variables in the sentence。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_98.png)

Other terms in the sentence。So if you want to say that every student likes some course。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_100.png)

You must include the category of the class membership of the two variables or the two terms which is the student and course so the correct way to say that is for all less。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_102.png)

If as is a student。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_104.png)

Then。There exists a C where C is a course and s like c this would be the correct way where you would also specify the categories of what you are talking about。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_106.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_107.png)

Simply saying。That for all student there exists a course such that。

Like student course would be wrong。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_109.png)

Because when you say for all student， the fact that we are using the name student doesn not mean anything。

 we are simply saying for anything in the domain。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_111.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_112.png)

So， that sentence is really saying that every element in the domain。Likes some element。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_114.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_115.png)

There can be type logics in which we can allow variables to have different types now we will not look at type first order logics but we will look at event calculus later where we will see that we will distinguish between different types of variable so for example time will be one kind of a variable event will be our action would be one kind of a variable proposition or predicate would be another kind of variable we will look at those things later but they are in a higher order logic essentially。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_117.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_118.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_119.png)

One thing that we would also like to do often is to。

Defying categories or or new categories in terms of what we already know。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_121.png)

So one thing one would define。Is so we can create certain classes of elements， right？

Using the relations that they are involved in。 So look at the example of a mother when you want to say x is a mother。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_123.png)

You can define it by saying。That for all x mother x is equivalent to saying that there exists a c such that x is the mother of c essentially so we have defined x as a class or a category and this we have extracted from the。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_125.png)

Binary relation that she is participating in。So， defining categories is something that one must learn to do。

 so I would ask you to define what are even numbers， what are odd numbers， what is a prime number。

 what is a Fibonacci number and so on。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_127.png)

Later in the course we will look at description logics which are logics about noun phrases so they only talk about categories they don't talk about individuals。

 I mean， they do talk about individuals in the sense that your an individual is allowed to be a。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_129.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_130.png)

Member of a category， but they don't talk about variables essentially individuals essentially so they only say that mothers are somebody who whatever whatever whatever like we have defined here mothers are somebody who have at least one child so that would what we would say in description logic。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_132.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_133.png)

They define concepts in terms of other concepts and relations essentially so this the other the statement that we have here could be expressed in description logics as well。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_135.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_136.png)

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_137.png)

So， when you say there exists c， I means there must be at least one。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_139.png)

这个。So， mother is a subset of the domain D says that there exists one role filler is the term we use in description logics for the child relations。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_141.png)

So， we have looked at some family relations and we have tried to define categories。



![](img/3b57bba89c5e9ba28442116d2f6fe6ee_143.png)

We will come back。And move to a different domain。Of graph TV。And。Just see how we can talk about。Gras。

 essentially。Well do that in the next session。

![](img/3b57bba89c5e9ba28442116d2f6fe6ee_145.png)