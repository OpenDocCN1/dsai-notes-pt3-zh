# 杜克大学《大规模数据科学（大数据操作，第1课／共3课有视频）｜Data Science at Scale》 - P57：56_MapReduce示例：单词长度直方图.zh_en - GPT中英字幕课程资源 - BV12s421T7tJ

。

![](img/92bcb4a3040e83a8d8c9c79d7af57e04_1.png)

So let's talk about another example that is sort of similar to this very simple word kind example。

 but has a slight change。So now we want to maybe know the makeup of a。Corpous of documents。

 a set of documents and try to understand the characteristics of the word length。

 and so now instead of a histogram on word usage， we're going to group things by the length of the word Okay so we want to know how many words have greater than 10 characters and so on You know here we might group words into big words。

 medium small words and tiny words。Where the big words are everything that's 10 plus letters and the medium words are in red here and they're everything from。

5ive to nine letters and so on。 and you could define your own sort of bucketing scheme or just not even try to bucket them and use the exact number we're basically showing here。

So I'm hoping that some of you are already kind of seeing how this is a essentially trivial。

Vant of what we already just did and this is one of the points I want to make is that you'll see these patterns in designing reproduce produceduce algorithms come up again and again and so once you try to get a feel for how to do it。

It won't be that every new problem looks looks different。

 but the other the other thing that about maybe the next few slides。

 I think is that it shows a little bit more detail in how these things are broken up。 So for example。

 if this is a document I guess the point I want to make is that before we sort of assume that every document was a small thing。

 but it's not impossible that you might have one document that's very， very， very large。

 This typically wouldn't happen with a document for various reasons。

 but imagine these weren't just documents， but these were just big data sets of words。

 an individual document may be so large that it can't be processed by a single map function at a time。

 And so the question is are are we stuck here this is is the map produceuce framework broken and it's going to crash And the answer is no what will happen is when you。

Load this large document into the system supporting map or do and we'll talk a little bit more about what this lower level system is and what I mean by loading。

The file system underneath Mapreuce， underneath implementations of Mapreduce。

When you do that loading， the file the data set the file will automatically be split into chunks and so we can pretend that this document was so large that it needed to be split into chunks okay and so chunk one is this top part and chunk two is this small part。

Now， if a small document is underneath the chunk size， then it won't get split。

 but a large document will okay。And so this could have happened with the word count example too。

 this is not something specific to word length， obviously， but。

It's another twist that we're exploring。