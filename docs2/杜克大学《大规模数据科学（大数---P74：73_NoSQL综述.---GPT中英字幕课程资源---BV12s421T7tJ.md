# 杜克大学《大规模数据科学（大数据操作，第1课／共3课有视频）｜Data Science at Scale》 - P74：73_NoSQL综述.zh_en - GPT中英字幕课程资源 - BV12s421T7tJ

。

![](img/870c9c8ca96efed1d56c58bbebe44907_1.png)

What we haven't talked about is this no SQL system。

 and so I want to use this table as a way to sort of organize the roadmap for this discussion。

 And so what I've done here is tried to list out。By feature。

 a bunch of relevant systems in this space。 And right now， they're sort of sorted by。Time。

 and so these features are。Amittedly selected by me for what the important ones are。

 but I don't think they'd be too controversial and I don't think there's anything obviously missing here either Okay so going through these briefly。

Then a major one here was that it needs to scale to sort of thousands of machines and there's some need to look up by a primary index。

 what I mean by that is by some key value you can look up by some record identifier。

And then another feature that they may or may not have is we'll look up by secondary indexes。

 So I mean， here is you can look up by some attribute that is not that key。Okay。

 and so databases have this， for example， you can build an index on any attribute you want and the optimizer will take advantage of it。

third one， and this is the one we'll spend a lot of time on because it's sort of。

Pretty fundamental to the motivation for why NesQL systems sort of earn their own moniker or different AR。

Transactions。Okay， and you can also see that there's some complexity here that I'll try to explain as we go through this。

 So it's not just a yes or no。 It's kind of depends on the case by gaze。Okay。And then this field is。

Whether or not these systems support。Essentially， joins， but I've generalized that to analytics。

 And I'm perhaps guilty of making those two things almost synonymous。 If you， if you can do some。

 if you can do joins， then there's a whole space of different kind of analytics things you can do。

 And if you can't do joins， then you're leaving all that work up to the client。

 And all you can do is retrieve data。 And so that's really a。

A key indicator of how much computation you can push into the system and how much you have to sort of bring the data back out to the client。

 okay？And then integrity constraints， so I debated about calling the schemas of integrity constraints。

As I think we'll see。呃。Arguably， some of these systems do indeed have a schema。😡。

But may or may not actually enforce that schema and so it's。Just to avoid the confusion。

 I'm going to call this integrity experience。 So this is sort of hard schemeche as， if you will。

 Okay， and then views， which if you remember is is I'm。

Declaring that to be synonymous with logical data independence。And then finally。

 is there some sort of decative language or algebraic way of programming against this thing。

 or is it really just sort of a low level simple operation API？Okay。All right。

 so a couple of caveats here one is I haven't included any parallel databases on this list at all。

 although there's absolutely no reason why you couldn't。Include them here。

 they would tend to have a lot of check marks across this。R。嗯。But since the focus is no SQL systems。

 I am leaving those out。And then the other caveat I make is that individual cells in this table。

Maybe debatable depending on how you interpret the columns。

 so this isn't necessarily meant to be hard and fast rules， but again。

 I don't think they'll be wildly controversial either okay。

So one of the first stories you can tell by staring at this table is that。Relational databases。

 you know， been around for quite a while and have check marks sort of everywhere。

 have all these features， except they weren't really ever shown to scale to lots and lots and lots of computers。

 right， Everything was sort on the order of tens of machines。 Okay， so why don't they scale。 Well。

 we talked in the map produce segment about sort of。

Read performance and related and sort of analyze some experimental results from a。

Paper in 2009 comparing sort of the benefits and strengths of mapreduce versus。呃。Databases。

So maybe on read performance， there's an argument to maybe that they did scale。

 but one area where they。Certainly didn't， or at least certainly weren't shown to scale to this level。

 was in。Updates okay， so not just the read and not just the analytic workload。

 but the transaction processing workloads。

![](img/870c9c8ca96efed1d56c58bbebe44907_3.png)