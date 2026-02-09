# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P131：31_在R绘图中处理颜色第2部分.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/463e1003763de534a78202d012e65114_0.png)

So the GR devices package has a few different functions to help you deal with colors and the ones that I'm going to talk about in this lecture are the color ramp function and the color ramp palette function basically these two function。

😊，Do take pallets of colors and interpolate between them。

 So the model that you can think of is basically you know if a painter has his palette or and there are a four or two or three blotches of specific colors on that palette and then what you might do is take your brush and kind of mix between the various colors or the various blotches on that palette to make new colors that are blends of the original colors that you had on the palette so I've never done any actual painting so I just the only thing I know about painting is you know from TV and movies。

 but that's kind of what I imagine a painter would do is take these primary colors and then blend them together with the brush and so that's what the color ramp and the color ramp palette functions do they take a set of colors that make up a palette and they interpolate in between them numerically of course。

 to make new colors that are blends of the original colors。

Another function that may be of interest to use is the colors function。

 which you just execute it with no arguments and it gives you a character vector of all the names of the colors that you can use in a ploting function。

 so these are colors that you can reference by name rather than having to reference their kind of red green and blue values we'll talk about later。

😊。

![](img/463e1003763de534a78202d012e65114_2.png)

嗯。So the color ramp function specifically takes a palette of colors and it returns another function。

And this function that's returned by color ramp will take values between 0 and 1 indicating the extremes of the color palette。

 and so a similar function that already exists in R is the gray function。

 and the gray function interpolates between black and white。

 and so it gives you kind of all the shades of gray there in between black and white。

The color ramp function is a generalization because it'll take any set of colors in your palette and it'll give you a function back that takes numbers between 01 and it can interpolate between the extremes of the color palette。

😊，The color ramp palette is a very similar type of function。

 it takes a palette of colors and what it does is it returns another function that rather than taking a value between 0 and1。

 it would takes an integer argument and will return a vector of colors interpolating that palette。

 so this is similar to the heat dot colors function or the toppo dot color function。

So let's just a very quick example here in the top here I've created I'm going to use a palette that consists of two colors。

 red and blue， so you can imagine that on your little painter's palette here you've got a blotch of red and a blotch of blue and you're going to mix them together in varying degrees to create new colors so when I pass this to color ramp it returns a function back and that function I've called pal and now palal can take numbers between0 and1 so when I say pal of zero。

😊，What do I get back， I get a little matrix here with one row and three columns and the three columns indicate represent the colors red。

 blue and green and so in the first column I've got 255。

 which is the maximum value that I can have in for these colors the numbers that you specify go between 0 and 255。

 this 256 total numbers that you can specify for each color and so when pal is0 gives the argument0。

 basically what it gives me back is red because that's kind of one end of the color spectrum that I've specified in my palette。

 the other end being blue of course， and so I've got the maximum value for red。

 I've got zero for green and I've got zero for blue。

So that color is red when I say pal of one down here， you see I've got 0 for red，0 for green。

 and then I've got the maximum 255 for blue。 So this just gives me the color blue。

 So that's the other end of my color palette。 So what if I do something in between like pal of 0。

5 So this gives me something that this should give me a color that's kind in the middle of red and blue。

 So it's going to give me 127。5 for red and then 0 for green 127。5 for blue。

 So it's kind of half red， half blue， whatever that color is happens to be。

 notice if there's no green in any of these calls because when you interpolate between red and blue。

 you don't encounter green along the way。😊。

![](img/463e1003763de534a78202d012e65114_4.png)

![](img/463e1003763de534a78202d012e65114_5.png)

![](img/463e1003763de534a78202d012e65114_6.png)

So if I were to give a sequence of numbers between0 and1s。

 Powell would give me a sequence of colors between red and blue。

 so here I'm giving a sequence between 0 and1 that's length 10。

 so it starts at zero and it ends at1 and there's eight numbers in between and so when I pass this sequence to pal you'll see at the very top here I've got I start with red so it's maximum red and then zero for green zero for blue and I slowly reduce the red amount and increase the blue amount until I get to the bottom here where I've got all blue and no green and no red so those are the various colors that you get in between red and blue as you interpolate the palette。



![](img/463e1003763de534a78202d012e65114_8.png)

So that's the color ramp function， the color ramp palette function is very similar but it just the type of function that it returns is slightly different。

 so here I'm passing it a different palette so this palette has two blotches。

 it has a red and a yellow blotch on it and we're going to try to interpolate between those two colors and so I've got a function here that's returned by color ramp palette called palal and now pal is going to take integer arguments。

 not numbers between0 and1 so suppose I give it two。😊。

So palettelet2 will return two colors that interpolate the palette Now because the palette itself only have two colors when I just give it two。

 it'll just give me the two colors on the palette so the first being red in the second being yellow and so though the way that the format here is slightly different instead of giving a matrix with red green and blue values it gives me a character vector which has numbers for values for red green and blue that are represented in hexadeadecimal and so if you ignore the pound symbol there。

 youll see there are two digits there are six digits in each character string。

 the first two represent red， the second two represent green and the third two represent blue so you can see for the first number here I've got FF0000 so in hexadecimal F is largest number you can have so FF on the red the red pair means a maximum for red and 00 for green。

00 for blue。

![](img/463e1003763de534a78202d012e65114_10.png)

![](img/463e1003763de534a78202d012e65114_11.png)

So that's red in the second string here， I've got FF for red， FF for green and then 0，0 for blue。

 So I've got the maximum on red and the maximum on green and Ive got nothing for blue。

 So what does that give me well that gives me yellow。

 I'm combined red and green I get yellow And so that's the other end of the spectrum on the palette。

 So when now if I say pal of 10， you'll see the first element here is going to be red because FF on red and0 and everything else。

 The last element here is going to be yellow because FF on red， FF on green，0 on the blue。

 But then in between， I've got my interpolation of colors。

 So you'll see that there'll be there be there'll be some red and then there'll be mix a little bit of green as you go along here for all the colors is no blue because you don encounter blue when you inter between red and yellow。

 So you can see now the representations of the colors in hexadecimal here changing as you go from red to yellow。

😊。

![](img/463e1003763de534a78202d012e65114_13.png)