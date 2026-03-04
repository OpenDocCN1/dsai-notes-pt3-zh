# 【NPTEL】计算机视觉的深度学习 p03 P03_图像形成 -BV1vNWkzpEua_p3-

![](img/81cfff28b2d987b2bf19f8f7c4828802_0.png)

![](img/81cfff28b2d987b2bf19f8f7c4828802_1.png)

Moving on from the history of computer vision。In this lecture。

 well talk about the formation of images。Before we go there。

Did you have a chance to check on the answer for the trivia question that we had last class？

What was Lawrence Roberts known for？Besides his contribution to computer vision。

He is more well known for being one of the founders of the Internet。In fact。

 he was the project leader of the ARPnet project that was the precursor to the Internet in the US Def organizationgan DRPA let's move on to the topic of this lecture。

As most of you may know。Images are formed when a light source hits as the surface of an object and light is reflected。

And some of that light is reflected onto an image plane。

Which is then captured through optics onto a sensor plane。

So that's the overall formation and the factors that affect the image formation are the light source strength and direction。

 the surface geometry。Material of the surface such as such as its texture。

 as well as other nearby surfaces that whose light could get reflected onto the surface。

The sensor capture properties well talk more about that as we go and the image representation and color space itself we'll talk about some of these as we go。

So to study all of these， one would probably need to study this from a geometrical perspective where you study 2D transformations。

 3D transformations， camera calibration distortion from a photometric perspective。

 where you study lighting， reflectance， shading， optics， so on。

 from a color perspective where you study the physics of color， human color， color representation。

 and from a sensor of perspective， looking at it from a human perception， camera design。

 sampling and alasing compression， so on and so forth。So we won't cover all of this。

 but cover a few relevant topics from these in this particular lecture。

 if you're interested in a more detailed coverage of these topics。

 please read chapters 1 to5 of the book by faucet and bonds starting with。

How light gets reflected of a surface。The more typical models of reflection state that when light hits a surface。

There are three simple reactions possible， there are more than three。

 but three simple reactions to start with。Firstly， sunlight is absorbed。

And that depends on a factor called albedo row。 And typically when you have a surface with low albedo。

 more light gets absorbed。 So that's why you say the factor is one minus lo for absorption。

Some light is reflected diffusively， it scatter in multiple directions。

So that happens independent of the viewing angle， the example of surfaces where light scatters diffusively is brick。

 cloth， rough wood or any other textured material。And in this scenario。

 Lambert's cosine law states that the amount of reflected light is proportional to cosine of angle from which you are viewing the reflection。

And thirdly， some light is also reflected specly。Where the the reflected light depends on the viewing direction。

So an example of a surface where this happens is a mirror where we all know that the reflected light follows the same angle as the incident light。

Generally， in the real world。Most surfaces have both specular and diffuse components。

And the intensity that you receive at the output depends also the illumination angle because when you have obque angle。

 lesser light comes through。And in addition to absorption， diffuse reflection and spec reflection。

 there are other。Actionions possible light there is transparency where light could pass through the surface。

 there is a refraction such as a prism where light could get refracted。

There is also subsurface scattering where multiple layers of the surface could result in certain levels of scattering。

And finally， there are also phenomena such as fluorescence where the output wavelength could be different from the input wavelength or other phenomena such as phosphoorescence。

An important concept that。Is also studied here is called the BRDF or the bidirectional reflectance distribution function。

Which is a model of local reflection that tells us how bright a surface appears。From one direction。

 when light falls on it from another direction， another pre specifiedified direction。

 and there are models to evaluate how bright the surface appears。From a viewpoint of color itself。

 we all know that visible light is one portion of the vast electromagnetic spectrum。

 so visible light is one small portion of the vast electromagnetic spectrum so we know that if it falls on one side ultraviolet star falls on the other side and there are many other forms of light across the electromagnetic spectrum。

So colored light， which arrives at a sensor typically involves。Two factors。

 color of the light source and color of the surface itself。So， an important。Development。

In sensing of color in cameras is what is known as the Bayer grid or the Bayer filter。

The Bayer grid talks about the arrangement of color filters in a camera sensor。

So not every sensing element in a cabinet captures all three components of light。

 you may be aware that typically we represent light as RGB， at least colored light as RGB， red。

 green and blue， we talk a little bit more about other ways of representing colored light a little later。

This is the typical way of representing colored light and not every sensing element on the camera captures all three colors being stick。

A person called Bayer proposed this method。In a grid manner where you have 50% green sensors。

 25% red sensors and 25% blue sensors， which is inspired by human visual receptors。

And this is how these sensors are checker， so in a real camera device you would have a sensor array and there is a set of sensors that captures only red light。

 there is a set of sensors that captures the green light and there is a set of sensors that captures the blue light。

And to obtain the full color image。Bmosaking algorithms are used where surrounding pixels are used to contribute to the value of the exact color at a given pixel so that particular sensing element will have its own color but you also use the surrounding elements to find out to assign a color at that particular sensing element these are known as bemosaing bemosackching algorithms。

This is not the only kind of color filter Bay filter is one filter that' is very popular。

 especially in single sensor cameras， but there have been other kinds of filters。

 other kinds of color。collor grading mechanisms that have been developed over the years too。

 so you can also read a little bit more about this on the Wikipedia entries of Bay filter。

 which also talks about other kinds of mechanisms that are used。So let's ask one question。

For you to think。A visible light spectrum is zipy。Or violet， indigo， blue， green， yellow。

 orange right？Why do we use an RGB way of representing colors？

There's something for you to think about， we will answer it in the next class。

 but least try to find this out yourself if you can。

So the image sensing pipeline in a camera follows the flow chart such as this。

Where you have the optics such as the lens， of course light falls into that。

 you have an upperture and a shutter parameters that you can specify or adjust。

And from there light falls onto the sensor， sensor can be CCD or CMs。

 we will talk about these variants very soon， then there is a gain factor。

We will talk about that also soon then the image is obtained in an analog or digital form which represents the raw image that you get but typically cameras don't stop there you then use demomosaking algorithms which we just talked about you could you could sharpen the image if you like。

Or do any any other important image processinging algorithms， some white balancing， some other。

Digital signal processing methods to improve the quality of the image。

 and finally you compress the image into a suitable fortnite to store the image。

So this is the general pipeline of image capture。So let's try tovisit visit some of these components over the next few minutes。

So first thing is the camera sensor itself， so you all must have heard of CCD and CMmoOS。

 this is often a common decision to be made when you buy a camera these days is a lesser issue but earlier days it used to be even more what's the difference。

So the main difference between CCD and CMmoOS is that in CCD， it stands for charged couple device。

You typically generate a charge at each sensing element and then you move that photo generated charge so the charge is generated by a photon strikingking that sensing element。

From pixel to pixel and you convert it to a voltage at an output node。On that particular column。

 then typically an ADC or an analog to digital converter converts each pixel's value into a digital value。

This is how the CCD sensors work。On the other hand。

 the CM sensors complementary metal oxide semiconductors。

They were by converting charge to voltage inside each element。

So CCD accumulates whereas CMmo converts at each element。

 it uses transistors at each pixel to amplify。And move the charge using more traditional virus。

 so the CMOS signal is digital， so it does not need any ADC at a later point in time。So today。

 CMs originally CMOS technologies had some limitations。

 but today CMOS technologies are fairly well developed and most of the cameras that we use today are actually CMs CMOS devices。

So the many properties that you actually see when you look at when you take a picture on a camera。

 shutter speed， which controls the amount of light rich in a sensor， or also called exposure time。

 sampling pitch which defines the spacing between the sensor cells on the imaging chip。

Fillll factor are also known as active sensing area size which sorry。

 which is the ratio of the active sensing area size with respect to the theoretically available sensing area on the sensing element。

 chip size， which is the entire size of area of the chip itself。Alog gain。

 which is the amplification of the sense signal using automatic game control logic。

 we won't go into the details of each of each of these once again if you are interested you can read the references provided at the end of this lecture to get more details of all of them typicallyy analog gain is what you control using your ISO setting on your camera。

You could also have sensor noise that comes from various sources in your sensing process。

Your resolution tells you how many bits you specify for each pixel。

Wwhich is also designed by an analog digital conversion module in CCD or in case of CMOS in the sensing in the sensing element。

 so which means if you use 8 bits to represent each pixel so you could get a value going from 0 to 255 for each pixel that gives you the sensing resolution for that particular pixel。

And finally， there are also post processing elements， as they already briefly mentioned。

 such as digital image enhancement methods used before compression and storage of the captured image。

So one public question that often can be asked here is these days smartphones seem to be so good。

 you have very high resolution cameras and smartphones。

 do you really need what are known as DSLR cameras so what are DSLR cameras。

DSLR camera stand for digital single lens reflectsx camera and the main difference between a DSLR camera or。

Any other pointed shoot camera or a cell phone camera is the use of mirrors。

DsLR camera uses a mirror mechanism to reflect light to a viewfinder or also can turn off the mirror moving the mirror out of the way to actually reflect the light on the image sensor so effectively the comparison here becomes between mirrored cameras and mirrorless cameras so mirrorless cameras such as what you see in your smartphones are more accessible portable low cost。

Whereas when you have a mirror the picture quality tends to be better you have more functionality possible again we won't step into more details here。

 but please do read on the sources on the links given under each slide if you want to know more。

Mirred cameras such as DSLR， DLR also give you a physical shutter mechanism。

 variable focal length and temperatureperture， so on and so forth。

 that's the reason there's value for DSLR cameras despite the advancement in smartphone cameras。

So the other factors that you need to understand when you talk about image formation is the concept of sampling allying we will talk about this in more detail a bit later。

 but a brief review now is Shannon sampling theorem states that。

If if the maximum frequency of your data on your image is F max。

 you should at least sample at twice that frequency。Why so we will see a bit later。

But for the moment， that frequency that you capture it is also called the Ns frequency。

And if you have frequencies about the Nqui frequency in your image。

Then the phenomenon called alaing happens。So why is this bad and what impact can it have on image formation？

This can often create issues when you upsample or downsample an image if you capture an image at a particular resolution。

 say256 cross 2 56。If you choose to ups sampleble or downs sampleampble aing can be dye in those settings。

 we will see this in more detail a bitilative in a lecture which will come up in some time。

Also in terms of representing the image itself there are multiple color spaces possible while RGB is the most common one people today use various other kinds of color spaces not necessarily in a camera。

 but in other kinds of devices well see that I'll mention that briefly now popular color spaces are RGB and C NYK CK stands for Cion maroon。

Maenta yellow and black that's what you see here so they are supposed to be so additive colors are RG R G and V subtractive colors are C N and Y particular application where CMYK is used in practice is is in printers so it happens that it's a lot easier to control colors using CYK in in printers you can read more about these on these links provided below other color spaces that are used in practice are X Y Z Y UV LAB YCBCR HSV so on and so forth。

There is actually an organization called the CE which establishes standards for color spaces because this is an important this is actually important for the printing and scanning industry I think this is extremely important for people working in that space so that's the reason there are standards established for these kinds of spaces we won't get into more details here once again if you are interested please go through these links below to know more about color spaces what do you mean by adjective subtractive so on and so forth please look at these links。

Finally， the last stage in image formation is image compression。

Because you have to store the image that you have captured。So typically。

 you convert the signal into a form called YCBCR。Where why is luminance， cCR talks about chrome。

 what is known as a color factor of the prominance。And the reason for this is that。

You typically try to compress luminance with a higher fidelity than prominance because of the way humans or the human visual system perceives light luminance is a bit more important than prominance so you ensure that luminance is actually compressed with a higher fidelity which means your reconstruction is better for luminance than for prominance so that's one reason why YCBCR is used as a popular color space before storage once again if I mean if you don't understand YCBCR go back to the previous light look at all of these links to understand YCBCR is one of the color space representations that are available in practice and as I just mentioned so the most common compression technique thats used to store an image is called the discrete cosine transform which is popularly used in standard such as Mg and JpeEG。

Dcrete cosine transform is actually a variant of discrete Fourier transform。

 and its a you can call it as a reasonable approximation of an eigen decomposition of image patches。

So you won't get into it all of that now videos， this is how images are compressed using a method called DCcT Vos also use what is known as block level motion compensation。

 So you also divide。Images into frames and a set of frames into the blocks。

 and then you store certain frames based on concept。From motion compensation。

 this is typically used in the impact standard which uses which divides all frames into what are known as I frames。

 P frames and B frames and then uses strategies to decide how each frame should be coded That's how videos are compressed。

And compression quality finally is measured through a metric called PSNR policies for the typo will be fixed before the slides are uploaded。

Which stands for peak signal to noise ratio， sorry photos thosetypo PNR is defined as。

10 log to the base 10 im square by MSc where imax is the maximum intensity and MSc is simply talks about the mean square error between the original image。

And the compressed image how much is the mean square error pixel vice between these two images and the numerator talks about the maximum intensity in that you can have in an image。

 so this is typically called as PSNR which is used to measure the quality of image compression there are other kinds of metrics which are based on human perception。

 but this is the most popular statistical metric that is used。

That's about this lecture on image formation so if you need to read more please read chapter 2 of Celleski's book。

 please also read the links provided on some of the slides。

 especially if one of those topics interestive or you're left with some questions please read those links。

If you want to know in a more detailed form about how images are captured。

 including the geometric aspect of it and the photometric aspect of it。

 please read chapters1 form of faut nu。

![](img/81cfff28b2d987b2bf19f8f7c4828802_3.png)