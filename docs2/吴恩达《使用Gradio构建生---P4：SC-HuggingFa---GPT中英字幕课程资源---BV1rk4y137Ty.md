# 吴恩达《使用Gradio构建生成式人工智能应用程序／Building Generative AI Applications with Gradio》 - P4：SC-HuggingFace_L3.zh - GPT中英字幕课程资源 - BV1rk4y137Ty

![](img/3debe5a7620fb7530158b03de96b66b4_0.png)

In this lesson， we're going to build an image generation app with an open source text2 image model。

 It takes a description and generates an image with it。 Let's do that。

 The image generation model is a diffusion model called stable diffusion。

 And we're connecting to this model on a server using an API URL。 So here we set up our API key。😊。



![](img/3debe5a7620fb7530158b03de96b66b4_2.png)

![](img/3debe5a7620fb7530158b03de96b66b4_3.png)

Here we have our gut completion function this time it is a text to image endpoint。

 so in a previous lesson we had an image to text endpoint。

 so basically we had a model that would take an image and output a text that describes it。Here。

 we have a model that was trained to do the opposite。

 So it was trained with the same subset of items。 So it was trained with an image and the text that describes it。

 But this time with a reverse objective。 So it it was trained to get a description or a text and generate the image that would be associated with it。



![](img/3debe5a7620fb7530158b03de96b66b4_5.png)

So let's dust it out。

![](img/3debe5a7620fb7530158b03de96b66b4_7.png)

Allright， it works。 so I can see from our text， a nice image was generated。



![](img/3debe5a7620fb7530158b03de96b66b4_9.png)

So let's build a radio app for this。

![](img/3debe5a7620fb7530158b03de96b66b4_11.png)

So here we have our radio app。 We have our helper functions like before for helping with the API locally。

 we wouldn't need that。 And we have a generate function。 And this time it's doing the opposite。

 So it's taking the prompt， and then it's resulting in an image。

 So here we have our image generation as you can see， it's very similar to the previous lessons app。

 but reversed。 So in the outputs， we have the image component and in the inputs we have the text component。

 And as you can see， when the image is in the output component。

 it displays an image and when an image is in the inputs component。

 it prompts you to upload an image。 So here we can type any sentence that we like。 So here。

 for example， we have this example， the spirit of a Tamagochi wander the city of Vienna kind of a complex prompt。

 And I actually live in Vienna， which ranks first is the most livable city in the world。

 It's super walkable and has a great public transportation。😊。



![](img/3debe5a7620fb7530158b03de96b66b4_13.png)

And if you remember， Tamagos were those little virtual paths on the 90s。

 So you can kind of see like this little Tamagochi。 and in the background。

 you see the city of Vienna。 And every time you run the function to generate an image。

 it generates a new image。 So with the same prompt you already have infinite fun if you want to keep generating images。

 And， of course， you can also very here you have a very where it goes。

 But we ask for a spirit anyways。 So feel free to experiment with whatever your imagination comes up with if you cannot think of anything。

 you can look around in the room you're at and maybe try to describe some objects。

 try to describe some fun memories you had here， for example， I'm in a room and I actually just a。

 So I will put something like in an empty box with some chopsticks。😊。



![](img/3debe5a7620fb7530158b03de96b66b4_15.png)

![](img/3debe5a7620fb7530158b03de96b66b4_16.png)

![](img/3debe5a7620fb7530158b03de96b66b4_17.png)

![](img/3debe5a7620fb7530158b03de96b66b4_18.png)

![](img/3debe5a7620fb7530158b03de96b66b4_19.png)

![](img/3debe5a7620fb7530158b03de96b66b4_20.png)

At the side of a laptop。 I don't even know if that's going work。 But let's see。

 Let's try it out together。

![](img/3debe5a7620fb7530158b03de96b66b4_22.png)

Yeah， kind of had the empty box with the with this chopstick。 the laptop it completely forgot。

 But yeah， those models are still not perfect。 and they don't follow the prompt fully。

 So it requires some experimentation for the prompting。

 But I encourage you to experiment and play a bit with this app。 And once you're done。



![](img/3debe5a7620fb7530158b03de96b66b4_24.png)

![](img/3debe5a7620fb7530158b03de96b66b4_25.png)

![](img/3debe5a7620fb7530158b03de96b66b4_26.png)

![](img/3debe5a7620fb7530158b03de96b66b4_27.png)

We will move on to the next step， which is， let's make this app a bit more fun。

 Stable diffusion is a powerful model， and it has a few more parameters。😊。

So we have our negative prompt。 The inference steps are guidance scale in the width and height of this image。

 So let's go back to our U why to understand what's going on。

So here we have two gradio text box elements， which are elements that we had already seen before。

 We have a gradial slideer， which is an element that we hadn't seen yet。Okay。

 so let's try this more complete U。 So here let's do a dog plane。On a park。Anime style。

 And let's say I don't want low quality in my image。 And surprisingly enough。

 if you type low quality as a negative prompt， it actually increases the quality because it will try to drive away from images that had low quality in their captions。

 I will increase a bit the number of inference tap。 And then this will also increase the quality。

 but it will take a bit more time。 And let's do this。



![](img/3debe5a7620fb7530158b03de96b66b4_29.png)

Here we have a dog drawn in anus style。

![](img/3debe5a7620fb7530158b03de96b66b4_31.png)

His face looks a bit strange， but it looks cute。

![](img/3debe5a7620fb7530158b03de96b66b4_33.png)

Okay， so we have an app that works and that has this more complex flares。

 But our user interface got a bit crowded so。

![](img/3debe5a7620fb7530158b03de96b66b4_35.png)

We can do something about that。 And for that， we're going to introduce gra blocks。

 So grad blocks are a different kind of interface。 So until now we have been using this structure here called Gdio interface。

 which essentially is a very streamlined way where we can do a function。

 the inputs outputs title description and it generates an app for us。



![](img/3debe5a7620fb7530158b03de96b66b4_37.png)

![](img/3debe5a7620fb7530158b03de96b66b4_38.png)

While gradio blocks enable us to build a bit more complex user interfaces by essentially letting you build yourself your ruless and columns and where to position elements in your app。

 So gradio interface makes it very easy to build。 So here we do with gradio blocks。😊。



![](img/3debe5a7620fb7530158b03de96b66b4_40.png)

As demo。In the same way that we could have a grad title before。

 here we have a gradial markdown that we can do whatever we like with the markdown。

 So here we are doing a title。And we also have our prompt。 But in grad block。

 if you want to use our elements as inputs or outputs， you have to attribute them to a variable。

 So here we attribute the grad text box to the prompt variable。And here， we will have the。

U Y building element。 So we have the gra row。 and here we will have two columns。So。

 two gradial columns。And there we have the same elements as we had before。 So we had。

The negative prompt stepss the guidance， the width and the height and a new gra button element。

 that is our submit button。 And on the other column， we will have our output。And with radiod blocks。

 we have to explicitly denote what clicking our button does。 So while gra interface。

 you just have a function that the button will execute no matter what gradio blocks。

 we can define what clicking on this button will do。

 So here we have button click and then a function generate。

 which is the same generate function that we use before。

 So we actually are not changing our generation function or we're just changing our user interface。

 the inputs are the same inputs as before。 now instead of defining the elements right into the inputs。

 we call each variable that was attribute to each input and the variable also attribute to the output。

And in the same way as the interface。We run。Demo launch。And we should have our app。

 And here you can see what I did。 I set the prompt outside of our row。

 So here we have the prompt in its own separate box and I set in the two columns in one column。

 I have all the advanced options element and in the other column I have our output and our button also here。

And this is really cool because basically， you can give control to your app。

 So with this basic element row column button， we can build the blocks the way we would like。😊。

You can pause here and try to code yourself。 Try to change these blocks in any way you like。

 Have fun。 In our next example， I will show you how a U I could be a bit more complex to build。

 You can see that it's a bit convoluted。 It has a lot of elements， but。😊，It is very simple to use。

 So you have prompt， a button， advanced options， and then the output。

 This is a bit of the trade off that we have with radio blocks that if you'd like to build a more simple Ui。

 you may have to build a bit of more complex code and vice versa。 So with radio interface。

 it's the simplest possible code。 But they I can get a bit complex and cluttered。

 So let's see what's going on here。😊，So here we set a grad markdown for the title。

 and this is where we have。 We have a gradial row with two columns。

 one being the prompt and the other being the button right by it。We have a scale element。

 So in the scale element， we divide up our element into the sum of chunks。 So here， for example。

 because we have one column with scale 4 and one column with scale 1。 we have five chunks。

 And then the first element would take four parts of it and the second element would take one part of it。

 But besides that， we can define that one element would not respect those chunks。

 And in case we need to give it a minimum width。 So in this case， for example。

 I said that the button cannot get smaller than than 50 pixels。

And here we have another element that can simplify our Ui。 and that is the grad accordion。

 So if we have something like advanced options that we don't want to expose to every user。

 we can have an accordion that will essentially。Hide some information and that can be prompted when opened。

 So here by default， the accordions are are already open。 So I have to define that they。Start closed。

And here we have a structure that inside of the accordion。

 we can also customize the elements in the way we would like。

 So here we have the negative prompt because we want to give it a bit more real estate So we put the negative prompt taking this entire row。

 And then below it， we have a row with two columns being the inference steps in the garden scale in one side and the width and height on the other side。

And after it all， we have the result。 So we close the accordion and we have a simple UI using radio blocks that can make your image generation application really easy to use。

I encourage you to pause here and try to build your Ui using radio blocks by changing the placement of these blocks the way you like。

And in the next lesson we're making a game， we're combining the image to text and the text to image models into a single application。



![](img/3debe5a7620fb7530158b03de96b66b4_42.png)