# 【全集】佐治亚理工学院-GPU编程：视频与游戏-中英字幕-p49-Lecture-49---自定义可编程渲染管线中的阴影--BV1GZfyBbEQn_p49-

🎼，うふふふふふふふ。🎼Who knows what evil。🎼Lurrks in the hearts of men。あはははは。🎼The shadow knows。



![](img/8b26138cc9a09f3c8b547806a43322e0_1.png)

Hi there。 My name is Er Landgerman。 I'm a professor of electricallect and computer engineering at Georgia Tech and in the last couple of lectures of GPU programming for video games。

 we looked at scriptable render pipelines that implemented For rendering and deferred rendering and this lecture we're going to take the For rendering code we did and extend it to include shadow maps。

 I'm going to assume that you've seen that lecture on custom forward scriptable render pipelines already So if you haven't watch that go watch that and then come back。

 This lecture is also going to use some ideas about render textures that first appeared in my lecture on deferred rendering in the scriptable render pipeline So it would be a good idea to watch that too。

 If you want to try out the demo I'm about to show you you can go to my CSEC4795 Github and get the unity package titled GPU 23 SRP shadows before installing it。

 you need to make sure。

![](img/8b26138cc9a09f3c8b547806a43322e0_3.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_4.png)

That you've installed the core RPp library and after that。

 make sure you set the lighting space to linear which looks like I forgot to do。

 so let's do that Okay everything's a little brighter now Also when you start a blank unity 3 project it will come up with the built in pipeline so you'll need to go into the graphic settings and set the scriptible render pipeline to use this my custom pipeline asset the code implements shadow mapping。

 which seems to be the dominant way of handling shadows in modern game engines So if you're not familiar with shadow mapping。

 you should check out my previous lectures on the topic creatively titled shadow mapping and real-time shadows and Unity to keep the code compact I don't have any draw gizmo routines implemented so the usual little icon you see associated with lights won't show up here if we click on this light here you can see it here Now I should warn you that this code is only guaranteed to work with one light and the light has to be a directional。



![](img/8b26138cc9a09f3c8b547806a43322e0_6.png)

It wouldn't be too hard to extend this to work with spotlights。

 but it would be a lot of work to extend this to work with point lights and it would also be a lot of work to extend it to work with shadows with multiple lights Now in theory I could add other lights to the scene either directional lights or point lights and those will work but they won't cast shadows and it will be unhappy unless you have a directionional light in the scene and it also interprets that as being light zero because that's hardcoded as far as what's casting the shadow。



![](img/8b26138cc9a09f3c8b547806a43322e0_8.png)

So to make things easy， just use one light and make sure that light is set to directional and set to either hard shadows or soft shadows。

 not that it makes a difference which one and the way we've coded it here。

Basically the way that shadow mapping works is we first need to render the scene from the point of view of the light。

 but we're not actually painting colors here， we're just rendering a Z buffer style depth map。

And then later when we actually render the scene， we compute the distance from a particular point to the light and then we compare that to what's in the depth buffer and if what's in the depth buffer matches more or less that distance that we have in the scene then we say that it's lit by the light。

 but if the distance from the light to the particular point is bigger than what's seen in the depth buffer than we assume something else is obscuring it and we black it out and this is natural to understand with spotlights。

 it's more complicated to think about in terms of directional lights because in theory the directional light is actually infinitely far away and so we're doing things using orthographic projection instead of perspective projection but we'll talk about that。

If you go to window and select analysis frame debugger something really cool shows up that will let you look at the individual stages of the rendering process so what we'll do is we'll say enable and let's go to render shadows we'll talk about this in detail later so first we draw the mesh plane I don't know why it's all flickery when't shown here but you can see it up here here it' showing the depth buffer after you've rendered the plane and here we're rendering the orange sphere and then the white sphere and then the science sphere and then the green sphere and you can see those spheres here so things that are closer to you are showing up as a lighter color than things that are further and away from you again we're not really interpreting this as a color when we're using it we're just displaying it that way things that are further from you or closer to zero and things that are closer to are closer to one。



![](img/8b26138cc9a09f3c8b547806a43322e0_10.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_11.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_12.png)

Remember this is from the point of view of the light for this demo I wrote a little script that just changes the rotation Y component of the orientation of the directional light just to have it kind of moving around a bit like this let's see if it will animate in the frame debugger I'm going to hit enable no it looks like it stops so I can't really actually show you this animating。



![](img/8b26138cc9a09f3c8b547806a43322e0_14.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_15.png)

把门。Not surprisingly because it's based on the same code I used in my for rendering demo。

 The code I'm about to show you is based on this tutorial from Catlight coding with bits from this directional shadows page and bits from this spotlight shadows page in particular I'm not actually implementing what's needed to do spotlight shadows although you could take my demo and extend it to include spotlight shadows。

 This one required a lot of tweaking of the original code because it uses an earlier version of the SRP API。

 I used it instead of this newer one because the newer one has a lot more stuff in it but a lot of the stuff is front loaded so it seemed like it would be a lot more difficult to take this demo and then strip it down to something that would make a good lecture。

 So the main shader has two passes。 This is a little different than most of the code we've looked at before that just has one pass So the first pass here is what you would typically expect。

 It does all of the。various lighting calculations and computes the final color shown to the player Don't worry about all this commented stuff this is some stuff I added for some demonstration we'll look at all of this in detail later but the second pass that's actually rendered from the point of view of the light and this is designed just to fill out that depth information we'll look at this all in detail in a second Since most of the code here is basically the same as what we had in the SRP forward rendering demo a couple of lectures ago I'm just going to point out the differences so we have a bunch of the usual standard boilerplate and the first main interesting thing in this new pass that's different is we're going to declare this world to shadow matrix and what this does is this is going to take a point in world space and map it to the clip space of the light as if the light was a camera。

Now when we're drawing the various objects in the scene。

 we're going to have to use the shadow map to figure out whether the particular pixel we're drawing is in shadow or not。

 so we need to be able to take in that shadow map and since it's a shadow map we use this underscore shadow that we add to the standard tech 2D macro now the sampler for that in this new style is also going to be a little bit different usually we just say sampler parentheses blah。

 blah， blah， here we have this underscore CMP and this is a special kind of sampler that supports the z value comparison that we need to do various structures for passing information from the CPU to the vertex shaders and from the vertex shaders to the fragment shaders is the same as before and the vertex shader is the same as what we had before。

Now， the basic structure of the fragment shader is the same as what we had before。

Actually all of this code is identical， the only real difference we have is that we'll take our final color。

 which was originally diffuse like times albeo and multiply it by this thing called shadow attenuation that we compute here。

So this first line takes the position of world space and converts it into the clip space associated with the light as if the light was a camera。

Now for directional lights， the projection matrix that's embedded in this role to shadow matrix uses orthographic projection。

 the W coordinate of this shadow position is going to be one so taking the XYz and divide it by one doesn't change anything so for directional lights I could just comment this out I left this in for future expansion so that somebody could come along and add support for spotlights and point lights which would need this prospective projection division adding spotlights to this wouldn't be too hard but adding point lights to this is actually fairly tricky because the light is going in all directions so you actually need sort of a shadow cube instead of just a single 2D shadow map Now we're using this special sample texture 2D shadow macro and what this does is it uses the XY coordinate of the shadow position to look up a value in the shadow map。

It then compares the value it finds with what's in the Z coordinate of the shadow position If the value it found in the shadow map is less than the Z coordinate。

 then you assume that the object is in shadow and this is going to return zero otherwise it return one generally that's the case where what it finds in the shadow map matches what's in the Z position。

 although as we'll see later， there's a little bit of slot here that we need to deal with。

So by multiplying by shadow attenuation， if the object is in shadow。

 shadow attenuation is going to be zero and gets blacked out， and if shadow intenuation is one。

 that indicates that the object is not a shadow and we just multiply everything over here by one。

 so we don't mess with it。So that's just one of the possible passes that's for actually drawing the final color the player sees The other pass is for rendering the scene from the point of view of the light and just getting that depth buffer and we're going to indicate that using this shadowcaster light mode the only difference made to the boilerp here is we don't need the inverse object to world matrix akaA the world object matrix。

 so we're going to leave that out。That bias is something we add to this comparison here that allows us to deal with some nasty artifacts。

 although there are some trade offs involved here we see that the bias is currently set to 0。01。

 If I set it to 0， We get this really nasty effect。 This is called shadow acne。

 Let's see what about 。001 Oh， that seemed to fix it。 What about。0001。



![](img/8b26138cc9a09f3c8b547806a43322e0_17.png)

What about 0。00001， okay， there we have a little bit of the shadow acne。

So it looks like pretty much any amount of bias here is fixing the shadow acne now if I use too much bias。

 then the shadows go away altogether， so that's with the bias of two， let's try a bias of one。

 how about bias 0。5。Maybe 0。4，321， what about 05，04， a， there we go。So 0。01 was okay， 0。

02 was kind of okay if you look at 0。03， let me compare that with 0。01。

 you'll see the shadows get smaller， so if the bias is too low we get the shadow acne。

 but if the bias is too high， then there's some stuff that should be shadowed that isn't。Let's see。

Can I make it just a little spot so 0。042 just has little spots here anyway let me put that back at 0。

001 So that's what the shadow bias does we can simplify the structures because we're not dealing with normal information here or we're doing is we're transforming things from object space into the clip space from the point of view of the light thinking about the light as if it was a camera and we do this transformation right here and this is the same way we've always done it The only new thing here is that we're going to offset our clip position in Z according to the shadow bias Now rather we add or subtract is going to depend on the particular convention used for Z rather higher Z is further away from you or rather higher Z is closer to and that may change depending on your hardware and your API virtually unity sets this unity reverse Z。



![](img/8b26138cc9a09f3c8b547806a43322e0_19.png)

To indicate which one we need to do So the GPU is going to use the X and Y values of the clip position to figure out which pixels to draw and it's going to use the Z values to figure out what to write in the depth buffer but we're not actually needing anything in the color buffer at all so the fragment shader is the simplest one we've ever looked at it just return zero just so the compiler won't complain Before moving on to the C sharpp code I thought it would be fun to play around with the HLS a little bit to try to visualize what's going on So ignore the stuff that's commented out for now we'll look at that in a bit look at this line here the first thing I'm going to try is to just return whatevers in the shadow map。



![](img/8b26138cc9a09f3c8b547806a43322e0_21.png)

So this is what we saw from that top down view earlier。

 from the point of view of the light when we're using the frame to bugger。

 but now what we're doing is we're looking at the various bits of that texture mapped onto the scene from the point of view of the camera。

 so for instance， here we have the depth associated with the top of the ball here in terms of depth from the light。

 but we also see those same values reported down here because that's what it's looking up in the buffer。



![](img/8b26138cc9a09f3c8b547806a43322e0_23.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_24.png)

Oh， I should mention that to make this demonstration work。

 I changed this weird comparing sampler to a regular sampler。



![](img/8b26138cc9a09f3c8b547806a43322e0_26.png)

Okay， let me comment that out and I'll put in this line where we'll visualize the Z component of the eclip spacecing from the point of view of the light and that looks like this。

 so anything that's not in shadow is going to look the same as what we saw earlier but the stuff that is in shadow will be different。



![](img/8b26138cc9a09f3c8b547806a43322e0_28.png)

let's visualize that with these lines here， so what I'm going to do is I'm going to take the shadow map。

 which is the first thing we saw and subtract the Z position， which is the second thing we saw。



![](img/8b26138cc9a09f3c8b547806a43322e0_30.png)

Okay so anything that is negative is going to get truncated to zero so these black sections represent places that are not in shadow。

 the places that aren't black， that's a place where what was seen in the shadow map is a larger value than the actual Z position and we have to remember that the Z coordinates here are kind of reversed from our intuition things that are closer to you or actually bigger numbers so these are the things that are in shadow so this shows that we didn't really need this fancy sample texture 2D shadow business we didn't need to actually use this fancy comparing sampler it would have been sufficient to use a regular sampler and just do the comparison ourselves in code so let me comment this stuff out and we'll go back to our original return。



![](img/8b26138cc9a09f3c8b547806a43322e0_32.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_33.png)

And we'll go back to our original color calculation。

 the only difference I'll have here instead of computing the shadow attenuation。

 using the shadow macro， we'll compute it with this bit of code here where we just do the comparison in code。

Now this will work I think there's a performance reason to use the macro I'm not really sure if you have some insight on that leave a comment below anyway we see that doing the comparison ourselves and code works just fine the script to actually create a pipeline asset is pretty much the same as what we had in the forward rendering demo the main thing we want to focus on is the actual pipeline script So this code starts with pretty much the same code as the original forward rendering demo notice that I've left in the code that can handle multiple lights and lights that aren't necessarily directional lights even though this demo overall really is only guaranteed to work if you have one light and that light needs to be a directional light leaving all of this code in makes this amenable for future expansion。



![](img/8b26138cc9a09f3c8b547806a43322e0_35.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_36.png)

In the deferred rendering lecture we introduced the idea of render textures These are targets that we can set as render targets that we can then write to in a draw process and then read from as a texture in another draw pass so here we're going to define a render texture to hold our shadow map we then create some ID variables so that we can refer to our shadow map world to shadow matrix and shadow bias as they appear in these shader code Now we could refer to these various properties with these strings but it's faster to refer to themes using these integer IDs Now the constructor for the pipeline and our render function that refers to multiple cameras that just loops through all the individual cameras this code here is the same as what we had originally to help clarify things we have two separate command buffers one for the main camera that's actually showing the colors we're showing the player。

One for creating the shadow map we'll define a shader tag ID SRP default unlit。

 This is what gets used for a shader that doesn't actually have a shader tag such as this main pass that renders the colors a little bit later we'll define another shader tag ID for the shadow pass So here's the main render function This starts out the same as what we've seen before with the only difference that we're going to set a instance variable here for the callingline parameters called shadow distance let's take a look at what this shadow distance does here I'm using the frame buffer to view the shadow map let's see let's change this to 200 and see what happens so it looks like we zoomed out a lot I'm not sure why the square is over here but now our little spheres are kind of way too small Let's try something in between like 100。



![](img/8b26138cc9a09f3c8b547806a43322e0_38.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_39.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_40.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_41.png)

hu。

![](img/8b26138cc9a09f3c8b547806a43322e0_43.png)

So that's not really great resolution， I it Let's look at the depth buffer here。

 the square is bigger on our shadow map， but we're still not using most of our shadow map texture。

 so we don't really have great resolution。 What about。



![](img/8b26138cc9a09f3c8b547806a43322e0_45.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_46.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_47.png)

50。Okay， that looks better， you can still see some artifacts。



![](img/8b26138cc9a09f3c8b547806a43322e0_49.png)

And if I look at the shadow map， here you can actually see some of the spheres in the shadow map still not great。

 let me set this back to 20。

![](img/8b26138cc9a09f3c8b547806a43322e0_51.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_52.png)

![](img/8b26138cc9a09f3c8b547806a43322e0_53.png)

That's what we had originally， and the shadow map looks like this。



![](img/8b26138cc9a09f3c8b547806a43322e0_55.png)

All right。Back to the code。The code that handles the lights is the same as what we had in the original forward rendering demo。

 This overall shadow demo assumes you have one light and that light is directional。

 but I left all of this code in here in case someone wanted to extend it to multiple lights and non-directional lights later。

 So the code that sets up the command buffers to draw the final color buffer shown to the player is the same as what we had previously。

 but all of the drawing we're doing here depends upon having that shadow map。

 So we're first going to call this render shadows function that I'll show you in a little bit。

 And the rest of this code for drawing objects is the same as what we had previously。

 note that I'm not including any of the code that we had in the original forward rendering demo for rendering transparent objects。

We're not quite done though， render textures exist in the GPU memory separate from the usual C sharpharp dotnet framework。

 so they're not subject to being cleaned up by the dotnet garbage collector。

 so we have to explicitly release that memory。Before we go on to the shadow rendering routine。

 I want to mention that it's probably bad programming practice for me to hardcode the shadow distance。

 it would be better to make this some sort of variable in the inspector Now remember we created a command buffer called shadow buffer that's used by this render shadows routine So we're going to set our render target according to this shadow buffer to be the shadow map and we set up the shadow map here we're going to ask for a 124 by 124 array of pixels that have 16 bits and we'll give it the render texture format shadow map because it's a shadow map。

Clearflag。 depth says that we're only clearing the depth buffer and that makes sense because we're not really doing anything with the color buffer。

Okay， let's look up rendernder buffer loadaction。 don't care When this rendernder buffer is activated。

 the GP is instructed not to care about the existing contents of that render buffer on tile based GPUs。

 this means that the render buffer contents do not need to be loaded into tile memory providing a performance boost。

There you go。 I'm not going to get into what tile based GPs are here。 Okay。

 now let's look up rendernder buffertaction do store。

 Let's see the rendernder buffer contents need to be stored to Ram。 If the surface has MSAA enabled。

 this stores the non resolve surface。M S A A stands for multi sample anti aliasing。

 I vote that we just take it on faith that this is a good thing to do and not think about it any more。

 What do you think。So this sets up something for our command buffer。

 we're also going to execute this big sample and what this does is this sets up some stuff for performance monitoring。

 we're not going to really worry about that here but I wanted to leave it in the code so we execute this command buffer and then we clear it out。

Okay here we go Shadow split data is associated with an advanced technique called shadowow cascades。

 we're not really doing shadow cascades here， but we still need to have a split data variable defined。

We then invoke the method with the longest name I think we've seen in the class。

 Comp directional shadow matrices and calling primitives。

 So this will give us the split data that we don't actually need。 So we're going to throw that away。

 but we do need the view matrix and the projection matrix from the point of view of the light。

 The first argument here is the number of the light that we're looking at。

 and that's hard coded to 0， which is why this code is really only guaranteed to work with one light。

 The 1024 is the size of the shadow map， and that matches the 1024 we used earlier。

 This is probably bad coding style to hard code this。 but I wanted to keep the code compact。

 Now we could put whatever number here we want for the near plane。

 but we might as well get the near plane that is set in the inspector for that particular light。

 and finally， the values you see here。 are associated with shadow cascades。 and these are kind。

The default values you use if you're not actually using shadow cascades we send our view and projection matrices through the API to the GPU via the creatively name set view projection matrices method and if you'll remember we had a shadow bias variable in our Shar code and here we assign that we could assign it whatever number we want here。

 but of course it makes the most sense to assign it whatever we set in the inspector。

Okay now we execute the command buffer and clear it and then we actually draw the objects in the shadow buffer。

 so here instead of drawing settings and draw， we have those thingses except we add the word shadows and things are customized to work better with shadows yada yada。

Okay， we're almost done we have our shadow map render target。

 but we need to actually tell our shader that's what it needs to use for its internal underscore shadow map variable that we accomplish with the set global texture command here we also need to tell the shader that its underscore World to shadow matrix in the shader needs to be assigned the data from our world to shadowow matrix that we have here on the C sharpp side and that we accomplish with the set global matrix command。

Okay to get that world to shadow matrix we of course multiply the projection matrix by the view matrix。

 but remember we actually need to look up things in the texture and the coordinates here in this clip space are going from minus1 to one so we need to multiply everything by a half and add a half to it to scale it to go from zero to1 so that we do with the scale offset matrix technically I don't need the parentheses here but I like to have them there to specify that this is the fundamental computation and the scale offset matrix here that we compute up here is just something we need to move the coordinates around to deal with the texture there is one more complication which has to do with some hardware API weirdness about how the Z coordinates work in the Z buffer so depending on what convention your API hardware etc。

 etca uses you might need to flip the sign on the rows。



![](img/8b26138cc9a09f3c8b547806a43322e0_57.png)

That handle the Z coordinate in your projection matrix。

