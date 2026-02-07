# 吴恩达《AI for Good专业课程》 AI与公共卫生、气候变化、灾难管理｜中英字幕 - P76：39_生物多样性迁移学习.zh_en - GPT中英字幕课程资源 - BV13u411F7xZ

![](img/a7340156a42f169270a3b43cdbba454d_0.png)

In the last video， you looked at some of the intuition behind how neural networks see image data and that when a neural network is trained to recognize particular objects and images through that training process。

 it will have learn some key features that are transferable to recognize in almost any kind of object in an image Now that's not to say the neural network trained to recognize say bicycles will also be able to recognize horses but instead that a model trained to recognize bicycles could with just a little bit more training also be able to recognize horses or trains or anything else that you have labeled images of in this lab you'll start with a model that' has been trained to recognize many different types of objects the training data that was used to prepare this model is a data known as imagenet and this is a wellknown historical benchmark data set that was commonly used for performance testing image recognition models imageagenet contains many different object categories and the pre-trained neural architecture search。



![](img/a7340156a42f169270a3b43cdbba454d_2.png)

or NsNe model that you'll be using is able to accurately identify many object classes right out of the box。

For your purposes， however， you'll apply the technique of transfer learning where you take this model that is already trained to recognize many object types and fine tunena to recognize your objects of interest。

 namely animals in the Carroll National Park， so let's head over to the lab and see how this works。



![](img/a7340156a42f169270a3b43cdbba454d_4.png)

This is the second part of the design phase in the first design lab you applied the mega detector to identify where animals were in an image in your data set。

 and then you crop those images and squared them to create a data set of pictures that contain only animals。

Now in this lab， you'll fine tune a pre traineded NAsSNe model to classify the animals in your data set。



![](img/a7340156a42f169270a3b43cdbba454d_6.png)

With this link here， you can learn more about the technical details of a NASnett model and follow this link to learn more about the INet data set that the model you used here was trained on。



![](img/a7340156a42f169270a3b43cdbba454d_8.png)

To begin you'll run this first cell to import all the Python packages that you'll need for this lab next you'll load the pretrained NASap model and try it out before phone tune in。



![](img/a7340156a42f169270a3b43cdbba454d_10.png)

So this image shows a simple visual of what you'll do next。

 you'll pass in an image like this image of a baboon here as an example。

 then you'll ask the NaSnet to classify that image into one of the 1000 existing classes of objects that NASnet was traineded on。



![](img/a7340156a42f169270a3b43cdbba454d_12.png)

![](img/a7340156a42f169270a3b43cdbba454d_13.png)

When you run this N cell， you can choose the type of animal mold to pass to the NeSNe model for classification by using this pull down menu。



![](img/a7340156a42f169270a3b43cdbba454d_15.png)

The output that you'll see here is the original image。

 and then the top three predictions from the model on the right。

 So here we've past an image of a baboon。 And now I'm trying an ostrich and the model。



![](img/a7340156a42f169270a3b43cdbba454d_17.png)

It thinks it might be a cartoon or a steel arch bridge。

 so this is obviously very wrong and let's try another one， let's try a black rhino。😊。



![](img/a7340156a42f169270a3b43cdbba454d_19.png)

![](img/a7340156a42f169270a3b43cdbba454d_20.png)

And once again， a still arch bridge and cardoon are our top two predictions and it might be a lemon well I think the model is a lemon in this particular case。

 so hopefully you've got a very good intuition now for how bad imagenet is in working on this particular data set so now let's look at a currybuted。

😊，And we cant get this right either is predicted as being either a speedboat， a lab coat。

Or my son would like this an electric locomotive， but it's also worth noting here that the probability is incredibly low。

 so less than 5% confidence for each of these so really this isn't the model saying that this is a speedbo it's the model saying I don't know。

😊，And let's do one more。 Let's look in an El and。Well。

We are now almost 100% confident that this is a still large bridge， so not only is the model wrong。

 it doesn't know how wrong it is。😊，And so I think this is funny in this case。

 but also I think a very good lesson for how models built on one data set can be really inaccurate when taken to a new data set。



![](img/a7340156a42f169270a3b43cdbba454d_22.png)

And for INe in particular， this is something that's well known。



![](img/a7340156a42f169270a3b43cdbba454d_24.png)

In fact， I was at Stanford when my colleagues first developed INet and at the very first presentation。

 myself and other people who had worked in wordnets for other languages had pointed out that yes。

 like this imageNe based on the English wordnet is going to be really biased towards a kind of。



![](img/a7340156a42f169270a3b43cdbba454d_26.png)

![](img/a7340156a42f169270a3b43cdbba454d_27.png)

![](img/a7340156a42f169270a3b43cdbba454d_28.png)

![](img/a7340156a42f169270a3b43cdbba454d_29.png)

![](img/a7340156a42f169270a3b43cdbba454d_30.png)

Animals and taxonomies of animals that you'll find in the Englishpeaking world in particular North America in Europe and disproportionately people who could afford to take digital photographs at a time when that was more expensive and so while in this case it's mainly funny there are lots of cases where this kind of bias if it's not carefully monitored and mitigated as much as possible can have a really negative impact and so we'll talk more about how we are addressing this in this data that and one of the positive things which we can take away is that well for one we can measure this bias we'll be able to look at the accuracy across different animals and we'll be able to know which of those do do not occur in IageNe but also given how terrible this is。

 I think it's kind of amazing that imagenet is going to be useful。



![](img/a7340156a42f169270a3b43cdbba454d_32.png)

![](img/a7340156a42f169270a3b43cdbba454d_33.png)

![](img/a7340156a42f169270a3b43cdbba454d_34.png)

![](img/a7340156a42f169270a3b43cdbba454d_35.png)

![](img/a7340156a42f169270a3b43cdbba454d_36.png)

![](img/a7340156a42f169270a3b43cdbba454d_37.png)

![](img/a7340156a42f169270a3b43cdbba454d_38.png)

![](img/a7340156a42f169270a3b43cdbba454d_39.png)

at all in the basis of transfer learning， but we'll find that it is because while the classification task here isn't really correct at all。

 a lot of the textures and edges that are found in the Inet data set can become useful components in identifying the images in our data set here Next you will load the data by first defining the folder where the cropped images you created in the last lab are stored。



![](img/a7340156a42f169270a3b43cdbba454d_41.png)

![](img/a7340156a42f169270a3b43cdbba454d_42.png)

And some details about how many images you want to use in each training batch。

 and we're saying 32 in this case here。As well as the size of the images in the pixels。

 and this is all just set up getting ready for training the model。



![](img/a7340156a42f169270a3b43cdbba454d_44.png)

Next， you'll apply a technique that we call data augmentation that you'll use to compensate for this fact that your data set is imbalanced across the different types of animals and camera locations。

Run these next two cells just to prepare some images for visual。When you run this N cell。

 you'll see a picture of a baboon that I'll use here as a sample to show different kinds of image or。



![](img/a7340156a42f169270a3b43cdbba454d_46.png)

![](img/a7340156a42f169270a3b43cdbba454d_47.png)

But if you want to change this number up here from anything from  zero to the 31。

 you will be able to see the same effects for different images。



![](img/a7340156a42f169270a3b43cdbba454d_49.png)

With augmentation， you will use your existing data to generate new labeled image examples to balance your data reset and help your model learn。

R this next cell to see examples of a simple augmentation technique of flipping an image about the horizontal or vertical access。



![](img/a7340156a42f169270a3b43cdbba454d_51.png)

So if you choose horizontal here， you can see what it would look like to flip this image from left to right。

Now， you can add this new flipped image to your data set as an example that's different from any of the existing data。

 but represents a realistic example of the object that you're trying to identify。

 You can also choose vertical here to flip the image top to bottom。 Now， in this case。

 you might say that this does not look like a realistic example because you're never going to see an image in the real world with an upside down baboon or pretty rarely。

 however， for the purposes of model training， this is a legitimate augmented example。

 because it still contains the animal and can help your model avoid learning things about the sky or bushes or the orientation of the animal that might confuse it in later attempts at classification。



![](img/a7340156a42f169270a3b43cdbba454d_53.png)

And I'm sure can imagine that if you're doing this for something like satellite imagery。

 we would have perhaps almost no concerns at all about flipping vertically。

 and of course you can also flip the image both horizontally and vertically to come up with a third variation。



![](img/a7340156a42f169270a3b43cdbba454d_55.png)

So by flipping an image like this， you can create three new example images for your model to train on that are different from the original data set and will help your model learn at this point though you're probably thinking this is not as good as having three images of completely different babos at different camera locations。



![](img/a7340156a42f169270a3b43cdbba454d_57.png)

![](img/a7340156a42f169270a3b43cdbba454d_58.png)

And you're certainly correct and again， this is something that you should be able to evaluate in the testing phase。

 are you less accurately able to identify animals that were less frequent despite the data augmentation。



![](img/a7340156a42f169270a3b43cdbba454d_60.png)

![](img/a7340156a42f169270a3b43cdbba454d_61.png)

Another way to augment your data is to apply Zoom factor to images when you run this next cell。

 you can use the slider here to adjust the zoom and see the different variations of this image that you could create with different Zoom factors。



![](img/a7340156a42f169270a3b43cdbba454d_63.png)

![](img/a7340156a42f169270a3b43cdbba454d_64.png)

Similarly， you can apply a rotation to the original image to come up with an augmented variation。



![](img/a7340156a42f169270a3b43cdbba454d_66.png)

Run this next cell and you can apply a rotation from negative 45 to 45 degrees on the original image。

 and finally， you can apply a contrast to simulated image taken under brighter or darker conditions。



![](img/a7340156a42f169270a3b43cdbba454d_68.png)

![](img/a7340156a42f169270a3b43cdbba454d_69.png)

When you run this next cell， you can use the slider to apply different contrasts。In practice。

 you will apply a random combination of flips， zooms。

 rotations and contrasts to generate the supplementary data for the purposes of trying to balance out your data set across the different classes in this case the different animal types when you run this next cell。

 try applying different combinations of flips zoom rotations and contrasts to see what kind of data this will generate。



![](img/a7340156a42f169270a3b43cdbba454d_71.png)

![](img/a7340156a42f169270a3b43cdbba454d_72.png)

![](img/a7340156a42f169270a3b43cdbba454d_73.png)

Next， we're going to do our best to balance the data set before fine tune here again。

 you'll split your data into training， validation and test sets in a similar way to what you did in the windpower forecasting lab in week two of this course。

Here again， your trading set will be the data that you would use to fine tune your NAsNet model。

You'll then evaluate the trained model iteratively on the validation set。

And then when you finish training， you'll test how well your model does on the test set。

 which is data it never saw during the training and validation process。

So as you will recall from your exploration of this data set， for some animal types。

 you have only a handful of example images and for the purposes of fine tuning。

 this will be problematic。So next in order to find tuner model。

 you'll restrict your trading set to only those animals that have a relatively large number of example images in the data set and at this point。

You're probably thinking， well， this is going to be a bias as well。

 Where animals might be just as important and you're absolutely right。

 So depending on the real world use case here， this might not be a viable option here in this lab。

 we have set a cutoff of at least 65 example images。

 which turns out to be about 11 different animals in total。

And so you'll map the numbers  zero to 10 to each of these animals here for training， you could。

 however， set a higher or lower cutoff on the number of example images。



![](img/a7340156a42f169270a3b43cdbba454d_75.png)

Next， you'll look again at how many images you have of each animal in your training set。

And then you'll resample each image class， which means up sampling some classes and down sampling others such that you have the same number of each class to train on What this means is that for some classes。

 you'll discard excess images and for others you'll make more copies of the images that you already have。



![](img/a7340156a42f169270a3b43cdbba454d_77.png)

Making copies of training examples might not sound like a particularly clever way to increase the number of examples in your training set。

 but next you'll look at how you can augment your data to simulate different training examples。



![](img/a7340156a42f169270a3b43cdbba454d_79.png)

Next you'll load another version of the NASNe model for fine tune in to our specific data here to do this。

 you'll freeze the lower layers， meaning for the layers of the network that have learned features that are common to detection of any kind of objects such as edges and specific textures。

 you'll leave those layers as they are and not modify them during training。

If you're an AI practitioner and you're interested in more detail of the model architecture。

 you can run this Excel cell to print out a summary of the model architecture。



![](img/a7340156a42f169270a3b43cdbba454d_81.png)

If you're not familiar with neural network models prior to this course。

 I guess one takeaway here is that there are very many layers in the NASNe model and this is pretty typical of large scale image recognitionition systems。



![](img/a7340156a42f169270a3b43cdbba454d_83.png)

And the next step is to train the model， this involves adding a final layer that is set up for the 11 classes that you hope to train on。

With the code that's written below here， you could train this model for as many epochs or iterations as you like for fine tuning the finalizer of your model to optimize for identifying the animals in your data set。



![](img/a7340156a42f169270a3b43cdbba454d_85.png)

To run fine tuning for a sufficient number of epochs， it would actually take a long time。

 possibly several hours， so we have already completed the fine tuning step for you by training for 150 epochs and save the result。

By running this D cell， you'll load the model that was trained for these 150 es。

To get a sense of what the training process looks like。

 you can run this next cell to train your model for one additional epoch which should take a minute or so to run。

You can try training for more than one epoch as well if you'd like by changing this number here。

In order to know whether you have trained your model for enough EpoOs。

 you can look at these plots below and these plots are shown you data from the original 150 APpoC training process that we performed for you。

On the left here you're looking at the number of trend epochs on the horizontal access and the accuracy of the model on the vertical access。

 so the accuracy is going up which is what you want blue is that the accuracy of your model on the training set and red is the accuracy of your model on the validation set。

What you can see is that while the accuracy of the training data continued to improve with each new ApoC of training。

 the accuracy of the validation set did not really improve that much beyond100 or so Airpos。

 so this tells you that training further will not be likely to improve your model performance and in fact you are doing what's known as overfiing your model and this is likely to lead to less reliable confidence metrics。

 like when we saw that an animal is predicted to be a bridge with near 100% confidence。Next。

 you'll evaluate your model by calculating accuracy on the test set that wasn't used during training。

When you run this cell， you'll find your accuracy on the test set is around 80%。

 which means that across all 11 animal classes that you trained on。

 you correctly predicted the animal in the image about 80% of the time。

 well 80% might not sound very high， it is actually quite an impressive result given that you have trained your model to recognize animals across 11 different classes with a relatively small data set。

 in some cases including less than 100 examples of a particular type of animal。

It is very likely that you can improve on this result by training on a larger number of labeled items。

 but by taking advantage of pretde models and transfer learning。

 youre able to create a fairly powerful animal detection pipeline with a relatively small data set。

 so this is the kind of data set that even in industry I could use as a starting point to bootstrap a much more accurate data set。

 expert human input。Here， beyond just looking at the overall accuracy of your model。

 it is informative to look at something called the confusion matrix to better understand where your model is succeeding and where it is failing。

😊。

![](img/a7340156a42f169270a3b43cdbba454d_87.png)

Now， what you're looking at is each animal class plotted along the vertical and horizontal axis。

Along the diagonal here， you can see the fraction of examples in the test set that your model correctly predicted for that animal。

 so for example， you can see that your model correctly identified babos 94% of the time。However。

 it only identified kuds 74% of the time。You can look at the cells of the diagonal to get a sense of how your model is failing when it does fail。

Here， if you read across any row， you can see that for a particular animal。

 how often your model predicted that it was something else？So for this example here。

 the blackback jackal，6% of the time， your model misclassified something that was actually a jackkyal as of a boon。

 or for the gemspo Rx。8% of the time， your modelt misclassified it as an El。And finally。

 it's important to visually inspect the results of your model for individual images。

 run this last cell to display an example image along with the top three results in terms of confidence level from your model。



![](img/a7340156a42f169270a3b43cdbba454d_89.png)

![](img/a7340156a42f169270a3b43cdbba454d_90.png)

So here is an image of a baboon from your test set and on the right you can see the confidence associated with the top three predictions for your model so you can see that for this image your model predicted correctly baboon with the highest confidence。

You can use this pull down menu to see examples of other animals in your test set along with your model results。



![](img/a7340156a42f169270a3b43cdbba454d_92.png)

So in this example， we have a curry busard and we have correctly predicted this with almost 100% confidence。

 so this is a great result。And here we have a gemswalk RX， which was misclassified as an El。

 and you can see the third classification here was the correct one。

 but that was at less than 10% confidence。

![](img/a7340156a42f169270a3b43cdbba454d_94.png)

And finally here we have a blackbacked jackkyal and again we correctly identified this with about 100% confidence。



![](img/a7340156a42f169270a3b43cdbba454d_96.png)

So try this across a number of different animals with this pull down menu to see examples of how other animals performed in your data set。



![](img/a7340156a42f169270a3b43cdbba454d_98.png)

![](img/a7340156a42f169270a3b43cdbba454d_99.png)

Congratulations， you have now prototyped a working model pipeline that can take you from a raw camera trap image on through to classification of each animal that appears in an image。

 and you've thought about the limitations of starting from a pre tradede model from very different data to the data that you're applying it to and consider how much you can make up with transfer learning。

The next step will be to pull your modeled pipelines together into a final implementation with the user interface。

 but before we do that， join me in the next video to wrap up the design phase。

