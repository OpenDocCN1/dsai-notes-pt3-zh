# UCB《计算机视觉与计算摄影导论｜CS180 Intro to Computer Vision and Computational Photography》 - P1 - GPT中英字幕课程资源 - BV11zaszyEKh

那这个。All right， folks。Look at this。Skeleton crew。I guess， people are thinking。

There is no way there's going to be a third。Third quiz。In， in the three lectures， right。

 definitelyly lightning never strikes twice。 But if it does strike。

 it will never strike three times in a row。Well， I guess you'll have to know youll have to see。

The end of this drama。When you see it。Okay。So what is this weird sound？All right。

 so today we are going to。😡，Hopefully finish up with 3D think I think maybe I don't have time to do。

HDR， we'll see but。But。Let's talk about 3D。 So we left off last time。At around here。

 the structure for motion， the key structure for motion slide。😡，So if we remember correctly。

What we have is we have multipleable views。😡，And we have correspondences across these multiple views right so we have the different colored points this you know the key points that we detected and we connected them together so we have the green one in all of the images。

 the red one and all the images， blue one etc okay。😡。

And now what we want to do is we want to solve for the 3D points。😡，Corresponding to these。

These features and for the positions of the cameras all at the same time。😡。

Okay so we went to Seul for the capital axis。😡，And we want to solve for the R's and Ts of each camera。

 the rotation and translation of each camera from some arbitrary center of origin point， okay？😡。

And the way we are doing this is we are basically just。Looking at where。

The 3D point projects in every image。😡，Okay， so we basically use our。

Our original projection equation to project the 3D point as if we knew it。😡。

Enter every one of the views know so basically you could start with some random。

 your x y z your xs in the beginning are just completely random for example。

 that's one way to start and then you just project them to in all the views right and you get the points。

😡，And now。All you want to do。😡，I so you want to optimize for the rotation translation and the capital axis such that the projections line up right so the fundamental equation that we are trying to solve here the structure for motion is basically were optimizing to minimize this reprojection error。

😡，Right， so we are looking at the observed X， Y points in each image。And comparing them with。

Those same points， as produced by projecting。The 3D vector using the camera parameters。😡，Down to 2D。

And these things hopefully should be matching。 And of course。

 we cannot make them match so we make them the L2 distance between them as small as possible， right。

 And we' are basically summing this off over all cameras and all features。😡。

This is really the fundamental thing that we are optimizing and。

And if we don't see a particular feature in particular view， just drop it out， it's fine。😡，O。And。

The bell rang when somebody asked me a very good question。Why is this。

Why is this a nonlinear optimization。Surely all the things here are linear。😡。

And I did not actually know the answer， but fear not because I looked it up。

It's true that if you think about okay， the projection equation。😡。

Is not linear there is a division there right but then you say， wait a minute。

 but we know how to deal with it。 We do homogeneous coordinates and homogeneous coordinates。

 everything can be made into into just matrix multiplies right so everything's fine。😡，Except。

The objective here。Is not in homo muchgeneous coordinates。

 The objective here is in the 2D coordinates， the X， Y， the images。😡。

So this is after were already divided by the homogeneous coordinate。😡。

So that division is in there already， and so that means it's not linear。😡。

And so that's why you cannot just solve this with least squares。

 you have to do something annoying and complicated and slow and nasty， that is the answer。😡。

Whoever asked that， thank you。 Yes， this is a good。 Okay， so this is where we got to last time。

Want to make sure that everyone's happy with this equation。

 this is really the only equation that you need to know。😡，Any questions？Everyone content。With this。

 everybody would know if I put this equation on the exam。

 everybody would know exactly what each term means。Now everybody， oh， wait around here。Like Gu。

 I don't ask you。😡，All the equations， but like this is the one。

Maybe good to put it on your cheat sheet。Okay， by the way， exam is going to be。The Wednesday after。

The Wednesday of next week。Okay， what， what is going， what Does anyone know what's this。

Is there like a bird trapped in somewhere？Oh， he says fire alarm。在。I see。

 but it not it's not like major py， it's just a little tiny baby fire or something。Is there okay。

 well， if anyone。Knows how to fix the doors， but， we'll assume that there is no fire。All right。Okay。

 so。So we're going to solve this thing。 So the input， the input are。

 the only thing we have as input is。A bunch of images and those feature tracks。😡，Okay。

 and the output is going to be。The pose positions of the cameras。😡，And。

The 3D positions of all of those teachers。Now challenge， of course。

 there is a large number of parameters， right， there's maybe like 100 cameras。😡。

And you know you guys already had like you 500 feature points even in yourhoography， I think right。

 imagine if you have like the whole city of Dubbrovnik。

 like there's going to be a huge number of features。😡，Huge number of cameras。😡，So it's very。

 very hard。😡，No nonlinear objective function， okay。And this。

 the tool for this is called bundle adjustment， okay？😡，Its I'm not going to go into too much detail。

😡，It's， if you want to have like a mental model of it。Okay， good。 Okay， Yeah， okay。

 So one mental model is kind of like， you know。Should。

 should remind you of something like you have this huge huge neural network and you have a whole bunch of weights。

 And you know， you just need to find something that makes。All the way。

 it's such that your output of your network consistent with the ground truth。

Kind of the same thing here。 have lots and lots of parameters。

 There is lots of nonlinear interactionss between them。

 But then you just just shake this thing long enough and， and。Hopefully good things will happen。😡。

But。Sometimes you need to maybe give it a little bit of help。 Okay。

 and one particular way to make it， to give it help is。If you just start with random initialization。

It's probably not going to converge。 So in。You know， in in， in， in back propagation， you know。

 we give it a little bit of help by basically having this kind of a hierarchical structure where you。

 you know， you back propagate from the， from the back forward。 So here。Initialization is a problem。

 There is not a clear kind of structure how to solve this thing。 And so usually what people do。Is。

They start， we initialize this thing with something that we know well how to do。😡。

And that something is basically the two camera case。 Okay， so essentially this。

 the trick to getting a good structure promotion solution is you initialize it with something reasonable。

 And then you run the the， the， the bundle adjustment to just get you get you big things that are consistent。

 So in fact， when I showed you。When we talked about panorama stitching。

 and I showed you an example that used the structure that used bundle adjustment。

 The initialization was done with what we did in class。 We did the。

 the the two view homoography estimation。So once you do the two view homoography information。

 then you can give it to bundle adjustment and it will adjust parameters。

 it's already kind of in just like any kind of gradient descent you need to get it in the right neighborhood and then once you are in the right neighborhood it will get you so we start with a small seed reconstruction and then we are going to grow。

😡，So the standard strategy for motion is incremental。 you basically you start with a pair of views。😡。

That you think you can get pretty well。 Okay， so youally select a couple of views that you feel like。

 okay， those， those， those I can， I can， I can do pretty well。 Okay。

 How do you pick this initial pair。Well， we wanted。To have as many matches as possible。Right， but。

Also as large a baseline as possible。😡，Which are， of course， conflicting。

Because if you have two images that are right next to each other。😡，Lots of correspondences。

 lots of matches。 You guys know this already， right。You'll get lots of good matches。

 everything's going to go， be good。Unlike homomography， where this is all fine。😡。

If you want to actually get some 3D， remember， you want to have parallax。

 you want to have a some baseline between the views to actually get some 3D if those thing if you the views are too close。

😡，No 3D， not that exciting， okay？But on the other hand。If you want to have a really nice。

 beautiful wide baseline。You're necessarily going to have very few matches because like the lighting is different。

 the viewpoint is different， like everything is different。😡，So that's also not going to work。

So basically you're looking for something that' kind of happy medium。😡，Something like this。Okay。

 so here is something that has。😡，You know lots of matches because the views are not that different but it's also quite a big baseline right so this thing is like much closer and this thing like on the other side of this trevy fountain so the distance between the views is actually pretty big but you know theyre basically looking at more or less the same thing so that's a very good pair to start okay。

😡，Now you start， you pick your initial pair imagess。

Then you initialize this by your just standard two frame structure for motion。😡，Essentially。

 right you， you can just。Do this for a pair of frames。

 It's essentially you can think of it as like your streo stereo reconstruction， right？😡，Now。

 while there are connected images。😡，Remaining that is while we have other images。😡。

With the same correspondences。We pick an next image with the most。呃。Which has。

Which sees as the most number of this the same features that you are seeing， okay。

Estimate the pose of that new third camera。Triangulate those new point。😡，And then。

 run bundle adjustment。And then you repeat this just adding one image at a time， one image at a time。

 one image at a time， okay。So basically， we are kind of growing from a very kind of。Very clear。

 consistent pair。 We say， okay， now the third one that is going to help is the third。

 fourth and fourth fourth。 and then。As you add a new view， you first run。

 just try to estimate the camera pose for that new camera。😡。

Do an initial triangulation and then give it to the bundle adjustment。

 which can now optimize everything。😡，So you unlike your project4。😡，You can kind of revisit。

Your your parameters as you you know as you add your images。

 it's not like you add the last image but all the other ones are fixed。

 no you can revisit all of them so you can update all of your hographies in your case in this case。

 it's all of the you know fundamental matrices。😡，Questions。Conentment， okay。Very good。O。Now。

 and that's basically how how all of these methods are working。

 There is a very related algorithm called Slam okay or visual slam。😡，Visual。

 simultaneous localization and mapping。呃。The main difference is that s was invented in the robotics community and Thr Pro invented in computer vision community。

 and somehow they did not talk to each other， and then we end up with two different terms for a very。

 very similar algorithm。The main difference， really， is that。Slam， because it's robotics。

It prefers to be an online algorithm。 So you don't want to just collect all your data first and then run this as a batch mode。

 No， you want to walk around and as you're walking around。

 you add new images and you incorporate them as you go to your structure for motion solution。 And。

 but still。You know， as you go around and maybe look you close some loop。

 you should retain the ability to update your old setup。😡，If you have new data。

 and that kind of makes a lot of sense for the robotics because let's say you have some holes in your reconstruction。

 Well， you can just send the robot to， you know， take more data and fill in those holes so you can have a nice kind of a feedback where the the the s algorithm tells you。

 well， I am not certain about this area of the of the environment。 you send your robot there again。

 you take more pictures and then you get more certain than， you know。

 better reconstruction is is obtained okay。Yeah， so continuous input from sensors over time gives race to problem such as closure often the goal is online real time。

Is that it？ Okay， yeah。Okayay。That's basically the story for。For structure for motion from last time。

Any questions？O。Now。The natural thing to ask is like， why， Why all these stupid dots。Why am I。

 you know， we are doing all of this。To get the stupid。Spae 3D points。

Surely we should be able to do something better。😡，And， indeed。We can do something better。

Okay so this is what we're going to talk about today。你改。So the first thing is。

Next step in the 3D saga is called multi view stereo。😡，你K。And multi wheel there is basically， okay。

 you start out， you have， you， you do stretch of motion。 you have your view3D points。 you have your。

 your 3D points， you have your cameras。 What you want is you want something like this。

 You want dense，3D， not just sparse points。 You want dense 3D with color， everything。

This is actually from I think， from Google Street View， right。So how do you go from？

What structure for motion gives you， which is the camera poses and the sparse 3D points that you got from your corner detector into something like that。

😡，Okay， so that is。That is multi view steo。 Okay， so the input is。

Calibrated images from several viewpoint， known camera intrinsic and intrinsic， extri。

 and the output is now a dense 3D model。😡，唔该。So。The structure of promotion happens after you did sorry。

 the multi view stereo happens after we done structure for。

 So we are now assuming we have our cameras already calibrated。We know where the cameras are。😡，Okay。

 and now。We can hopefully do something better than just these cloud of points。😡，Okay。

 we can do something like this。OK。Yeah。And then if you can do that， then can you can do these。

Need things like this is a man Mattport。 This is a company that basically， you can like。

 if you sell a house， they can go to your house and you can take your picture， take pictures or they。

 you can upload pictures。 and then you， you can get a。A dense3D representation。Of your。Of your flat。

 And then it sells for much higher， okay。走。😡，What is the setup for the multi view stereo？😡，Basically。

It's very similar to binocular stereo right What is binocular stereo， So you have two images。😡。

The cameras are calibrated， usually the cameras are parallel， you know exactly the baseline。

 you know the focal length， everything is known and you're basically just searching for correspondence points right and so that's why you can get nice dense 3D for every pixel you can figure out the disparity and if you can figure out the disparity you know exactly the depth of that point and you can get dense 3D。

😡，Right， the only problem is that。You know， you move a little bit out of the you know。

 around and there is no more pixels because you know you only have two views。😡。

So the idea of multi view stereo is that use the same idea as in stereo。😡，But allow it to have many。

 many more images so that there are no holes。😡，So that's why we want the cameras to be already calibrated。

 we need to know where the cameras are， so now we just reduce it to a stereo problem。

 but a stereo problem on lots and lots of images。😡，Questions。Some contentment。Nobody is arguing。

Maybe everybody's already thinking of turkey with cranberry sauce。Okay， so。

 how are we going to do this？😡，So in a sense。Kind of。Maybe surprisingly， but for me。

 not very surprisingly at all。😡，But kind of very consistently。😡，You get more data。

 Things become easier。 So in a sense， a multi view stereo problem turns out to be easier to solve than just your standard2 view stereo problem。

 Okay， why。Because more data makes it easy to find good correspondences。 Okay。

 so let's say that you have。So in a stircase， you have two images。😡，In the multi view case。

 you have your reference view here， but now somehow instead of one other view， you have like a bunch。

 like three。😡，Okay， now let's do our standard。😡，Steo algorithm。 So we pick a particular point。

In the left image， cameras are calibrated， here is your point。😡，Here is our little array。

So the depth。😡，The 3D point， the 3D。Location of that。

 of the point that that image there should be somewhere along this way。😡，Right。

So where along this ray？😡，Is the actual 3D point？😡，Well。We don't know with a single view。

 that's why we have all these other views， okay？😡，So now what we can do is we can basically。😡。

March along this ray and for every position in this ray， for every depth。😡，We can ask， okay。

 if this is the correct depth。How would that point look？In all the other views。Because remember。

 it's all carel braid now we know exactly where all the cameras are。 So this is， again。

 just projection。😡，This is just very simple projection math。😡。

Because we know exactly where all the cameras are， okay？😡，So you say， okay， for this point。

 if this is indeed。😡，The depth of the object。Then that point should look like so in the other views。

😡，Well， like what， well， like here。Okay， so we can actually look so this is the patch from the reference view。

😡，And this is the corresponding patches from the three other views。😡，So what do you guys think？

Is this a correct depth？Or not correct depth。Not correct， why？Yeah， they're all look different。Right。

Now， in a stiro case， you're only looking at two patches and you're comparing。

 are they the same or not， And then， you know， it's kind of a hard and sometimes you get false positives and but here it's much easier because actually you have a whole bunch of point patches。

😡，And they're basically all telling you， we're all different。😡。

And this is so it's pretty easy to say， no， this is not。😡，This is not right， okay？😡。

So the algorithm is。😡，Given an image， reference image， you pick a point。😡。

And then you march along the ray。😡，And for every depth position with some discretized steps， you say。

😡，Is this the correct depth？😡，Okay， and then look at all the other patches。😡。

Okay and then you essentially compute kind of a joint。😡，L2 distance across all the passions。

 How well do they all。Or I think maybe it's actually you're just summing up pairwise distances from the from the reference patch to each one of them。

 and then you're summing them up together， okay。And。

You do this for the first one and you get some error and the error is pretty high。 So say， no， no no。

 this is， this is wrong。😡，Then you march down。😡，And gets a little bit better。

 And they lo down and get， oh， look at this。 This one is actually。Pretty low error。😡。

The patches are all kind of looking similar now they are not going to be always exactly the same。

 but it's very clear that this is kind of a global minima of that consistency function。😡，Okay。

 so you march along this way， You try， try all of them。

 and then you find the global minima and you say， okay， that's， that's my correct depth。Okay。

 super simple algorithm。😡，You know， it's not the fastest。Traor on the field， but。

It gets the job done， very nice。😡，Okay， questions。Yes。い。So well。

 you only need to search for one of the images and then because all the images share the same 3D space。

😡，So if you do it for one。You know， you basically get it for all。Now。

 sometimes you maybe you do it for each one of them， and then you try to make it consistent。

 Maybe some sort of symmetry。 Also， there might be something in the other images that's not imaged in the first image。

 Yeah， so you， you know。翻了。Oh know， you do it for all the points。

 just scan line just just every single point chuk ch chck ch chook。

 so that's why it's dense because we can do this for every point we don't need to rely on this corner detectors。

 feature descriptors， matching features， none of that， no you know no ransack。😡，At this point。

 we just do it densely for every single point。😡，Okay，Now， we already did all of that to。

 to do structure promotion to get our cameras。 So this assumes that our cameras are no。

Although if you you know， if you have your own setup， you can like have a dome， for example。

 and you put all of your cameras in the you glue them in and then then you don't need to do any of this because you already know exactly where where edge camera is。

 If you don't have that， then you first run of motion， get all of your cameras。 And after that。

 you don't need to do any feature detection。 You don't need to do any handset。

 you don't need to do anything， you basically just for every point。😡。

Findine correspond for every pixel， and you get dense， beautiful depth。Questions， yes。对。

Good question I think the standard algorithm just。Just does it separately for every point。 I mean。

 you're right that there is probably some smoothness。In there。 But I'm not sure they even use that。

 I think we just boom， boom， boom， boom， just just。Compute them separately。😡。

What you used to do for each pixel。For every pixel， yes。Yeah。Yeah， okay， yes。

Should be able to approximate rough me。I guess you。现在你给。发院。Well。

 I guess the question is like once you have four points or even three points。

 like if you have three points， then you basically can make a mesh。😡，Right。

 you can create a you know triangangleular mesh or you can do yeah。 So basically。

 this allows you to actually go from stupid points fly floating in in midair to something that's actually connected。

 Yes， and so， so in fact， this is how you get mesh meshes。 you know， you get a bunch of these points。

 and then you just connect them because the points are small enough and just triangulating between them。

 You get a mesh， right， meshes just basically a whole bunch of triangles。

That you assume is one surface。Okay， and I'm skipping a lot of。Little graphics it tricks of。

 you know what what to do if， you if there's disjoint objects。

 so it's a little bit trickier than that， but the fundamental story is relatively simple。 Yes。

 other questions。不要。If the object is too far， then then you're screwed， because then your baseline。

Becomes not sufficient。Remember how。How we in， in for hographies， we said， you know， your。You。

 you can only rotate the camera。 You cannot translate the camera。

Unless you're taking picture of a plane。😡，Or if you're taking picture of something really。

 really far away， which is so far away， it basically you can treat it as a plane because。

Because any movement， any movement you have here is so tiny compared to like the mountains over there。

😡，It doesn't matter。 So it's the same thing at some point， if your object is too far。

It becomes like a homography kind of situation。 There is no baseline。

 So you are not going to get any depth。Yeah。Which then you get into your Jeeep and you come closer。

There is only one way to do。To go， okay？Any other questions？那快我。Okay。Yeah。

So for that over the whole reference view。 Okay， good。And now。W is this better than two views？😡，Well。

Basically， you know， you can have more than one image。

 So you you basically have stronger matching signal。 the correspondence is much， much stronger and。

You can also figure out if you have lots and lots of images。

 you can figure out kind of the the closest images to， to， to get you， you know， the best match。

 Okay， so there is， you know， you can kind of do some sort of kind of course to find searching， okay。

😡，诶。And you can also do a little bit better if you just do this for every single image as the reference image。

 So every one of them is giving gonna give you some sort of like a 3D3D reconstruction。

 And then you merge them together。To say， okay， well， all of these need to be consistent。

 So with merg， you again， kind of denoing and making things better。 So this is kind of a one exam。

 great example when， you know， more data makes your life easier rather than harder。Okay。

 and here is just a kind of an example where。If you， if you're in a stereo setting， well。

 you can have a very large baseline。Which is， of course， good for depth。

 but hard to find correspondences。 If you have a very small baseline， then。

It's great for correspondences， but not good for depth。

 but if youre in a multi if you're in a multi view setting that in sense， you have both。Right。

 you have。You have small baseline to get you good corresponds。

 but then transitly between a whole bunch of views， you get pretty good baseline。

 so you can also get very good depth。😡，So it's like， you know。

 you can have your cake cake and eat it too。Okay。Now。The one thing， though， that。This doesn't quite。

Do very well is it's still kind of a。Looking at an object from one side。

 So you're basically like taking a picture from one side。 And then you're， you're trying to。

 estimate it。 So you're basically only going to get。Half of what you're looking at。

 What you ideally want is you want basically to have a full view of the entire object， okay。

Something like this。Okay， and so what people usually do here， although you could。

 you could basically do a whole bunch of like。A local depth representation that then try to merge them afterwards。

 like you can have a bunch of meshes and then merge them into one big mesh。😡。

Or you can do what's called volumetric stereo， okay？😡，And volumetric stereo。😡。

Is or volumetric representations。😡，Is basically this idea that。We， instead of representing 3D with。

Boys or。Meshes， we can represent them with a 3D version of pixels。And these things are called voxels。

So boxoxel is basically a pixel but in 3D， so instead of a square。

 it's a cube but then you have you know you have X， Y，z and it's basically just like an image。

 but it's in 3D。😡，唔该。And now you have a bunch of views。 They're all looking at， they're all。

Looking at some volume。😡，And they're voting or they're basically putting stuff into that volume right And now you can just say。

 okay， instead of just having this you know X， Y， Z points。

 we can just think of them as as voxels and we can essentially kind of fill in the 3D representation using these voxeles。

 and of course， in the end the voxels you want the voxels to be very， very small so that。😡。

So that it doesn't， you know， you don't see the jaggedness， right？😡。

So the goal is to assign RGB values to voxels in。In the volume。

Which are photo consistent with the images。 Okay， so it's a kind of variant of multi view stereo except what youre assigning is not。

Continuous depth value is X， Y， Z， but dis discretized voxels， X， Y， Z， Okay。

 one standard way of doing this is called seam calming。呃。The kind of classic quote， I think。

 comes from Leonardo da Vinci， unless I'm mistaken， so Leonardo was asked。

How do you make these beautiful sculptures， and he answered。😡，Oh it's very easy。

 I take a hunk of marble and I just cut out everything that's extra， all the extra bits okay。😡。

So this is exactly what this algorithm is is doing。 So the idea is you start with a h of voxels。Okay。

 something like this。And your hunk of vels is known to be larger than。

Whatever the actual object that that that you want to reconstruct， Okay， and then。Essentially。

 it's kind of the kind of the inspired by multi view stereo for every。ray in every image。

 you say okay。For this vaw。😡，Is this voxel part of a 3D， right？😡，And you。You see if。

 if this v is actually correct。Then there should be some。View consistency， right。

 just like in multi view stereo。But。If there is no consistency。😡，Then you say， well。

 that means that this vuxel is actually should be empty space， that it shouldn't be solid。

 It should be empty。 So you just remove。That voxel。

 you carve it out k done okay and then you just repeat the process and you just keep for every voxel。

 you just say， is this consistent or not， you start with something that's overcomplete so you know that you didn't miss anything so that if something is not consistent。

 You know that the correct answer is somewhere on the inside。 So just keep cutting， keep cutting。

 keep cutting。 And then in the end， what remains。😡。

Is when you cut this algorithm converges when you cannot cut anymore。

 when everything becomes photo consistentist。 Okay， and then you get something like this。

 This is some of the results from， from the。Space， the space carving。The reconstructions for this。

You do see a little bit of like voxization。 You know， it's not super smooth。 So that's the。

 that's the issue with voxels。 So it's。knowIt's kind of discretized。

 but you know you can make those vels really， really small and then those effects are not that visible questions。

嗯，Okay， so。To summarize all of this。😡，呃。There is this kind of a standard pipeline that you do。

 if you want to get。Nice 3D。You start out with a whole bunch， you take lots。

 first step is you take lots and lots of pictures。😡，Okay。

Then you throw them into structure for motion。😡，And you basically compute。Camera。

Boses for every one of those pictures。 and also， you know。呃。Se depth， okay。At this point。

 probably like half of your images is going to gonna， you're gonna lose because， you know。

 it couldn't find the correct poses for it。 So it you drop that。 Okay。

 and then you send the rest of it to this multi view stereo， which is doing nice。

 beautiful denser reconstruction。 Okay， so there is this。Se for motion plus MVF pipeline。

 and you don't even need to do it yourself anymore because there is a bunch of kind of standard tools and。

😡，Probably the most。Used right now is called Co map。

There is the Gitthub repository and it does both for you。

 it does structure for motion and multi view stereo。😡，Okay， the one thing， though。

 is that you really do need to give it lots of images like， you know。Multiple hundreds。

 so often what people do is that they go and they take a video for example。

 and they send the whole video to callmap and then callmap probably is going to drop like more than half of them or maybe two thirds of them and then try to get you something for the rest and you know you can you can do it with your own data It's kind of fun。

 you can check it out。Okay， questions， yes。他们。O。If you're， if second， if you're。

And it's sitting on the table， you're screwed。😡，Right， there， there is no way。 I mean。

 you can hang it by a thread。And maybe if the thread is transparent， that， it might not see it。

 or then you have to basically somehow。Have multiple views。 And then， yeah。

 maybe like calibrate your cameras and then tell it that。Okay， these things are you know。

 give it to actual camera positions manually。😡，That's， I think， the only way to do it。Yeah， yeah。两。

Generate two。嗯。I see。I say， I say， I say， right， And。

 and I guess you can do the same if you have like a moving， moving objects， right， So I say Okay。

 So you basically you take。Different views。 And then you align them in post processing。 Yeah， okay。

Other questions。Okay，All right， so now。We can do better。Okay， so multi view stereo。😡。

On our little summary slide here。E we had the camera positions that we got from Starsha Form motion。

And then with correspondences that we are basically searched for。😡，We can get dense 3D。Okay。

But there is a new kid on the block。And this new kid of the block is called neural rendering。

 volumemetric neural rendering。Which essentially。Doesn't need explicit correspondences。 Okay。

 the correspondences are somehow happening implicitly。But explicitly， we don't need correspondences。

 Instead， we rely on reconstruction loss。😡，To kind of figure out the correspondences on the go。 Okay。

 and this is called analysis by synthesis。 so you basically you try different things and you see which ones work out and this is what we are going to talk about next and kind of the main example of this is called N neural radiance fields。

😡，This is。Thing out of Berkeley that kind of exploded。😡，And。

This is the original paper that was this was done here in 2020。 Okay， and the idea here is。

You start from structure for motion， so you get your cameras， the cameras are known。😡。

And after you get your cameras。You can basically。Interpolate in this nice way。 did I， Okay， Yeah。

 you can interpolate in this nice way that basically feels like。YouYou're right there。

Inside of the scene， without dealing with any。In explicit depth。 We' are not getting any 3 Ds here。

Right， we just。Kind of make。Generate views that just look good。 Okay， so in a sense。

 this is kind of like 3D without 3D。😡，Okay， so that's basically the idea。😡，Okay。Yeah。

 and it's like been， well， now it's been four years， five years， I guess。

 and it's like tons and tons of work。There has been some really cool follow ups。

 so this is for example， an example of having this representation allowing you to change illumination。

😡，As part of the nerve representation， okay？嗯。There is。Probably my favorite is it's called blocknerf。

 This is basically a nerve representation of like。A large part of San Francisco， okay。And。

 and it's basically like the largest， this is quite a bit bigger than than duubbrovnik。

 but it's also， it's also dense， right。So what they did is they took a whole bunch of video from Waymo。

Tons and tons of video from Wemo。And they compressed it into this volumetric neuro representationpresentation。

😡，Okay， so not only is it like you can get cool 3D。😡，Out of this。

 But it's also much smaller than the original videos。Yes。ジ？I think you get basically the the， the。

 it's kind of like this MV S kind of thing that like things that are not consistent。

I just going to fall out。Because if they' are not consistent， they're just。

 they're going to disappear。 So I think I， I don't think they had to do anything special。 It just。

 it just got dropped。Yeah， so it this thing assumes that everything is static。

 There is a bunch of stuff on dynamic nerves， but I'm not going to。Focus on that， okay？

Then there is this cool idea of connecting nerves to diffusion。 this is called deep diusion。

 okay that was a very influential paper and basically the idea is that you generate a whole bunch of views。

😡，Over。 So you type in， you know， whatever cat。 and then you generate a whole bunch of diffusion views of the cat。

 and then you basically use Nf to make them all consistent with each other。

 So you basically back prop。Back to the diffusions to get your cat to be consistent from all the sides now it looks a little bit this original paper looks a little bit cartoonish。

 but nowadays it's getting better and better and better okay。😡。

So kind of nice way to get diffusion into 3D。😡，And this is something that we were doing。

 and this is basically kind of。Doing that for editing。

 So I think did Alex talk about it and pick to picks。

So it track mixix depicts as using diffusion to edit images and this is the same thing except now you're editing not images but volumes using nerve okay so you're basically in type in your edit and it's able to do that and it's consistent across multiple views again。

 you're basically just forcing diffusion to be consistent across multiple views and you're forcing it using nerve as as the kind of the consistency objective。

该。嗯，对。And this is， again， Berkeley thing。 this is Andju Kazzawa's group that is。

Kind of decided to do a。Public。Good did and created a free nerve library。

That combines all these gazillions of papers and all the gazious methods。

 including the brand new Gaussian splating that I'm not going to talk about。

 but it's all in this one repository Nf studio， you can it's easy to run。

 it's kind of user friendly and hang one of the GSIs is actually I think also Ryan also was working on it so like some of the staff in this class have been working on it So you if you want to play around with it。

 they will be happy to help you and supposedly very user friendlyly。

 so if you want to create your own nerve at home。This is one very nice tool to use。Yeah。

 this is somebody somebody's apartment， okay？Okay， and this is， I think， somewhere in。Where is this。

 I think this is on campus。 Yeah， this is， this is the euclipyptus growth。 Okay。

 so let me just give you a。Kind of a overview of Ns。 Now， Ns is one of the projects that we。We。

 you can do as your final project。 Okay， it's kind of hard。 So it was。Originally， it was， I think。

 three lectures or nerves。 So make you do the project because that project was actually Project 5。

This year， we decided to switch to diffusion。 So that's why we spend more time of diffusion。

 So then for nerves， youre getting a very。😊，Quick overview， but。

The project should be self explanatory。😡，Yeah， so you should be able to do it Okay， Okay。

 so but today I'll just talk about what is Nf。😡，And how it connects with other approaches Okay so the problem statement is the input is again。

 we are always assuming we are starting with a calibrated set of cameras so first the first thing you do is you run call map you get your cameras。

 okay something like this calibrated set of images。😡，And the output。Some amazing thing like this。😡。

Okay。Let's play the original video from p radiance fields or Nerf。

 a new method for representing complex scenes that achieves state of the art results for geo synthesis。

Given a set of input images of a scene， which in this visualization is a Lego bulldozer。

 we optimize a volumetric representation of the scene as a vector valued function。

 which is defined for any continuous 5 D coordinate consisting of a location and view direction。

We parameterize this scene representation as a fully connected deep network that takes each single 5 D coordinate and outputs the corresponding volume density and view dependent emitted RGB radiance at that location。

We can then use techniques from volume rendering to composite these values along a camera array to render any pixel。

This rendering is fully differentiable， so we are able to optimize this scene representation by minimizing the error of rendering all camera rates from a collection of standard RGB images。

😊，We first show comparisons to top performing methods on synthetically rendered data。

Seecene representation networks implicitly represent a scene using a fully connected neural network。

 SRNs have issues with multi view consistency and unable to， we present neural radiance fields。

No need to sell it okay。So， again。AB's eye view， three key components。

The first component is a neural volumetric 3D scene representation neural because there is a neural network in there。

 Now， it turns out。The neural network here is not。necessarily needed it。

 You can actually do it with with something else as well。 Its just basically just a way to。

 to represent something So stuff some parameters in something。 Okay。

 but a neural representation is a good one， okay so we'll just stick with that。

 even though you should remember that this is not the only thing that's possible。

 And this is just a fully， you know， it it's it's it's not convolutional is's just just a whole bunch of fully connected layers。

 okay。😡，Now， second is a differentiable volumetric cring function。 Okay。

 that basically deals with looking at rays and figuring out。How you go from race to volumes。

 And this is something that's。Very much connected with multi view stereo and volumeum graing we just talked about。

 Okay， and finally， sorry， some weird thing optimization yeah analysis and。 Okay。

 so essentially some sort of a big， big optimization that makes everybody happy。😊，Okay。

And the objective is to basically synthesize all the training views being consistent。 again。

 this is something that is similar to what weve seen in search promotion and multi view stereo。

 Basically， you want to have all the views agree with each other and be happy okay。

 so the first thing is the representation。 okay。😡，So what we get here is we are representing a 3D scene。

😡，As a continuous 5 D function， okay。So the function is the inputs of the function are X， Y， Z。😡。

And a vector theta phi。 So for every point。😡，And every direction。

This guy is going to tell us the color。And also the transparency， okay？

Don't worry about the transparency for now， just think about the call。

 So this is the spatial location。 This is the viewing direction。😡，This this is your neural network。

This is the outputward Po color。😡，And this is the， the density。 Okay， we'll。

 we'll get to the density in a bit， okay。What kind of a 3D representation is this？😡，Anyone？

We have seen bunch of 3D representation what kind of is it？Well， actually， it's not。

Anything that we have quite seen before。 Is it a mesh。 No， it's not a mesh， right？ There is no。

There is no surface is basically just gives you。knowFor every view， for every ray。

 there is just a color。😡，It's not a point cloud， either。唔该。It is volumetric。😡。

Just like the vuxel is volumetric。😡，But voxels are discrete， where this thing。Is continuous。

 so you can the closest thing you can think of it is it's basically if if the volumeitric representation had continuous voxels。

 it's something like this。😡，It's this density where something might have more density and less density。

 So you can think of it as。And you call them shiny， transparent cubes， okay。So that's more。

 maybe the best。Thing you want to keep in your head about what， what kind of representation is。

 It's a continuous。Kind of probabilistic thing， which basically。When you have。

 you know when the rabbit starts， then you get you get more probabil， so it becomes denser。

 more stuff。😡，You know， the the， the cubes become less transparent and then outside。

 the cubes are more transparent。 Okay， so basically， that's， that's representation。So whats。

 what is the problem being solved。 Now we all， we talked about panoptic functions way。

 way before we talked about hographies。 And I think it's， it's worth connecting this back。 Remember。

 plortic function。It's the set of all things that we will ever be able to see。该。

It's basically that thing right there， do you remember that？😡，It's， it's the。It's the brightness。

 the light that you see at all the points X， Y， Z in the world， at all the directions。

Theta phi with some at some unit of time， at some wavelength。

 Remember that it's the seven dimensional function that captures everything in the world。

 everything you have ever seen。😡，Everything with that will see everything， right。

 It's purely a kind of a a mental construction。 It's the intensity of light。

 See that any position in any direction over time function of waveing， okay。So。え呀。

And it captures everything， it has all the movies in the world。

 it has all of your photos in the world， it has everything， right？😡，Remember， we talked about how。没有。

You know， the the， the， the。Quick time。 VR was like an early version of this。

 And then Google Street 2 is also kind of a version of it where you， you basically。

You basically try to capture everything and just put it all in one big table， right， Well。

 that's yeah， that's that's basically what the proic function is， right。😡。

So the goal of capturing the P option function is to you know， represent our， our visual reality。嗯。

And its， it， it has。 it doesn't know anything about depth。 So we talked about before we talked about。

 look， there is depth。 There is X， Y， Z in the world。This thing knows nothing about this。

 It's all about light， right， It's， it's totally view。Based， it's always， it's all about photons。

 It's not about anything physical。 It's all about just about light， right， Because if you have。

 if you know， if you know。What light is coming at any given point， you don't need to know geometry。

 The geometry is kind of implicit in all the light。😡，So， it's kind of a。

A kind of alternative way to represent reality。 You can represent the chairs here。

 or you can just represent light from every single point so that you get the chair to come out just from the difference in the light。

😡，Right。It's kind of a cool thing， like the geometry is implicit in the light field。😡，唔该。Now。

When I talked about the ptic function， I sold it as just completely like a thought experiment。

 a conceptual device， right。And Ederson and Bergen didn't even actually tell you how do you do it。

 it you say， okay， this thing exists。😡，Right。嗯。But。But in a sense， people have tried to represent it。

 right， maybe you know simplifying it a little bit。 So let's get rid of time。 I mean。

 we don't know what the future is going to be and past is too much。😡。

Let's get off the light light wave instead of just representing this RGB。And now look at this。

 we have X， Y， Z。Pify the location and direction over eight。That should look familiar， in fact。

 that's exactly the representation that a nerve does， okay？3D location。To thedirect。

 you have a 5 d array and you are basically representing every one of these 5 d arrays。😡，Questions？

Yes。Good question， we'll get there one on second。So。This， nerve is not the first to do this。😡。

20 years ago， there was a pair of very influential papers called Lightfield and Lumograph。

 two papers came the same the same year from different labs。 I think Lightfield is a better name。

And it basically proposes proposals for modeling the poptic function。

So the idea is to really just do a data driven solution， just take a whole bunch of pictures。😡。

From many， many views。😡，And then just interpolate them。 So kind of like。Take Google Street view。

 but then also have interpolated views between different views， Okay， so。

One proposal out of Stanford was this Stanford Gantry， the light field array。

 so you just basically buy yourself at 200 cameras。😡。

And those 200 cameras capture a slob of the light field。

And now you can produce any you within the kind of convex all of these 200 cameras。😡。

And our own ran in when he was a grad student at Stanford， he said， okay， I can do this。

 but I can do it in a single camera。 And this is the idea of a light field camera。

 He had a company called Lighter that would actually manufacture these cameras。 Okay， and you。

 you take one shot with this。😊，Light field camera。 And then after that， you can move around。

 you can move around。 You can refocus， You can go close and farther。 It's， it's very cool。

 It's very cool。 Okay， but it's basically just a whole bunch of interpolation in this。

 in this race space， okay。😊，But all of these light field approaches。😡。

They made one simplifying assumption。 They basically said that。On the way。

 when you have a ray going from a surface。😡，Or light source toward the camera。😡。

Nothing is going to change。 Remember， I talked about this， too， like， I don't know how far。

The the photon has traveled。 It might have traveled from the projector here。

 or it might have traveled from the sun。 huge difference in distance。

 but the the the photon does not tell me it doesn't have a speedometer。

 It doesn't have like how many miles it has traversed it doesn't know， right。😡。

And the kind of the assumption here is that。Those photons are traveling in a vacuum。

 so there is no change in radiance。As that photon is flying from the sun towards me。Okay。

 that is the assumption that allowed us to go from a 5 d。

A representation to afford the representation。Okay， because you can say， wait a minute here。

 basically。Any points along this way？Are going to have the same， the same RGB， the same， the same。

Amount of light， because I am assuming that I'm going for vacuum that nothing is going to happen。

 Okay， and so that's why all of these methods， they are basically reducing this to a 4D program problem。

 And then you can basically kind of reuse a whole bunch of ray。

 So you have this light field surfaces。 and then you just put your object around the light field surface。

 And then you just basically represent。😡，They represent the color at every X Y。😡，And every theta p。

 So that's your 4D representation， X， Y and theta I， but you don't need to do it in 3D。

 You can just do it in 2D and like put like a， like a light field surface around each object。 Okay。

 so it's kind of like your， you have your like your Christmas globe。

 And you can look on the outside and all use like all you， everything that you look at。

You can can be able to restruct， but you never break the blue glass， so you can never go inside。

 You can never see what happens inside， right， So that's basically the assumption that that that all these methods have used。

 And then you can syntheize new views by， you know。

 creating in moving new cameras and just reling rays。 blah， blah， blah， I'm gonna， yeah。

 and this is kind of the lightfil camera。Okay。Now， nerve。Basically says， you know what。

 I'm going to take this idea of sampling modeling the planoptic function。😡，But。

I'm going to do it in 3D。 I'm not。😡，Going to take the simplifying assumption。

That the caller stays the same along the way。I'm going to allow for fog。For rain。For， you know。

 stuff to be transparent stuff， right， I I， I allow for things to happen as the photon goes along that train。

 Okay， so basically， a nerve allows you， given that you have enough data to go inside of the snow globe。

Okay。So here is the idea over a nerve and the nerve。😡，Basically says。I can parametermetize。

Different colors along the Ray。And the way I'm going to do it is with that transparency。

 the transparency parameter。The density parameter is going to model。What happens along the ray， Okay。

 so nerve represents the integration along the view array to compute the poly optic function， okay。

It models the full 5D planopic function， not not the 4D representation。应该。

And that is basically what this guy is being modeling and this density here is what allows you to do that。

😡，嗯开。But other than that， it's really very much connected to the planoptic function from you know 30 years ago。

 which is very nice， yes。Yes yes。It can。Well。no， no， no， it's， it's sorry， sorry， sorry it's。It is。

 it's it is 3D。So unlike a light field， which is only 2D here， this thing is 3D。

 so you actually can change RGB because you're parameterizing its in 3D。Okay。

 so so you you can change RGB， so you could have something occlu something， including something。 Now。

 whether you have data for that or not， thats that's a different story yeah。两个可以。他直接可有垃圾。

So all you have is a whole bunch of images。 your input is a whole bunch of images。😡。

It will have to optimize for。😡，To do this， disentangle it between RGB and the density。

 it will have to solve for that itself。😡，Yeah。But kind of the cool thing is that here。The， the。

 the things like the influence of light is， is， is， is baked in。

 So you don't have like a separate thing for light。 No， you basically。You capture the nonleer。

 the shiny things， because it basically。The the RGB contains everything you needed。

 it's in its view dependent， so you can represent things like like mirrors in this direct way okay。😡。

嗯改。Yeah， okay， so。This is And slide or Nf on one slide， so。

What you have is you have the volumetric 3D representation。😡，It takes in。When there is a fivehi。Who。

 okay。So it's R G， X， Y， Z， theta and thighhii， which。Which， I guess， got lost in the。

In the PowerPoint shuffle。 Okay， and you have some mapping of that。 In this case。

 it's a neural network2。RGB， and。And density。So you learn this mapping from x， Y， z。

 theta phii 5 d to the RGB and density。😡，And。How do you actually optimize for this thing。

You basically。You have your cameras are calibrated， so you know where all of your cameras are in 3D。

 so you can shoot rays in all directions and they' are consistent， right？😡，And basically。

 what you're going to do is for every point along this way， you're going to remember this thing。😡。

Okay。And。You're basically going to have a whole bunch of possible。3D。Volumes。That you can produce by。

 you know， you start this thing randomly。 So in in in the beginning， everything is random。

 So you basically have some completely random RGB， right， But then。Just like what we did before。

 we can say dude。All of these things have to be consistent。 All of these， you know， thousands of you。

Of this scene have to agree with each other。And this consistency。Is what forces you？

To forces the network to find the RGBs and the denities， such that。😡，Everybody is happy。

 So it's the same kind of idea。 You just throw in a whole bunch of measurements and you say， look。

 they should have the same consistent 3D representation except that in this case。

 the 3D representation is this Nf。Okay。And。Yeah。So that's basically that's Nf in one slide， again。

 something that I already mentioned。😡，The cameras have to be already calibrated。

 So you already have to know。The pose of your cameras。

 so you need to essentially run something like coal map before nerve ever starts okay。😡。

And then then you get something like this。 And then once once this is all set。

 then you can do your nerve representation Okay， and how do you get this from images again。

You just run call map and everything's fine。Okay， questions。Yes。定为。気在感。There is a number of methods。

 Actually， I have a method already or trying to do this。 I think our paper is called call map free。

Gausian spting or something like this。 This is definitely something that all of us want。

I think for best results， it's still that you want to use this call map thing， but。

In the last three minutes， I'm going to pitch something completely different。So which is。All of this。

 even though the nerve has a neural network。😡，Basically， in that case。

 the neural network is just to compress a whole bunch of race， it's just a compressor right。

 but still the thing about all of everything we talked about before is that you start from scratch。

 you take a whole bunch of images。😡，And then you create your structure for。

 So multi view stereo or your nerve。 It has never seen anything before。 It has completely。

 It comes in blind， right， It does not learn anything before。😡，Naturally， what we have seen is。

In all the other areas that。The more data that a model has seen before。

 the better it should be when it's faced with a new scene， correct？😡，And this is where there is。

 I think， kind of a revolution in， in， in， in， in 3D。 Okay， this is just an argument that， you know。

 kind of what happened revolution， depth， deep revolution in classical computer vision。Same thing。

 you know， instead of going through this detect features， Collibrate cameras。

 run transfer for motion， and then run multivi stereo or run nervef。Instead。

 can we do something end to end。And this is a very exciting direction that has just came out this。

 this this year。 And this is， this is kind of the first paper on this called Duster。 Okay。

 and I'm just gonna give you just a little bit。😊，Of a little taste。Okay， and it basically。

Essentially， it says everything I taught you in the last like three lectures you could forget。😡。

You can forget pipelines， you can camera collaboration， you can projection error， triangulation。

 Epolar constraints。Throw all of that out the window。 Okay， well。

 don't throw it down with the window because actually， you need a little bit of that bag， but。

You don't need it。😡，To do what these guys do， Okay， here is the， it's amazingly done。

 So I I basically just can do it in one slide。😡，You basically， it's a stereo setup， so you have two。

😡，Cameras， two views， okay？😡，And then you have two。Do networks。

I think there are transformer networks。That are connected with some cross attention， okay。

The first network。Basically does single view depth prediction， so you go from an image。😡，2。3D。

 but in this case， the 3D is not in terms of depth， but in terms of what they call point maps。

 which is。X， Y， Z for every X Y position in the image。😡，It predicts an X， Y，z point in space， okay？😡。

You can see over there， okay？But there is a second view。

And the second view basically does the same thing。But instead of predicting it in the camera coordinates of the second camera。

 it predicts it in the camera coordinates of the first camera。

 and this is basically just a supervised learning problem。

 So you have a huge amount of pairs of images。😡，And a huge amount of corresponding。3D point maps。

From the point of view of the first camera。So it's just a ginormous。

And to end supervisized learning problem， okay？😡，Where you predict from images to point maps with this kind of representation。

😡，And the cool thing is because both views are forced to predict things in the same coordinate system。

Correspondence and collaboration kind of emerges automatically inside of those transformers because they need to talk to each other because they need to say。

 dude， you know， we need to predict in the same space。 So we need to somehow know， you know。

