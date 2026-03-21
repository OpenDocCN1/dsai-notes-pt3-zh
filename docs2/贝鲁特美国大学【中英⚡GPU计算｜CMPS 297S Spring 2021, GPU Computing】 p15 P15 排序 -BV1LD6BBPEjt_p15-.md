# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p15 P15 排序 -BV1LD6BBPEjt_p15-

![](img/fa5c4ccd173ce13f38f29f47826212d2_0.png)

Hello everyone and welcome to Le 15 of GPU computinguting today we're going to be talking about sorting。

Oh。Last time we spoke about a one parallel pattern which was merge。

 and we said that an ordered merge is an operation where we take two ordered lists。

And we combine them into a single ordered list， and we said that in order for us to paralyze this operation。

 one way to do it is to divide the output list that we are about to generate into equal segments and give each thread one of these segments。

And then each of these thread needs to find the corresponding input segments in the two input matrices input arrays A and B and merge those two input segments sequentially and we the key challenge and doing this parallel merge is basically how does each thread find the corresponding input segments in A and B now to do that what we said is you know given an index K that points to an element in C or the beginning of a segment in C the key challenge is how do we find I and J that points to the corresponding elements in the corresponding segments in A and B and we call these d co ranks so we said that I here is the core rank of K and same thing J is the core rank of K in the arrayB and we observed that J is simply K。

It eyes so the real trans was just finding eye and what we did is we set a bound on eye we and then we said that given this bounds。

 we do a binary search in this bounds and we determined the condition。For when our guess is correct。

 when our guess is too high and when our guess is too low and these conditions were based on the observation that the element before I and A should be less than the element after J in B and similarly the element before J and B should be less than the element after I inside of a。

😊，And then so basically each thread that takes a segment will do a binary search to figure out I and then correspondingly find J and then just does a sequential merge of the two input segments into the output segment。

The memory aes for this operation were not coalesced because when we do a binary search。

 we're doing a random access into our array so we're not gonna to have coalescing but also after we do the binary search and identify the co rank when we come to do the sequential merge each thread is merging a different input segment in the input array so the aes during this merge are also not coalesced so to do that the optimization that we did is to figure out the blocks the segment for the entire block by one of the threads in the block and then the threads in the block will collaborate to load that segment into shared memory in a coalesced way and then we do the binary searches of all the different threads inside of shared memory and then we do the merge of each thread inside of shared memory and then we store the merged array from shared memory to global memory also in a coalesced way and that looked like this so here one of the threads in the center block will determine I blocklock and J block。

That corresponds to the K block segment and then the threads will collaborate to load the i block and the J block segments to shared memory here As and BS and then each thread will find its own each thread will determine its own output segment and figure out the the coreex in the input segments inside of shared memory so here one thread well find the I J to correspond to its K using a binary search and then this thread will do the sequential merge inside of shared memory and then when all the threads are done merging inside of shared memory we go back and we store we store from C to C at K block in a coalesced manner so this is the optimization that we did in order for us to have coalesced memory aes we loaded in a coalesccent manner to shared memory did the uncoesced aes inside of shared memory and then stored in a coalesccent manner back to global memory final thing I forgot talk about last line is thread cosing so what is the price that we pay。

To paralyze merge in this case， well， the price that we paid to paralyze merge is that every thread。

Needs to do its own binary search。 So the more threads we have right the more binary search operations we're doing So the advantage of coing is we have fewer binary searches and in fact。

 we already applied thread coing by assigning multiple output elements to each thread So in our in our previous merge we were already assigneding multiple output elements to each thread。

 we could have paralyzed it in a way where every output array received once every every output element was assigned to one thread and then every we do a binary search for every single output element。

 but what we did instead is we actually assigned every thread to a segment of the output and so we've already applied thread coing by assigning multiple output elements to each thread Now we could have assigned a single output element to each per thread like I said in this case。

 the output segment would have had length one。 The reason we didn't do that is this would have been slightly less intuitive to。

😊，It easier it's easier to explainrg merging you know multiple segments than merging two segments where the output has size one so this is part of the reason why we explained it with coalescing already applied and another reason is that we did have a shortage of time in the last lecture。

So again， the price of parallellyization here is the cost of performing binary search so by not assigning each thread to a single output element but assigning each thread to multiple output elements per then what we do is we amortize the cost of binary search over larger input segment okay so this was a kind of a quick overview what we covered last time and today we're going to start talking about we're going to talk about sorting and we're going to look at two sort algorithms we'll spend most of the time talking about Radix sort and then we'll talk a little bit about merge sort before I begin talking about sort does anybody have any questions about what we covered last time before I move on talking about sort。

😊，Okay， well， if there are no questions， then let's begin talking about sorting。

So we'll start with Radix sort and like I said， we're going to spend most of the time looking at Radix sort and then we'll look a little bit at merge sort towards the end so what is Radix sort。

Radix sort is a sorting algorithm where the way it works is we distribute the keys that we're sorting into buckets based on a radix or a base。

 so if input is the input keys are represented in some base in a positional numeral system。

 then we use that base and we iterate over the digits and every iteration。

 we distribute the keys into buckets based on the radix。😊。

Distributing the keys into the buckets is repeated for each digit in the key and one important thing is that for every iteration。

 we should preserve the order from the previous iteration within each bucket So this is important and I'll show you why this is important。

 and usually when we do raix sort in computers we like to use a rads that is a power of two because that simplifies processing binary numbers right because we're iterating over the digits in the key So it's easy to slice the key into multiple digits where the digits are our slices of a binary number and that's why we like to use powers of two So each iteration is going to handle a fixed slice of bits from the key Now to keep things simple and for the ease of illustration。

 we're going to start by looking at a radix of two。😊，Okay， in other words。

 we're going to start looking at the case where our radix is one bit and then we're going to extend this later on in the lecture Okay。

 so we'll start by demonstrating Radix sort using one bit one bit radix and then we'll extend it。😊。

Okay， so let's get started。 So if I have this array over here。

And what I would like to do is I would like to sort this array。

Then what we would need to do is we would need to divide this array into bits and iterate over the bits one bit at a time because we're using a one bit radix okay and every iteration what we will do is we will divide our inputs into buckets based on our based on our radix so somebody is asking isn't Radix sort a non-comparison based algorithm yes。

 so Radix sort is a non-comp based algorithm as we will see and that's why we're going to cover merge sort and Radix sort merge sort is comparison based and radix sort is non-comparison based。

😊，Somebody is also asking if these elements need to have a fixed size so yes usually if we're sorting we're going to assume that our key needs to have a fixed size so that we can divide it into digits so if we're sorting 32 bit integers then that size of our integers is obviously going to be 32 bits in general if our keys don't fall into this category then we would need a comparison based sort and that's why we're going to look at comparison based sorts we're going to look at merge sort towards the end so yes we will look at comparison based sorts but we're starting by looking at radic sort which is an noncompar based sort so thank you for that question。

😊，Okay， so what we said is the way Ra sort works is we're going to start by looking at one of the bits。

 we're going to look at the least significant bit okay， and the least significant bit of each number。

 you know some of them are going to be zero and some of them are going to be one。😊。

So what we're going to do is we are going to separate our keys so these are our keys and we're going to separate our keys into two buckets based on the first bit or the least significant fit so we're going to put all the zeros together and all the ones together Okay so we're going to do this we're going to put all the zeros here at the beginning and then we're going to put all the ones after all of the zeros and after we do this now what we have is we have the array is sorted by only the least significant fit。

😊，Okay， and now what we're going to do is we're going to repeat this process。

 but every time we're going to look at a different bit and we're going to go from the least significant bit to the most significant bit。

 So on the next iteration we're going to look at the second bit and next what we're going to do is we're going to separate the key is based on the second bit。

 So now second bit we have some of them are zeros and some of them are ones so what we will do is we're going to put all the elements whose second bit is zero together and then we're going to put all the elements whose second bit is one together。

😊，Okay and one important thing over here is that when we are separating when we are separating the elements whose second bit is0 from the elements whose second bit is one。

 we are maintaining the the original order within each bucket so the order of the elements inside of this bucket is the same as the order of the element in the original array。

 meaning that this first element who that had a second digit as zero came first here。

 the second element who had the second digit bit being zero came second。

 the third element with the second bit being0 came third right we can't take this element and put it here and then take this element and put it before it and the reason is that if we did that we would mess up the order that we got from the previous iteration so the previous iteration sorted the array by the first bit now the second iteration sorts the array by the second bit while preserving the order from the first iteration and what that does so preserving the order from the previous iteration within each bucket。

😊，What that does is that it ensures that the keys are now sorted by the lower two bits。Okay。

 so now if you look， our keys are sorted by lower two bit。 So we have 0，0，0，00，0，0，0。

 And then when we're done with the00s， we're gonna have 0，1，0，1，0，1，0，1。 when we're done with the01s。

 we're gonna have 10，1，0，10，10。 and then when we're done with the 10s， we have 1，1，1，1，1，1，1，1。

 So by preserving the order now we have an array that is sorted by the lower2 bits。 Okay。

 and then we do the same thing on the next step。 So on the next step。

 we're gonna look at the third digit now， So the third digit。

 we have some of them are ones and some of them are0s。

 So we're gonna do is we're gonna separate the keys based on the third bit。

 So we're gonna put the elements whose third bit is 0 here and we're gonna put the elements whose third bit is1 over here。

 And again， we're gonna preserve the order。 So now if you look our elements are sorted by the lower  three bits。

 So here we have00，0，0，0，0， then we have 0，0，1。😊，001 then we have the0，10s together。

 then the01 ones together then the100s together。 the10 ones together， etcter。 Okay。

 so the keys are now sorted by the lower three bits。

 And the last step is to sort them by the last bit。 So now we look at the most significant bit。

 the fourth bit。 And what we do is we separate the elements based on the fourth bit。

 So we put all the elements we separate the keys based on the last bit。

 so we put all the elements whose last bit is zero together and then all the elements whose last bit is one together and now we have a sort and array。

 So this is how radix sort works Okay I assume that a lot of you have covered radix sort in a previous course on algorithms。

 But this was just to refresh your memory on how radix sort works next we're gonna talk about how to do it in parallel。

 But before I get into that does anybody have any questions about radix sort。😊。

So somebody is saying how do you preserve the order without comparing so right now I'm not talking about how we do this I'm I'm about to talk about this。

 but the keyith the point is that what we would like to do is on every iteration we would like to separate the elements based on the bit that we're interested in search that we have all the zeros together followed by all the ones while preserving the order this is what we need to do how we will do that is something that I will discuss next okay but is what we need to do clear to everyone。

😊，Okay， so then the question is， which you guys have already asked in the chat。

 how do we separate the keys based on one of the bits？And of course， while preserving the order。

 Okay how you know， I can do this in multiple iterations。

 So really the most important question is how do I take this input array and separate all the elements whose bit I'm interested in is zero。

 put them to the left and then put all the bits all the elements whose bits are one to the right Okay。

 I'm going to zoom in on this and what I want to do is my problem now I've reduced it to taking an array and separating the elements whose bits are0 to the left and and the elements whose bits are one putting them also together on the right and again。

 while preserving the order Okay， now how to do it， the key question here。

 how to separate the keys is how do I find the destination index of each element。😊，Okay。

 for each element， I want to take it from the original array。putut it somewhere in the new array。

 the sorted array， right， I want to take this element at position 0。 I want to put it in position 0。

 I want to take the element of position 2， put it in position 1。

 I want to take the element at position 1 and put put it in this position。

 I think this is position 8。 Okay， so for each one of these elements。

 what I need to do is I need to find where what its destination index is in the sorted array。 Okay。

 so the real question is， how do I find the destination index of each element in my input array。😊，ok。

😊，Well， let's， let's think about this。 Let's let's take a look at how we can do this。

So the destination， let's first look at our zeros， the destination of our zeroes。

Is going to be the number of zeros to my left right so here the first zero。

 the destination of this first zero is going to be zero because there are no zeros to its left。😡。

The destination of the second zero is going to be one because there is only one zero to its left。

The destination of this third zero well this one is going to go to the third position in the destination array because there are two zeros to the left right so this is going to go on position zero。

 this goes in position one， this goes in position two because we have two zeros before it。

 this goes in position three because we have three zeros before it， etc。😊，Okay。😊，It's a scan。

Well we'll get to that， yes， so as you observe you can see where we're heading。

 we're heading towards scan exactly。Okay， but let's formulate it a little bit first and then we'll see how we can use scan to accomplish this。

So the destination of a zero is the number of zeros to the left of the zero。Now。

 the number of zeros to the left of the zero。Is also the number of elements to the left of the zero minus the number of ones to the left of the zero。

Right。Because the elements on get to my left are either going to be zeros or ones。😡。

So the number of zeros to my left is the total number of elements to my left minus the number of ones to my left。

😡，Okay， so for example， this zero over here is in position， you know， 0，1，2，3，4，5。

 so this0 is in position 5， so this zero has five elements to its left。Okay。

 I can say that the position of this zero is2 because it has two zeros to its left or another way to figure out that this element has two zeros to its left is to count the number of ones to its left。

 which is one，2，3 and since I know that this element is in position five I know there's five elements to its left so I do five elements minus three ones that gives me20。

ok。😊，So the number of zeros to the left is the number of elements to the left。

 minus the number of ones to the left。And the number of elements to the left is just the element of the the index of the element。

 right， This element is at index 0 and it has zero elements to Islam。 This element is at index 1。

 It has one element to Islam。 This element at index 2， it has two elements to Islam。😊，Okay。

 so the number of elements to the left is basically the index of the element。

 so basically the destination of a zero is going to be the index of the element。

Minus the number of ones to the left of the element。That's going to be the destination of the zero。

Okay， clear。Questions。Okay， now let's look at the destination of the ones。

 so the destination of a one is going to be the number of zeros in total。Plus。

 the number of ones to the left。 So for example， if look at this one over here。

 where is this one going to go， Well this one is going to go after all of the zeroes。😡。

What about this one， This one is going to go after all of the zeros and this one over here so the destination of this one is the total number of zeros because we're going to put all the zeros first and then we're going to put this one and then we're going to put this one so this one is going to be the position of this one is going to be the total number of zeros in the whole array okay plus the number of ones to the left which in this case is one where this elements is going to be the total number of zeros plus the number of ones to the left which in this case is two we're going to put all the zeros and I'm going to put these two ones and then I'm going to put this element。

😊，Okay， so by doing this， by finding the total number of zeros in total plus the number of ones to the left。

 this is what helps me preserve the order。😡，Same thing here by the way。

 when I do I count the number of zeros to my left， this helps me make sure that I stay in the right order and I don't interfere with the zeros to my left and go behind them。

Okay， so the destination number one is the number of zeros in total plus the number of ones to the left。

Now， the number of zeros in total in the whole array is going to be the number of elements in the whole array minus the number of ones in the whole array。

 Okay， so the number of zeros in total is going to be the number of elements in total。😡。

Minus the number of ones in total。Okay。😊，And then the number of elements in total is basically the size of the input array。

 which I should have。And the number of ones in total is basically the number of ones to the left of the Ask。

Okay， the number of ones to the left of the last element。Okay。

 well not necessarily if the last element was zero。

 it's going to be the kind of the total number of ones so but the point is that by figuring out the total number of ones to the left of each element。

 I can figure out the number of ones in total。Okay。

 so then the destination of a one is the input size minus the number of ones in total plus the number of ones to left。

So here what I've done is I've defined the destination of a zero in terms of the index of the destination of a zero element in terms of the index of the element which I trivially have and the number of ones to the left of an element and I've defined the destination index of a one in terms of the input size which I trivially have and the number of ones to the left of an element and the number of ones in total which I automatically get when I find the number of ones to the left of each element okay so really the remaining problem here is to just find the number of ones to the left of each of the elements inside of this array if I can find the number of ones to the left of each element inside of this array。

 I can then easily con find the destination of each zero element in the array and the destination of each one element in the array。

😊，Okay。So if I want to find the number of ones to the left of each element in the array。

 what pattern have we seen before that allows us to do that， somebody has already said it。😡。

An in exclusiveclusive scam。Right， an exclusive scan exactly。 So if I want to find。

 if I want to count how many ones are to my left， I can simply do an exclusive scan that does this count for me。

 So I will use an exclusive scan。Okay， and by the way we're not going to write code in today's lecture just because most of what we're going to be doing is based on patterns that we've already seen before and that we've already implemented before。

 implementing sort is basically putting together a bunch of previous patterns that we've seen so that is why I'm not going to be implementing any code just for the sake of time for today's lecture。

 but we're going to be basing it on patterns that we already saw and we already know how to implement。

Okay， professor， yes。Since we since we're putting things in a bin two bins so isn't it a bit similar to the histogram so we can paralyze it maybe this no it's different in histogram we're not putting things in bins we're counting things so in histogram each bin just is counting how many elements fall into that bin over here we're not we're not counting we're actually moving things around and placing them physically inside of a location so we need to calculate the location that we need to place them in。

Okay， thank you。 Yeah， you're welcome so we're not we're not just counting elements。

 we're actually placing elements physically inside of different buckets。Okay。

 so then so now basically what we need to do is we have to figure out the number of ones to the left。

 once we have the number of ones to the left of each element。

 we can find the destination of our zeros and the destination of our ones。So let's do this。😡。

So here I have my， my array。 Okay， I have the bit that I'm interested in in each year。 in this case。

 it's the first bit， but this could be the second bit。 It could be the third bit。

 It could be the first bit， et ceter。 The first step is basically to extract the bit that I'm interested in。

😊，Okay， so for this zero， I'm just going to have a zero for the ones and I'm just going to have a one I're just going to have an array of zeros and ones。

Now this array is going to tell me if something is a one or not。😡，Now。

 if I want to calculate that for each element， the number of ones to the left， what do I do？😡，Well。

 simply， I'm going to do an exclusive scan on this array。 If I do an exclusive scan on this array。

 what now I what now I have is the number of ones to the left of each element in this array right over here for this element。

 This one has one to its left。 How do I do that。 How do I figure that out。 Why I simply add 0 and 1。

😊，Okay， and that tells me that this element has a total number of has one， one to its left。

This element has one， two， three ones to its left How do I know that well。

 if I simply add all the all the zeros and ones before it。

 I have one plus one plus one that's three Okay， so I figure out that this element has three ones to its left Okay。

 etcter。Okay， so I extract a bit， I do an exclusive scan and this exclusive scan tells me the number of ones to the left of each element。

And then once I've done that， what do I do while I simply apply I use the expressions I derived earlier to find the destination of each zero element and the destination of each one element。

 the destination of each zero is going to be the element index minus the ones to the left So for example。

 this zero element is going to be that the index of this element which is five right， 0，1，2，3，4。

5 minus the number of ones to the left which is three。

 so that's how I find out that the destination of this element is two。Okay， same thing。

 same thing for all the other zero elements。As for the ones。

 the destination of the one is going to be the input size minus the total number of ones plus the number of ones to the left。

So for example， this element over here。Okay， we know that this element has two ones to the left， one。

 two， and we also got that from the exclusive scan。Well。

 my total input size is 16 in this case and the total number ones I have in the whole array is8 right I got that from the end result of the exclusive scan okay。

 so 16 minus8 is8 that means I have eight zeros and then I simply add two to eight to figure out that this element should go at position 10。

😊，Yhy 10， because I have8 zeros that need to go before this element。

 and then I have two ones that need to go before this element。 So 8 plus 2 is 10。All right。

 is it clear how I found the destination of each element using exclusive scan。

 any questions about this？Doctor， the partial sum of know the number of total number of ones it can be9 here。

 know if the last element was one said since it's the exclusive scan set。

 I would need the partial sum， right， not the last What you're saying is what you're saying is I will also need the total sum。

 after I do an exclusive scan right， So this was a one over here then I would have a9。

 So if you remember when we did the exclusive scan， we actually had the total sum we found it。

 we put it aside because because we we were not we were not going to use it immediately。Okay， so yes。

 we do need the total sum and when we do the exclusive scan we are going to find the total sum and we're going to remember it so that we can use it。

 you're absolutely right。😊，Okay， so the only point that I'm making is that I don't need to do a separate operation to find the total number of ones by simply doing the exclusive scan。

 I can find the total number of ones on my way。Okay。😊，Clear。All right great。

 so then once I find the destination of each input if each input element。

 then simply what I do is I take each of these input element and store it in the output array at its corresponding destination so this element I found that its destination is zero so I take it and I store it at point position zero for this element I found the destination is8 so I take it and I store it at position 8 for this element I found the position destination is 12 so I take it I input it at position 12 for this element I found that the destination is 5 so I take it and I store it at position5。

😊，Professor， can you repeat how we got the destination today。Yes， can I repeat how okay。

 do you mean I can I repeat how I how I derive these expressions or do you want to repeat how should I repeat how I did be extracted within an exclusive scan No。

 just just that step， I understand how we got number of ones to the left。

I just I didn't make the connection between those do you understand how we got so these are these are the two expressions that we used to get this array right we checked't understand。

We apply the first expression if this is a one， we apply the second expression。

 so as your question how do I arrive at these expressions？No how we got the destination already。

Is we just apply the expressions yeah， we just apply the expression so if something I have if I know something is zero or a1。

 if it's a zero， I apply this expression， if it's a one I apply this expression。Professor。

 can we repeat how we derive the second expression， the destination of the one。Yes。

 let'ss so you want me to repeat how how we arrived at this expression for the destination of O。

 so let me repeat that。Let's second when me go to the slide that I want。Okay。

 so we said that the destination of a1 is the number of zeros in total。Plus。

 the number of ones to the left is this part clear。Yes。

The number of zeros in total is the number of elements in total minus the number of ones in total。

 is that part clear。要。Okay， and then the number of elements in total is basically the size of my input。

Okay， and then then that's。The size of my input， minus the number of ones in total plus the number of ones in the right。

哦。And we just array so we can get the destination。Yeah。Okay。😊，Thank， thank you。

So thats how we arrive at the second expression and you know once we have the destination。

 we can simply store the element at the destination that we care about。Okay， by the way。

 this may not necessarily be the best thing the best approach at doing it sequentially。

 but I'm explaining an approach to doing Radic sort and then we will talk about how to paralyze this。

Okay so yeah so somebody's asking about about shared memory and global memory all these things。

 so let's let's hold on you know i'm not talking about paralyzing I'm just talking about a logical approach to doing this and actually next step I'm going to talk about paralyzing so that brings me to my next step so how do we paralyze this。

Well extracting the bit is quite so simple right we know how to do paralyze scan here we're just applying an expression to each element in an array。

 so we know how to paralyze each of these individual steps Okay so to paralyze this what we can do is we can simply assign one thread to each element in our input array。

Okay， and we already know how to paralyze scan and the rest is just is trivial。

So we assign a thread to each element in our input array。

 each of these threads will extract 0 or1 for the element that it is responsible for the threads will collaborate to perform an exclusive scan we've seen how to do that and then each thread will find you know the destination index of its element based on whether its element is a zero or a1 and then once each thread finds the destination of the element that it is responsible for the thread takes that element and stores it in the destination array okay。

Is it clear how we paralyzeize it？香 point啊。Yes， but a professor。

 I had a question on on this since we're using only one bit of。Like with the comparators。

 are we using 32 bit comparators to compare one bit？

So we're not doing any comparison here right this is to add I mean， yeah。

 we're not doing comparisons， but like to add zero and one to do the exclusive scan。We will be using。

ISo you can use a bit wise and operation to extract the one bit that we care about。Okay。

 then based on that bitwise n， if you' get a 0 or a1。

 you would store0 or1 as an integer here so that when you do the scan。

 you actually you're going to need to sum these。Oh， I see okay， and the end is just for one bit。Yeah。

 so you can extract if you have a 32 bit number， for example。

 and you want to extract one bit in that 32 bit number， you can do that using a bitwise M。Right。

 but that will that won't that be a 32 bit gate where like we use a 0001 as a lake I mean how how the hardware does it is is kind of is a different issue right but yes。

 there will be an AOU in the hardware that's going to do a a bit wise and operation。喂。I see。

 but it's not like the number is trimmed to be1 bit it's still 32 bits。

 but we're just extracting by using it by doing an end right Yes， yes。

 so the number 32 bit integer or it could be a 64 bit integer it could be a 16 bit integer and8 bit integer right maybe we're sorting characters Okay so this could be any any number of bits。

Okay， but we're going through it one bit at a time， okay。

 so in each it we don't use a bitwise n to extract the specific bit that we care about。I see。 Okay。

 thank you。 Yeah， yeah， you're welcome。Okay， so now we've we know how to paralyze Ra sort Okay。

 so as we've been doing all previous lectures， once we learn how to paralyze something。

 the next step is to observe what is not efficient about what we're doing here and how can we optimize it。

So what's not efficient about what we've done so far？So extracting the bit。

 that's embarrassingly parallel right every thread is doing its own operation without without affecting any other thread as a local operation。

Scan we already looked at how how to optimize scan and then given a number。

 you're just calculating what it's a zero whether it's a one， so that's straightforward。

 but then you have to take these values and you have to store them into the destination array。

Okay so I guess my input here is is in global memory right and my output is also going to be some global memory array right so is what is going to be inefficient in this entire procedure。

The stories are not coalesced。Right exactly the stores are not coalesced。

 So after all these threads finished doing all this stuff。

 we're going to have this stage where all the store all the threads now are trying to store to arbitrary locations in the destination array and just to emphasize that。

 if we look at this first thread block over here again obviously thread blocks are larger than four threads。

 we're going to have maybe 1024 threads and you know a warp is 32 threads。

 but we'll just have you know four threads for simplicity here Okay。

 you'll notice that this first thread is storing to this location here。But then the second thread。

 which is most likely going to be in the same warp， is storing all the way over here。

And then this third thread comes back and stores over here and then this fourth thread comes and stores all the way over here Okay。

 so our aes are our stores are not coalesced you know each the adjacent threads are going to very distant locations in global memory。

All right。So the challenge here is that the stores are not coalesced because nearby threads right to distant locations and global memory。

So， having observed this， what can we do to optimize coales？

Make threads responsible for output elements， instead of input。

So we want to make threads responsible for output elements。

 but that's a little bit difficult right because if you make a thread responsible for an output element。

 how's the thread going to go and find the input element that it's responsible for？😊。

That's quite challenging。Yes， I'm just giving idea。No， it's it's， it's a。That's a worthy idea。

 thank you for suggesting。What if we birthday array， but that will require an uncoesed access。Right。

 so somebody is saying what we can do is we can。Sot locally in shared memory and then write each bucket to global memory in a coalesced manner。

 So if look at over here these threads that are in this block。

 even though their aes are not coalesced， they're all over the place。

 if you look at the total amount of global memory locations that this entire thread block is writing to。

 youll notice that we have we have two kind of distinct location。

 we have the zeros that are being written to the zero bucket and we have the ones that are being written to the one bucket。

Okay， so as one of you suggested， what we can do is rather than writing out these zeros and ones in an unalestic global memory。

 we can separate the zeros and ones locally in shared memory。

 and then we can write the zeros altogether from shared memory to global memory and the ones altogether from shared memory to global memory。

😊，Okay， so this is what we can do to improve the coalesescence。Okay。

 so let's see what this would look like。 So what we will do is we're going to start by sorting locally so the threads in this block right。

 they will take their elements and they will split them inside of shared memory。😊，Okay。

 and all the other thread blockss will do the same。

 each thread block will have its own shared memory array that it will use to split the threads。

So time to split the elements。And now that I' have done this with within each thread block。

 within the shared memory of that each block is accessing my my zeros are not together and my ones are now together here。

 my zeros are together， my ones are together， here my zeros are together， my ones are together。

 my zeros are together， my ones are together。😡，So now that we've done this。

 the next question is now each thread lock wants to come and take its zeros and put them in global memory and take its ones and put them in global memory。

Okay， by the way， there's another benefit of doing this because because well yeah the main benefit is that we are separating the zeros and ones or we're doing our uncoes ases to shared memory Also here we're just doing a scan locally now and in order for us to do the separation right remember because if for us to do the separation we need to do a scan so now the scan right is being done locally within the thread block okay but we will need another scan to be done globally but it's going to have fewer elements。

😊，Okay， so now each thread block is going to do a scan to do the separation locally。Now。

 each thread block needs to know where it needs to write each bucket。

 So each the question now remains where should each block write each bucket。 Well， let's take a look。

 This first block over here， it has two zeros and it has two ones。

The second block also has two zeros and two ones， the third block has one0 and three ones。

 this one has three zeros and one one， so every block is going to have a different number of zeros and ones。

Now， this first block needs to put its two zeros in the beginning at position 0。And。

Block needs to put its zeros where at position2 because there are two zeros before this block needs to put its zero at position4 because it has two blocks over here。

 two zeros here and two zeros in this block。This block needs to put its zeros at position five because it has two zeros here。

 two zeros here and one zero here， so it needs to put its result after that。

So what do I do to figure out where each thread block needs to put at zeros， same thing for its one。

So how did I know that this thread block needs to put its zeros at position for。

 I counted the number of zeros in the previous two blocks。

Can we create a global variable to count at which position we are right now。

 I know how many positions after a certain block we need to put it at。Is one global variable enough。

 How will one global variable help you help you do that or or two， I'm not sure。

So we will have to put just scan again what is the operation we'll talk about how we can do it。

 what's the operation that we need to do。Can we just do scan again。

 But with these numbers instead of。0 and one。Right。

 so what we will do is now we need to do us another scan。But this time。

 the scan is over these numbers over here。For this block。

 we need to count the number of four zeros in the previous two blocks For this block。

 we need to count the number of zeros in the previous three blocks。 Okay， for the ones。

 like for this one over here， I need to count the total number of zeros。

 So this and this and this and this。So in order for me to know where I put these one。For these ones。

 I need to find the total number of zeros so this and this and this and this。

 and I need to find the total number of ones in the previous。Okay， et cetera。

 So all we can do is we can take these numbers， we can store them in global memory。

So here I have an array in global memory where I have for each b。

I'm going to have the number of zeros in that block and then the number of ones in that block。Okay。

 and then for the zeros， I basically want to find the number of zeros in the previous blocks。

For the ones， I want to find the total number of zeros and the number of ones in the previous。

 So what do I do on on this array。I just do a brieffix example for an exclusive。Okay。

 so I can think of this array like this as a 1D array for the zeros。

 I need to kind of find the number of zeros in the previous block。For the ones。

 I need to know that all the number， all the zeros and all the blocks。

 plus the number of ones and the previous。So I do an exclusive scan on this array and with this exclusive scan。

 now what I have is if I go back and I look at this array again as a table like this。

 now I have for each block， the destination of the zeros in that block and the destination of the one。

Okay， so then all of these blocks are going to put these values in somewhere and then they're going to do a scan on these values and then we're going to bring back these numbers and now each blow clock knows for each of its bucket where it needs to put the zeros are the ones in that box。

So this block knows that needs to put these two zeros at position zero。

 starting at position zero this block knows that needs to put these two zeros starting at position2。

 this block knows that needs to put this zero starting at position4。Okay。😊。

And same thing for the one。Okay， so once I know that。

 now each v can come and it can take its zeros or its ones and store them to global memory， okay。

 so now each v comes and it will take its zeros and ones and it' will store them to global memory and as you can tell now our access are coalescce。

😡，Why if we zoom in on what this first redb is doing？

This thread block has separated all its zeros and its ones。

And then all the zeroes are going go to share it to one to this position in global memory and all the ones are going go to this position in global memory。

 And because all the zeros are next to each other followed by all the ones。

 the threads that are next to each other are all are all going to be writing to nearby locations in global memory。

 remember before before we did this， this thread was writing a zero。

 and this thread was writing a one。 and then this thread was writing a0。

 and then this thread was writing a one。 Now we don't have that。

 Now the first half of the threads in my block are all writing zeros。

 and then second half not necessarily half they could be because the number of zeros and ones is not necessarily equal right。

 But the first part of you know the first partition of threads in my block is going to be writing all writing zeros to the same global memory locations and the remaining partitions of threads in my block are all going to be writing ones to global memory locations。

 So by doing this， we have。Better memory coalescing。 Okay， is this clear to everyone， Any questions。

Now stores are coalesced because nearby threads right to nearby locations and global movement。Okay。

 sir， Josh this is this extra step actually worth it because it seems like you lose a lot of time doing the over again。

I mean， so two things， you have the local scan and you have the global scan。

Right you're going to do a global scan anyways， so when you did it when you were doing it without this local approach。

 when you did a scan across all of the elements you were doing a local scan inside of each block and then you had to do a global scan so we haven't really increased the number of steps we're still doing a local scan but this time we do a local scan and we partition and then we get the total numbers and then we do a global scan。

So we haven't increased the number of steps in terms of the amount of work we do to do the scan However。

 yes we did we have increased the overall amount of work that we're doing however。

 we've we've saved a lot on the memory coalescing we've significantly reduced the number of memory requests that we need to make。

So yes， it turns out that， yes， this approach is definitely worth it。Okay。

 just imagine what happens to my memory system when all my threads and all my blog are all of a sudden writing at the same time to all these different random locations。

😡，You can imagine this is going to put a lot of stress on my memory system so what I end up doing is I end up you know just sitting there spending a whole amount of time just waiting for these memory I request to complete instead it is actually rather than just sitting there waiting for the memory it is actually worth doing a little bit more work in order for you to be able to make sure that your rights to to memory are nice and well behaved。

Okay， and by the way。Were just talking about radix of one here。

 so now we're only seeing the case where we have two buckets inside of the block。😡，Okay， but next。

 and we're about to talk about that next， if I have multiple buckets or more than two buckets。

 if my radix is greater than one bit or it's greater than two， I'm I can have four buckets。

 I can have eight bucket。Okay， the more buckets I have， the more of these， you know。

 the more of these unclecoesed aes I can get。 So if I go back。Oh。

I have you know this thread writing to this place， this thread writing to this other place okay。

 but then you know all the threads they're either going to write here or here。

 so within a single warp I'm probably going to have two different requests one to the zero bucket one to the one bucket。

 but if I use a radix that is larger than two。😡，You know。

 if I use the radix where I have made four buckets or eight buckets。

 then I could have one warp writing to。At you know， four or eight different memory locations。

Which means that every warp is going to have to be served using eight different memory requests。

 so that's where applying this optimization is actually definitely worth it。Okay， that clear？Yes。

 thank you。Yeah， you're welcome。Professor， sorry， when you mean two buckets， you know。

 it's a binary when it's。It market， for example， it's O。Yeah。

 actually let me I'm going to look I'm going to look at this case next。

Hold your questions about having multiple buckets because I'm we about to cover that example。

 but does anybody have questions on this before I move on？Somebody's asking about course knitning。

 yes， we're going to look at coursening， but let move bit。Professor， I was wondering。

 how do you make the threads weight while the global scan is happening。

So there's two ways one way is to actually terminate the kernel and then launch it again and if you were to do that you would actually have to write out your shared memory to global memory and then read it back from global memory but those writes and those reads will be coalescceed so that's one way another way is they're actually you know fancy tricks that you can play in order for you to to do a global scan and have all the thread box communicate with each other if you know that you're doing you can actually have different thread box communicate with each other but that's an advanced technique that we haven't looked at yet so don't worry about that it's a very good observation that you made but don't worry about that and is another reason why I didn't want to write code for this lecture just because some of these things start getting a little bit complicated。

ok， thank you。Okay， so now let's talk about the choice of radix value so so far we use the one bit radix or we use the radix of2 and what that means is that if I have a 32 bit key right my keys are 32 bits then I'm going to need 32 iterations to do the radix sort in general I will need n iterations if my keys are n bits long so what can we do to reduce the number of iterations well what we can do is we can use a larger radix。

😊，Okay， so a larger radix can also be used， and the advantage of a larger radix is that I have a fewer a smaller number of iterations so I might finish more quickly。

 but what is the disadvantage of using a larger radix。I kind of mentioned it already。

There's a higher chance that the stores are not going be wirelessesed。

Right exactly so at the disadvantage of a largeerx is I have more buckets。

 so there's more buckets that I need to write from shared memory to global memory。

 so there's more distinct locations I need to write to so this results in who are coalescing as I'm about to show。

So then when we choose the rax。Okay， when we choose the redx。

The choice of the rax value must balance between two things。

 we must balance between the number of iterations and the coalescent behavior。😡，We want to have。

A largege enough forx values so that we have a reasonable number of iterations。

But we don't want to make it too large such that the cola zc starts to her outer performanceer。

How do we do the scan with a higher raixs let's take at that so let's now look at the example of a tubebit raix。

So let's say I have a this input array over here and instead of using a one bit rax。

 I'm going to use a two bit radx Okay so way I do is I start I'm going to look at the lower two bits。

😊，Okay， so they're either going to be0，0 or 01 or 10 or 11， Okay。

 and now Im going to take these elements and I'm going to divide them into four buckets。😊，Okay。

 so we'm going to put all the zero zeros together， all the zero ones together。

 all the ones zeros together and all the one ones together。O。

And then what I will do is I will now in the next iteration， I will look at the next two bits。

 So the upper two bits。 Okay， and again， I am going to separate them into four buckets。

 I'm going to put all the0 zeros together， the0 ones together。

 the one zeros together and then the one ones together。 Okay， so here， as you can see。

 we need few iterations for a two bit radix， we need n over two iterations for n bit key。😊，All right。

 so we need fewer iterations so this is the advantage of using a larger radix。

 but now let's look at the disadvantage， let's look at how the larger radix affects coalescent so let's zoom in and focus on just one of these iterations。

😊，Okay， and let's say I do the same thing that I wanted to do before I'm going to assign a thread block to each I'm going to assign a thread to each one of these input elements so and then inside of each thread block I'm going to take these elements and I'm going to separate them I'm going to sort them locally I'm going to separate them into buckets locally and then I'm going to do a global I'm going to do the global separation so here when I sort locally。

So one of you asked， how can I？Divide these elements into four buckets as opposed to just two。

 we saw how to calculate the index of each of these elements when there was just zeros or one。

How can can we do the separation when I have adix of multiple elements， well。

 it turns out the best way to do this is actually to just use multiple one bit steps。

So if you remember when we did the different iterations of Raic sort。

After first when we did the one bit version， after the first iteration。

 the elements were sorted by the first bit。After the second iteration。

 the elements were sortsorted by both the first and the second bit。

 then after the third iteration they were sortsorted by the lower three bits and it kept on going。

If we want to do this locally， what we can do is we can use two one bit steps in order for me to do a two bit separation of my sorting element。

😡，But the nice thing here is that I'm not doing these two， one bit steps globally。😡。

I'm only doing the two1 bit steps locally。And that's much cheaper because that means the each one good step is going to be its own scan。

 Okay， but I can these two consecutive scans are both going to be local with within the thread block So I don't have to synchronize across all the other blocks Ex that clear。

Is it clear how two1 bit scans give me a two bit scan sorry sorry a two1 bit rad sort gives me a or two1 bit separations give me a two bit separation？

Okay， can you repeat and oh sorry， go ahead。I'm asking you to。Okay。

 let me go back and show you something。when we did the separation by the first bit。Okay。

 and then what we did is we separated keys by the second bit。So because we preserved the order here。

 what happened？You'll notice that over here， these elements are sorted in both the lower twobits。

These elements are sorted， we have all the zero zeros together and then all the zero ones together and then all the ones zeros together and then all the one ones together。

So when we do two， one big sort。That equivalent to doing one tube it sort。But if I want to sell。

the elements in my array into four buckets for0001，10 and11。

 I can do that by doing two consecutive one bit separation I that clear？Yes， yes yes， yes。Yeah。

 so this is exactly what we do。That's not the fight I want to go to。

So here what we do is in order for us to separate our elements into these four buckets。

 so what we can do is we can do two consecutive one bit steps to give us the effect of a single two bit step。

So then each thread block is going to locally apply two scans right to do these two one bit steps in order for us to sort into four buckets。

 so each thread block is going to do the same。And now each thread block needs to find out which bucket it needs to write to。

So how do we do that？Same as before no right same as before。

 but this but we have four rows instead of two right exactly same as before。

 but this time we have more buckets so now for each thread we have the number of zero zero for each block we have the number of zero zeros。

 the number of zero ones， the number of one zeros， the number of one ones zero zeros to know to know where I'm going to put my zero zeros。

 I need to find the number of zero zeros before me。To know where I want to put my zero ones， okay。

 I need to find the number the total number of zero zeros and the number of zero ones before me。😡。

To know where I want to put my1 zeros， I need to find out the total number of zero zeros and the total number of zero ones and the total number of1 zeros before me。

Et cetera。So each thread block is going to store。It's number of zeros。

 the number of zero zeros it has， the number of zero ones has the number of ones it has the number of ones it has。

And then we take this array， we look at it as if it's a flattened array。

 we do an exclusive scan on this array， so now for each element for this element。

 these elements here， they're going have the number of zero zeros in the previous blocks for these elements here we're going to get the number of zero zeros in the previous in all the blocks and the number of zero ones in the previous blocks for these elements we have the number of zero zeros in all the blocks plus the number of zero ones in all the blocks plus the number of one zeros in the previous blocks for these elements we're going have the number of zero zeros and zero ones and one zeros and all the blocks and the number of one ones in the previous block okay so then this array over here。

 we go back look at it like this this is going to give us the destinations of the zero zeros。

 the zero ones the one zeros and the one ones for each thread block。😊。

So we send these back to the blocks and now each block knows where it needs to write out each of its buckets。

So having done that， what we do is each thread block will take its buckets and it'll write them out to global memory and as you can tell。

 these threads will be coalesced so if we look at this thread block for example。

 the zero ones that the nearby thread block， nearby threads will be writing out nearby elements to nearby locations in global memory。

Okay。The the president Singapore。Yes， go ahead。Sorry。

 I just wanted to say there is it that if we go too far there will be a decrease in coalvalescing if we increase the rate。

Absolutely， absolutely。And absolutely and that's exactly the point， the more we increase the raix。

 the fewer iterations we have， however， the worse our coalescing becomes because now instead of only having to write out two buckets。

 now I need to write out three or four buckets。Okay， so obviously。

 if a thread needs to write out to four different global memory locations。

 I'm going to have more places where I I don't have good cocing than if I just have to write out to two display memory locations。

ok。😊，But if we do， for example， something like a threat coing。

 we will improve actually a lot more than if we had only two buckets， right。

 we will do both actually。 So that's that's actually my next my next topic is threat couring。

 So as you can see， we said that by improving by increasing the raix。

 we make we reduce the number of iterations， but we make coalescing work coalescing worse。

 So one way that So August we're gonna to find the sweet spot。 You know。

 what is the best redx value that that has gives me a good number of iterations。

 but at the same time doesn't hurt coalescing too much。

 But another way that we can optimize coalescing is as you said， through threat coing。

So here for Raix sort， the price of parallellyzization across more blocks is that the more blocks I have。

😊，The fewer elements I have per block， and therefore the fewer elements I'm going to have per bucket per block。

 and therefore the fewer opportunities I have for coalescing。So if again。

 if these all these blocks are running in parallel grape， if these blocks are going to be sterized。

 I might as well give each block more work so that each block has larger buckets so that each block has better coalescing opportunities so if I process more elements per block this will result in larger buckets per block and hence better coalescing so let's take a look at what that looks like here if rather than giving each thread one element so if this block of four threads has four elements I'm going to give the block twice as many elements as it has threads。

😡，So each block is going to be responsible for more keys here I'm doing this is the thread corening step。

And now what this block will do is it's going to again。

 you know it it's going to do the scan and figure out the destinations and then it's going to separate the buckets in shared memory right this other block will also do the same thing in parallel so each block separated into its buckets and shared memory。

😊，And then finally， each thread block will go and will write out the buckets to global memory。

 And now what you can see this time is that we have better coalescing because now our buckets are larger。

 So now when we write out the buckets from shared memory to global memory。

 our our aes are more coalesced here we can have the thread block first write out these two buckets and then write out these two buckets。

 But each time the aes will have more better coalescing okay。😊，A。Is it clear to everyone。

 any questions？Okay， so this was Radix sort， the next sort is merge sort and I know that I only have a few minutes left in the lecture。

 but this will not be that this will not take that long because we've already covered merge last time。

So Ra sort is very applicable to all kinds of keys， as you guys observed， sorry。

 somebody has a question。Concerning bus。So each kernel will handle one ambitrax operation to the fullest and will need the bike。

I don't know bit's a number divided by the divided by and kernelel Yes， of course。

 if we're going if we're going have if we're going to have， for example32 bit ingers and2 bit ras。

 then we're going to need to have 16 iterations so we'll need to have 16 separate kernel calls one for each iteration Okay and depending how we implement it we might need multiple kernel calls for each iteration。

Okay， okay。Okay。Yeah， so this is a more complex pattern than the ones that we've seen before and that's again part of the reason why I didn't want to spend time in the lecture writing code because the lecture there's already enough material to discuss without presenting the code to you。

😊，So Radic sort like we said is not applicable to all keys as you guys observed earlier in the lecture okay so we still need to have some kind of comparison based sort that is also amenable to parallellyization and one popular one is merge sort so the way merge sort works is that it divides a list into two sublists and then sorts the sublist and then merges them okay so divide and conquer algorithm。

😊，Let's take a look at how merge sort works the way merge sort works is I take my array。

 I divide it into many， many small pieces， you know， small subarrays， Okay。

 I sort each of these subarrays， you know how I sort them doesn't matter。

 I might sort them using merge sort or I might sort them using some other sort Okay。

 and then once I have all these sort an arrays。😊，I merge the nearby array。

 So I'm going to merge these two。 have two sorted arrays。

 I'm gonna to merge them into one sorted array。 I have these two sorted arrays。

 I'm gonna to merge them into one sorted one。 I have these two。

 I'm going merge them into one sorted one。 I have these two sorted arrays。

 I'll merge them into one sorted one。 Okay， now I have these four sorted arrays。

 Now I'm going to do merge again。 So I'm going take these two arrays。

 and I'm going to merge them into one sorted array， and I'm going to take these two。

 and I'm going merge them into one sorted array。Okay。

 and then finally I do a final merge where I take my two sorted arrays and I merge them into one final sorted array。

Okay， so this is how merge sort works， how can we paralyze this？How can we paralyze merge story？

You guys already know how to paralyze mergech， so right？It's the same thing。Right。Exactly。

So what we can do is we can paralyze each of these steps。Okay。

 so each step performs a different merge operation in parallel and also parallellyzes each merge operation。

 we've already seen how to parallellyze a merge operation。 So for example。

 we'll assign we can assign a thread block， for example， to each one of these segments。

The thread block will sort this segment locally， somehow。Okay， using some kind of sort algorithm。

 and then once we have these sorted segments。On the next iteration we can assign two blocks to this output array to merge these two input segments。

 we can assign these two blocks to this output segment to merge these two input segments。

 we can assign these two blocks to this output segment to merge these two input segments and we can assign these two blocks to each this output segment to merge of these two input segment and like we saw in the merge lecture。

 these two blocks will have to find their co rank and sign of each of these input segments in order for them to do the merge。

In the next iteration we'll assign four blocks to this input segment and then each of these blocks will find its co rank and this sorry we'll assign these four blocks to this output segment and each of these blocks will find its co rank and each of the input segment and do emerge。

 similarly we'll assign these four blocks to this output segment and each block will find its co rank and do emerge and then the last iteration we will assign all these blocks to this entire input output segment and each block will find its co rank and the input segments to do emerge。

So in the earlier steps， we have more parallelism across merge operations。

 we have different blocks working on different merge operations。

 but then also within a merge operation we have multiple blocks working and as as we proceed we're going to have fewer merge operations being done in parallel so we have less parallelism across the merge operations where we're going to have more parallelism within the merge operation so for the later steps we're going to have more parallelism within merge operation okay。

😊，Is this clear？Any questions？All right， well then so what we covered today is we covered Draic sort and we covered merge sort and that is all that I have for today Does anybody have any final questions before we end。

😊，Yes， professorfessor， can you go back to the last slide for erratic sort？Yes。

Is it it possible in this case to get even better memory coalescing。

 so instead of arranging the buckets in this way， why don't we write everything to global memory from the block for each block to its corresponding location in global memory？

And then we do some kind of operation with a stride or something like that。

 and that way we would be able to coalesce the memory and update it after each stride jump I'm not sure I'm not sure what you mean by that。

 but can if I can guess or speculate what you're driving at if you want to put this all in global memory and put this all in global memory and then somehow shuffle the elements around。

Well， that's going to require uncoesced access， right？

So what we're doing here is exactly that we're shtling these elements around so that they're sorted in the final destination array。

Okay， because if I to I to take these and store them to global memory in a coalesced way。

 I'm going to take these and I store them all to global memory in coalesced way。😡。

But when I want to come and shuffle them around， I'm going to have to read them back and then store them in an uncoes way。

😡，Right， I might as well just do it directly。Okay， so basically it what I said only delays the coalescing yes we're going to to pay the uncoas aes anyways。

 but here fortunately， these aes are actually quite coalesed。Okay， I see。 Thank you。 Okay。

 so if I have four or eight buckets and I have， you know。

 I'm gonna to have more than four or8 works inside of my thread block。

 if each warp takes a bucket and stores it to global memory。

 my coalescing behavior is actually going to be pretty good。Okay， thank you。Okay。

 yeah you're welcome questions。Okay， if not， then that's all for today and I'll see you next time。

喂 everyone。

![](img/fa5c4ccd173ce13f38f29f47826212d2_2.png)