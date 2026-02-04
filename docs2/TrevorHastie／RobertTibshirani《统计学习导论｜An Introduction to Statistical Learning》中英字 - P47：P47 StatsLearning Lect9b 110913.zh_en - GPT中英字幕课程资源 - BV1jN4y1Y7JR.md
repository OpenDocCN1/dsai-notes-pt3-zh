# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P47：P47 StatsLearning Lect9b 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/ef70dc32dbfb60a76e750fe978587b8f_0.png)

Okay。Now we're going to talk about more adventurous methods。



![](img/ef70dc32dbfb60a76e750fe978587b8f_2.png)

And more modern， as well。And so piecewise polynomials。



![](img/ef70dc32dbfb60a76e750fe978587b8f_4.png)

Generalize the idea of piecewise constants。 So instead of having a single polynomial in x over its whole domain。

 you can use different polynomial in each region instead of different constants for different polynomials。



![](img/ef70dc32dbfb60a76e750fe978587b8f_6.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_7.png)

So this next figure。Shows a piecewise polynomial in two regions。 So you're in the top left panel。



![](img/ef70dc32dbfb60a76e750fe978587b8f_9.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_10.png)

There's a piecewise polynomial。 It's a cubic polynomial。 There's the knot at 50。



![](img/ef70dc32dbfb60a76e750fe978587b8f_12.png)

And it' it's a cubic to the left and a cubic to the right。 They're two different cubic polynomials。

 and they just fit to the data。 This one's fit to the data on the left。

 This one's fit to the data on the right。

![](img/ef70dc32dbfb60a76e750fe978587b8f_14.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_15.png)

What do you think of that， Rob？There's a break in the middle。 It is not pretty ugly， isn't it？



![](img/ef70dc32dbfb60a76e750fe978587b8f_17.png)

It's pretty ugly。

![](img/ef70dc32dbfb60a76e750fe978587b8f_19.png)

But that is a piece where as cubic polynomial。

![](img/ef70dc32dbfb60a76e750fe978587b8f_21.png)

But the brake's ugly， so it's better to add constraints to the polynomials， for example， continuity。



![](img/ef70dc32dbfb60a76e750fe978587b8f_23.png)

So in this top right panel， we've got a cubic polynomial in the left， a cubic in the right。

 but we forced it。

![](img/ef70dc32dbfb60a76e750fe978587b8f_25.png)

To be continuous at the knot。

![](img/ef70dc32dbfb60a76e750fe978587b8f_27.png)

So that looks much better already。 this is already starting to look like the function we got from the polynomial。

 a global polynomial but。

![](img/ef70dc32dbfb60a76e750fe978587b8f_29.png)

We can actually see this little kink in the middle here。 And in this case， it's not too egregious。

 but in some situations。

![](img/ef70dc32dbfb60a76e750fe978587b8f_31.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_32.png)

Continuity is not enough。So。

![](img/ef70dc32dbfb60a76e750fe978587b8f_34.png)

You can enforce continuity in on the derivatives as well。



![](img/ef70dc32dbfb60a76e750fe978587b8f_36.png)

So this function here， this red one is actually called a cubic spline。😊。



![](img/ef70dc32dbfb60a76e750fe978587b8f_38.png)

And what it is is it's a cubic polynomial in the left and the right。It's continuous at the not。



![](img/ef70dc32dbfb60a76e750fe978587b8f_40.png)

The first derivatives continues。At the knot， and the second derivatives continues at the knot。



![](img/ef70dc32dbfb60a76e750fe978587b8f_42.png)

So there's three constraints。

![](img/ef70dc32dbfb60a76e750fe978587b8f_44.png)

And that's called display。

![](img/ef70dc32dbfb60a76e750fe978587b8f_46.png)

Now， we couldn't make the third derivative continuous because then would just be a global cubic polynomial。

 So we've made as enough continuity as we can still allowing some separate。

 separate functions in cubic in each region。

![](img/ef70dc32dbfb60a76e750fe978587b8f_48.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_49.png)

That's called a cubic sp。

![](img/ef70dc32dbfb60a76e750fe978587b8f_51.png)

While we on it， we could have linear polynomials and here's a linear spline。

 so it's piecewise linear function。 it's linear in the left and the right。



![](img/ef70dc32dbfb60a76e750fe978587b8f_53.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_54.png)

And it forced to be continuous at the knot。

![](img/ef70dc32dbfb60a76e750fe978587b8f_56.png)

So the amount of continuity you can enforce is one。

 the order of continuity is one less than the degree of the polynomial。



![](img/ef70dc32dbfb60a76e750fe978587b8f_58.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_59.png)

So yeah， we can only enforce degree 0 continuity， whereas yeah we're force in degree 2。



![](img/ef70dc32dbfb60a76e750fe978587b8f_61.png)

While it's a third degree of polynomial。 So maybe to sort to be clear where we thoughts evolved right we started off with a global polynomial and we didn't like that because it was global right so because the if it at one end would be effective by points at the other end。

 So then we move to something which is more local piecewise constants。

 and they were local except they're not very smooth。

 So now you want something that's both smooth and local。 So that on the top left panel。

 we have something which is local， it's smooth in each panel， but it's not smooth at the knots。

 So now we sort of move towards a compromise where it's。



![](img/ef70dc32dbfb60a76e750fe978587b8f_63.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_64.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_65.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_66.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_67.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_68.png)

It's local， but it's also smooth throughout the whole range。



![](img/ef70dc32dbfb60a76e750fe978587b8f_70.png)

Thanks， thanks， sir。嗯。

![](img/ef70dc32dbfb60a76e750fe978587b8f_72.png)

And as I said， splines have the maximum amount of continuity。 By the way。

 it's believed that a cubic spline。

![](img/ef70dc32dbfb60a76e750fe978587b8f_74.png)

The this continuity， which exists in the third derivative， is not detectable by the human eye。

 and it certainly seems right for my eyes。

![](img/ef70dc32dbfb60a76e750fe978587b8f_76.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_77.png)

But I wouldn't trust my eyes。

![](img/ef70dc32dbfb60a76e750fe978587b8f_79.png)

Okay， so let's go into a bit more detail about these liness。

 so we'll first do linear liness and then we'll do cubic sps。



![](img/ef70dc32dbfb60a76e750fe978587b8f_81.png)

So in the linear spline with knots at psi k k equals 1 to capital k。

 so you can put down we've had one knot in these pictures， but you can put down multiple knots。



![](img/ef70dc32dbfb60a76e750fe978587b8f_83.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_84.png)

Is the definition is the piecewise linear polynomial continuous at each knot。



![](img/ef70dc32dbfb60a76e750fe978587b8f_86.png)

And just like with the in the previous cases， with the global polynomials and the。



![](img/ef70dc32dbfb60a76e750fe978587b8f_88.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_89.png)

The constant function， piecewise constant functions。 You can represent this as a。

 we call it a linear expansion in basis functions。 So transformations of the variables。



![](img/ef70dc32dbfb60a76e750fe978587b8f_91.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_92.png)

In this case， what you have is you have the variable itself。

 so one of these basis functions is just the variable itself。



![](img/ef70dc32dbfb60a76e750fe978587b8f_94.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_95.png)

And then you have a collection of these。

![](img/ef70dc32dbfb60a76e750fe978587b8f_97.png)

Trunncated functions， basis functions。 they call truncated power functions。

 but this one's to power 1。

![](img/ef70dc32dbfb60a76e750fe978587b8f_99.png)

And here it is， it's Xi minus CK positive part。

![](img/ef70dc32dbfb60a76e750fe978587b8f_101.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_102.png)

And what that means is described below you。

![](img/ef70dc32dbfb60a76e750fe978587b8f_104.png)

Is it's equal to X minus C K。 If X is bigger than C， K and it's 0 otherwise。

 So it's not allowed to go negative。

![](img/ef70dc32dbfb60a76e750fe978587b8f_106.png)

And so you make one of these functions at each of the knot。And。

These transformations and you throw them in as additional variables。



![](img/ef70dc32dbfb60a76e750fe978587b8f_108.png)

So to see how this works， let's look at a figure。So the blue curve is just a global linear function。



![](img/ef70dc32dbfb60a76e750fe978587b8f_110.png)

I。

![](img/ef70dc32dbfb60a76e750fe978587b8f_112.png)

We've only got one not here。 So here's one of these basis functions。 See。

 it starts off at0 at the knot， and then it goes up linearly。



![](img/ef70dc32dbfb60a76e750fe978587b8f_114.png)

So this is x minus 0。6 positive part。

![](img/ef70dc32dbfb60a76e750fe978587b8f_116.png)

Below 。6 at 0。

![](img/ef70dc32dbfb60a76e750fe978587b8f_118.png)

So now when you fit a linear model with a global linear function， plus one of these in。



![](img/ef70dc32dbfb60a76e750fe978587b8f_120.png)

And each of them gets a coefficient。

![](img/ef70dc32dbfb60a76e750fe978587b8f_122.png)

What you get is you get a function that's allowed to change its slope at the knot。



![](img/ef70dc32dbfb60a76e750fe978587b8f_124.png)

So if you add in some mix of this to a linear function， it'll。



![](img/ef70dc32dbfb60a76e750fe978587b8f_126.png)

Change the slope of this point。 And so here， we see it over year。Okay。

 and because this starts with at0， it makes sure it's continuous here。



![](img/ef70dc32dbfb60a76e750fe978587b8f_128.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_129.png)

They're very handy and you can make a bunch of these functions for however many knots you got。



![](img/ef70dc32dbfb60a76e750fe978587b8f_131.png)

Cubic explains。Very similar idea。 So， first of all， the definition， the cubic sp with not at C。

 K K going from one to capital K is a piecewise cubic polynomial with continuous derivatives up to order 2 at each knot。

 So that's the definition of a cubic sp。

![](img/ef70dc32dbfb60a76e750fe978587b8f_133.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_134.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_135.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_136.png)

Again， you can represent this as a basis expansion in the original variables。



![](img/ef70dc32dbfb60a76e750fe978587b8f_138.png)

In this case。You need x1， x1 sorry， X， x squared and x cubed。



![](img/ef70dc32dbfb60a76e750fe978587b8f_140.png)

So the a basis for cubic polynomials， of course， the constants always in the model。



![](img/ef70dc32dbfb60a76e750fe978587b8f_142.png)

Okay。And then you have similar。

![](img/ef70dc32dbfb60a76e750fe978587b8f_144.png)

Tncated power functions。 but now they race to the power 3。



![](img/ef70dc32dbfb60a76e750fe978587b8f_146.png)

One at each knot。this guy is defined to be Xi minus CK cubed if X is bigger than C and0 otherwise。



![](img/ef70dc32dbfb60a76e750fe978587b8f_148.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_149.png)

But the idea is the same。And here's the picture。 So now here's the little basis function。

 this truncated power basis function， and it's a little cubic polynomial that's zero at the knot。



![](img/ef70dc32dbfb60a76e750fe978587b8f_151.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_152.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_153.png)

In this figure over here， here's the global cubic polynomial， the blue1。 and years。



![](img/ef70dc32dbfb60a76e750fe978587b8f_155.png)

Added in some little linear combination of this orange guy。

 And that'll change the cubic part of the function in this region。



![](img/ef70dc32dbfb60a76e750fe978587b8f_157.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_158.png)

And a bit of a detail， this spaces function。

![](img/ef70dc32dbfb60a76e750fe978587b8f_160.png)

If you， if you check it out for yourself， you'll find out that it's。



![](img/ef70dc32dbfb60a76e750fe978587b8f_162.png)

It's0 at the knot。 It's also got zero first derivative and0 second derivative at the knot。



![](img/ef70dc32dbfb60a76e750fe978587b8f_164.png)

So when you add it in here， you don't change those derivatives of the function。

 and so it has the required continuity of a cubic plane。



![](img/ef70dc32dbfb60a76e750fe978587b8f_166.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_167.png)

It's a really handy representation。

![](img/ef70dc32dbfb60a76e750fe978587b8f_169.png)

Okay， so Cbic explains are used all over the place and you'll see we even got fancier versions。



![](img/ef70dc32dbfb60a76e750fe978587b8f_171.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_172.png)

One fancier version is very handy， and it's the one I tend to use all the time。

 it's called a natural cube explain。

![](img/ef70dc32dbfb60a76e750fe978587b8f_174.png)

If you had the choice of a cubic explain and a natural cubic explainer， which one would you use。



![](img/ef70dc32dbfb60a76e750fe978587b8f_176.png)

Natural like this。It's a good choice of names。

![](img/ef70dc32dbfb60a76e750fe978587b8f_178.png)

What a natural cubic sp is it's a cubic sp where you've added two extra at the boundaries。



![](img/ef70dc32dbfb60a76e750fe978587b8f_180.png)

And the constraints make the function extrapolate linearly beyond the boundary nodes。



![](img/ef70dc32dbfb60a76e750fe978587b8f_182.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_183.png)

And what that means is that。😊，The ends of the the function aren't just left unconstrained。

 We saw for a global cubic polynomial that the tail could wag quite a lot。 Well。

 we're not going to let that happen yet because we're going to make the function go off linearly beyond the range of the data。

 Okay， and so what that does is it it adds four constraints to on each end。



![](img/ef70dc32dbfb60a76e750fe978587b8f_185.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_186.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_187.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_188.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_189.png)

And that frees up four parameters。 So for the same number of degrees of freedom or parameters in your model。



![](img/ef70dc32dbfb60a76e750fe978587b8f_191.png)

You can， you can put extra knots in the middle and get more flexibility。



![](img/ef70dc32dbfb60a76e750fe978587b8f_193.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_194.png)

So in this figure， we've got a cubic sp and a natural cuic sp。



![](img/ef70dc32dbfb60a76e750fe978587b8f_196.png)

Now， you don't in the fitted function， you don't see much difference。

 You'll see the cubic explains a bit more weakly at this end over year。



![](img/ef70dc32dbfb60a76e750fe978587b8f_198.png)

The standard errors you see are much wider in places for the cubic spleline。

 especially at the boundary， which is where the the effect of the natural spleline is taking place。

 and the standard errors for the natural sple are better there。



![](img/ef70dc32dbfb60a76e750fe978587b8f_200.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_201.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_202.png)

I'm actually working on something called Or Cubic explains， which I can't give you details yet。

 but that bunch should catch on I think， especially here in California， especially in California。

Very good。

![](img/ef70dc32dbfb60a76e750fe978587b8f_204.png)

Okay， filling splines in R is easy， there's a function Bs。



![](img/ef70dc32dbfb60a76e750fe978587b8f_206.png)

Which takes a variable X and has some arguments。 You can give it the knots， for example。

 and or there's other ways of specifying the flexibility and it'll just do the work。

 you put that in a formula and you can put one of those for whichever function you want to be a nonlinear and it'll just do the work for you。

 Did you think of the name of that function。 I can see you don't like the name。 Now don't get rude。



![](img/ef70dc32dbfb60a76e750fe978587b8f_208.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_209.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_210.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_211.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_212.png)

And that's for cubic sps and for natural splinees， Ns。



![](img/ef70dc32dbfb60a76e750fe978587b8f_214.png)

And here we see a function of age， here's a natural cubic sp， you can see it's got three knots。

 interior knots， and it's a function of age and gives you a very nice fit。

 standard errorss are included。

![](img/ef70dc32dbfb60a76e750fe978587b8f_216.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_217.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_218.png)

Yeah， it's done for the logistic regression at the same time。And for this。

 you need to use the package splines。

![](img/ef70dc32dbfb60a76e750fe978587b8f_220.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_221.png)

Okay， so there's some details and one is not placement。



![](img/ef70dc32dbfb60a76e750fe978587b8f_223.png)

As in cannot placement。

![](img/ef70dc32dbfb60a76e750fe978587b8f_225.png)

So one strategy is to decide on the total number of knots， say capital K and then。



![](img/ef70dc32dbfb60a76e750fe978587b8f_227.png)

And then given that number， just place the knot at appropriate quantiles of the observed variable x。



![](img/ef70dc32dbfb60a76e750fe978587b8f_229.png)

Okay， so just to spread them out sort of uniformly。

 having roughly the same amount of data in each of the regions created by the knots。



![](img/ef70dc32dbfb60a76e750fe978587b8f_231.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_232.png)

And when you do that， that results in a certain number of parameters， so a cubic sp with K knots。

 turns out it's got K plus four parameters， or we call them degrees of freedom。



![](img/ef70dc32dbfb60a76e750fe978587b8f_234.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_235.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_236.png)

And as I mentioned before， if you use a natural slime with K knots。



![](img/ef70dc32dbfb60a76e750fe978587b8f_238.png)

It only has K degrees of freedom， because you get back two degrees of freedom for the two constraints on each of the boundaries。



![](img/ef70dc32dbfb60a76e750fe978587b8f_240.png)

And so in this figure over year， we've grown a little extreme。



![](img/ef70dc32dbfb60a76e750fe978587b8f_242.png)

We show comparison of a degree 14 polynomial and a natural cubic sp。



![](img/ef70dc32dbfb60a76e750fe978587b8f_244.png)

The net the natural cubic spine will have。

![](img/ef70dc32dbfb60a76e750fe978587b8f_246.png)

嗯。It will， will have also 14 knots。 Turns out there's 15 degrees of freedom because the constant， we。

 we not count in the constants in in these specifications over。



![](img/ef70dc32dbfb60a76e750fe978587b8f_248.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_249.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_250.png)

And and so yeah we see them the natural cubic plane is much smoother than the very wgggly polynomial。

 okay and you can see the tail of this polynomial going crazy。



![](img/ef70dc32dbfb60a76e750fe978587b8f_252.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_253.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_254.png)

So generally， I think the takeaway message is， although polynomials are easy to think of。

 Splines are are much better behaved and more local。 And so they are the way to go。

 And since they' so easy to work with。

![](img/ef70dc32dbfb60a76e750fe978587b8f_256.png)

![](img/ef70dc32dbfb60a76e750fe978587b8f_257.png)