# 吴恩达《深入模型量化｜Quantization in Depth》中英字幕 - P4：4.Get the Scale and Zero Point.zh_en - GPT中英字幕课程资源 - BV1kw4m1X7Bi

As we saw in the notebook， the last piece we are missing is how to determine the optimal S and z to obtain the scale and the zero point。

 we need to look at the extreme values。 R mean should map Q min and or max should map to Q max and we get the following two equation since we have two unknowns s and z we cancel this equation If we subtract the first equation from the second one。

 we can get the scale， so this equation minus this one will give us the scale and for the zero point since we always determine S we just need for example。

 to use the first equation and replace s by the value we got before to get the zero point and at the end we end up with the specific formula we also need to round the value and to cast it to the correct D type since we saw that Z has the same D type as the quant value。



![](img/322cf34391c48c9a232ef1d5a2591d69_1.png)

If you want to have a look at the details of how we derive the scale and the zero point。

 I invite you to pause the video and take a screenshot at the following slides。

 so this one is for the scales derivation。

![](img/322cf34391c48c9a232ef1d5a2591d69_3.png)

And this one is for the zero point erivation。As you saw previously we make Z as the same D type as the quantized tensor。

 for example， as an integer and this is not the same D type as the scale。

 The goal behind this choice is to represent0 in the original range as an integer in the quantize range。

 So thanks to that， when you quantize the value 0， it will take the value with z in the quantize range and what is great is that if you dequize the value with z。

 It will become0 again。 now let's have a quick look at how we calculate the scale and the zero point on this example that you saw in the previous slides。



![](img/322cf34391c48c9a232ef1d5a2591d69_5.png)

So first we need to get the maximum and minimum range of the original tensor。

 so we have- 184 and 728。6。 So this is the maximum value and this is the minimum value and for the range of the quant value since we are quantized it in torch do in8 the minimum value is 128 and the maximum value is 127 So if you take the formula we learned before you get that the scale is equal to 3。

58 and the 0 point is equal to minus77。 the last h case we need to figure out is what happens when the 0 point is out of range for example。

 since we need to cast z to the quantized data types such as in8 what should we do when z is out of range So if z is less than Q min we set z equals to Q in and if that is superior to Q max we set Z to be equal to  Q。

axSo this way， we don't have overflow and underflow。 Now。

 we have everything to code how to get the scale and the0 point。 Let's do that。

 And don't worry about this slide。 We'll code it directly in the notebook。Now。

 let's get the scale and the zero point。Let's first start with the scale。

 as you saw in the formula we need ormax ormin Q maxax and Qing。

 we already saw how to get the Qax and the Qmin， so I'll just copy paste the code。

 so Qmin will be equal to the minimum value of the torch in8 information。

And the samevol max where we have max here。And as you say in the example。

 Qing should be equal to minus-128 and Qac should be equal to 127。 Let's have a look。

And we indeed have the same results now we need to get Rmin and Rmax to get the minimum value of the tensor。

 we can just use the min methods and we also need to call item to get the value and not the tensor。

As you can see here， we have the tensor。But we need to call also item to only get the value。

We do the same thing for R max， but this time we can get the maximum value by calling max。

Now we have everything to get the scale， as we said earlier， the scale is equal sew。Orm。

 man is Ormin。Divided by Q max minus cumin。And if you remember the example we just saw before。

 we have the right scale around 3。58。As you can see here。Now let's get the zero point。

To get the zero points， we just use the formula。So 0 point equals to Q min minus or mean。

Divid it by scale。And let's have a look at the0 point。We have-76。5 around。

 so we need to round and cast it to int and we get that the0 point is equal to minus-77 as we saw before if the zero point was inferior to Q in we will set it to Q in and if the zero point was superior to Q max we will set it to  Q max Now let's define the general function to get the scale and the zero point we'll call it getq scale and0 point this function takes two argument the tensor and the D type。



![](img/322cf34391c48c9a232ef1d5a2591d69_7.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_8.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_9.png)

And well set it to torch that in8 by default。As we saw before。

 we need to define the Qmin and the Q max， then we need to define the armmin and the ormax of the tensor。

We then define the scale。And the0 point。For the zero point， as we saw in the slide。

 there are three cases indicates the zero point is less than Qmin。

 we set the zero point to be equal to Qmin。Each the zero point is superior to Q max。We said it。

To Qax。 And the last case is we just round it and cast it to an integer。



![](img/322cf34391c48c9a232ef1d5a2591d69_11.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_12.png)

And we just return the scale and the zero point。Now。

 let's test this general function with the test tensor we define earlier。



![](img/322cf34391c48c9a232ef1d5a2591d69_14.png)

You can see that indeed we get the same scale and the same zero point as the one we saw in the lecture and before now using these new scales and new0 point。

 let's quant our tensor， So we will call the linear Q with scale and0 point function。



![](img/322cf34391c48c9a232ef1d5a2591d69_16.png)

By passing the new scale and the new zero point。 So the quant sensoror is equals to this function where we pass this time。

The test answer。But with the new scale。And new0 points。



![](img/322cf34391c48c9a232ef1d5a2591d69_18.png)

And as we did earlier year so， we also need to dequantitize our tensor to compare with the original tensor。

 So we call the linear deco quantization function when we pass the quantized tensor。And。

The new scale and the new zero points。

![](img/322cf34391c48c9a232ef1d5a2591d69_20.png)

To have a summary of what we just did， let's call the plot quantization error function with the test sensors。

 the quant sensor and the de quantized sensors。

![](img/322cf34391c48c9a232ef1d5a2591d69_22.png)

And as you can see this time， the original tensor and the deco quantized tensor are very similar。

 and the quantization error tensor looks also way much better。

 Now let's also have a look at the quantization error to see if it has decreased a lot or not。



![](img/322cf34391c48c9a232ef1d5a2591d69_24.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_25.png)

So if you remember well to get the quantization error。

 you subtract the deco quantized sensor and the test sensor， you take the square and you do the mean。



![](img/322cf34391c48c9a232ef1d5a2591d69_27.png)

And this time， as you can see， compared with the quantization error of around 170。

 now we only have a quantization error of around 1。

 Now let's put everything inside a linear quantization function that will only take a tensor and will return to you the quant sensorsor。

 the scale and the zero point， so we define the linear quantization function。

 it takes as inputs a tensor and。

![](img/322cf34391c48c9a232ef1d5a2591d69_29.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_30.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_31.png)

A D type that will set to torch do in8 by default in this function。

 we will use the two function that we coded before。 So the get Q scales and0 point。

To get the scales and the zero point。So we just call that function， and we just pass the tensor。

And also， the detail。Then after getting the scale and the zero point。

 we can perform the quantization of the tensor。 So we will get the quant tensor。

If we use the linear Q with scale and zero point function， we code it before。

Where we pass the tensor， and。The scale， the0 point。And the the type。

We just returned the quant sensor， the scale and the zero point。

Now let's play with this linear quantizer on a random matrix。 So we'll define a tensor。

Which will take random values and will be of size 4 by4。As you can see。

 we do have a random tensor of size5 by4。And we can just call the linear quantization function on our random tensor to get the quant tensor。

 the scale and the zero point。Let's have a look at the contest sensor。As you can see， the tensil was。

Quantized and we also have the following values for the scales and the zero points to have a summary of deco quantitization process。

 let's also deco quantetize the tensor by calling the linear deco quantitization and bypassing the quantized tensor the scale and the zero points。



![](img/322cf34391c48c9a232ef1d5a2591d69_33.png)

And we can use the plot quantization error function to have a summary of the quantization process。



![](img/322cf34391c48c9a232ef1d5a2591d69_35.png)

We pass the random tensor， the quantized tensor， and the de quantized tensor。



![](img/322cf34391c48c9a232ef1d5a2591d69_37.png)

好。

![](img/322cf34391c48c9a232ef1d5a2591d69_39.png)

And as you can see。The original tensor here is pretty much the same as the deco quantantized tensor and the quantitization era tensor is very small。

And we can also print the quantization error。

![](img/322cf34391c48c9a232ef1d5a2591d69_41.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_42.png)

Which is also pretty low。And now I invite you to pause the video and try to play with this quantizer with your own inputs and see how it performs in the next lesson we will div diaper into linear quantization by learning its symmetric variants and we will also look into quantization granular such as pertensor per channel and per group quantization。

 Finally， we will also look at how to perform inference with quantized models。



![](img/322cf34391c48c9a232ef1d5a2591d69_44.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_45.png)

![](img/322cf34391c48c9a232ef1d5a2591d69_46.png)