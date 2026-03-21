# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p12 P12 扫描（Brent-Kung算法） -BV1LD6BBPEjt_p12-

Hello everyone and welcome to lecture 12 of GPU computing today we're going to talk about a different parallel scan algorithm than we one we talked about last time in particular we'll be talking about the Brent conung parallel algorithm for scan so last time we spoke about about the scan pattern and in particular we looked at the cojistone method for doing parallel scan and we also looked at an optimization that was applied in this context but it' also applicable in many other context and that is double buffering so we said that scan is basically a pattern where given an array the output array is going to every element output array is going to be the combination of the preceding element elements as well as if it's an inclusive scan the corresponding element if it's an exclusive scan it's just the preceding elements without the corresponding element and we were using addition as an example throughout the lecture but we said that in general。

😊，can it be applicable to other associative operators like product， minimum max， et cetera？

We said that to do scan we segment it like we did with reduction and that's because doing scan and parallel requires synchronization which we cannot do across different thread blockss so what happens is that we take the input we divide it into segments。

 each thread block does a scanned of its own segment and then they store the partial sums in subar and then we scanned the partial sums array and then we take the scanned partial sums and then we go back and each block adds the scanned partial sub of of the blocks that preceded to tos the elements inside of the thread block to get finally the fully scanned global array and the algorithm we looked at for doing a scanned within a single block was the code stone parallel algorithm which looked like this what we did is we had each thread add the element that is once dried away and then add the elements that。

Striide 20A， then add the elements that stride 4 away until we have but we have reached the whole array that the thread block is responsible for and we said that because we have this situation which we did not have a reduction by the way。

 but here we had a situation where on the same iteration。

One thread was reading a value that was reading from a location that another thread was writing to what happened is we had to synchronize between the read and the right。

 so we would read from this array， synchronize right to the array and then synchronize again。

We also saw that these memory locations are being reused so what we did is we loaded the data initially to shared memory and then performed our scan operation inside of shared memory and then we also saw that well reason the reason that we had to do a synchronization between reads and writes is because we were using the same array for each iteration so to avoid having to do two synchronizations every iteration instead of one we instead used an approach called double buffering where the threads don't read and write to the same buffer every iteration instead we have an input buffer and an output buffer and we read from the input buffer and write to the output buffer and we swap input buffers and output buffers every iteration that way we only need to have two buffers we don't need to have a buffer for every single iteration and this optimization was called double buffering then we looked at cool scan and we said that for the。

Cojistone approach we can simply do an exclusive scan using the inclusive scan but shifting the elements of the array by one element and we finally analyzed the work efficiency of the algorithm and we observed that although the sequential approach to doing scan performs n additions the Cojistone approach to log n steps every step it did n minus2 power step operations so that came out to n times log n minus n minus1 operations which is O of n log n operations and with this observation saw that we said that this algorithm is not work efficient because the parallel algorithm does more work than the sequential algorithm it does more additions that a sequential algorithm which means that there is some redundant work that this algorithm is doing that the sequential algorithm does not do now if the work is being done in parallel that's a great idea and that's fine it's a price that we pay。

😊，If the thread blocks end up getting serialized because of limited resources。

 then we can expect this low work efficiency to hurt us。Okay， and with ending at that note。

 we said that today， what we want to do is we want to talk about a difference can algorithm。

 which is which is the Bt con method for doing scan。

 And then also we we didn't look at co setting last time。

 and we will look at co setting today in the context of scan to see how how course setting would be useful for scan。

 So this is what we' will talk about today。 But before I continue today's material。

 anybody have any questions about last brain's material。😊，Is everything clear to everyone？Okay。

 so then today we'll going be talking about the Brentth K method for parallel scan。

So the bread come method for a parallel inclusive scan。

 Well I'll start with inclusive skin is as follows。 We have an array。

And what we do is this method has two steps。The first step resembles a reduction tree。 So here。

 what we will do in the first step is we will add the elements that are next to each other。

 So you'll notice here that these two elements now are ready。Okay。

 and the next step we're going to add the elements so here we have oh yeah and one thing to point out is that we're going to have one element for every other one thread for every other element Okay。

 so in coaches stone we need to have one thread for every element here we have one thread for every two elements at the beginning because the additions that we're doing at each step are fewer okay。

😊，So here we have a thread that adds every two adjacent elements and then we continue the next we have a thread adds you know these two elements that are two strides apart and these elements that are two strides apart and and over here you'll notice that we have a complete reduction tree for this subsegment over here from zero to three so now we have the this value is ready and then we're going to add the elements that are stride four apart okay and you'll notice that now we have a complete reduction tree for the entire array so now we have this value ready as well so we essentially have done a reduction tree。

😊，Okay， and the intermediate results of the reduction tree。

 we have some of the scan values are ready， but some values are not。Okay。

 and because this looks like a reduction tree， we call this the reduction step。Okay。

 we call this the reductions though。Now， after doing this。

 we still have these other values that are not ready yet。

 So what we're gonna do is we're gonna do a second phase。

 a second phase where we complete these other values that are not ready。 So， for example。

 we observe here that x 4， x 5 is not ready。 It's missing x 0 to x 3。

 Well we have x 0 to x 3 over here。 So in in this stage， we're going so we had stride1。

 stride two stride 4。 Now we're going to go back to stride 2。

 and we're going add x 0 to x 3 with x 4 to x 5 in order for us to get x 0 to x 5。

 And now this value is ready。😊，But what we noticed is that we still have x2， x4 and x6 are not ready。

 but here x2 can be added to x0 and x1 so that we get x0 to x2 x4 can be added to x0 to x3 so that we get x0 to x4 and then x6 can be added to x0 and x5 so that we get x0 to x6。

 so essentially what we do is we simply add the values that are1 to the left one stripe to the left in order for us to complete the scanner rate。

😊，Okay， and this step following the reduction step that we use to complete the remaining values is called the post reduction step。

ok。😊，Has it cleared everyone realized how this works？

Okay so then now let's compare these two methods so here on the left we have the Kojistone method that we saw before and here on the right we have the brand method that we looked at now and what do you what do you notice about the similarities and differences between these two methods well differences what's what's different what are the differences between these two methods。

😊，We have fewer additions， total， right。For which one。

 which one has fewer editions for the Brent con？Right。

 so the brand Kung approach has fewer additions in total。Okay， somebody is saying de。

 what do you mean by de？The vent count goes deeper into the tree。

I think like it means there are more steps， Right， exactly。 So the Bt Kung has more steps。

So the brandcom approach performs more steps。However。

 it performs fewer operations per step and fewer operations in total。Okay， and let's。

 let's kind of do an analysis of these two approaches。 So if you remember。

When we talked about work efficiency， we concluded that the Kojistone approach has log N steps。

 however it does O of and log and operations。😊，Now let's let's do an analysis of Brent Kung。

 So Brent Kung does how many steps。Well， let's， let's take a look。 There's two different。

 There's two different stages。 There is the。There's that， let me go back。 There's the reduction step。

 and there's the post reduction step。 and the reduction step。 How many steps do we。

 How many steps do we do。Well， here I have eight elements。 I did one，2， three steps。 So in general。

 if I have n elements， I do log n steps Okay， and then in the post reduction step。

 you know here I went one，2，4 and then I go back I do go back and I do two and then one。

 So how many steps do I do in the post reduction step。Log n。

 -1 or roughlyee log n exactlyact exactly log n -1。 So so in total。

 we're going to have two log n -1 steps。 that's more steps than Coji Stone， which finished on log N。

However， how many operations do we do in each step here when we have8 elements。

 we did  four and then two and then one。 So that's 7。 So that's around log and operations。

 And then we go back and we do one and then three。 Okay， if we have a， if you have another iteration。

 we're going do more than that。 So let's go and and do the full analysis。

 So with Brent K we said the reduction step， does log n steps。 And， and it does it does。

1 plus 2 plus 4 up until n minus2， which is equal to n minus-1 operations。Okay。

 and maybe I should have written this as n over two plus n over4 plus do plus1 because the first step was n over two that the second step does n over four and then the very last step does one operation in the reduction step。

 okay？For the post reduction step， we said that we have log n minus one steps。Okay。

 and then in the first step， we did one1 one operation。 That's 2-1。

 In the second step did we did three operations。 That's 4-1。 And in general。

 we're gonna keep going until we get to n over 2-1。 So we'll do 2 -1，4-1，8-1。

160-1 until we get to n over 2 -1。 So if you add this up， this comes out to n-2 log n -1， right。

 because we have 2 plus 4 until you get to n over 2。 that adds up to n -2。 Okay。

 and then you have1 plus1 plus1 log n -1 times。 So that's log n -1。Okay。

 so if you add the steps and the operations for the reduction step and the post reduction step。

 in total， we find that the Bt kg approach takes two log n minus one steps。

 so that's more steps than the Kojistone approach。ok。😊，However， it does， if we add， you know。

 n -1 and n-2 log n -1， it comes out to two times n minus log n minus-2， which is O of N operation。

ok。😊，So that the bread kung approach does fewer operations。Okay， so Brent Cog takes more steps。

But it is more work efficient。Is that clear Abul？Okay。

 so then let's go and implement the B cong approach but before that in the past lectures we've been kind of implementing something and then gradually optimizing it what I'm going to do is I'm just going implement the optimized version in one step just to save time today because the doing the optimizations incrementally is something we we already did it in the last lecture for Cojistone So what optimizations are we going to apply to the brand cong approach the optimizations we applied last time where that we use shared memory we double buffering and and what we did have a problem with divergence but what we're going to do today is we're also going to use shared memory so similar to Cojistone okay and this should be August however there is one thing to note when compared use shared memory for Cojistone versus Bt con so in both cases we're reusing the same memory look。

😊，So using shared memory is useful。However， with the Kojistone approach， when we used global memory。

 the memory aes were actually coalesced。😊，Okay， now when we use shared memory。

 it wasn't a problem Coesing was not a problem， but in the brand kung approach。

 if we use global memory， the aes are actually not coalesced。

So using Sha memory has two advantages with the brand K approach。

 the first advantage is that we get data reused so we don't have to go to global area every time。

 but then the other the second advantage is the fact that we get better behavior because we can load the whole array in a coalesced way and then we continue with these non coalesced accesses。

Okay， so those are the two advantages。So using shared memory is similar to Coji stone we get better data re useuse。

 but it also enables coalescing of global memory loads in Coji Stone the global memory loads were already coalesced before we applied shared memory time。

Do we need to do， Do we need to do double buffering in in tongue。 So in Co stone。

 we we had to do double buffering。 Do we need double buffering in the brand kung approach。No。

 why not it。Because we don't access the same areas we are writing to。

Right exactly so the reason we needed a double buffering with Kooji stone is that on the same iteration X1 for example。

 was being read by one thread and it was being written by another thread。

 so we needed to make sure that the thread that is writing doesn't interfere with the thread that is reading and that's why we wanted to read from a buffer and write to a different buffer。

In Bren Kk， it is never the case that the same value is being written by one thread and read by another thread on the same iteration。

 so we don't need to worry about double buffering， we can use a single buffer for all our steps。Okay。

So then we no need for double buffering because unlike Kojistone。

 no data element is read and written by different threads on the same itration。

 the one thing though that we need to be careful about with the Kojistone approach is sorry the breadkk approach is control divergence。

😊，So with coaches stone。The control divergence was not a problem right because in the first step。

 you know all the threads were active except maybe the first one right but that's okay the threads that were active were all next to each other sos threads one to seven were active and the second step threads two to seven were active and the third step threads four to seven were active but the point is that the threads that were active in each step were all next to each other。

Whereas in the B Kg approach if we assign a thread to every input value input value。

 if a thread owns an input value， then we're going to have a problem with control divergence and that is that you know because you know we don't process all the input values and every step these input values drop out so if I'm going to assign a thread to every input value。

 then if the first iteration I'm going to have one， two three， four all busy the second iteration。

 every other thread drops out and the third iteration and every other thread drops out etc。😊，ok。So。

 to avoid。So we need to minimize control divergence and to avoid this control divergence。

 what we're going to do is that we are not going to assign threats to specific data elements like we did with the conjistone approach。

Instead， what we will。 So we're not going do what we've been doing so far with these tree reductions and scans where every thread owes a particular element in them。

Instead， what we're going to do is we're going to use a different approach。

 and that approach is to reinex the threads every iteration to different data elements。 Okay。

 in other words， and every iteration。Right， the thread and the thread is going to be responsible for a different data element so that I can always have threads that are next to each other active and threads that are that are kind of the threads that are farther away inactive。

 So， for example， what I would like to do over here is on the first iteration。Okay。

 I looked to have thread  zero， do this this edition， thread one， do this edition， thread2。

 do this edition， thread3， do this edition， etc cetera。On the second iteration， I'm gonna have。

 I'm not gonna have thread rather than so first I had 0，1，2，3， et cetera。

 I'm not gonna have thread 0 inactive and then thread1。

 do this and thread2 inactive and3 do this and then thread4 inactive thread5 do this etc ce。

 I'm not gonna do that。 instead I'm going to reinex my threads to be responsible for different data elements in each generation。

 So what I will do is I I will have thread0 process this element， thread one process this element。

 thread2 perform this edition and thread3， perform this edition。 And then on the third step。

 I will have thread 0 perform this edition and thread 1 perform this edition。

 And then on the final step， I will have thread 0 perform this edition。

 And then the same thing as they go back and back out and'm going to have thread 0 perform this edition。

 thread1， thread 0，1， and 2 perform these。 and then thread 0，1，2，3，4，5，6 perform these。

 So we always want to assign the leftmost edition to the left。😊，The first thread and so on。

 regardless of what element that is and what that means is that each thread will be responsible for a different input element in each of these iterations。

😊，Okay， is that clear？嗯。Do why do we need the threads to be contiguous like Because to maximize the like the war passage。

 you know， if we have more than more than one wart and we want them to be， know。

 as packed as possible， Right， exactly。 So what I want to do is I wna， I w to fill up the first war。

Before I fill up the second warp， et ce， I don't want to have every other thread in the block active or inactive because then I'm going to have a lot of control divergence。

I guess what I'm trying to do is to minimize control divergence by always assigning the work to the thread starting from the left。

So I fill up the you here here。 Maybe it's not August because I just have 16 elements。

 but this could be1024 elements。 So this was 10 or it could be 2048 elements。

 and it could have 1024 threads。 Okay， so I want to fill up the initial works before I fill up the later works。

Okay， is that clear。Yes， thank you。Okay， so then to do this， we need to be able to。

Play some tricks with the thread indexing and to figure out how how we're going to index the threads。

 So every iteration， the thread， the element that the thread is going to be responsible for is now not the same for all iterations。

 It's going to be a combination of the thread index as well as the iteration and the iteration was represented with the stride。

 We use the stride somehow as our loop index that was doing the iterations。😊。

So what we will do is we want to express the index。

 the element that the thread is responsible for in terms of the thread index。

 which I will denote as T and the stride which I will denote as S so if you notice in the first iteration。

 if we look at the index of the right source opera source element and the destination element of the thread。

 okay， these are the indices。Okay， so and the first when the stride is one。

Thread 0 needs to be responsible for element 1， thread one for element 3， thread2 for element 5。

 thread3 for element 7， et cetera。 So here I have1，3，5，7。When the stride is two。

 my my threads are responsible for element 3 element 7 element 11 and element 15。 so I have3，7，1115。

 so here this is a thread  zero is responsible for element 3。

 thread one should be responsible for element 7 thread2 is responsible for element 11 etc ce。

 When my stride is4 then here the first thread so thread0 should be responsible for element 7 and thread one should be responsible for element 15。

 So here when my stride is 4， thread  zero is responsible for element 7 and is one responsible for element 15 and then when my stride is 8 then over here only thread0 is going to be active and thread  zero is going to be responsible for element 15。

 So here I'm gonna to have 15。ok。So this is for the reduction step and the post reduction step now let's figure out the indexing and the post reduction step and here I'm going to look at in the reduction step I was looking at the right element that the thread is responsible for and the post reduction step I'm going to look at the left element that the thread is responsible for so here in the post reduction step or the stride is for thread where I'm going to have thread zero responsible for element7。

😊，Okay， when the stride is2， I'm going to have thread zero responsible for element 3。

 thread one responsible for element 7 and thread two responsible for element 11 Okay。

 and et cetera here I'm going to have7 here I'm going to have3，7。

11 notice how these resemble these up here so when str is2 in both cases it's the same and then when the stride is one。

 I'm going to have13，7 sorry 1，3，5 and 7。Okay， the reason I'm doing this is I'm just trying to figure out some closed form representation of the element that the thread is responsible for in terms of the thread index and the stride。

Okay， so this is for each， this is for each value of the stride and for each thread。

 what element they are responsible for in each for each stride value。Okay， so now the question is。

 how can I represent the index of the element that a threat is responsible for in terms of the stride value。

And the thread index。O。😊，Well what we observe here is that over here the thread elements are two apart right so plus2 plus2 plus2 here they're four apart here they're the eight apart here I just have 15 when here when I come back here they're four apart again here they're two apart so in general they are two times s apart okay but they're an odd number not an even number okay so what I will do is I will I will represent them as something minus1 so here one I will represent it as2 minus1 I will represent3 as4 minus1 so I will just represent everything as something minus1 okay and now it becomes more apparent that these are all a multiple of two times the stride right so here when the stride is1 246 and8 are all multiples of two when the stride of two is then 4812 and 16 are all multiples of4 when the stride is 4 than 8 and 16 or multiples of8 so in general the thread。

C are a multiple of two times the stride so I can represent them that way。

 I'm going to represent the indices as multiples of two times the stride。

 Okay so here now each index is here it's one times two times the stride minus-1。

 two times two of the stride 1 etc cetera here it's one times times the stride minus-1。

 two times two times the stride minus-1 etc cetera。

 and what you'll notice is that these remaining numbers in black these are just the thread index plus one。

Okay， so for the thread zero is always going to be responsible for one times the element at index1 times two times S minus1。

 thread one is always going to be responsible for the element at index  two times2 times S minus1 and et。

So this is simply going to be so the indexes are the t plus one multiple of two times s and then of course minus1 so we just replace this with  two minus1 and this this over here t plus1 times2 times S minus1 gives me the index of the element that each trend is responsible for for each stride value Okay。

 is it clear。So figuring out this indexing， remember what I told you guys that parallel computing is all about indexing and boundary checks。

 well figuring out this indexing is the hardest part of writing this kernel okay。

 once we have this expression for the index， everything else is fairly easy as you will see。😊。

All right， so every thread is going to process the T plus1 times two times S minus one element。

Of course， if the destination is in bound right so over here we will need to check if the values are in bounds so in this situation this equation will take thread zero here but will'll take thread one somewhere all the way out here which is out of bounds。

 so I simply don't process that's how I know that and this for this Str value thread one is not going to do anything。

ok。😊，Professor， is this clear any questions？Yeah， professor。

 I was just confused in the post reduction step。 Why was there。

I thought it was supposed to be 11 when the stride was four， but there was another value。

 I think there was seven。Okay， yeah。 So what I wanted to do is I wanted to。

I wanted to have the same index for S 4 here and here。And that is why what we did is for Strtri4。

 the first thread was the index that we used was the index of the right upper end and the destination。

Where in the reduction step， but in the post reduction step。

 the index that we use is the index of the left operator。

And what this allowed us to do is allowed us force stride4 that thread zero had the same index in both reduction and post reduction。

Oh， I see。 Okay， okay， thank you， I you noticed here， the left it was tried this too。

The the right opera are 3，7， 11 and 15。Okay， and then when strike is2 down here， the left opera are3。

7，11， and of course， for 15， it will be out of bound。 so there's no 15。Okay。

 so using the right opera as the index， the reduction step and the left operator as the index and the post reduction step allows us to have the same index both in both cases。

I see you looking。Yeah， you're welcome。Okay so so this is this is an example of how we can reindex the threads so rather than assigning threads to fix data。

 we reinex the threads every time in order for us to make sure that we do not have control divergence and this idea of reindexing threads is a general approach to to avoiding control divergence that we apply every time here we are applying it in this context。

 but in other workloads we might apply to a different context does someone have a question。😊。

So best district that we use， you know， the right indexing versus left indexing， you know。

 it's something we have to try already。 And if say if I have a new algorithm that I don't know I don't know the pattern I don't know it's parallel pattern。

 I have to try different things right， know there is no like fixed way to right which right left Yes。

 you're right。 So different algorithms Yes， so this is this here is something that's specific to what we're working on today。

 You're absolutely right。What I'm saying is the general idea of reindexing threads as opposed to fixing the threads to specific data and letting them diverge is what we're trying to showcase here。

O o。行别什么。All right， well， having explained this， let's go and implement this Bt K approach for Para scale。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_1.png)

Okay， so this here I've set up the code already。 This code is quite similar to the code that we wrote last time we have this the host code that's calling a scan kernel。

😊，And then we have this recursive step that scans the partial subs and then there's an ad kernel that adds the final result。

Okay， and ad kernel is already implemented。 We just need to implement the scan kernel based on what we saw today。

 So let's begin to implement the scan kernels。 The first step is I want to find the segment and the input that the thread block is responsible for。

 Now， one distinction between Cojistone and and brand cook is that in Coji stone。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_3.png)

So let me go back。In code use stone， I had as many threads as I had input elements and the reason was that I needed that many threads because I was doing an operation for every input element in the first step。

 whereas in Bren Kung， I need half as many threads as I have input elements。😊，ok。

So the size of my input is going to be twice my block dimension， all right？

That's that's one thing to to keep in mind。 Okay， so here， the size of my input。

 the number of threads that I need is half the size of my input。

 So every thread lock is going to take a segment that is twice the block size。 Okay。

 so in other words， I'm going to start。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_5.png)

By finding the segment of the thread block and the segment of this third block is basically going to block index。

 x。Times lock them dot X times 2， because I have twice as many input elements as I have threats。ok。😊。

Now the next thing to do， remember we said we're just going to do all the optimizations together。

 so what we want to do is we're going to load this input array from low memory to shared memory。

 so I'm going to create a shared memory array。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_7.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_8.png)

I'm just going to call it buffer。A just for S。Okay， and what's the size of the sugar we going to be？

If this is my block then， then what's the size of the chain will we are able to be？Block them。

Is it going to be blocked them only It's block them times2 right， It's going to be blocked in times2。

 because again， I have twice as many as many elements as I have threads。 Okay。

 since the size is blocked them times2， I'm going I'm going to need every thread to load two elements and doing this in a coalesced way。

 I'm going to have all my threads load the first half of the segment and then all the threads load the second half of the segment。

 Okay， so I will do。😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_10.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_11.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_12.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_13.png)

Baffer underscore S of。Trenread index dot x is equal to input of segment plus。

Thread index x so heres segment is the index of the Four first element and the segment of the block owns and then each thread is going to load one element starting from the beginning of the segment okay and then in the next step each thread is going to load a second element which is going to be the top half of the segment that the block is supposed to compute with so here is going to be thread in x x pluss go plus segment thread x x plus blocked in。

😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_15.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_16.png)

Andll turn next not plus lockd over you okay， and then of course。

 I need to sync threads to make sure that I've read all the values from global memory before I start doing my tree。

Okay。😊，Mired everyone。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_18.png)

Okay， now that I have my data in shared memory so now this is this array is a shared memory the next step is for me to do this tree and what I will do is I will first start with the reduction。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_20.png)

Okay， and' first going to start with the reduction step。

So let's write the loop that iterates through the reduction step initially my str is one and then it's two and then it's four and then it's eight okay and it's stops at eight。

 what is eight？

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_22.png)

8 is the。8 is half the size of the input。 The input is two times the block dimension。

 so two times the block dimension over two is simply the block dimension。 Okay。

 so my so my loop is going to。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_24.png)

Soect。S strideide equals one and instead's going to keep going until stride is equal to B in。

 so stride less than or equal to block in， okay， where did I get blocked in again。

 the size of my input array is two times blocked in and the largest stride is going to be half the size of the array。

 so half of two times block in is blocked in。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_26.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_27.png)

NowThere stride equals one， stride is less than or equal to block them。

 and then every iteration I'm going to multiize stride by two。Okay， and then on each step。

 what am I going to do but I'm going to add。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_29.png)

I first I want to figure out so this is where the indexing comes in。

 I want to figure out what element my thread is responsible for。😡，Okay。

 and the way I figured out is using this equation。 And this this equation。

 T plus one times two times S minus-1。 Okay， un sign and I is equal to。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_31.png)

转。Bus one times two times。Side minus-1。ok。😊，So now every thread knows the it's responsible for now each thread is going to add the elements it's responsible for to the element that is str to the left。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_33.png)

Okay， so I'm going to write。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_35.png)

Buffffer underscore S of I。Plus equals， so each thread will add the element it's responsible for to the element that is strike to the left。

 so it's going to add it to buffer others for s of I minus strike。ok。😊，And of course。

 I need to make sure that the element that I'm responsible for is actually within bounds right so I don't want the thread and this I want some threads are going to be all the way out here I don't want I only want threads0 and one operating over here Thrhread two is going to be somewhere all the way out here and I don't want and that's going to be out of bound so I don't want thread two to do anything so to do that I'm going to make sure that I the element I'm responsible for is actually within bounds what is the bounds here。

 what is the size of this array。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_37.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_38.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_39.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_40.png)

It's two times。Llockocked in。Okay， it's two times。Led him。

Right and you can you can easily see how how this works right because here buffer underscore S the size of buffer underscore S is two times blocked in So obviously when I access buffer underscore S of I。

 I want I to be less than two times blocked in So this is kind of another example of how these boundary checks always correspond to some memory location that I'm accessing and I want to make sure my access is within bounds okay。

All right， so after I do this suggestion on each iteration， I'm going to sync threads。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_42.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_43.png)

Okay， and then when this loop is over， I'm done with my reduction step。

 so next what I need to do is I need to do my post reduction step。Okay。So it's my post reduction。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_45.png)

mMy stride is going to start at， in this case four。Okay， so in general。Okay。

 if I want to write I write the loop bounds for the post reduction step， I'm going to start。

 I'm going to unsigned。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_47.png)

And stride is equal to what is the first value up stride and the post reduction step？



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_49.png)

Where did I get four from？Well， it is half of the stride at the end of the reduction step， the。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_51.png)

St is blocked in。Okay， so then the stride at the beginning of the post reduction step is going to be locked in over to。

Okay， is that clear to everyone where I got blocked over over to from。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_53.png)

Okay， and then I'm going to keep going on。So4，2，1， I'm going to keep going until the sky is1。

 So why so4 stride equals lo in over2 stride as greater than or equal to one。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_55.png)

Okay， and then I go to divide slide by two every iteration。 Okay， so in this slide。Divide by2。ok。😊。

Now what do I do Well again figure out what element the thread is responsible for and fortunately we were able able to cleverly use the same index for the reduction step and the post reduction step so I'm simply just going to copy index that used up here so thread index on x plus one times two times tried minus1。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_57.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_58.png)

Okay， however， this time what's going to happen is every thread is going to remember this index x for the left element。

 so every thread is going to add this element to the element that is stride to the right and store the result in the element that is stride to the right Okay。

 so so I'm going to increment the element that is stride to the right by the element that I'm responsible for。

 Okay， so I'm going to do。😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_60.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_61.png)

Buffffer underscore S of I plus。Stripe。😊，Plus， equals。Bffer underscore S of I， Okay。

 so I take the element on the right and I acroement it by the element that I'm responsible for the I take。

 if I'm responsible for this element， then I take the element that strike to my right and I add to it the element that I'm responsible for。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_63.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_64.png)

Okay， and of course， I need to have a boundary check over here。 Okay， so basically。

 I need to check that not only should my element be in bounds。

 but the element to my right should also be within bounds。 Okay， Okay。

 so you're ready to make sure that I plus stride is less than what is the bound。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_66.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_67.png)

What is the balance of the year？

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_69.png)

我你。😔。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_71.png)

啊。Ts locked in okay， it's two times locked in。So， two times。O。It's two times。L it。ok。😊。

So the previous tree， I had to make sure that I was less than two times blocked in and this tree I have to make sure that I plus stride is less than two times blocked in okay。

 and then I will synchronize。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_73.png)

And by that I'm done with the post reduction step Now once I finish the post reduction step what are what are the final things I need to do well I need to update my partial sum so the partial sum is going to be the value of the and the very last element of the buffer so I'm going to I would have one thread be responsible for updating the partial sum it can be any thread okay I'm just going to use threads zero so if there nextx equals zero。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_75.png)

Then the partial sum。Of the block， so partial sums of block index dot x。

 the partial sum of the block is going to be equal to the value at the very end of the buffer。

 So buffer underscore S of how big is the buffer it's two times blocked in。

 So what is the index of the last element of the buffer it's two times locked in minus1。😊。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_77.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_78.png)

Okay， so this way I've updated the partial sum and this will be used later on to scan the partial sums and then go back and do the addition。

Okay and then finally， what I need to do is I need to store my output value and just like each thread responsible for loading two input values。

 each thread is going to be responsible for storing two output values okay so I will index the output the beginning of my the segment tells me the beginning of my input segment and therefore it also tells me the beginning of my output segment so here I'm going to have output of segment plus thread indexdex X。

Is equal to buffer this for s of threat index dot x okay and of course。

 I also want to add the element that so what this does is is store to the output the first half of the result array。

 I also want to store the second half of the result array， so to do that I'm going to also have this。

 but then I'm also going to add at the end here locked in。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_80.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_81.png)

Again， so segment plus N the x+ blocked in， and will add to I will store there buffer Al index dot x+ blocked in。

Okay， now of course， here when I access the input and when I access the output。

 I need to make sure that these indices are within bounds okay so I will need to use n to make sure that these indices are within bounds and I'm not doing that on intentionally in the lectures I'm not worrying about boundary check and'm assuming that n is evenly divisible by two times blocked in but in practice this might not be the case so in the assignment when you solve a similar when you write similar code。

 you're going to have to make sure that that you handle the case where n is not evenly divisible by two times blocked in and make sure that when you access the input here and that when you access the output here that you perform the right boundary check。

Okay， so this is the code for the Brent Kung scan， any questions about it before I run it？Yes。

 can repeat past the last two lines what we what we did。 Okay。

 so what we did is we loaded in at the beginning up here。

 we loaded the input segments to shared memory。 and then we did our scan in shared memory。

 And then we have a result in shared memory。 So we wantna we wantna store our scanned result to global memory。

 Okay， so here but when we're done with the reduction step of the post reduction step。

 my result is still in shared memory。 and I will store that to the output， which is global memory。

 So here that's what I did。 Okay， clear。😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_83.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_84.png)

Yeah， okay。 yeah， but we did we did twice because we have two two blockss。Oh we did this sorry。

We did it twice and once for segment plus so the reason we did it twice is because the thread block is responsible for twice as many elements as the number of threads that it have。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_86.png)

Okay， so that is why when we loaded the input out。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_88.png)

Each thread had to load two input values and when we stored the output elements。

 each thread has to store two output values。Okay， otherwise we would we would need to have threads that were only active when we are loading the input over here and then storing the input output over here。

 which is a waste。ok。Then let's compile it。Let's hope it runs correctly for the first time and we don't have to do any debugging。

Okay there we go， so the result is correct and as you can see the baseline code took 50 milliseconds whereas in the CPU code。

 whereas on the GPU it took around six milliseconds to perform the scan。

Okay now of course the total time is high because there's high overhead from doing the copy2 and the copy back。

 however， in practice if your data is already on the GPU。

 it's definitely worthwhile doing this scan on the GPU and not bringing the data to the CPU。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_90.png)

ok。😊，So this is the code that。Sat and if we want to do it in an exclusive scan。Okay。

 there's two approaches to do the exclusive skill。We can do what we did with the coji zone approach where we just formulate the exclusive scan as an inclusive scan by shifting the elements one input to the left。

Okay， but there's also kind of another way to do the exclusive scan and that is by using a different post reduction step Okay。

 let me show you what that looks like so if we want so theres so there's there's a kind of another way and the rent con approach to do the exclusive scan the reduction step remains the same so we do a reduction step just like with the inclusive scan。

However， what changes is the post reduction step。So when I want to do the exclusive scan。

 I can change the post reduction step in order for me to achieve an exclusive scan， okay？

And this is what I will do。The first thing I do is that I'm going to set aside this x0 to x7。

 this is going to be the sum of all the elements in my array。

 so I will need that because this is going to be the partial sum of the block。

 but it's not going to be part of the result in the actual array because this is an exclusive scale。

Okay， so I will set aside x 0 to x 7。 I will save it as the blockss partial sum。Okay。

 but I will replace it with zero。And now， now， since this is exclusive skin， this0 is misplaced。

 I'm supposed to have 0 in the very beginning， right， This x 0 is misplaced。

 X0 is supposed to be here。 This x 0 to x 1 is misplaced， It's supposed to be here。

 This x 0 to x 3 is misplaced。 It's supposed to be here。😊。

So somehow I want to take the zero back all the way here to where to its place。

 I want to take x0 to its place， I'm going to take an exit x1 to its place。

 and also I want to complete these other values。Okay， and the way I will do it is as follows。

And the first step。My stride is four， and what I will do is I will move the zero here。

And I will add the zero to x0 to x3 and put the result over here。Okay。

 now I know this looks a little bit weird， but it'll make sense in a minute。Okay。

 what I'm doing is I wantanna， I want to move x 0 to x 3 over here eventually。

 But intermediatemedialy， what I will do is I'm gonna move it all the way here。 And then later on。

 I'm gonna move it back。 And I'm gonna to move this 0 all the way here eventually。

 But what I'm going to do is I'm actually gonna move it only this， this far。 And later on。

 I'm gonna move it back。😊，Okay。So I moved the zero here and I moved at  zero to x through over here while adding it to zero。

And the next step what I want to do is I want to move this zero closer to where it's supposed to be。

 which is here。 and I want to move x0 to x3 closer to where it's supposed to be。 Okay。

 so in the next step， I will move the0 over here， and I will move x0 to x3 over here。

 but I will also add0 to x0 to x1 and put the result here。 Okay。

 remember x0 to x1 needs to come here， but I will temporarily move it here。😊，Okay。

 and here x4 to x5 still needs x0 to x3 so that I can get x0 to x5 and then I need to move it here eventually。

 but what I will do is I will add it to x0 to x3 and bring it here okay and then later on I'm going to bring it back to where it's supposed to be which。

Okay， and you can probably now see more clearly where this is going。

Okay so here I have a stride of four and what I do is I move one of the elements and then I add another one of the elements okay and the next step I have a stride2 and again I move one of the elements and then I add another one of the elements and then the final step I will do the same thing with stride equals1 and voila everything now works I move0 over here I move x0 over here by adding it to x1 here x2 was missing x0 to x1 so I add it to x0 to x1 to get x0 to x2 over here and I move x0 to x1 down here Okay same thing with over here and safety with over here and this post reduction step is indeed a clever way of achieving an xs scan without formulating it as an inclusive。

😊，ok。😊，Is this clear to everyone， so here this post reduction step is exclusively for the exclusive scan。

Any questions？Now professorfes， I'm struggling to see why we just don't do it the same way and then。

I keep the zero at the end and then just。Send whatever， like。

 send it all with like a delayed index of one， like I-1 We can it We can't do it that way。

 We can do it that way。So two ways to do it。Okay。One way is to formulate it as an inclusive scan by shifting all the input elements。

Okay， and another way is to use a different post reduction step。

Right and both of these are valid ways of doing it right I just wanted to show you this way because it's a clever way of doing it and it's kind of nice to observe how it works。

Okay， and there's actually a second reason why I want to show you this approach。

 the reason I would like to show you this approach is because we're not going to implement this approach in class that you will have to implement this approach for your assignment。

😊，Okay， so so another reason why I'm showing you this is you'll implement this approach for your assignment。

 it is true that we can also use the inclusive formulation。

 however this hopefully you will find this as an enjoyable exercise to practice reasoning about thread indices and how to pick the right indices and reindex the threads when you are implementing something like this。

😊，Okay， we have to worry about the。The array not being a like multiple of the number like of the size of the block。

 So having edge， so in the homework assignment， you will have two things to worry about that we didn't do in class。

 One of them is you will need to worry about the boundary checks when you read the input from global memory and store the output to global memory and the other thing that you will have to do in the assignment is you will have to implement this post reduction step for the exclusive scan as opposed to the post reduction step for the inclusive scan that we did in class。

Okay， thank you， okay。Okay， so so what do you guys think do you guys like this Brent Kung approach for doing parallel scan？

What do you guys like more， this approach or the Cojistone approach？This is more convoluted， but。

It's nice。RightSo this is yeah， this is I think the coaches stood was maybe a little simpler。😊。

But remember， this is more work efficient， right， remember。

 the Coji student approach was less work efficient。 This approach is more work efficient。😊。

But it takes more steps。That will certainly times better performance。

 the coaches Thor approach or this approach。The Koge Stone approach。

Why do you think the country that approach does better？I mean。

 my point of view is just if we're running it on a GPU might as well ferize it as like as much as possible and not have many steps。

 like this is more sequential than the other one in some regards。 So this one。

 this would takes more steps， but it does do less work， right。Yeah but of N work。

 Cojistone does all of N log and work。So thats remember the performance of our Coji Stone approach。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_92.png)

So here， remember， we got six milliseconds for the Brent kga inclusive scan。Let's go back。4， I think。

Let's go back and this is our code for a Kooji stone， so let's run it。

Let's see what the performance we had and it was around four point something。Okay。

So the lesson here is as you know work efficiency is very important， but we always have to。

 sometimes there's a trade off that we have to make。Okay， let's see what's going on。

 So work efficiency is the reality， while the redk approach has higher theoretical work efficiency than the coachjistone approach。

😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_94.png)

In practice， its actual resource consumption on the GPU after accounting for the inactive threads is O of N logM。

 and what do I mean by that？If we go to a。We go back to the comparison。Okay。

 it is true that the cogistone approach does more work than the bread flu approach。

 the bread cl approach does less work。However， on many of the itdoerations that the bread Co approach is doing less work。

The work that I'm saving。ItBe done by threads that are bound to these threads by S0 anyways。Okay。

 so once I get to the point where I'm using a single warp right when I'm using multiple wars fine right I'm saving up。

 I'm saving a lot of work。😡，But once I get to a point where I'm' inside of a single war。

Right using fewer threads， using 16 threads in the warp instead of using 32 threads in the warp。

 so having the warp， having 16 threads do an addition in the warp instead of having 32 threads do an addition in the warp doesn't really benefit me。

Because even if I've saved those threats from doing any work。

 they are still occupying resources because of the way that S works。ok。😊，Yeah。So in practice。

 it's actual resource consumption on GPUs after accounting for inactive threads。

 so if I consider the inactive threads that are occupying cores because they're bound by Cindy。

 it actually is more similar to N log N than it is similar to log N so it is log N perhaps in the amount of real work that it does。

 but it is N log n closer to N log N， if you consider the inactive threads the threads that are not doing work。

 but they are occupying cores because of Cindy if you consider those to be doing work。

 then it would be closer to O of N log。Okay， and that is why the performance of Brent Kong on GPUs in particular。

 or in general， if we have C is similar or sometimes maybe even worse than Koji Stone as we saw。Okay。

 so it is still an interesting case study。 We still showed you this bread cook approach because we think it was an important case to study in order for us to learn about work efficiency and see the trade off。

Between work efficiency and parallelism， so sometimes it might be worth paying to it might be worth performing more redundant work in order for us to be able to get more parallelism。

ok。😊，Any questions？Somebody saying if we're bound by Cindy。

 the inactive threads are actually performing the same computation as the active threads。

 but we're disregarding their result， what I mean is that。

If those the inactive threads that are bound to the active threads by Cindy。

 if they performed computation or they didn't， it will not impact the performance。Okay。

 so had they been active and doing and performing actual computations。

 we would not have seen a performance difference because that work was completely hidden because they were bound by S。

Okay so yeah， the power construction dynamic power where the A is are surrounding and they're still performing computation。

 but we're just not taking the result and because they're bound by C you know it's not you know they're still performing the instructions right right。

 I mean it just depends how you want to think about C you can think about them as performing the instructions is not taking the result if you know。

Okay， so so having seen this， a final topic I'd like to talk about。

 since we've spoken about Oic efficiency， a final talk I want talk about is threat coening。Okay。

 so remember， we said that thread coursening is an optimization that is useful whenever we have a certain price that we pay to paralyze something。

Okay， and what is the price that we pay to parazes skin？Well similar to reduction。

 we have the synchronization overhead and we have the control divergence Okay。

 well there's another price that we paid the paralyzed1， particularly with Kojistone， what is it？

Sure that I mentioned on the previous slide。Shared memory。Well， that's not what I had in mind。

What's the overhead？Paralyzing skin。The work so you're doing more work。

 I guess right exactly work efficiency， So paralyzings can incur the overhead of lowering the work efficiency of our algorithm。

Okay， now if all my thread locks are going to run in parallel， then that's great。 Okay。

 I'm paying that price of lower work efficiency in order for me to get parallelism。😊。

But if the resources are insufficient and the hardware will serialize these threadlocks。

 then this this work， this lowering of the work efficiency that I'm paying is unnecessary。

 So what can we do in this case in order for us to to reduce the loss in work efficiency that we're getting from over paralyzing the workload。

When we can apply thread courses。Okay。And the way to apply thread cosing in the context of a scan。

 one way to apply thread cosing in the context of scan is using a segmented scan and the way we do that is that every thread is going to scan one is going to have its own segment。

 it's going to scan that segment sequentially。Okay， and remember。

 sequential scan is more at work efficient than parallel scan。

And then we're going to only have a parallel scan on the partial sums of each thread。😡，Okay。

 so if you remember， before what we did is we took the input， we segmented it。

 each block got a segment， each block did a scan of its segment and it produced partial sums。Okay。

 we scan the partial sums and then each block added the corresponding partial sum block to its elements。

Well， what we can do is within each block。We can also do a se method scan。

 so if we zoom in one of these blocks。We can also do a segmented kit。

 so if this is the segment that the thread block is responsible for。

What we can do is we can have each thread in the block take a sub segmentegment of this segment。

The thread scans its subsegment。Okay， each thread places its value and another array。

The thread block does a scan of this array of these thread partial sums in parallel。

 We've already seen how the thread block can do a scan in parallel。Okay。

 and then each thread is going to take the partial sum that corresponds to it and it's going to add it to its element。

And then we produce the final scanned result for the entire thread block。ok。😊。

So just like we use segmented scan to segment the input and divide across many blocks。

 we can use segmented scan to divide the block segment across many threads and have the threads do a sequential partial scan in order for us to improve the work efficiency of the algorithm。

 is this clear to everyone。Would do you guys like to implement this？All right， let's give it a try。

And see what this will look like。Let's go back to our code。

 I'm going to implement it in the context of the Cojistone。

 but it's the same thing whether we use Cojistone or brandcon okay so here。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_96.png)

Remember our time must for millisecond and let's see how much improvement we can get if we apply courseing to improve the work efficiency of ourco so the first thing I'm going to do is I'm going to define a co settinging factor so I'm going to call it course。

😊，Factor and let's set it to8 for example， so every thread is going to take eight elements。

 scan them sequentially produce a partial sum for those eight elements and then we're going to scan those partial sums in parallel okay。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_98.png)

So let's get started。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_100.png)

The first thing we need to do is we need to identify the segment that the thread block is responsible for so this time and there's going to be two doses of segment there's going to be a block segment and there's going to be the thread segment so I'm going to call this BB segment。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_102.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_103.png)

Okay so the thread block is going to be responsible for remember this is Coji stone so if I have block dim threads then without cosing i'm going to have block dim elements in the in the block so web coaring how how many elements am I going to have per block。

😊，So when each thread took one element， I had block in elements。

 when each thread is going to take eight elements， I'm going to have block dim times eight elements or in general。

 I'm going to have block dim。Times， correspondingse winning factor elements forla。Okay。

 so to find out where the blocks segment starts， I'm going to multiply block the times person in character by the block index。

Okay， so now every thread block has 1024 elements and every thread block is going to take 1024 times8 sorry every thread block has 1024 threads so every thread block is going to take 1024 times eight elements okay。

 so block  zero is going to start at zero block one is going to start at eight times 1024 block two is going to start with it's times 2024 etc。

All right， now that I know where the block segment starts。

 the next thing I want to do is I want to load。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_105.png)

The entire block segment into shared memory。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_107.png)

ok。😊，So that I'm going to have to create。A shared memory buffer。

I'm going to call buffer underscore for S。Okay， and I'm gonna need to load the whole block segment。

 So how big is the shared memory buffer going to be。 Well。

 every thread block we said is going to be responsible for block dim times coning factor elements。

 So the size of the shared memory buffer is going to be block dim times coning factor。Okay。

 now that I've declared this buffer， what I want to do is I want to load this entire buffer into shared memory。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_109.png)

Okay， now what's the best way to do this， Should I have thread zero load these elements and thread one load these elements and thread to load these elements。

 is this the best way to do it。No， is there a better way？

The thread zero loads element at position zero and then zero plus block times one plus long da times two right right exactly so I want threads zero to all the threads to load the first part that all the threads to load the second part all the threads load the third part etc。

 because I don't understand what each thread to load the elements it's responsible for because that won't have good coalescing behavior okay。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_111.png)

So what I do is I want to load， I have eight subsegs in my segment。

 okay and I'm going to load them one at a time so I will have a loop。4。Unsstein and C equals0。

 C is less than the coarening factor。Plus plus C。ok and then。Wofffer underscore as of。And again。

 every thread is going to load just when C is0， every thread is just going to load the element corresponding to its index When C is one。

 every thread is going to load at block them plus its index when C is two。

 every thread is going to load at two times lock and plus index。

 its index in general and if we're going to have C times block them。Plus。😊，Threat indexd。ex。

And the value that it loads from the input is going to start at the block segment in the input and plus c times block in plus thread index。

Okay， so here what we've done is we've loaded the eight segments in the block in a coalesced manner Okay。

 next we're going to sync threads。To make sure that we've loaded the entire block segment before we proceed to processing it。

Okay， now that we've done this， the next step is。huge threat to scan its own segment。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_113.png)

Alright， so now we're going do the thread。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_115.png)

S。Okay， and to do that， I'm first want to find each thread segment。

 so I'm going to call that each thread segment within buffer underscore S Okay。

 so I'm going to call that。T segment。So unsigned N T segment。

 a T segment is going to point to the segment of the thread within buffer underscore score S。Okay。

 so what's that going to be， what it's going to be the every thread is going to have how many elements。

 every thread has eight elements。Right so then it's going to be the co setting factor times。Bread。

Index dotex。Okay。After finding out the beginning of the thread segment。

 we're going to loop through the element that the thread is responsible for and perform as can okay。

 so we're going loop over the elements we have course factor elements we're going to unsign and C equals and we're going to start at one you'll see Y C is less than the coing factor。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_117.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_118.png)

And plus plus D。Okay， and then we're going to do the scan。

 How do we do the scan Well buffer underscore S of we go to the thread segment。Okay， and we add C。

 Okay， is equal to。Bffer underscore S。Of the thread segment plus c minus-1。 Okay。

 the reason we start at one is because the first element in the in the inclusive scan array is just the element itself。

 Okay， so we don't need to do anything。 But when we do the sequential scan， the second element。

 we add to it the first element。 Now the second element becomes the sum of the first two elements。

 and then the third element， we add to it， the second element。

 which was some of the first two element。 And now the third element becomes the sum of the three etc。

 Okay， so is basically a sequential scan。 And remember sequential scan is work efficient。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_120.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_121.png)

Okay， so for C equals one C is less than corresponding factor plus plus C buffer of T segment plus C is equal to buffer of t segment plus c minus1。

 so now when we're done with this， every thread is done scanning its own segment。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_123.png)

Okay。The next part is for each thread to put the sum of all the elements inside of its segment in some array where the thread block will do the scan of the partial sums in parallel。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_125.png)

Well， we've already written the code to do a thread block wide partial sum parallel。

 That's the code down here。 Okay， so then all that we have to do。

Is over here in this in buffer over here remember this is the Co stone approach that was doing double buffering。

 So the first thing we were doing is we were initializing the buffer rather than loading from global memory。

 we already loaded from global memory So what we're going to do is we're simply going to put in this buffer that we're scanning in parallel we're going to put the partial sum of the thread law of the thread okay so the partial sum of the thread is going to be the last element in the thread segment so it's going to be at buffer underscore S of the thread segment okay but we're going to look for the last element in the thread segment so that's going to be plus the size of the segment which is course factor minus1。

ok。Clear to everyone。Okay， so then after we placed the threads inside of the this array。

 the thread block is going to do the partial southern parallel。

 So so now each the block is going to do its own scan and。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_127.png)

And then it's going to give us the scanned buffer underscore S。

 So here this in buffer is going to get scanned by the thread block in parallel using this code that we wrote before。

 And at the very end over here， we're going to have in buffer underscore S is going to have the scanned partial sums of the threads segments。

 So after we've finished the partial sum Now each thread is going to take the corresponding partial sum and add it to its own threads。

 Well it's going to take the partial sum for the previous blocks for the previous previous threads and add it to all of its own elements。

 Okay now obviously the first thread doesn't have to do any addition because these results are already complete Okay。

 so what do we need do。😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_129.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_130.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_131.png)

We're going to write F。To index dot x is greater than zero。 So the first not going to do a scan。

Is not going to do any addition， okay， each thread is going to loop over its elements。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_133.png)

And add to them the result of these stand partial sum。Okay。

 so how do I loop over the elements of a thread segment where we just loop over the loop over we have a core setting loop。

 so we're going to unsigned。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_135.png)

And C equals0， C is less than the coening factor。pl plus z。Okay， and then each thread。

The B rid score S of T segment。Plus C， so for each for each element that the thread is responsible for。

 it's going to add the partial sum。Of the previous。Ths。

 because said at the partial sum of the previous threads。 Where are the partial sums of the threads。

Sorry， this is not supposed to be no sorry this is buffer as the partial sum of the threads are inside of end buffer okay because this is where we because end buffer was produced by the block parallel scan。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_137.png)

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_138.png)

Okay， so here we're going to do。In buffer underscore S of。Bread index dot x minus-1， right because。

Thread 1 is going to add the sum of thread 0 the elements and thread0。

 thread2 is going to add the sum of the elements and thread 0 and thread1， Okay。

 which are going to be in the scanned array， it's going to be this value here。

 Tread 3 is going to add the elements once to add the elements and thread 0，1 and2。

 which in the scanned array， it's going to be the result at index 2。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_140.png)

Okay。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_142.png)

So we're going to do buffer of T segment plus C， we're going to add to it in buffer ofendex that x minus1。

Okay， of course we're going to put the partial sum of the entire thread block so that that gets scanned separately and then finally when we store the result of the output just like at the very beginning over here every thread。

Loaded multiple input elements。 Okay， now every is going to have to store multiple output elements。

 So here we're going need to have four。Of course， we need to sync threads over here， by the way。

 because we need to make sure that all the threads have updated their buffer underscore S。

We we're ready to think。Brereads。Okay， and then we're going to。

Loop over the outputs for unscied speed equals 0。 speed is less than the。

For sittingtting factor plus plus C。And then the output of the block。Segment plus B times D。

Locked in。Plus。Td indexd do x right so this is the same index that we use when we were loading the inputs right so the block segment plus c times log in plus red index do x。

Okay， is equal to。And in this case， I'm going to use。

The shared memory buffer for the entire block segment， which is buffer underscore square S now。

 and I'm going to index it with C times locked in once start an index product。Okay。So with that。

 what we've done is we've implemented the Sened version of S。

Okay professor best yes question at some point maybe there's a mistake I'm not sure when you do the when you place back the part in the partial sum。

 you're using in buffer， but shouldn't you be using buffer？This is fine。 You can do either。

 The reason is that these the sum of。😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_144.png)

The result of adding。This value to the last value here。 Well， the last value here is this value here。

 right， last value in thread 3 is this value over here。

 So the result of adding this value to the last value here。It's the same as this value here。

All right， okay， okay， sorry， So the last element in in buffer， which is this array。

 is the same as the last element in buffer underscore S， which is this whole array。I see。 Okay。

 thank you。 So yes， I could have numbers class over here， either as white。



![](img/482f2f0d92befbcc79cf261f4a8d8f5b_146.png)

啊ok， so啊呃 so then。😊，Two more things to take care of and my ad kernelel i'm going to co in that as well just so that I have the same correspondence between blocks so here going I'm going to define again a block segment so i'm going to have。

Andign and。B segment is equal to block them times。Forest factor。

 which is the number of elements that' responsible for times block indexdex。X。And then similarly。

 I'm going to have a loop， let me just copy it for the sake of time。Okay。

 I'm going to have a loop over here and then every in every iteration。

 the thread is going to take the elements responsible for which is B segment plus。

Same thing as lock in for x x and it's going to add to it the partial sums from the previous thread block okay and then finally I applied course settings I need to launch fewer blocks right so then I'm going to go all the way down here I'm defining the number of elements per block and rather than the number of elements per block being none threads per block it's going to be non threads per block times the。

Lorth the in。Fact， okay。So with that， thank you for being patient and waiting for the whole implementation of courseing to complete so having said that let's compile and now let's run it。

And remember before we had formally seconds and now， oh， we have a mismatch。ok。

So there must be a bug somewhere。One second， let me figure out what the bug is。Okay。

 so here we're back in the code。And basically the problem was that over here when we were doing the thread scan rather than doing buffer of t segment plus c plus equals a buffer of t segment plus t minus1。

 I just did equals over here， so this was the problem this was supposed to be a plus equal。

The screen is frozen， rec canian。I sorry about that。It's fine。Okay。

 so I'm back in the code over here and the main problem the reason behind the bug was that over here rather than having plus equals I just had an equal sign so this is the part that was doing the thread scan where scan the thread was doing a sequential scan of its own segment so this was supposed to be plus equals so every thread is going to add the previous the previous accumulation to the current value okay so let's compile this。

And now let's run it and see the time and as you can tell we're down before we were at around four and a half milliseconds and now we were at around one and a half milliseconds from applying threat course living sorry our code is almost three and a half almost three times faster than it was without course okay。

😊。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_148.png)

So this over here is the code that we just wrote and you can read what we talked about today and chapter8 of the textbook and that is all for today does anybody have any final questions before I finish？

Okay， if not， then that's all for today and I will see you next time， bye everyone。Thank you。

 professor。

![](img/482f2f0d92befbcc79cf261f4a8d8f5b_150.png)