# 杜克大学《R语言数据科学｜Data Science with R》中英字幕 p39 02_01_05_模型语言.zh_en -BV1Zpv6BaEkB_p39-

![](img/9e26fb2927149855cd224101ad1bb839_0.png)

![](img/9e26fb2927149855cd224101ad1bb839_1.png)

🎼。

![](img/9e26fb2927149855cd224101ad1bb839_3.png)

Hello， in this video， we'll dive deep into understanding what models are。

 how they work and how we use them to make sense of data。 Let's start with the obvious question。

 What is a model。At its core， we use models to explain the relationship between variables and to make predictions。

 Think of a model as a mathematical way of describing how one thing affects another or how one thing is associated with another。

 For now， we'll focus on linear models。 These are models that describe relationships with straight lines。

 But remember， this is just the beginning。 There are many， many other types of models out there。

Look at these two examples。 On the left， we have a linear relationship。

 The data points follow a relatively straight line pattern。 On the right。

 we see a nonlinear relationship。 The pattern curves and bends。 In this course。

 We'll focus on linear relationships， but it's important to know that not all relationships are linear and what you learn in this course about linear models provides a strong foundation for learning about nonlinear models。

 Let's do some modeling。 then。 We'll work through a concrete example to introduce modeling terminology。

 We have a data set。 Our old friend empty cars data set on fuel efficiency of cars。

 This scatter plot shows the relationship between cars weights and their fuel efficiency measured in miles per gallon MPG。

😊，I want you to consider two questions。 What's the relationship between car weights and their mileage and what would be your best guess for a car's mileage if it weighs 3500。

 Looking at this scatter plot， we can see the individual data points。

 Each point represents one car with its weight on the X axis and its fuel efficiency see on the y axis。

 Can you see a pattern emerging， Now， let's address our first question。

 What is the relationship between car's weights and their mileage。

 When we add a trend line to our data， The relationship becomes pretty clear。

 We can see a negative linear relationship as weight increases， miles per gallon decreases。

 This should make intuitive sense。 heavier cars typically get fewer miles per gallon and hence use more fuel。

The line helps us see the overall pattern in the data。

 even though individual cars might vary from this trend。Now， for our second question。

 what would be your best guess for a car's MPG if it weighs 3500。

 This is where the predictive power of our model comes in。

 We can use our trend line to make this prediction。 If we draw a vertical line from 3。

5 on the X axis up to our regression line and then draw a horizontal line from that point to the Y axis。

 we get our prediction approximately 18。5 m per gallon。

 This demonstrates how models allow us to make predictions about values we haven't directly observed In by the trend emerging from the observed data。

😊，So to summarize， we use models to explain relationships between variables and to make predictions。

 We're focusing on linear models。 But to remember， there are many other types of models for different kinds of relationships。

Now let's establish the key vocabulary we'll use when talking about models。

 these terms are essential for understanding how models work。First， the outcome。

 This is the variable whose behavior we're trying to understand。 It goes on the Y axis。

 You might also hear this called the response variable or dependent variable。 Second。

 the predictor or predictors。 These are the variables we use to explain the variation in the outcome。

 They go on the X axis。 These are also called explanatory variables or independent variables。

The model function is our regression line itself， it's what we use for making predictions。

 it's comprised of an intercept and a slope for each predictor。

The predicted value is what our model function gives us the typical or expected value of the outcome based on the predictor values。

Finally， residuals measure how far actual observation is from its predicted value。

 The residual equals the observed value minus the predicted value。

 This tells us how far above or below the expected value each case is。😊。

Let's see these concepts in action with our fuel efficiency data here。

 the predictor is weight shown in the highlighted column of our data table and emphasize on the x axis of our plot。

 The weight is what we're using to predict fuel efficiency。And here's our outcome variable。

 Miles per gallon。 This is what we're trying to predict or explain shown in the highlighted column and emphasized on the y axis。

 This is the variable whose behavior we want to understand。 This is our regression line。

 The model function that describes the relationship between weight and MPG。

 This line represents our best estimate of how MPG changes as weight changes。😊。

The slope of our regression line tells us how much the outcome changes for each unit increase in the predictor。

 In this case， the slope is negative， meaning that for each additional thousand of weight。

 we expect MPG to decrease by a certain amount。 The intercept is where our regression line crosses the y axis。

 It's the predicted value when the predictor equals 0。 In our car example。

 this would be the predicted MPG for a car that weighs 0。

 While this might not be practically meaningful， It's mathematically necessary for defining the regression line。

Correlation measures the strength and direction of the linear relationship between two variables。

 The correlation between weights and fuel efficiencies of these cars is negative 0。87。

Correlation ranges from negative 1 to one values closer to negative one indicate a strong negative relationship。

 values closer to positive one indicate a strong positive relationship。

 and values near zero indicate little to no a linear relationship。Our correlation of negative 0。

87 indicates a strong negative relationship between weight and fuel efficiency。

Here are some examples of different correlation values notice how correlation ranges between negative 1 and 1 and importantly it always has the same sign as the slope of the regression line Str correlations produce tighter patterns around the line while weak correlations show more scatter。

And here's a visualization of the model overlaid on the data。

 The line summarizes the overall relationship while the individual points show us the actual data and how much our variability exists around our model。

 to make this plot。 we use the Gm point function to add the point。

 and then add another layer with Gm smoothth to overlay the regression line。

 the method argument in Gem smoothth is set to LM short for linear model。

Residuals are crucial for understanding how well our model fits the data here。

 The points are colored based on whether they have positive or negative residuals。

 Positive residuals shown in pink are cases where the observed value is higher than predicted。

 These points lie above the regression line。 Negative residuals shown in yellow are cases where the observed value is lower than predicted。

These points lie below the line。 The magnitude of the residuals tell us how well our model is performing。

 Smalller residuals indicate better predictions。It's important to be cautious about extending regression lines beyond the range of our data。

 While mathematically， we can extend the line infinitely in both directions。

 doing so for prediction purposes can be dangerous。 Our model is based on the data we observed。

 making predictions far outside this range called extrapolation assumes the same relationship continues。

 which may not be true。 For example， in this case is not possible to have a car that weighs less than  zero。

 or even positive but a small number of pounds。 And it might not be possible for a car to weigh much more than 6000。

 or for the relationship between weight and fuel efficiency of cars to be the same for cars that are so large as regularly sized cars。

😊，Therefore， you should always be cautious about predictions outside your data range and avoid extrapolation without caution or very good reason。

 or with more advanced models that are specifically designed for making extrapolation。

 like forecasting， predicting for the future based on past time series data。

Models have both advantages and limitations。 On the positive side。

 models can reveal patterns that aren't immediately evident from just looking at the data。

 They provide a systematic way to understand relationships， and make predictions。However。

 there's a real risk that a model might impose structure that isn't really there。

 like seeing animal shapes and random starern patterns。Models are simplifications of reality。

 and we should always maintain a healthy skepticism about their conclusions。

The variation around our model， those residuals we talked about。

 is just as important as the model itself。 If not more so。 After all。

 statistics is the explanation of variation in the context of what remains unexplained。

 The scatter around our line suggest there might be other factors affecting fuel efficiency that we haven't accounted for。

 or perhaps randomness plays a big role。 Adding more explanatory variables or predictors to our model can sometimes reduce the scatter and improve our predictions。

 We'll explore this idea more later。😊，There are two main ways we use models first。

 to predict or classify， we plug in the values of our predictors to get a predicted value for the outcome。

 Second to describe， we use the slopes in our model to quantify the relationships between predictors and outcomes。

Let's think about prediction and classification in the real world。

How do self driving cars decide whether an object in front of them is a human。

 Another car or trash can。 They use models trained on thousands of images to classify what they're seeing。

 How does an online shopping website decide which ad to serve you for your next potential purchase。

 They use models that predict what you're most likely to buy based on your browsing history and other factors。

 But here's a crucial question。 What happens if either of these gets it wrong。

 The consequences can range from annoying to life threatening。

 Which is why understanding model accuracy and limitations is so important。

Now let's look at the descriptive use of models through a real research example this study on leisure。

 commute， physical activity and blood pressure examined the relationship between different types of physical activity and blood pressure in over 125。

000 adults the researchers wanted to understand how leisure time commuting and occupational physical activity relate to blood pressure levels。



![](img/9e26fb2927149855cd224101ad1bb839_5.png)

The study found that higher levels of commuting and leisure time physical activity。

 but not occupational physical activity were associated with lower blood pressure and reduced hypertension risk。

The relationship was dose dependent。 More activity LED to greater benefits。 For example。

 compared to no activity， the highest level of combined commuting and leisure activity was associated with 2。

9 mm of mercury reduction in systolic blood pressure。Interestingly。

 this relationship was age dependent。 The association was stronger in older adults。

 Those over 60 showed 4。64 mm of mercury reduction， compared to just 1。

67 mm of mercury in adults under 40。 This demonstrates how models help us describe and quantify relationships in complex real world data。

 allowing researchers to understand not just whether relationships exist。

 but how strong they are and how they vary across different groups。😊，In this video。

 we've explored fundamental language of models， from basic vocabulary。

 like predictors and outcomes to concepts like correlation and residuals。

 We've seen how models serve two key purposes， making predictions and describing relationships。

 Remember， models are powerful tools for understanding data。

 but theyre also simplifications of reality。 Always consider both what your model tells you and what it doesn't capture。

😊。