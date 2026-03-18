# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p14 P14 Lecture 14 -  Texture mapping -BV1M9JVzpEBk_p14-

See here。 So go live。And start recording。All right， folks。How are we doing。

We've got the few in something around here。Excellent， so nice to see everybody。

 in terms of course announcements。 You guys have a few deliverables in next 48 hours here。

 So there's a nano quiz that will go out at the end of lecture。 I hope。

 and you have a homework assignment do。😊，Tomorrow， tomorrow so you know。

 it's about time to get started on that。 So that's what your simulation assignment。

 After that you've got ray tracing and then as real time graphics is there one in between， I forget。

😊，Okay， we' not like bonus Pet。呃。Excellent， so， so in a sense， you're actually you're getting there。

 which is great。 And don't forget you do have an exam in this course。

 It's like a week or two before the draft deadline。

 So check the course calendar for that because I'm inevitably gonna get the date wrong if I try to say it now。

😊，But'll just keep reminding you of all the things。Right， so it's nice to see everybody here today。

 any questions， procedural questions， comments， concerns？Weather predictions。呀。

And weatherath prediction。Gen。呃。Breing when we try to。That object。Accerate our。啊哈。

Do we also use like。The camera。Yeah I think you。20个。That something is so far away。标。Sure。

 I was expecting questions about the homework。 but that's a great question too。

 So Maxim asks if we have last time we talked about these different data structures for like sorting the objects in our scene。

 like we talked about bounding volume hierarchy and kd tree remember the condition being whether or not essentially the boxes overlap or things can go more than one box that's kind of the dividing line and the question which is totally reasonable is like well。

 neither of these data sets seems to be cognizant of where the viewer is asset data sets neither of these data structures seems to know where the viewer is and that seems really important and you're absolutely right。

 so there are a lot of different places where that can come in in graphics。 So for one。

 it might be that you tend to choose the splitting plane for your bounding volume hierarchy in where you know where the camera is。

 but a different thing is that there are a lot of cu techniques for rendering that really do depend on the position of the viewer。

 So for example， a lot of old video games tend to。😊，To take place in dungeons。

And like weird underground prisons。 And in addition to that being reflective of a stupid 1980s macho culture。

 there was a different matter which was rendering So any idea why that was a valuable thing to have these video games happen in like the sequences of rooms with very small entryway。

诶 yeah对。Like from one room。啊。That's right。 So essentially。

 what you would do is you'd really strategically place the doors between the different rooms in your building in such a way that you could never see from one room through another room to a third right And so that way you never have to page into memory more than like a room and the adjacent rooms when you're doing your rendering right so that would be an example of a technique where by being like a little bit cognizant of where the viewer is。

 you can do better than just these generic data structures。

 and there's all kinds of tricks out there like that。😊，What was that。Yeah。

 there's a lot of these kinds of things。 a different one is something called Fstum callinging。

 where essentially like you can think of all the stuff you can see as like forming some little square shaped thing coming out of your eye。

 you can just throw away any object that is invisible in that fretum。 and that's perfectly fine。

 Its to be a little careful in ray tracing doing these kinds of tricks， though。

 because like reflection might mean that something outside of your view F them is actually quite important for what you render。

 So yeah， there's a whole like there are books and books worth of these kinds of tricks。

 The basic data structures don't use the viewer， but there's certainly ones that do。😊，Great question。

 yes。At point think。Yeah， that's right。 So so you to's sort of was mentioning like you have to be really careful if you're gonna to use these tricks for like using the viewer to construct your data structure。

 like there's still good likelihood that light could bounce in a funny way that you wouldn't predict that doesn't mean that you can there's a lot of kind of engineering decisions that go into these things。

 So it could be like you construct a Kd tree， which is always correct。

 but it makes it faster for the typical rendering， you think you're going to do and that would be perfectly fine。

 Now， later in this course， we're going to talk about rasterization where you draw one object at a time instead of one ray at a time。

 and in rasterization and there are all kinds of techniques like this where you just throw away objects that you think are not visible。

 And there you can， because typically the lighting the reflection model is much simpler So you can get away with that kind of stuff。

😊，All right， excellent question， any other questions about either ray tracing or your homework deadlines？

WhereI'm a full service professor。Okay， so。With that。

 we're going to continue our discussion of making essentially more interesting visual content in our rendered scenes。

 If you recall last time we were all about material right。

 and essentially what we were able to do was to take our ray tracer and take every object in our scene and attach to an information that says like how the material reflects light right like light that comes into this angle tends to be reflected this way。

 Anyone remember like what the the big acronym was that we use for this stuff。😊，Bardia。

 everybody wake up， say it after me， Bardia。There you go， Oh， and the hand gestures， too。 What。

 what a day。 Yeah， that's great。 So， so anybody remember what it stands for。😊，By direct。

should be so close。 Yeah， by bi directionional reflectance distribution function。 So mouthful。

 whoever invented B RD Fs wasn't thinking about branding very carefully。😊。

But we're stuck with it now。Okay， so essentially where we lost left off。

 we now can talk about material locally， right Like I can hold up a little magnifying glass to my material and describe how it interacts with light。

 But of course， the reality is that material very spatially right like is's very rare to find an object in your everyday life that's just uniformly made of one reflectance。

 material kind of all the way across the surface。 right。

 there's roughness and color and texture and all of these things vary from point to point。

 And so your BDF is not typically just like。😊，A set of numbers attached to an object。 But rather。

 it's a set of numbers attached to a location on an object that might change spatially。

 Does that make sense。And so essentially， that's going to be our goal for today is to talk about what it means to attach texture and shading information to a surface in a way that varies with relatively high frequency along the surface。

 okay？And this is a really important task。 So for example， here。

 we have what's his bucket from the matrix。 and essentially in each of these pairs。

 one of them is rendered and one of them is just like a guy standing in front of a camera。

 And you can see that it's actually really hard to figure out the difference between agent。

 whatever his name is and his digital double Oza。😊，Smith， thank you。

 And it's not a very memorable name。Right and in particular。

 what's really important for shading this character here is all the different material that shows up in addition to the geometry。

 In fact actually， I think the geometry here is relatively simple。

 especially in this kind of pixelated image that I'm showing you but you guys laugh。

 but like the resolution of these old movies was not super high。

 you know but you've got shiny texture on his shoes， you know his suit is made of a particular thing。

 his skin has different texture and of course all of these things are varying spatially and that's what we want to keep track of today。

😊，So essentially， all the materials we've seen so far are the same everywhere。

 But if we want to render this like weird double teapot thing。

 we're going to need to do better than that。 And， and that's our goal today。

 And so the way that we're going to do that。😊，And when I say we， I mean like the graphics community。

 the consensus scientifically of the approach that people use for this kind of thing。

Is to take your B RDF and allow it to vary over space。 right， So， for example， we had， you know。

 like the the Fng shading model had this diffus color， right， case of D。

And that was going to give you， you know， the color of the material that kind of reflects every which way as opposed to like the specular color would be the one that bounces off like a reflection。

And now we're going to think of diffuse color as a function of position。 So like。

 I point to a location on the teapot。 And then my graphic system tells me at that location。

 the diffuse color is blue。😊，RightAnd if you think about it from like the perspective of your rendering algorithm。

 that's good enough right because like all the decision making you do about deciding on a color of a pixel is local。

 you're not like integrating over the surface of the teapot or something wild like that。😊，Yet。Okay。

 and and of course， all of these things can vary spatially， right。

 like the spectral specular component， you know， the exponent of that， that fong model。

 even even some really wild things like， you know， translucent or whatever else。

 any any of these things you want。😊，Okay， so that's our basic motivation and there's really one standard approach here。

 which is where we'll spend most of our time。 and then at the end we'll suggest a second one。

 which is also important， especially in the more artistic side。😊。

So the principal approach to solving problems like this is something called texture mapping。

The basic idea here is that the meshes that we have on hand and graphics are often pretty coarse。

Right， like the the meshes that you guys have used in your assignments。

 which are already like taxing the load on your laptops somewhat like those meshes。

 you can see the triangles， right， like， like you can see the flat facets there。

 And so you'd like your， your your detail， like your texture to be。😊。

Probably denser than the density of the triangles along the surface。 that's the basic point。

 And so the way that we can bridge that gap is rather than like storing one color per triangle or something like that。

 which might be your initial thought。 What you're going to do is you're going take your 3D surface like。

 this bunny here。😊，You're going to cut it up because bununny's a spirit。

And you're going to map each of these pieces into the plane like what you see on the right hand side。

And the idea is that I can store like a JPg like a photograph or an image with the texture on the right。

 and then I'm going to take that texture and wrap it around the 3D surface。

 and that procedure is called texture mapping。😊，Okay。

 and so essentially what I'm gonna do is every triangle is actually going to store two sets of coordinates。

 It's going to store its position in 3D， right， like the shape of the bunny。

 And then it's going to store a second set of coordinates。

 which are like the vertices of the triangle in the texture map。😊，Okay。

 so does everybody kind of understand that high level strategy。

 we're going to spend quite a bit of time digging into that today。Now。

 the second type of way that we can make interesting。

 spatially varying material is using procedural rendering。So in procedural rendering。

 we're going to write a little piece of code that actually produces the color on the fly。Right，Like。

 so， for example， let's say that I have a material which like waves between red and blue， right。

 And it's like a function of the X coordinate。 You know， like， I take the cosine of X。

 And that's the amount of red that's in my， my image or something。

 Then I can just write a piece of code that produces that color on the fly。

 I don't need to store it in a texture map。😊，And so that little piece of code is going to be our very first introduction to a really important object in computer graphics。

 like banging my fist on the podium。 so you know it's important， and that's called a shader。😊。

And the basic idea of a shader is going to be like a little piece of code that gets run every single time I need to compute the color of a pixel or something like that。

So shaders were actually originally introduced for really high fidelity fancy graphics。

 They're introduced as with many of these technologies at Pixar animation Studios by Pat Hanhan and Company。

 There's a particular tool called Renderman， which was popular。😊，20。

30 years ago and continues to be used today。These days shaders are probably better known in the realtime graphics universe。

 where essentially almost all of the computation you do in OpenGL is sort of centered around different types of shaders。

 for example you all implemented some really simple one in your homework zero and on homework5 you'll implement some really annoying ones because that's my job。

😊，Okay， so so texture mapping is incredibly important part of the graphics pipeline。

 It's one that we spend a lot of time on， and I don't think it's terribly surprising。

 so here's another example with like a very typical in this case。

 quad mesh of a face right So here this is extremely smooth surface right it's probably not faceted。

 This is probably rendered using subdivision。😊，But of course。

 you get all this nice high frequency detail on this guy by doing these lookups into the texture map。

 which is basically wrapped up from the plane。😊，So that's going to be the strategy we talk about today and it really is just like wallpapering right like essentially all we're doing is taking like a two dimensional image and kind of stretching it over the mesh。

But while that sounds easy to kind of agree with， the details are kind of a headache， right。

 Like we need to figure out how to compute such a texture map。And more。

 there's a problem which is the plane is flat and your surface is not， and so no matter what。

 you're going to induce some distortion of that texture map when you map it onto the 3D surface。😊。

And a really bad texture amount could be a big problem。 right， Like when we， for example， you know。

 every， every year you buy your new phone， I just got a big fight with A and T and spent my whole weekend getting a new phone。

 And you know， they always tell you how many megapixels there are。😊，An issue here， of course。

 is that the megapixels are going to vary along the surface because your texture mount could get squashed on some parts of the bunny and stretched out in other ones。

 and that's actually necessary from the perspective of geometry。

 you have to do something to cope with the fact that your image is flat and the surface isn't And so parameterization tools。

 which continue to be proposed every year are essentially trying to optimize that distortion and make it meet different demands of artistic setup。

😊，I like this topic a lot so I can get all excited and then have to like calm down a little bit。Okay。

 so we're going to talk about the texture mapping procedure and essentially there's two different things we have to do。

 We have to tell you how to get a texture map， like who figures out how to map that bunny into the plane。

😊，The answer usually is artists who aren't paid very well。

 but there is some automatic tools out there that can help with that process。

And then the other thing we have to do is say， like， well once I have that texture map。

 how do I actually do rendering， Right， Like， we haven't really talked about how to do that shading calculation。

 And so these are the things we'll focus on today。So first。

 let's talk about actually that second question。 So let's say that I have for every triangle on my bunny here。

I have a map of that triangle into the plane。 So in other words。

 I just know the three vertices in in the image plane。

So the first thing that I have to do is figure out how to actually do my shading， right。

 so let's say that I've implemented my ray tracer。😊。

I send my ray out from the eye through my little virtual image plane。

 and it hits that green point on the bunny。Now， the question is， what color do I choose。

 that's what I have to do。So how did I intersect rays with triangles？ you guys remember like。

 what was the big calculation that we did。Barycentric coordinates。 Thank you。

 So remember the the point of veryrycentric coordinate is kind of telling me like where inside of the triangle I am。

 right， That's that's what the veryrycentric coordinate is。😊，But now I actually have two triangles。

 right， I have the triangle in 3D， and then I have another triangle in the texture plane down here。

Which is essentially where I'm going to try and read off the color。So。

 so what do you think is going to be the trick here。

 So I know they're very centric coordinates of the position of my。

 my intersection of my ray and the 3D object。 Now， how do I choose the right color。Yeah。

 I take it basically， well， I just use the same coordinate。On that triangle in the。

That's exactly right。 Do guys see what's what's going on there。 So like I have。You know。

 here's my eye。 Here's a bunny。It's made of one triangle。 I send the ray out， and it。

Hits that triangle somewhere。 and this is in 3D。 This is sitting in R 3。And that gives me。

Very centric coordinate， as supposed to be a gamma of the position of the intersection。Right。

 but now I have another。Triangle， which is sitting in the texture plane。And essentially。

 you know this is like the first vertex corresponds to the first vertex here and so on， right。

 I have them because of my texture map。😊，And essentially what I'm going to do is just use exactly these very centric coordinates。

 but with respect to these positions in 2D。😊，To find a position in the texture plane。

 and that's the color that I'm going to use。Yes。やめですか。No， so。

 so so alpha beta and gamma are these verycentric coordinates。 So they're relative to the triangle。

 So they're actually already planar coordinates。 right。

 So this is there's no interesting 3D structure here。 You're absolutely right。

 but all three coordinates are needed。😊，They're sort of redundant。 right。

 Gamma is is 1 minus alpha minus beta。 Remember， they all sum up to one。Yes， just。Yeah。

 so this is a really critical point for one。😊，The likelihood of array hitting exactly on the corner is zero。

 so we don't have to worry about that case a whole lot， but there is a really important issue。😊。

Which is。What do I notice about the texture map in this image relative to the actual bunny？😊。

And it cut them up。And that's 100% necessary。 There's no way to squash this bunny onto the plane without cutting it up。

 sadly for the bunny， right？And what does that mean， Well， that means that like。

 let's say that I have two triangles in 3D。That share an edge like that。Well。

 if those triangles happen to be kind of along the edge of the texture map here。

Then what's going to end up happening， Well， essentially this triangle might get mapped to the one that I've drawn here and the one right next to it。

I'll put a star on it could get mapped somewhere completely different。Right。

So this is actually a really important point。 So in particular， when I store my texture map。

The temptation would be to store one texture coordinate per vertex of my triangle mesh。

Like for example， like my triangle mesh in 3D， what do I do。

 Like every vertex just has a position in 3D。But notice that， like in this picture。This vertex here。

Has two different positions in the plane， right， Like it might be here and then there。

Does that make sense。So really what I need to do is for every triangle。

 I need to store all three of its vertices as positions in the texture plane。

 even though that vertex might be shared in 3D。That makes sense。

 so to return to Justice' question and then I'll let him ask the next one。Essential， you know。

 when I do my ray triangle intersection， I look up which triangle I'm working with。

 and that tells me which are the ones to go to the plane down here。Oh。

 like like who cooked up that texture map？For now we're going to assume that we're given。

 so in other words， every triangle has positions of his vertices in 3D and also positions of his vertices in 2D。

But there's a really important question， which is who designs such a thing， right。

I don't think it would be so natural to ask somebody to like draw this image。

 And that's a great question。 We're going return to that。 In fact。

 this happens to be a topic I personally work on。 So I can tell you for days about all the tools that we do here。

😊，Right， so so to review I suppose you what we just drew on the board here using an ugly picture on the screen。

 if I want to have like this nice stone texture on my 3D triangle。

 essentially what do I do well again I intersect in 3D I use exactly the same coordinates in the image plane。

 often people in computer graphics call this the UV plane。😊。

The phraseU comes up a lot in parameterization， a lot of people call this the UV map。But anyway。

 and that's the color that I use to read off of the image。 and that's what I put in 3D。Okay。

That makes sense。Any questions about the basics here， we'll start with Ari and then I。有一滴雪 had了吗。

And when they're first designers。About like。Kind of like instead of doing the weird thing。打。

Skinm the bunny。Like Edwin， if you seem like like a。Ter。Mmhmm。Oh yeah。 So its a good question。

 which is like， do you really need so many cuts here？ And the answer is is yes and no。😊。

So here's the thing， let's say I have one triangle just on its own。

I think we could all agree that we could map that one triangle into the plane with zero distortion。

Right， because triangleles are plainer。And so here's a really brain dead way that I could come up with the texture map of this bunny。

 I could forget adjacency of the vertices altogether。 Every single triangle。

 I could just put them in a long line。😊，And I could map them and have no distortion at all。

Why might that be not a great strategy， Some people do this， by the way， for simple models。

 it might be fine。I don't think it would be complicated to paint because you'd probably be painting on the 3D surface。

 so the computer's taking care of all those weird lookups。Yeah。Yeah。

 it might interact with subdivision， what about something simpler， what could go wrong？Actually。

 you could use a tiny amount of memory， right， I mean， like。

 you're just squashing everything into one little line。 That's also bad。Well， here's the thing。

 So I've got a pixel grid on my， my， my texture image， right， So in this case。

 it's just like vertical and horizontal slices。And let's draw it down here。And here's the second one。

Now。Let's say that I have like this edge here。Right so that corresponds to now two different edges like this guy and this guy。

 do you guys understand my picture despite having now drawn on top of it 10 times。

Essentially my point is that like there's one edge here that's like maybe shared among two triangles。

So that gets mapped to two different edges in the texture plane because they got broken apart。

So if you look at the intersection of that edge with the pixel grid。It intersects in different ways。

 In fact， the edge might have two different lengths in in the map。

 And so what what will end up happening is when you render。

 you'll see little artifacts right along that edge because you're not seeing perfect alignment of the texture map on the two sides。

So I think that's a pretty typical reason why you might not want to just break up the whole mesh。

They would be the same length。 in this extreme example， you unglue everything。

 they'd be the same length， but they probably wouldn't align with the pixel grid the same way。Yeah。

イやス。Iこ。Well， on the other side， if we cut it up as little as possible。

 well then necessarily we're going to have distortion， right。

 Anytime there's a vertex with curvature。 So like if you look at a bunch of triangles that are adjacent to a vertex。

😊，And you sum up the interior angles。Unless those things sum up to two pi。

 that vertex will necessarily be distorted when you map it into the plane。

And so with every vertex that you choose not to cut， you have induced distortion of your map。

 So there's an interesting trade off。 We're gonna come back to this later。

 but I'm glad you guys are thinking about it， which is on the one hand。

 we'd like to keep it all in one coherent piece。 Some that can make for a nicer texture。

 It's also easier to work with。 Like you can paint in the texture plane。😊，On the other hand。

 that induces some distortion， so there's a trade off between the length of the cut and the distortion of the map。

いや。In fact， we'll see an example of precisely that playing out an optimization tool in a few minutes。

没必用。Good really perfect。Need to cut the rabbits up。 That's what they say。

You't there like a theory that says we can a map。Y。And went。うん，老。That's right。 In fact。

 there are many different themems。 If you take a topology class or differential geometry class。

 you'll spend most of your time proving these things。 If you're topologist。

 you might notice that the bunny is a sphere， right It's just a big ball and this thing is a disk。

 and so necessarily there has to be a cut to have a continuous map from one to the other Gaus's theorem。

 which I can never say in Latin。 so I will just write it。😊，嗯。

I think roughly translates to totally awesome theorem in Latin I not even kidding。

 that's that's what it is。 It actually says that if you integrate curvature over different things。

 you get this sort of topological invariant is a different way to kind of understand the issues that can come up here。

In any event， it doesn't really matter。 This is fancy math for saying that like bunny' is a around thing and the plane's flat。

 and clearly something has to happen in between。I think that's enough intuition for now。

Got to click the button。All right， so that's the basic way that we do our rendering。

 and this is pretty called a texture lookup。😊，And it's exactly what it sounds like。 right。

 So at the end of the day， you have this texture image。 like。

 here's this gross hand texture thing that I'm using to render this 3D hand here。

 So now that I have my very centric coordinate， I just lift the the pixel color there。😊。

What we're going to see over the next couple of lectures is that this texture lookup is a little more complicated。

 of course， than we might anticipate。😊，Can I give you guys。

Anticipate some problems that might occur here。In particular， I was just watching that， you。

 that Seinfeld episode with with the hand model。never mind let's say that I'm rendering this hand。

 and I've used this extremely detailed texture。Because I want like a really nice looking texture skin thing。

But then the character walks really far away from the camera。Okay， now， now arm makes an oof noise。

 it's good to dig into that a little psychologically。

 I it feels like a lot of data for the image you're trying to render。

 But that's actually not a big deal。 in the sense that your texture lookups only look up the color you need。

 right Like you know where to look in the pixel grid。😊，But what could go wrong？Look give your hint。

 So， so think about two like basically adjacent pixels on the hand。

Where are they going to end up in the texture map？Really far away， because this is a big image。

 right， Like， there's a lot of texture being squeezed into very few pixels in the rendered image。

But take a look at this image here。 there's a lot of high frequency information， right， I mean。

 you've got like bright pixels， where's shiny， you've got darker pixels。

 which is just the color of the skin。And essentially， when you're taking these big jumps。

It's more or less as random。 which of those colors you're going to get。

 So what do you think that hand is going to look like when you render it。S noiseす。Yeah。

 so this is one of these examples where you， you make this like hello detailed texture because you feel like it's gonna make your graphics better。

 And it actually makes it worse。😊，嗯。😊，The reality is that one pixel color isn't enough here， right。

 Like somehow you should be taking integrals over regions here。😊。

And that's what we're going to talk about in our next lecture， yes。

It is where a nice trafficpic filtering takes place， because now。

 if my hand texture is like that and then I tilt it away from the camera。

 then one square pixel on my screen gets mapped to like an ellipse on the hand。

 So the integral act to take is a little complicated。😊，That's right。

 So keep that in the back of your head。 And we're gonna talk about mi mapping in our next lecture。

 which is one way around that kind of an issue。Okay， so anyway， that's the basic procedure。

 I don't know why。There you go， yeah。Although， ironically， I think this ended。It's a triceratops。

Your instructor is a little bit sloppy when it comes to drawing these diagrams。

It's also a different issue， so we talked about minification。

 which is the issues that come up when something gets far away from the camera。😊。

There's also magnification where I get up in the hands business， of course， there's one issue。

 which is that maybe the texture map like the texture is not detailed enough。

 The second one is that most likely your texture lookup is not going to land on like an integer lattice It's going to land somewhere in between your pixels on your image。

😊，So what should I do？Yeah， average， right like there's a lot of different ways I could do this。

 right， So the simplest thing I might do is just round， like take the closest pixel color。😊，But then。

 of course， you'll see discontinuities in the texture。 like you'll jump， you'll see little squares。

So probably what most people do is by linear interpolation。

 I don't think it's worth like totally belavoing this point because by linear interpolation is exactly what it sounds like。

 So for example， if I have a particular position inside of my pixel whose color I'm trying to get I could you know interpolate linearly across the horizontal lines first and then vertically and get some color there just using a straight line。

😊，The good news， by the way， is if you went the other way， like vertically and then horizontally。

 you can convince yourself you get the same color。So that makes sense。

 I mean we can dig into the formulas here， but I think this is like roughly what I think if you guys all sat with some pen and paper and wanted to guess like how to interpolate color inside of a pixel。

 what you probably do。There are actually other filters that take larger neighborhoods into account。

 it turns out from a Fourier perspective that's actually a good thing。

 if you've taken signal processing， you might have heard of sync and like sampling and reconstruction filters。

In case you haven't， every year in 837， I feel professionally obligated to attempt to teach all of four year theory in about a half a lecture that will be next time。

Hold on to something or another and we'll see how well we do。Okay， so。

 so these are the kinds of challenges you have to worry about。

 Here's the other one that we already talked about that like， if you miniify something。

 then you could end up with a bunch of noise in your image。

So the basic way we're going to solve this is using a technique called mi mapping。

Mit mapping is really sneaky。 So what you do is you have your original texture image。

And then you scale it by one half。You you scale that by one half and so on。

 just by like averaging like maybe four pixels at a time。

RightSo you have like your original picture of pixel， which is maybe back your original texture。

 which is like 32 by 32。 then you get another one that's like 16 by 16， another one's8 by 8。😊，Right。

 so you end up with texture maps that looks something like this。

 And then what you do during rendering is you sample your texture from the the， the MI level。

 like the size texture， which is roughly on the scale of like the depth to your camera。

And notice that like one pixel in this like small part of the Mimap is actually representative of many pixels in the original。

 So it's kind of doing that averaging that we talked about。 This high level trick makes sense。

 We're going to dig into it more next time。 but just as a quick preview。😊，Yeah。Is在这。ちょっと待けて。

When you say empty space。Rogan。1月份。Oh。What exactly like that？They're just wasted pixels。 Yeah。

 so there's just no triangles that sit there。 They're just taking up memory。Yeah。

 here here's a good question。 So here's your mim。 So again， remember how we got it。

 It's by taking the image。😊，And then making an image half as big。

 And then making another one that's like a quarter is big and an eighth and so on。

You can imagine a universe where like。I don't like that because it's going to take up a bunch of space in my memory。

 right， Like I'm making a bunch of textures instead of one。Is that a concern that I should have？

Roughly， what do we think。Yeah， let's think about this a little bit。And so in particular。

Let's say that my original image is like， one unit of memory。

How much memory does the one that's half as big tick？Quarter go。 sorry， gotcha。

And then how much memory does the next MI level take？Yeah， or one over four squared。Yeah。

 now I'm bad at math， so I don't remember what this number is。

 but I certainly know that it's less than or equal to two。😊，So in particular。

 the nice observation about mit mapping is that it actually really doesn't take a whole lot more memory than storing the original texture and you get this nice antialliasing。

😊，Any questions about that？Cool， so we'll come back to that more when we discuss sampling。 In fact。

 we'll， we'll discuss some， some sophisticated techniques for making those myth levels and sampling them。

 You know， we， we asked earlier about antiisotropic sampling。

 like if they surface tips away from the camera， then in that case。

 you might want your mi to like squeeze half horizontally or vertically or something like that。

 So there are a lot of variations on this this story。😊，Okay。

 so now we've covered how to render using a U map。 The other question we should answer is how to actually get one。

 right and many of you were already asking a lot of questions and thinking critically about how you might go about that。

AndThe reality is that obtaining U coordinates is a hard problem。

 This this is a problem that we continue to study today as a geometry guy。

 It's like one that I really like because it's somehow very well posed and easy to like。😊。

Fight with mathematically。 And the reality is that there are many different strategies out there for obtaining UV coordinates。

😊，And they range wildly， everything from just manually， which sounds ridiculous。 But actually。

 I think is the sort of。State of the art in a lot of artistic settings with some tools to kind of help you with that。

There's some special surfaces where you can maybe come up with a reasonable close form map。

 we'll talk about that a little bit。And then what we all study in academia and what's starting to get implemented in graphics world are these algorithms out there for doing parametertrization automatically。

 and these are a lot of fun。😊，So here's what a typical parameterization tool looks like。

 I'm told that they are extremely tedious and painful。

 I don't personally have any interest in playing with them。

 I find this as a differential geometry person who studies graphics， I find this to be fascinating。

Essential， we' are asking artists to solve an annoying geometry problem by hand because we don't know how to do it algorithmically。

 that's exactly what's going on。 So you make your 3D model here。 And literally。

 you might hire somebody that will just。😊，Take virtual scissors to that model。

Place the boundary and then maybe kind of like you know optimize the distortion a little bit in the interior to create the UV map。

And it turns out that this is a problem that that like you can study in， in art school。

 And there are actually some really interesting considerations that go into this。

 I'll try not to get like too excited about this。 But I think it's just fascinating。 Like。

 if you watch somebody do this， it's really interesting。😊。

In addition to the concerns we already talked about， like distortion versus number of cuts。

 a lot of times people will place the cuts very strategically in these 3D models。 So， for example。

 like in this character。Yeah， so you can see like theyre cuts behind his ears and that's because those are very unlikely to be just seen in the course of the animated sequence。

 So if there's like some visual artifact there because your texture doesn't quite match up。

 it's probably okay because it's like behind your ears and nobody's going to see it。😊。

So there's actually some semantic information that goes into this as well。

 it's not just like distortion that goes into help people design these UV maps。

 which is kind of cool。😊，Moreover， sometimes people design it so that like。

 I go out into nature and I take a photo of something。

 and I't want to wrap it around my 3D character。 So then like， maybe you have to kind of。

Design your texture map cognizant of the photo you already took。 right， In that case。

 you're kind of solving the reverse problem。 right。

 You have the 2D thing and you're trying to make it work in 3D。So these are the typical things。

 this is I think in 3D Studio Max， almost any 3D modeling tool has some UV mapping code inside of it。

 where essentially you usually place the boundary and then there's some automatic thing that will try to fix the interior。

😊，If you forget to veteran。a secondMDons behind。Yeah， we'll come back to that in just a moment。

Excellent， so so this is one strategy which is called， you know this is a shortterm gain strategy。

 you know， rather than hiring a software engineer， you hire much cheaper artist。

 they do it by hand and then you make your movie and you're done。😊。

There are other models where you can just come up with a formula for your UV map。 So for example。

 if you want to make this extremely high resolution soup can that we have here。

 you could all probably cook up a pretty reasonable UV map for that using your favorite polar coordinate kind of projection。

 you know there's lots of cylindrical spherical ones。😊。

One reasonable thing for a lot of surfaces that don't have crevices。

Like surfaces that you can kind of reasonably view from the outside。

 one trick that used to be popular in the 80s and 90s was to kind of like simulate there being a projector sitting on the side of the surface。

So like if I wanted to know the texture coordinate of a vertex on my 3D mesh。

 I would just do that camera projection to some virtual camera where my texture lived and this is a calculation I can do right like I don't need to actually compute that ahead of time。

I don't think that too many people do that anymore。 So it's not worth worrying about a whole lot。

 The one place where it does get used is in an area of computer vision called image based rendering。

We' like I want to composite together stuff that I've gotten from photographs with， you know。

 some virtual model or like take a photo and then simulate you know a view of that image from a different angle or something like that。

 So here's like an early example of one of these from Berkeley， horrible football team。

Where essentially they were able to do that because it Campanil right like the Berkeley。

 so it looks so 90s。Its like this relatively simple piece of geometry， right。

 like it's basically just a giant rectangle。So we can see in a moment the impressive things that we could do with the simple imagebased rendering technique。

哎。As we all know， computer scientists are known for their acting ability。An。

RightSo this is done with image based rendering where they're a really rudimentary model of the Campanil。

 and then they're able to map basically their photos from some fixed camera angles onto the 3D geometry。

 and that's what's making this effect。Wait。It's the virtual one， Yeah。

 they didn't have drones in the '90s。Actually， I they probably did。嗯。Yeah， but yeah yeah。😊，嗯。Yeah。

 there you거。 so anyway。Berkeley， it was one of the early demos of this kind of stuff。

Exciting and also makes your instructor a little seaick。Okay。So to return to Maxine's question。

One totally reasonable question to ask is like， well。

 why aren't computers just doing this automatically like it seems like。

UV mapping is inherently just a byproduct of how we do render English。

 There's no artistic decision making to be done there。 And so maybe really。

 we should just rely on software to compute it。 And indeed。

 there are a number of software tools out there that want to。

Sold this kind of an optimization problem。But as an optimization problem。

 it turns out U mapping is quite difficult。 And， and here's， here's the reason why。 So you have。

Essentially， like， if you think the first question is。

 how many variables do you have in your optimization， then the question is， well。

The answer is like at least one position in the plane per vertex of your triangle mesh。

 which is already a lot。 right， So if your mesh has 1000 vertices。

 that's 20000 unknowns in your optimization problem you're solving for。

So what does your objective function look like， Well。

 for every single triangle you want its edge lengths， maybe not to stretch out too much。

It's already a bit of a headache。 You have to decide whether or not to unglue any edge if you're trying to figure out the cuts while you're at it。

 many people ignore that problem and say， like maybe the cuts are given and I just don't know the U map。

And then moreover， there's actually a really subtle one。

 which is where essentially a lot of the modern research comes into play， which is injectivity。😊。

So here's the thing。 Let's say that my automatic parameterization software。

Accidentally put two triangles on the same part of the plane。Can I use that UV map？No。

 because like now those two triangles will always be textured the same。Right， so what does that mean。

 That means that I have。And2 n variables， and I have n squared constraints because for every pair of triangles。

 I have to make sure they don't overlap。😊，And if any pair of them does， I throw the whole thing away。

And so it turns out this is what makes it really， really hard problem to study literally just this morning our research group published another paper on this topic。

 it's one that people work on very very hard， you can take 838 or I believe vortex class 839 both clever some strategies for this and I'll also show you some images from some modern papers in just a moment。

😊，我就。Because remember how texture mapping works， if they map to the same part of the plane。

Right what's going to happen， Well， no matter what that location of overlap is essentially getting the same part of the texture map。

 right？So like in my triceratops rug， they have to be the same color。

 so I've got two different triangles that no matter what get painted the same。That's true， I mean。

 like maybe you could cook up a special case where like you want that to happen。

 like maybe this' is a left right symmetry or something， but like in general。

 you'd like it to happen because you decided so not just because your paratization tool made a mistake。

Cool， so there are a lot of different algorithms out there。

 the most famous one and the one that is implemented in most of these U mapping tools is something called touch parameterization。

 T U， TTE。😊，I think a lot of people think it's Italian， but apparently he's actually British。

Todd is a really simple algorithm， and it's actually， I think。😊。

One of relatively few that has theoretical guarantees， it's a nice example of linear algebra。

 which I know you guys all know and love。So here's the basic idea of tut parameterization。 So tut。

I think actually in the original paper， he kind of guessed a condition that turns about to be equivalent to a lot of other nice conditions。

So here's an example of a 3D face that's getting mapped into the parameter plane。

And Tt made an observation was that oftentimes when you look at vertices in the interior of your paratization here。

They tend to be at the average of their neighbors。Right， so like if I have a vertex， let me draw。

Picture。I know I'm going to go over time lectures today because I just really like this stuff。

 I'm sorry。So let's say I have a vertex。V。Then somehow， if I look at the one ring of that vertex。

 like all the triangles that are jased into it， So here's like W。

Then oftentimes what happens in a good perr station is that V is like roughly one over the number of neighbors of V。

Times the sum。Like that so like essentially if I take all these neighboring vertices and I average their positions。

 I get V's position here。😊，I think this is kind of a reasonable model for like what a good one ring looks like。

 right that you're like the average of your neighbors。So in a parameterization problem。

 what are my unknowns， they're like all these positions。Now。Look at this condition。

 This condition is linear in the vertex positions。 You see that。This is a linear condition。

 It's just saying that V minus this weighted sum here is equal to 0。

Where the unknowns are like the V's and the W。So I could write this condition down for every single internal vertex。

Of my system， I could say that every single vertex wants to be the average of its neighboring vertices。

And that's exactly what tu parameterization does。 It sets up a linear system of equations。

 or which says for each vertex V I， I'd like it to be the average of its neighbors。

And that's true for any interior vertex。 And on the boundary， I just prescribed the position。

And this turns out to be kind of like just setting up a bunch of springs on other vertices and letting them relax。

And then the optimal thing here is called the tu parameterization。😊。

Top parameterization is to my knowledge， the only kind of linear strategy that guarantees injectivity。

Meaning that if you solve this system of equations， no two triangles will ever overlap。

So long as the boundary of your shape is convex。If you want a really hard math problem。

 like really hard， try and prove that at home。Convex is like a circle， so it can't dip inward。

So this was a really nice result in geometry it's not easy to prove that this happens。

 but it's very nice because this is exactly the property you want for parametermettrization。😊。

The only problem with Td is that it often creates really bad maps。

 that tend to be really stretchy and weird looking。

 And that's where all of us come in and work with these things。 So， for example， actually。

 here's an image of exactly what Ari was asking about with a cow that got mapped using a relatively modern algorithm from our group。

😊，The even harder versions of these actually deal with taking a surface。😊。

Cutting it into pieces and paraizing all the individual pieces。 In that case。

 there's a trade off between the length of the cut and the distortion of the individual pieces that you have to navigate。

 This is an open problem。 There are relatively few research papers that try to tackle this。

 There are a few。 So for fun， I thought I'd show you a video from one。

 which is a couple years ago with some some colleagues at another school at Adobe and。😊，UBC。

 so the way that we do it is really start with the parameterization because that's the only one that has guarantee of being injective。

 And that way， as you optimize distortion， if two triangles overlap。

 you just kind of backtrack and you keep optimizing。

 And so this is a system that does that by essentially at any given step。

 it can either move the vertices around in the parameter plane or cut a little bit。

 And it's trying to optimize some trade off between the length of the cut and the distortion of the interior。

😊，And so you can see what happens。 So essentially， we。

 we take this little letter texture on the plane， and we're using that to map onto the surface because it's a nice visualization of distortion。

 right， So like a good map of。😊，All these letters are roughly the same size。And， and essentially， as。

Paation proceeds， it goes from some crazy thing which is squash。

 like that's a very typical tu parametturtization。To one that looks a little better。

 so we'll let our octopus converge for a moment。Notice that we have to do all kinds of crazy tricks right here not only we were parameterizing the surface。

 but actually， it turns out for technical reasons， you have to parameterize the space around the surface too。

😊，So these are hard problems。So the orange things here are showing you that cuts as like get computed from a system like that。

So the advantage here is that you don't have to hire somebody to do this by hand and probably like parameterizing this octopus would be pretty hard to do by hand because it's got so many。

Things， on the other hand， I mean， this tool is， is hardly real time。

 So like we're playing this video at 5 x speed， you know。

 relative to the algorithm actually running behind the scenes。😊。

So these are really tough computations to do well。 And every year。

 people come out with new techniques for this。 Like this paper has been replaced four times over。

Okay， so anyway， to return to your question， like these are tough problems and these are things people keep thinking about。

 And it's a really nice intersection between large scale optimization and art really。

 because you're really trying to meet the demands of this kind of ill-defined artistic task。

 which is tricky to do。😊，In fact， these days， of course。

 machine learning people are trying to tackle this stuff as well。It's a little bit unclear。

 precisely the role of learning here， but there is one。 specifically。

 remember that artists tend to place the cuts in sort of semantically meaningful places。

 So it might be that you find a data set of parameterized models and you try to learn like artists tend to cut behind the ears。

 that kind of thing。😊，So all kinds of good things， you know， stay tuned。

Okay so that's the high level picture。 Let's fill in a a few more details and kind of standard practices。

 So here's one a very typical thing to do is render big brick buildings and of course it seems wasteful to store a giant photograph of the whole brick building's texture from beginning to end。

 So' a typical thing to do。😊，Might be to come up with a procedure for just wrapping your texture。

 That's very easy to do， right， Like modular arithmetic。 lets you do that。

 So like maybe you round your， your coordinates and you just keep wrapping around the same little texture patch。

 It's also easy enough to draw textures that kind of meet up from one side to the other。

 So like this brick texture is a bad example because you can see the seam。

 but it would be easy enough to draw one that didn't。

 You just had to be careful on the boundary to make things match。😊。

The other thing that's worth noting is that like so far。

 I've basically shown you examples where it's just this color that's getting texture map。

 But I can texture map anything that I want， right It doesn't have to be color。 It could be。

 you know， the diffuse， specular and ambient information。

 It could be parameters of the lighting model， which B R D F to use any of that is fair game to stare storing your texture map。

Essential， what I've been like I've been using the word image to refer to this。😊，Thing。

 but it's not just an image。 It can be just a big grid of numbers that contains whatever information you need to render。

So for example， here's a rusty sheet。 So here， remember in the Fong shading model。😊。

There's that parameter， right there's that specular shading coefficient。

 which tells you how shiny your material is。😊，So here， obviously。

 the metallic part has a very high specular component and the rusty part does not。

 And so that's the kind of information you might store in a texture map。😊，Does that make sense？Cool。

And in fact， we can go wild with this idea。 like once people realize that their texture map doesn't have to contain texture。

 they started storing all kinds of weird stuff。 So here's one very typical thing。

 which is a little bit unexpected。 I think the first time you see it This is idea called normal mapping。

 Does anybody encounter normal mapping before。 It's a pretty typical video game trick。😊，Oh， good。

 All right。 So normal mapping says that actually， what I'm going to store in my texture map is the normal to my 3D surface。

😊，Which sounds totally wild， right， because the normal feels like a geometry thing like I should get it off of the triangle mesh。

But there's a good reason to do that， which is that you can kind of simulate really high frequency texture like like like a rough material on your surface without like making little tiny vertices that are bumped up and down by just perturbing the normal vector because remember the normal vector is sort of the key thing that goes into all these shading calculations like reflection and everything else。

😊，And so that's exactly what a normal map is or bump map。😊。

Is essentially you have a coarse triangle mesh， but you simulate having a really fine one by storing a different normal vector as just like a texture that varies along the interior of a triangle。

 and that's the one that you use for your shading calculation。So here's what this might look like。

 So， for example， remember your diffuse component of your shading is like the dot product between your normal and the lighting vector。

😊，So now during shading， you actually look up your UV and you read the normal vector not by like taking the cross product。

 the edges of the triangle， but you just read it off of your normal map and so that way your normal might actually kind of vary back and forth along the surface and that's going to simulate that rough texture。

That makes sense。Yes， yeah。Oh， that's a great question， which is， how do I represent the normal。

 right， So like， I could represent an X， Y， Z coordinate。 You're absolutely right。

 that that actually， that's a great question。 It turns out not to be a great way to store it。

 because like if I rotate my 3D model， I got to figure out what happens to all those normals。😊。

So I think a more typical thing is to do exactly what you suggest。

 which is to actually store a displacement of the triangle normal。

 maybe in the plane of the triangle or something like that。

 There are a lot of engineering decisions to be made there。 But that's。

 that's a really fantastic point。😊，Any others？Yeah， so let's see an example。So here。

 so one reason why you might use normal mapping is just for compression。

 especially in like video games where like high frequency texture is hard to deal with。

 So here's a 3D scan of some， some statue or another。 It has 4 million triangles。

 and it catches all those little crevices very well。😊。

So one thing you could do is really aggressively simplify that triangle mesh。

And then what you're going to do is in the interior of the triangles。

 you're going to store the kind of normal to the denser mesh as a texture。

And so like if you take a look， like if you compare， you know， here's the original model。

Here's the normal map 1。 I think it's actually kind of hard to see the difference。 You will。

 If you get close enough to it， you'll have this weird effect where the surface is somehow flat and the shading is varying。

 But from a distance， it's very hard to tell because occlusion just doesn't really happen。

Does that makes sense， this is kind of sneaky trick。

So like here's an example of like sort of an industry ready normal map and they're extremely detailed。

 people store all kinds of cool stuff and these things。

 and that's what makes for some of the interesting rendering effects。😊，Again。

 notice that these tricks are starting to move toward like video game style rendering where like。

These kinds of tricks， like storing things in textures to make it faster are going to really matter。

 but they also work in ray tracing。 You can do both。嗯。Generating a normal map。

 there are a lot of different ways you can do that。

 I think the image that I showed you before is pretty suggestive of a good strategy where you like。

 take your really dense mesh。 You simplify it， and then you kind of read off the text the normal map from the the dense 1。

 I don't think this matters a whole lot。 I'll let you guys look at this slide later。

 if you're curious， but there are a lot of ways to compute normal maps out there。😊，I think again。

 a very typical thing to do is to just paint it。 A lot of people paint like perturbations of the。

 the surface normal or like， you know， to some roughness parameter or something like that。

I think one of the most common places that you see this kind of thing is in like brick buildings in video games where like you want to simulate a little bit of like parallax kind of effect like walking past the brick building affects the shading or like moving the light around。

 but you're not going to get close enough to the bricks where you're going actually see the bricks occlude each other which is where the geometry would matter and so that's the kind of place where this thing works well。

😊，It have to be really careful dealing with like， for example。

 curved surfaces or like tiling and so on。 Then And suggestions is absolutely right。

 You need to like。😊，Maybe store like a displacement of the normal instead of the normal itself is probably smart。

Okay， so that concludes our discussion of texture mapping and remember I promise you a second strategy for generating texture which is procedural rendering any questions about texture mapping before we move on to our next little discussion here？

😊，I think it's somehow pretty intuitive。The main point here is that like。

Given a texture map or a normal map or a bump map or whatever。

 it's really not so hard to implement the rendering procedure。

 the really hard part is how do you obtain that texture map。😊，And。

 and that's a problem we continue to think about today。Okay。So。Now。

 we're going jump back 20 years and look at our our favorite kind of 1980s style ray trace image for a little longer。

 And here we've got our our favorite two spheres on a checkerboard a scene of a favorite in the。😊。

Ray tracing robe。 and we're going to use this to motivate the idea that some textures we don't need to store in an image at all。

😊，So for example， let's say I want to render this checkerboard on the ground here。

 the ground maybe is the X Y plane。What could I do？Indeed， the color goes from yellow to red。

 precisely how would I do that？い。Yeah， that's right， I couldn't be like use， you know。

 like if the X coordinate， you know I don't know， I round it to an integer and if it's even。

 then I make it red， if it's odd， I make it yellow or something like that， right？

And that's a piece of code I could write， that doesn't get evaluated until almost until test time。

 but that's the wrong course， like until rendering time。Right， so here if I， if I like。

 while I'm rendering my image， I do my ray tracing。 It runs into the plane。 I get this position。

 And only then do I do that rounding calculation， that is different from texture map where kind of all the colors computed at priori。

😊，Right the advantage here is that I could walk for days along this checkerboard floor and it will continue looking like a checkerboard。

 which is different from texture mapping where eventually I' reach the end。😊。

And so that's one nice advantage。 The other nice one， kind of similar to like， you know。

 the difference between vector graphics and raster graphics。

 like I can zoom in infinitely close to this checkerboard and it will still have sharp edges right。

 So like， if I get really close to this little corner here。

 it's not like I'll eventually see pixels because I'm doing some close form calculation。

 It allows me to zoom in or out as far as I like。😊，Now。

 some of those miification issues we talked about are still important， right。

 Like if I move far enough away from the texture， the checker board， I'll still see noise。

 but that's something we'll talk about later。😊，Okay。

 so the idea of procedural rendering is the idea that for a lot of materials we can just write down a little piece of code that takes maybe X。

YZ and outputs color， doesn't have to look it up in a texture map it just does it on the fly。😊。

This is a really early idea on computer graphics， and it actually was one of the more influential kind of tricks for some of the early movies。

 We'll see some examples of that later on。😊，So this is our first example of this thing called a shader。

 this is a really important keyword in this course。So a shader is like a function。 for now。

 a function that gets executed when light interacts with the surface。 So think like， you know。😊。

I detected that array intersected this thing， and I want to know its color。

 so I'm going to call it a shader。Later on， we're also going to talk about vertex shaders。

 which can do the same thing， but kind of iterate over geometry instead of pixels。

So a shader typically will like input basically all the information that you need about the material and maybe the surface itself。

 and then just output a piece of color。😊，And the idea is that maybe I even have a really good compiler that makes that little piece of shadedr code really。

 really fast。And that's important because it's going to get evaluated roughly like 10 gajillion times because like for every single pixel it's going to get evaluated at least once So it's like worthwhile for me to really accelerate that little micro programgram that's sitting inside of my ray tracer。

😊，Does makes sense。That's a high level idea of a shader。

 And this turned out to be really the tip of the iceberg。

 But like what people notice in graphics is that like。😊。

There's just certain functions that just get called over and over and over again and that like if we can just optimize those。

 then we can get really far into a fast graphics pipeline and that idea really goes back to this idea of shading。

And so shaders originally were for like production style rendering like some of the old shaders for like fancy movie scenes were actually many like thousands of lines of code and very detailed and doing quadrture and integrals and like all kinds of fancy sampling。

 these days are mostly used in realtime graphics and video games。 Open GL starting with OpenGL 2。

0 is completely built around shaders。 And it's like sort of the basic unit of all graphics computation。

 in that setting。😊，Incidentally shaders also typically are really optimized for texture mapping。

 it turns out that that texture lookup like give me the color at this position in my pixelix grid or maybe bilinely interpolated。

 it usually hardware accelerated in your graphics car。

 and so typically your shader is sort of built sub sit right next to that piece of hardware and be evaluated really fast。

😊，Okay， so for now we're going to talk about the sort of math and procedure rendering。

 we'll get to the hardware aspects later。 The advantages here is that they tend to be easy to implement。

 They've got infinite resolution。 Sometimes they take up less memory， right。

 You don't have to store a whole image just this little piece of code。😊。

disadvantage is that now you need a programmer， right， programmers are annoying。😊，Moreover。

 it can be kind of hard to match an existing texture， right？For texture mapping。

 like if I want a texture that looks like this chair， I would probably take a photo of this chair。

RightAnd then I could do that。 if I wanted to do that procedurally。

 I'd have to like write a piece of code that replicates this little funky pattern。

 and that seems much harder。Okay， any question about the high level like what a procedural texture is。

 why you might want it？I think it's pretty reasonable。Okay。

 so there's one really famous example of a procedural texture， maybe I happen to know， by the way。

So this is called pearlin noise。Named after Ken Perarland， professors NYU。

 the weirdest job interview I've ever had， but I'll save that for when the camera's not on。

And essentially Pearlin noise is the sort of strategy for creating。

Stuff that like like what you see in this image here， where it's like somehow noisy。

 but not that noisy。Like notice that this isn't just white noise。 It doesn't look like TV speckle。

 like it's smooth， but it still varies kind of randomly。

And this turns out to be the building block of many really cool texturing functions。

 even though it just looks pretty boring， we're going to see that momentarily。

 the basic idea being that like somehow there is a scale to this noise。

 like there's some spatial radius where it looks like noise and some spatial radius where it looks smooth。

 and then I'm gonna be able to kind of crank that up and down。😊。

And that artists can actually use this to make some really interesting kind of textures on models。

So we call this a pseudo random function。 It's like kind of random。

 but obviously there's like some smoothness here， So it's not just like IID sampling from some distribution。

Okay。So by the way， Pearlin noise is just like a hack。

 It's like a series of steps that Pearlin came up with that happened to be very effective for graphics tests。

 This is not like somehow something that you're going to go like take a probability class and prove their about。

😊，I think you can， by the way， there are some， but they came later。嗯。

So the basic idea of parallel noise is I'd like a function that takes like X，Y。

 Z and then just gives me back a number， which is kind of random， but kind of smooth。Right。

 and it works in some kind of arbitrary low dimension， you know。

 like four dimensions is is pretty typical for X， Y， Z in time。

 And essentially the the deceerta here， in addition to being like smooth at some prescribed scale。

 random at some other scale， is that you don't want to like take up a bunch of memory。

 basically storing a big grid of random numbers on your computer that that feels wasteful。😊。

So here was Berlin's big idea。Guess what it's built on？Slinees。

 because everything is built on splines。 So， so here's what what Pearlin did in in one dimension。

 It's actually quite clever。 So， so what you do in 1 D is you have like a grid。 or in this case。

 just says， you know， a set of vertices along the line。😊，And in every vertex。

 you're going to generate a random number， which is the slope of your curve。Okay， so。

Pearlin noise is the function which is zero at each of these grid points。

But has a randomly generated slope。That makes sense。So remember， by the way， good midterm review。

 I've got two points and two slopes。How should they interpolate？First of all。

 what degree polynomial do I need？I think just heard like four people groan。

t four pieces of information， two points and two slopes。Degree3 polynomial。 Yeah。

 anybody remember the name of the basis I'd probably use？It rhymes with。Car meat。Yeah， right。

 so this is our meat sp right when you have two points and two slopes。😊，Okay。Right so。Rightai。

 so there's our one dimensional noise。 You used to have all the formulas in this slide。

 then I realized， like， you can just look back at your spine lecture。

 You don't need all these formulas。😊，But that's， that's the basic point here。 Oops。

 I do have all the formulas， but you can ignore them because they're just same meat splin。Okay。

 so that's it for Perarlin noise， you just store this long line of random numbers that are like slopes。

 and then you're just interpolating between them using cubic spinelines。

 But there are few tricks that Perlin proposed to make that a little more efficient and to use up less memory because again。

 it's like storing a big grid of random numbers feels wasteful。 Moreover， we need to deal with 3D。😊。

In three， pro noise is no more complicated， essentially you now just store a random slope in X。

 Y and z at every node of your lattice， and then you just interpolate like bicbically like1 and x1 and y and1 and Z。

So， so that that person's not too bad。Okay， so so that's it for the pearlan noise algorithm in its basic incarnation。

 you have a position inside of some lattice， you have this randomly generated set of slopes on the vertices of the lattice and you just interpolate them bilinely。

😊，嗯。One thing that Pearlin noticed is that humans are really bad at persceiving random numbers。

 This is absolutely true。 like there are so many different perceptual studies that measure this in different ways。

So what he found is that it was enough to like just have one long list of random numbers that just。

Its length doesn't happen to is like maybe co prime with the size of your grid。

And then to just kind of keep looping through that list of random numbers over and over again。

 and that's probably good enough right so Perlin in practice what you do typically is rather than having a giant grid of random numbers you have some relatively short lists and then you just keep cycling from beginning to end and turnss are you're not going to see the difference。

😊，Should you use this for your like RSA， cryptography， whatever thing on your laptop， No。

 but for rendering it's probably good enough。Okay so。The high level point here。

 which I hope you all can agree with is that prolanno gives you a function that roughly averages up to 0。

😊，And essentially， it's sort of noisy at the scale of the spacing between the grid points and kind of smooth in between。

 That makes sense。 That's， that's how it was designed。 And again， there's nothing magic。

 You guys could have all gone home and designed your own， you know， like， like Max noise。

 and it would be perfectly fine。 Like， you know， like， there's nothing special here。😊。

But what Prolong found is that there are really clever ways to combine these into interesting functions。

So here's an example。 So here's a sphere where I think we've taken purarla noise in 3D and then just restricted it to the surface of the sphere。

😊，So it kind of looks like， you know， a bloy function。 This case， we made it blue。

One vocabulary word that gets used a lot in this area isoctave。

 which I think is kind of cute The idea is that like you typically store like a really dense grid with like very high frequency pear and noise then one that's like half as big and half as big and half as big and so those are called octaves so kind of like the scale of the noise。

😊，And so here's the idea， is that。These create a nice。

 kind of just simple function that you then can apply other stuff to。 So， for example。

 I could like round this between blue and black。 And suddenly I get a function which kind of looks like an interesting。

 like black and blue pattern with sharp boundaries。😊，Right， or like I combine multiple octaves。

 and now I have like a little planet kind of thing。

Right so here's one very high frequency octave that I think was rendered in red and another low frequency one that's in bloom。

 So there's the low frequency part。 There's the high frequency part added onto it。😊。

And you can see that like with remarkably few terms。

 suddenly pear noise actually starts to look like something interesting。

 It's kind of surprising how quickly this happens。😊，So in this case。

 I think what we did is each octave has like weight that like decays in the size of the octave or something like that。

Is this science， Is there any like materials going on here or like。

 this is how planets form or something？ No， this is just like， he just said， like， w， I want。

 you know， like big noise to be big and small noise to be small。 Here's like a function I cooked up。

But notice that this is what procedural rendering is all about。 right。

 You cook up these kinds of functions。 You probably have a little preview sitting right next to it and you iterate until you get the material you like yep。

So here's the different thing you could do。😊，So remember my purar noise function。Again。

 it looks like something that's like kind of smooth locally， kind of noisy globally。

 and averages out to zero。So like here maybes an example of pear and noise， something like that。

What would happen if I took the absolute value of this function？Well for the most part。

 it would look smooth and that every once in a while it changes sign。

And like suddenly there's like a little curvature discontinuity。

 So now there's like some interesting sharp feature。

So maybe I throw that into my procedural shader for fun。

 and now I get this like very dramatic looking planet because now I have these sharp features every once in a while where my pelin noise changed things。

😊，Again。I can do anything I want to this function。 This is just like art disguised as cooking up weird equations。

Yeah。So I think we just put them in different channels。 So like here we've got like the blue channel。

 the red channel and the yellow channel recently，Here's the different thing I could do。

 maybe I want a marble texture that my marble texture has some stripes in it。😊。

So here's one way I could do it is I could use sign of like the x coordinate like from left to right。

 but of course that would make just like perfect stripes， So now I pertubed that using my per noise。

😊，And now I get this nice marble texture。So a remarkably large number of these like somehow very realistic looking textures that you see in rendered content。

 at least rendered content from maybe 20 years ago， I think I don't know how popular it is anymore。😊。

Really are just like cooked up functions of these low frequency noise things that people。

Gs over time。 So like， here's a comparison of the ones that we've seen so far。

 And these are all just different。Combinations of different octaves of pearlin noise。

So that makes sense to what we've done here。Really sneaky。

 This is just Pearlin's basic observation was just that like smooth， kind of noisy stuff is useful。

 That's the high level takeaway here。😊，And this is the beginning。

 I mean like artists that work with the stuff can do like remarkable things with these these functions。

 so like here's here's some more examples feel like here's a more detailed marble texture。

 I some turbulence some other stuff here's one where like before adding pear and noise they did like a polar coordinate transformation。

 So now you get like kind of tree ring looking structure。😊，And so on。

 So so like here's an example from from Ken Purlin himself。Make a corona。

 I suppose it's not great example anymore。 where here you， you've got like your son。

 So maybe you'll just like put a big black disc in the center。 And now you have， you know。

 your color is kind of a gradient that's dropping off from， from the center， but you。

 you perturb it in different ways。 You can animate it and so on。😊，So it turns out this was used。

 I mean this is one of historically the very first procedural shaders。

 I believe it was used in the original like Star Trek or something like that。

 T have been used for displacement for fur， all kinds of stuff。

 This turns out to be one of these tricks of the trade that you see a lot in computer graphics universe and it's really not so hard to implement and certainly。

 this is another popular choice for a course project probably because it's frankly not terribly difficult to get to work。

😊，Yeah， so so the high level point here is that essentially。😊。

The typical ingredients that might go into your shader is not just your position。

 but it might also be the texture of your surface at that point and even some predetermined noise function。

 like purarlin noise， all these ingredients get combined as input to your shader and then how you choose to engineer them can really make for some pretty impressive effects without too much code。

😊，And that this can be used to， again， the key point here is that it's not just color。

 it really is any rendering effect that you want， right specular stuff， roughness， whatever。

Incidentally you can also layer these things right you can like do multiple passes over your image。

 you can have one shade or input values to another It usually you can get as creative as you want。

 it's like programming language right you can compose things in all kinds of interesting ways。😊。

So the bottom line so far is， of course， that programmable shaders are giving us a lot of flexibility。

😊，They can be extremely complex， but we're going to see later on that in real time graphics。

 they often aren't。 or if they are， they're doing some really tricky stuff。

Any questions about pear noise or procedural texturing that kind stuff？

I feel like this span of a couple of weeks in this course is relatively are a lot of pictures that easy to digest。

 which is nice。Okay， so as a quick recap for today。

 essentially hopefully now we have a lot of tools out there that are going to really increase the complexity and the visual content of the scenes we're able to render。

 that now we can take all of our interesting materials in the previous lecture and make them very spatially So the two basic strategies that you need to remember are texture mapping where literally you just store the texture in an image and you wrap it back or procedural rendering where you do that on the fly by doing some。

😊。