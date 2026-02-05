# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P18：17_性能审计.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

Even when your learning our room is doing well on accuracy or F1 score or some appropriate metric。

 is often worth one last performance audit before you push it to production and this can sometimes save you from significant post deployment problems。

 let's take a look。You've seen this diagram before after you've gone around this loop multiple times to develop a good learning algorithm。

 it's worthwhile auditing this performance one last time。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_1.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_2.png)

Here's a framework for how you can double check your system for accuracy for fairness of bias and for other possible problems Step one is brainstorm to different ways the system might go wrong for example。

 does the algorithm perform sufficiently well on different subsets of the data such as individuals of a certain ethnicity or individuals of different genders or does the algorithm make certain errors such as false positives of false negatives which you might worry about in sked datasets or how does it perform on certain rare and important classes so the types of issues we talked about in the key challenges video earlier this week。

 any of them that concern you you might include them in this list of brainstormed ways that the system might go wrong for all the ways that you're worried about the system going wrong you might then establish metrics。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_4.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_5.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_6.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_7.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_8.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_9.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_10.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_11.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_12.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_13.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_14.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_15.png)

To assess the performance of your algorithm against these issues。

 one very common design pattern you see is that you often be evaluating performance on slices of the data。

 So rather than。

![](img/fc5bb41266a6985c7bd2b63b5acf762d_17.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_18.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_19.png)

Evaluating performance on your entire depth set。

![](img/fc5bb41266a6985c7bd2b63b5acf762d_21.png)

You may be taking out all of the individuals of a certain ethnicity or all the individuals of a certain gender。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_23.png)

Or all of the examples where there is a scratch defect on the smartphone。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_25.png)

But to take a subset of the data， also called a slice of the data to analyze performance on those slices in order to check against these things that may。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_27.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_28.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_29.png)

The problems After establishing appropriate metrics。

 M ops tools can also help trigger an automatic evaluation for each model to audit this performance。

 For instance， Tensorflow has a package for Tensorflow model analysis or TFMA that computes detailed metrics on new machine learning models on different slices of data。

 You learn more about this tool in the next course。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_31.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_32.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_33.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_34.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_35.png)

And as part of this process， I would also advise you to get buy in from the business or the product owner。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_37.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_38.png)

That these are the most appropriate。

![](img/fc5bb41266a6985c7bd2b63b5acf762d_40.png)

Set of problems， the worryabouts and a reasonable set of metrics to assess against these possible problems。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_42.png)

And if you do find a problem， then it is great that you discovered this problem before pushing your system to production。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_44.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_45.png)

And you can then go back to update the system to address it before deploying a system。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_47.png)

That may cause problems downstream。 Let's walk through this framework with an example。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_49.png)

I'm going to use speech recognition again。😊，If you built a speech recognition system you might then brainstorm the ways the system might go wrong。

 so one thing I've looked at before for systems I worked on was accuracy on different genders and different ethnicities。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_51.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_52.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_53.png)

For example， a speech system that does poorly on certain genders may be problematic。

 or also ethnicities， one type of analysis I've done before is to carry out analysis of our accuracy。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_55.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_56.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_57.png)

Depending on the perceived accent of the speaker， because we want to understand if the speech system's performance was a huge function of the accent of the speaker。

 or you might worry about the accuracy on different devices because different devices may have different microphones and so if you do much worse on one brand of cellphone so that if there is a problem。

 you can proactively fix it。

![](img/fc5bb41266a6985c7bd2b63b5acf762d_59.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_60.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_61.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_62.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_63.png)

Or finally， this might not be an example you would have thought of but prevalence of root and misranscriptions here's one example of something that actually happens to some of deep learning AI's causes one of our instructors Lawrence Moroni was talking about GANs generative adversarial networks but because the transcription system was mistranscribing GNs because this unfortunately is not a common word in English language and so the subtitles had a lot of references to gun and Gang which were mis transcriptionscriptions of what the instructor actually said which is GN so it made it look like there's a lot of gun violence in that deep learning AI course and we actually had to go into to fix it because we didn't want that much gun gangang violence in the subtitles It turns out more generally that misrancribing someone's speech into a root。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_65.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_66.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_67.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_68.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_69.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_70.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_71.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_72.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_73.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_74.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_75.png)

Ro word or a square word that's perceived much more negatively than a more neutral misranscription。

 And so I've built speech systems as well， where we pay special attention to avoiding mis transcriptionscriptions that resulted in the speech system thinking someone said a square word when maybe they didn't actually say that square word。

 based on this list of brainstorm ways that a speech system might go wrong。

 you can then establish metrics to assess performance against these issues on the appropriate slices of data。

 For example， you can measure the mean accuracy of the speech system for different genders and for different actionss represented in the data。

 and also check for accuracy on different devices and check for offensive or root words in the output。

 I find that the ways a system might go wrong turns out to be very problem dependent。

Different industries， different。

![](img/fc5bb41266a6985c7bd2b63b5acf762d_77.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_78.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_79.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_80.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_81.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_82.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_83.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_84.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_85.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_86.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_87.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_88.png)

Cost will have very different standards。 And， in fact， today。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_90.png)

Our standards in AI for what to consider an unacceptable level of bias or what is there and what is not there。

 though standards are still continuing to evolve in AI and in many specific industries。

 so I would advise you to do a search for your industry to see what is acceptable and to keep current with standards of fairness and all of our growing awareness for how to make our systems more fair and less biased。



![](img/fc5bb41266a6985c7bd2b63b5acf762d_92.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_93.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_94.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_95.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_96.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_97.png)

![](img/fc5bb41266a6985c7bd2b63b5acf762d_98.png)

One last tip， I find that rather than just one person trying to brainstorm what could go wrong for high stakes applications。

 if you can have a team or sometimes even external advisors help you brainstorm things that you want to watch out for that can reduce the risk of you or your team being caught later by something that you hadn't thought of。

 I know that standards are still evolving for what we consider fair and sufficiently unbiased in many industries。

 but this is one of the topics that I think it'd be good for us to get ahead of and to proactively try to identify。

 measure against and solve problems rather than deploy a system to be surprised much later by some unexpected consequences。

So that's it for performance auditing with this， I hope you have higher confidence in your learning algorithm when you go out to push it to production。

