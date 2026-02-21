# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p39 Recitation_HW1_Trees.zh_en -BV1Z2cUefE4A_p39-

![](img/a8695c14c3d216c8cfe10135e0fe40db_0.png)

Hey guys， so we look at the tree data structure in this part of the CS fundamentalist recitation so we'll be looking at 3。

2 and 3。4 and 3。5 basically those are the questions that count trees so to start with trees as just a kind of data structure it's an hierarchical data structure that is usually used to represent an organized data in a way that is easy to navigate and search so it's essentially just an hierarchical collection of nodes and edges so that is the textbook definition of trees。

Now let's go in and see what makes a tree a tree yeah so this diagram that you see here it's how a tree data structure looks like essentially have like a set off nodes and edges every circle that you see here is a node and every arrow direction which connects to nodes is called an edge so as you can see from this diagram if a tree has n nodes then it has n minus and edges to connect h and every node。

You can also give specific names to each of these nodes。 So essentially if if you look at it。

 like if。Note is connected to another child node， so essentially you can call this a parent node and this a child node because of how the directed edges。

So you can have a lot of these parent child relationships and if you look at all the node in a tree。

 a tree without any parent is called the root node， which is usually at the very top。

 the tree without any child is called the leaf node which is at the very end and in every other node that is not a root leaf node is usually an intermediate node。

So those are different ways you can classify nodes and also there's this relation where every node that's on the same level are called sibling nodes。

 so essentially one full here are sibling nodes and three and eight here are sibling nodes。

So those are the different types of nodes that you can have in a tree and also one more thing is right now we are looking at a tree with with a branching factor of two so from this level to next level we are essentially branching out twice this is specific a special case of a tree you can if you can also have like。

tree with more than two or one bching factor successful well in the general case it's called an an tree here what you're seeing specifically is a binary tree you can also have towards the very end you can have leaf node with just one child and that's a different type of btching factor that you can have there。

So now that we know what trees are there's different ways to traverse a tree。

 essentially depth first search and breath first search are the two options that we'll be covering here and breath search is straightforward essentially what it means is。

You just have this tree and you're traversing the tree at every level like looking at all the nodes in one level before going on to the next level imagine you are in a building you cover every node in the first floor before going to the every node the second floor or third floor one and so forth so in this tree to give an analogy you start at the fifth node which is considered the very first load here then you look at all the node in the second level which is three and eight。

And then you look at all the nodes in the third level and the last level。

 which is all the child notess that you see here。So if and one more thing to notice irrespective for this breakfast search or breakfast search left node always takes precedence over right notes when you write them out in orders so given that we know that if you were to do a breakfast search tra us from the root node which nodes could we see first that's essentially what this question is targeting so if you start for BFs if you let's write it out if you start at5 you pretty much cover all the notes in the first level then you go to the next level so then you see three and then eight so you will see three and then eight。

So then you are covered with all the you covered all the notes and the second level。

 then you go to the last level， so then you'll see one， four， seven and 10。So one，4。

 seven and1 so those are all the nodes that you'd see if you were to do a breakfast search troubleal using industry sorry so now that we are covered DFS let's get into DFS so for DF essentially it's the other way around instead of looking at all the nodes in a given level you'll go along a certain path。

Go as deep as possible， you're doing a depth first search as the。

The term says and then once you exhaust all the notes in the direction。

 you come back and then pursue the next direction so on and so forth。And for DFs。

 I'm sorry and for DFs， you can do this traveral in three different ways。

 suppose let's write a small tree for our use case here。 lets assume let's just we have5。

3 and eight assume we only have these three nodes， let's call this the root node n。

Let me clear that up。Let me redr this， sorry。Suppose we have。A root not fire。

And then we only have two nodes，3。M8， let's call this the left node and right node。嗯。

So we can look traverse this small tree that we have in three different ways。

 The first our order is pre order in this order of traveral， we essentially。Follow the NLR order。

 which means we look at this node that we are in first。

Then we look at all the nodes in the left tree。And then we look at all the nodes in the right tree。

 so we look at n first， which is going to be p， suppose were going to tverssle from。

N5 so well write on5 first then well go through all the nodes in the left which is going to be three and after three there's no child notess in this scenario so we have exhausted all the options in the left three and so we come back to5 we have all returned on 5 so we go go back to the right node which is8 so if you have to do a preorder for us so the nodes you would see in order are53 and8 in similar way if we are to do an in order throw so。

You would follow the L and R order， which means if you start at5。

 you don't immediately look at5 where instead you go down the left path。Which in this case is three。

 so you write on three first and then you come back to five you haven't returned on five yet。

 which means you haven't troubleverse to five yet and then write on five and then you finally go to the right node and then you see。

8， so this is the order of the notes that you'd see if you were to do an in order traveral and finally。

 if you were to do a post order traveral。So。In post order， you would follow an L R N order。

Which means you first go to the left node as before， so you see three first。

And then when you come back， you don't immediately see5。

 but instead you go down and exhaust all the options to you the right。

 which means you would see eight and then you come back again。

 so youve exhausted all the options the left and right three and eight。

now you write down the node that you're at which is now5 and says5 so these are three different ways in which you can traverse a decision tree in the def first search approach here' is very simple because just like one root node and then two default nodes with zero interior nodes and these are the essentially three things the need to keep in mind the shorthand for doing preorder in order of post orderder tra cell。

As the name suggests pre in and post it just shows the position of the note in the traversal that you do so now that we know this how preoring node and post or trareversor works。

 let's apply it to this tree。If we do pre order traveral we first with five。

 then we'd go down this throat， we'd visit three， then we'd go down this throat again， with one。

 come back。And then we four and then we will come back again。

 we have already visited three so we only tried that down， we've all visited five。

 we only tried that down so now we go to the right part of the tree which is eight。

And we write down eight。And then again， we go to the left part of this sub， which is seven。

And then finally1。 So this is the order of the notes that we visit in。Preorta。 Now， let's do。

In order and post order。Similarly。So in order you would again start with phi but you wouldn't write on phi in the beginning because you want to exhaust L first before n so you' would go down3 and3 is still not the leftmost node that you can possibly get into because you have one which is left or leftmost than three so you come down again and then so you write out one and then once you're done with one you go back and then now you have three but I'm sorry now then you can write on three and then youd go ahead and exhaust your right option I mean the right sub three which is four and then now you are done with all these three nodes you go back and then you write on phi。

And similarly， then you go down。eight， you still have a leftmost tree that is pending before you can write down the interior node。

 so write down seven and then eight and then10。So that's pretty straightforward following the same approach as before。

 so that is what that is a lot of words that you've seen in order tra usle。And post order travel。

Similarly similar like before so you just follow LrN approach so again you start from5 but you would want to exhaust the left tree before writing the current node or the right node so you would come down to three you come down to one and if you follow that LRN criteria you will see the nodes in one and then four and then three so you would want to go like this and then you would see。

7 and then 10， and then 8 before finally coming back to the root node 5。

 So the root node is always the last in course order， like you see 5。

Yeah so those the nodes that you'd seen in the three trasal approaches。

 so what is the time complexity of all these different traverss that we saw we saw one in BFs and3 in DFs it is all often because you're looking at all the trees and all the nodes in the tree one at a time so it is well it a number of nodes in the tree。

So that is 3。2 now let's move on to 3。4 so we were looking at binary trees before now we are looking at binary search tree binary search tree is just like a special I mean its it's just binary trees with one more constraint the constraint being like if you had a binary tree say for example。

Excuse me。 say， for example， if you had we。And then A， and then C。Or we can follow the。

Same convention as before。 So it's easier。 So if we had N。

And then L and then R suppose we had a subree like this this binary tree is called a binary search tree which sat the criteria that n is always greater than L which is the value the node is always greater than the value in the left and it is。

Less than or equal to the value in the right。So it's kind of balanced that way。

And the same as what is said here。 Each nodes value。嗯。Strictly greater than。

The value of the node to its left and less than or equal to the value of node to its right。

So that' what that's what makes binary tree or binary search tree。

Now that we know what a binary search tree is， which is a binary tree with one more equality constrain on left and right nodes。

 we need to go ahead and fill this function， it is essentially just an insertion subprooutin method in this BSA class that we have。

😊，So we in the constructor we have just this value which is the value at that particular node and we have this insert method which takes in a value and returns the sort object at that point so given that we know that these are the two constraints that makes up a binary search string we just use that to write down these A B C D E blanks over here and we can also leverage the fact that the constructor itself defines these values for the PSD class we can leverage that for filling in。

These values now let's go to the insert function so theyre asking if value blanks if not well so we know we have to go left if we are going to left it means the node value is greater than left and here they're asking the e relation of value with respect to the node value so which means you have to a is going to be let me take blue here。

It is less than self taught value。 That is the value of。So whenever our value is less than top value。

 which means like strictly less than。The node value then we go into this f plot。

 which means if it's scaled or equal to we are going into the right block now if you're checking if self or left not left notice none so there's two scenarios once we are going into the left block so either we have a decision tree I'm sorry we have a tree like three。

And then， to。Let's say this was fine and suppose the value that's coming in is one you're looking at three here I suppose you are trying to insert a value at this two here and after two there is no child notes at all。

 which means you you can just directly insert one， but you cannot be just a direct integer value it has to be this。

BSD class object。 So you just。He use the BST class to initiate an object and then assign assign it to self do node。

 so V is going to be just VSing。Of value。So we can automatically use this built in constructor to assign that value and then return that so here you would have this one in the leftmost loop if instead if instead of one。

Its this。Yes。Instead of one， suppose the value that was coming in was 2。5。

So then you'd have to insert this node over here， which means then you'd want to take care of it by handing it with a recursive call。

 so you would want to call this is the scenario where the left node is not none like you're trying to insert it here。

 the left node is alreadyvalue which is two so you cannot just directly use it。

So you can just call this insert function and that insert function will take care of。

Inserting it in the recursal clause， so you can just do self taught left node。Do insert。哦。Value。

So that those are the two blacks for the F condition and L condition is again going to be the same it's similar to the left block so if the self not right notice none we cannot directly assign it we need to create an object to assign it so we just save BST of value。

And if it is not none， which means there is already a node object there。

 then you want to handle it in the recursive call。Selft。Right mode。Do。Iner。哦。

Value yeah so that is how weve inserted in this PSD for this particular function and now let's move on to the next question which is we have already being given with the sorted list that we see here essentially this is the sorted list that we're provided with and we want to complete the recursive Python function below that will take this list and create a binary search tree with the minimum height possible okay so given we all know that this free sorted we can write a binary search tree that is not necessarily the most efficient that it's not necessarily the one with the minimum possible height。

Essentially you can write a tree that starts with one and goes to two and from two you go to p and likewise you go all the way to 22 so this is still a binary search tree there' is no left nodes in any of these nodes but the height of the tree is going to be the length of this list and it still satisfied the conditions that the right node should be greater than equal to the left I in the parent node and the constant right the other way around which is just writing in a dising order with all the nodes on left but this is not necessarily the binary search tree with the minimum possible height so if you want to go a possible height the way to do it is to balance the tree such that there's equal number of nodes in the left tree and the right tree。

So essentially having a parent node， and then having。Child node， I mean left node and right node。

 which again has a set of left node and right node。

 so that would be the ideal way to write a minimum。

I mean a binary has shape the minimum possible height so given that you know we want to balance the tree。

 we would want to start then from the middle of this sorted list that is essentially the trick to solving this question。

And now that we know that let's go and solve I mean clean the plans and usually for recursion problems。

 not only for this for any recursion problems， it's easy if you like。嗯。

Normal case that you want to handle during your question。

And then you can come back to the base case later it's easier to solve it that way。

 So let we'll come back to A B at last and then we'll try to solve the other blanks first。

 So minute is just finding the middle element given that we know this is the list。

 we want to find what of the middle element which is going to be。

The length of this list divided by two。 so nus is the list that's being founded here so you can write it's going to be length of。

Nms is going to give us a length of the list in Python and you can get the integer。

Value of it by diveriding by  two。 We don't want to float index value because we're going to use this index for indexing data。

 It won't have intention is。 So we're going double slash by 2。And if you know the middle value。

 then the root value is just using that to index from the nuMS list and we'd want to assign an object not the value directly so we need to use the its construct again like before。

 so we just use BSing。Of。Nouns of。Gent。So we index the middle value and create a binary using that as the root so now that we have figured out the root。

 let's just go ahead and figure out the left node and I mean the left norms and right norms。

 which is just essentially getting the。So in essentially getting the left half and right half of the list。

 so in this particular list that we are seeing。😊，And the middle element is going to be 10。I'm sorry。

The， middle element is going to be 10 and then you have this four elements on the left and。

The other four elements on the right。 So you would have。10 as a root node。

And then you want to get the other list of elements on the left。And again。

 you can use Python indexing for this。So， it's going to be。Nos。Of。Meed。

And I again one more thing to note is at in Python if you're using a mid index like this。

 I mid was four， then youd get the element still the fourth index you would get0，1，2。

3 that's how Python this work so that's how we get the left half of the。N less that we started with。

 if you want to get the remaining elements then， then you want to start I mean write it as。Nos。哦。

Med class  one。And the index to the end so that is just the other half of the list that is going to be assigned to right notes Now that we have the two sub list that we water。

 we can just make a recursive call to get the left node and right node essentially want to fill this half and this half。

With the two sublets that we have。So then if you want to just make a recursor call。

 you can just call the function again， which is just。嗯。Hide。Bsing of。Left armss。 and again。

 here it's going to be。嗯。Rightight。Weing。哦。Right mouse。So。

We know the root note is 10 so in the recursor call for left nus its which is going to be 1257 if you call the recursor list again you would find the midpoint of that sub list so the midpoint of that sub list with one。

2 phi7 is going to be5hi and so youd have5 in this particularicular node before you recursively call the remaining list again so if you go out and fill it youd get two and then seven here and then have to handle one at last based on the edge case so we un out A and B which is the final base case for this recursive function。

嗯。So there is going to be a point where once you are two and7 one is going to be left hanging so essentially nus is going to be a list of one element where the value is one so if the length of that nus is one will come into this。

Base case， we there's no point in doing this recursive split again。

 we only know that we know there's only one list so we can just directly add it as。

The child of this particular note that we are currently at in this stack race。

 so you can just directlyly write Pesteeem。哦。谂嗯。喂但。嗯。No。Bing of。Nuns of0。

 so that is going to be the base case one so then of norms is0， which is the first base case。

 then we essentially don't want to assign a new object when we don't really have any value to begin with so then we can just assign none as it is。

So what is none doesn't mean doesn't have it has no child like here。

 so we just assign none back and skip that call。So we already if based on the base case。

 we just un through， so you'll have one over here。And。We look at the remaining list 1314。

1422 that's going to be filled as again， we look at the midpoint of that list。

 which is again going to be 15。And again， you fill 14。嗯，所以但系附天。And 22 here。

 And then you are going to have one more child node here， just 3。😔，Yeah。

 so basically that's binary search trees。

![](img/a8695c14c3d216c8cfe10135e0fe40db_2.png)

Let me stop the recording yeah。