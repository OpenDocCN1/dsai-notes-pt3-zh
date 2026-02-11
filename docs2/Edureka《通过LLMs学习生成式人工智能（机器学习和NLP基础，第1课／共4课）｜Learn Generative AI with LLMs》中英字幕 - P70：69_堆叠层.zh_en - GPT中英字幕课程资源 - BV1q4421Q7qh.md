# Edureka《通过LLMs学习生成式人工智能（机器学习和NLP基础，第1课／共4课）｜Learn Generative AI with LLMs》中英字幕 - P70：69_堆叠层.zh_en - GPT中英字幕课程资源 - BV1q4421Q7qh

![](img/eb97f5c16c72c6c1e5563520ee901395_0.png)

So let's now explore the progression from our previous discussion。

 Each stage plays a very important role in extracting and refining features from the input data ultimately leading to effective image recognition and other visual tasks then here we are having each time the image gets more filtered as it goes through convolutional layers and smaller as it goes through pullinging layers in this example first of all we are providing the input grid the grid represents the initial image of the data with minus one in black places and the plus1 in the diagonal representation then it can be passed through the layer1 that is convolution plus re1 re in this the input grid undergoes to the first convolutional layer followed by the relu activation function this stage filters the。

😊。

![](img/eb97f5c16c72c6c1e5563520ee901395_2.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_3.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_4.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_5.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_6.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_7.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_8.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_9.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_10.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_11.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_12.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_13.png)

P image to extract the features and introduces non nonlinearity to the network。

 The output grid from this stage represents the first set of feature maps。 Then the second step。

 again， the convolution place relu。 So the feature maps from the previous stage undergo another convolutional layer followed by the relu activation。

 This stage further filters the feature maps to extract higher level features and enable the networks represent capabilities。

 The output grid from the stage represents the refined feature maps。 Then again。

 we are having the pulling layer here after two layers of convolution place relu， the pulling layer。

 the feature maps from the previous stage are subjected to the pulling operation。

 this pulling operation reduces the spatial dimensions of the。😊。



![](img/eb97f5c16c72c6c1e5563520ee901395_15.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_16.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_17.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_18.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_19.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_20.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_21.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_22.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_23.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_24.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_25.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_26.png)

Feature maps， helping to control overfitting and improve the computational efficiency。

 the output grids from this stage represents the pool feature maps with reduced spatial dimensions。

 Then it will again undergo third layer that is convolution placelu again So the pool feature maps undergo another convolutional layer followed by the relu activation。

 This stage further refines the feature maps and captures more complex patterns in the data the output grid from this stage represents final setoff feature maps。

 then again it will go to the pooling。 so similar to the previous polling operation。

 this stage further reduces the spatial dimensions of the feature maps。

 the output grids from this layer represents the final pool feature maps then coming to the output grid the final。

😊。

![](img/eb97f5c16c72c6c1e5563520ee901395_28.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_29.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_30.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_31.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_32.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_33.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_34.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_35.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_36.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_37.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_38.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_39.png)

Output consists of three grids， each representing the processed feature maps。

 The values in the grid represents the filtered and pool feature maps with higher values indicating stronger activation or presence of the features means provided sequence of operation illustrates how the input image undergoes multiple layers of convolution and relu activation resulting progressively filtered and downsampled feature maps。

 This sequential process helps the network extract the refined features。

 ultimately leading to the final output grids that represent the networks learned representation of the input data。

 Once if it is done we are performing the flattening。

 Imagine you have a stack of pancakes arranged in a grid on a plate， for example， let。😊。



![](img/eb97f5c16c72c6c1e5563520ee901395_41.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_42.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_43.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_44.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_45.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_46.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_47.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_48.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_49.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_50.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_51.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_52.png)

this is a plate and you are having a pancakes。 Okay， so you are having pancakes arranged on a plate。

 Each pancake represents a value of two dimensional array in case if you are thinking it as a vector space。

 now you can imagine if you want to eat the pancakes one by one。

 you would need to flatten the stack by removing each pancake from the top and placing it in a single line to another plate。

 right， in case if you want to eat them。 So this is the way you can easily access and consume each pancake individually rather going from the top to bottom once if you place all these in one dimension with all the way around like this you can directly access them right。

 So like this， this way you can easily access。

![](img/eb97f5c16c72c6c1e5563520ee901395_54.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_55.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_56.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_57.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_58.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_59.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_60.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_61.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_62.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_63.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_64.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_65.png)

Consume each pancake individually means technically flattering is a process in neural network where multidimensional data such as feature maps produced by the convolutional or pulling layer are transformed into one dimensional array this transformation is essential for passing the data to fully connected layers where which expects inputs in the vector format in a neural network after processing an image through convolution and pooling layers。

 you end up with feature maps containing spatial information flattening these feature maps convert them into linear array of values where each value corresponds to a specific feature or activation from the previous layer means technically flattening shapes the multidimensal arrays into one。

😊。

![](img/eb97f5c16c72c6c1e5563520ee901395_67.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_68.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_69.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_70.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_71.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_72.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_73.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_74.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_75.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_76.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_77.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_78.png)

Dimmensional vector without losing any of the original information。

 this transformation allows the subsequent fully connected layers to receive the inputs in a format they can process enabling the network to learn complex patterns and make predictions based on the extracted features just like we。

 however， we flatten the tag of pancakes for each consumption in the neural network flattening simplifies the representation of feature maps making it easier for subsequent layers to process the data by converting multidimensional data into linear format so the upcoming video will delve further into the ongoing discussion。

😊。

![](img/eb97f5c16c72c6c1e5563520ee901395_80.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_81.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_82.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_83.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_84.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_85.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_86.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_87.png)

![](img/eb97f5c16c72c6c1e5563520ee901395_88.png)