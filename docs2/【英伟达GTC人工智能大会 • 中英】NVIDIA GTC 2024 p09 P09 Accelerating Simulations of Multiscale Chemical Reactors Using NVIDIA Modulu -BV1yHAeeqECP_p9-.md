# 【英伟达GTC人工智能大会 • 中英】NVIDIA GTC 2024 p09 P09 Accelerating Simulations of Multiscale Chemical Reactors Using NVIDIA Modulu -BV1yHAeeqECP_p9-

![](img/3aa4c14aac3456673fd5b3bc445e7d0b_0.png)

![](img/3aa4c14aac3456673fd5b3bc445e7d0b_1.png)

Hi， welcome to the session on acceleratingating simulations of multiface chemical reactors using N media models。

 I am a youth partner working as a scientific machine learning researcher in my current role and an HPC researcher in my past wallet shellll。

 I'll be kicking off this presentation on behalf of my team as listed out on the slide with Herschel antimophy。

😊，This work is a result of a collaboration between shell and soft serve。

 and the motivation for this work comes from a shell process called gas to liquids。

 which will become clearer by the end of my part in setting the context of this presentation。

Before we step into the details of this talk， I must flash an obligatory but just long cautionary note。

 which in summary says that please don't take any financial decisions around investing in Shell based on what you are going to hear from us in this talk。

Let's begin with some bird's eye O view of pins pins or physics informed neural networks can be said to lie at the intersection of three areas that is physics。

 data and artificial neural networks or art ANN。Physics is related to the conventional simulation in which we solve equations known from some first principles theory。

 the second circle represents data that is used in order to capture some complex interrelationships in situations when the underlying equations are not known or to incorporate real field data coming from sensors。

 and last but not the least pins benefit from theory behind artificial neural networks which can interpolate the available data in order to predict the target variables while minimizing of physics+ data driven loss function。

The system hence provides an alternative theory for physics based simulations。

 which are based on conventional numerical methods that are iterative in nature and computationally expensive。

 in summary the key value proposition of pins is that they are trained in such a way that allows them to avoid making senseless predictions which is in contrast to a traditional machine learning method。

Now let's look at the process that is behind the motivation for this project with the help of the value chain of a modern energy system。

The gas to liquid conversion or GTL for short takes an important place in the value chain of a modern hydrocarbon production。

Specifically， these GTL capabilities allow leveraging carbon sources。

 which are different from raw oil to synthesize hydrocarbons that can be used as fuels or other commodities。

 This is especially relevant in making fuels compliant with net emission strategy because apart from the natural gas as an initial source of carbon。

 the same GTL process can operate on carbon captured from air， biogas or waste etc ce。

 Shell is a market in GTL with its first commercial plant that came in operation in Bentuulu in 1993。

 and a state of the R GTL plant called pearl currently in operation at Qatar。一。

In practice carbon containing materials are first preproces to convert them into the so called syn gas。

 which is in fact a mixture of carbon monoide and hydrogen molecules。When this stage is done。

 the key stage for today's presentation comes into play， which is the socal fiser to process。

 which is a sequence of chemical transformations undergoing inside a chemical reactor。

 which we could be considering in a little bit more detail in a couple of moments in these chemical transformation。

 synm gas gets converted into synthetic hydrocarbons which can be liquid fuels or wax。

 These products themselves are sometimes pro process using another catalytic process called hydrocracking and isomomerization to create some other chemical products suitable for consumption as petrochemical feedstock or downstream processing。

From the previous slide， it is evident that the key stage in the synthesis of GTL products is the fisherrops reactor。

 It is a relatively complex piece of industrial chemical equipment。

 and several different theories need to be leveraged to simulated performance characteristics。

 we can conveniently classify them according to the scales at which the simulation occurs and such scales are encapsulated one into the another。

 At the largest scale， this is the scale of the entire chemical plant。

 the ultimate goal of the modeling would be to build a digital twin。

 a physically accurate digital twin would require considering all the processes at different length and time scales occurring inside the reactor。

 as well as in the neighboring units。 If you look at the schematic of the reactor。

 the mixture of carbon monoide and hydrogen pump through several tubes filled with cataltic material leading to the chemical transformation of syn gas into hydrocarbons。

 These hydrocarbons along with unutilized reactants and products leave the reactor through a dedicated。

Yet another system is used to supply the cooling water that is needed to control the temperature within the reactor because of the heat generated during the chemical transformation of the syn gas。

The heat needs to be removed to maintain a somewhat constant temperature of the reactor that leads to high yield and selectivity of the catalyst from a mathematical point of view。

 if one has to must simulate such a complex system。

 multi physicss and multiscale modeling is needed multi physicssics because one would need to solve for transport equations for flow heat transfer and mass transfer through porous media and multiscale because transport equations at the macroscopic scale of reactors or single tubes need information about the transport characteristics of individual pellets which。

In turn requires good mathematical model for the chemical transformation that happens at the catalyst surface。

 these theories describing each of the scales are in essence， encapsulated into one another。

In other words， we would need to simulate the finer scale first in order to simulate the next one。

 as you can see in this illustration the reactor model relies on a flow model that occurs within a tube which then relies on a pellet model for modeling the physics happening at the lens scale of a pellet。

The pellet model then relies on a microkinetic model which presents a mathematical formulation of the surface level reaction kinetics of all participating species relying on a very detailed reaction mechanism founded on molecular theories。

In this particular presentation， we would be focusing on the first two scales on the right that is the kinetic model and the pellet model。

 we will be describing the kinetic model first followed by the pellet model。

 and since the key value proposition for the use of pins the speed speed up to solve such problems。

 we would quantify the speed up and accuracy and compare them against。

Conventional ways of solving such models。I would now hand over the presentation to my colleague Herschel to take you through the description of the kinetic model。

Thanks Andrew for setting the stage Hi everyone I'm Herschel Patel。

 I'm working as scientific machine learning researcher at Technologyn Center Bangalore and I'm here to describe more about microkinetics model for GTL reactor what is microkinetic model let's start with that simply speaking microkinetic model is basically set of governing equations which describes how fast is a reactants are going to be converted into products and which products s do you expect out of that reaction for GTL reactor the primary reactions which are happening are listed at the right hand of the screen holistically it is called fissuretro synthesis model and if you want to know more details about it you can refer to the paper described on the screen essentially for GTL reactor hydrogen and carbon monoxide is is the reactants and after all the intermediateent reaction。

What you expect as a final product are chain of allkes and alkenes different length chains now let's try to understand where these reactions are happening so on the left top of your screen a picture of cataltic palate is shown now this is a poorrous substance with a loss of porosity in build。

On this catalytic palette the catalyst is deposited and on this deposited catalyst the reaction happens Now reactants come and gets gets deposited on this specific catalytic surface and then reaction happens Now for the reaction to happen the most important thing it it should find an empty space on the catalytic pallet and thats when the reaction will start and this is the most important criteria of the of any reaction which is fraction of vacant side let's move to the next slide where it it will be more apparent。

As I was described on the previous slide， the most important factor for reaction to happen is fraction of vac catalytic sites theynoted as s and for thresholdov synthesis。

 another important thing is chain growth probabilities since we are dealing with a range of alkes and alkes with different carbon length。

So if if you simplify the set of equations which were described on the previous slide you end up with the system which is described on this slide。

 this system is algebra coupled nonlinearar system of equations where total there are n plus one equations where any number of carbon atoms that you want to model if you say I want to model total 100 carbon atom you will end up with 1001 equations out of that total 100 equations will be denoted for chain growth probabilities and coupling with that you will have one equation for fraction of vac kaltic side now the aim of this system is to find out sn alphas and the givens of this system are the concentrations slash partial pressures of carbon monoxide hydrogen and H2O and of course the temperature at with the reaction is happening if see。

This system holistically， this is root solving or root finding a problem。

Traditionally you use let's say s pi aol kind of solvers to arrive at a root of this system it takes around 01 second on single core CPU the problem with that is this process of finding root has to be repeated multiple times and this number the time becomes prohibitively big for it to be used for actual multi multiscale modeling so the aim of developing pins for this model as a surrogate is to is to basically twofold we accelerate to we accelerate this root finding method by orders of magnitude while basically maintaining the same accuracy so we use NviD modulus for training this spin and and we get to know more about how the。

Training of pins happen in the next slide。Now let's try to understand the difference between data driven training and physics informed training in case of data driven training。

 you have a fixed data with features and labels， you pass the features from the neural network you predict the output and you compare that output with the true values and the difference between predicted and true values becomes your loss function for training that neural network as compared to that the physics informed training。

 you don't have any fixed data， you take random sampling from the parameter space in case of microkinetic model your parameters are the inputs of the model which are concentrations slash parsa pressure of CO H2 H2 and the temperature of the system Now using this random samples you pass those random samples from the neural network and you basically try to predict the fraction of vacant cataltic site that will be your as predicted Now you already have a model which describes how this S behaves with respect to the input。

Using that model you define the difference between the predicted s and the s which is given by the model and using that difference you actually train this neural network and this is how you infuse the physics inside your neural network and that becomes the surrogate for you to do the exact work that your system of equations we're doing at very fast rate and almost at the same accuracy。

Let's try to assess the performance of Spin model on accuracy and speedup on accuracy front the table describes the relative percentage error with respect to the ground truth obtained 10 using the conventional methods for the con of interest in fier of microkinetics as you can see we are at 0。

1% median relative error and this all things are in percentage so this is an absolutely amazing accuracy to have at the speedups that we are getting so as I mentioned in my previous slides if you use the traditional spi aold solver on single core CPU it takes around 0。

1 second for a single solution if you use the Spin model on the same CPU you will basically get the speedup of around 10ness to 3 as you increase the bath size now cherrry on the cake if you use NviDdia v00 GP you could achieve the speed up of210 to5hi now this is。

Amazing speedup to have at 0。1% median relative error。

Now let's try to understand one use case of pin pin for optimizing the reaction conditions。

 so let's assume you have a train spin model available and this spin model will give you the reaction rates of alkene and alkes given the input conditions of temperatures and pressures now if you have let's say certain yield profile in your mind and this yield profile may may be a result of certain economic conditions or supply demand shocks etc what you can do is you can run an optimizer on top of pin and this optimizer will basically find out the input conditions specifically temperatures and pressures to reduce the difference between the between the desired yield profile and the yield profile given by the fiser drops synthesis process now in this process the whole idea is that the pin。

Itself will give you the gradients which are essential for the optimizationr to do fast optimization and this is the byproduct of having a pin as a surrogate now my collea Timmoophile basically take this conversionation forward for diffusion pin。

😊，Thank you， Hersll。 I am Dimainni Colanca， and I work as a researcher at R& D Department of Soft Surf。

In this final part of our presentation， I'd like to cover the next scale for which we also developed one more physics for neural network。

 Its objective is to simulate the performance of an entire cat palette and to provide the quantities。

 which would be necessary for building the full scale model of the reactor。As we have already seen。

 the previously introduced SPNN has already been shown to be usable as a replacement of a conventional algebraic equation solver at the most microscopic or mikinetic scale。

Generally， we could， of course， now just use that already trained neural network to speed up the evaluation of the source term in the diffusion and heat transfer equations。

 However， we went even further and train the second physics informed neural network。

 We call it DPnN for short with letter D denoting diffusion， which is the key transport process here。

 The aim of DPnN is to output the entire curves representing the radial distributions of temperature and substances concentrations in the pallet。

The inputs for that prediction are just the reaction conditions at the outer surface of the p。

Let's see why having this additional PNN is useful。

When its prediction is done so that the concentration and temperature across all the points inside of the pellletets are known。

 we can just put them into the previously trained aspenN and find the fraction of wakeant catalytical sites at all the points。

When these quantities are combined with the complete temperature and concentration profiles in the pellet。

 we can finally compute the reaction rates for all of the fish drops products。

And by summing up these old rates， that is by integrating them across the pate volume。

 we thus find the overall production rates for the synthesized hydrocarbons and also the overall rates at which the entire palate consumes the reactants。

And all of that can be computed efficiently with the conditions at the surface of the pt as the only needed input。

Of course， this entire workflow starting from the boundary conditions and yielding the blood performance can equally well be used to simulate how the density of chemical transformation rates occurring at each point of the reactor tube would depend on the corresponding local concentrations of substances。

And this is exactly what is needed to close the fundamental equations of the reor model from here and to come up with the full scale reactor model。

 This is， by the way， a good opportunity to contrast our approach to the so-called empirical source terms approach used in many existing reactor models。

 These empirical approach actually aims at approximating the same relationships as in our case。

 but it achieves this by using the heavily parameterized empirical formulas in which the caffians are usually found just by fading to experimental data。

😊，In contrast to that， what our theory based groundup modeling does。

 it provides the overalls based on microscopic models with clear chemical interpretation and not by empirical feeling。

At the same time， while using chemical justified workflows by using the neural networks as the core component of our model。

 we still keep relatively low computational cost。 This cost is just slightly higher than with the empirical relationships。

Now， because some aspects of this plet scale model based of PnNs is still our work in progress。

 we share here only the key results and don't go into much details of its implementation。

 Let's just focus on the performance characteristics。 Naly。

 we see here the box plots showing relative errors in the cumulative formation rates for the hydrocarbons synthesized in the pate。

 These plots are for elephantphs and pphs， which are the two types of these hydrocarbons。

We also show here relative errors for the rates that whichidge belt consumes the reactants。

 and finally the relative errors for temperature profile of the palellet。

 we see that all these errors are generally smaller than 2 percent。

 which makes them perfectly suitable for further use in the reaction models。The last but not least。

 among the benefits brought by using physics and foreign neural networks as a computational tool in cataly pallet modeling。

 there is a speedup achieved by this model in comparison to the conventional equation solver。

 specifically， we compared here the runtime needed to obtain the solution of the diffusion and heat transfer equations on a single CPU core when using PNs or the conventional solver。

As we see here， the PNN based approach as such allows almost three orders of magnitude speed up。

In both cases， the source terms in all the equations were already speeded up by SNN。

 so in the absolute values， all running times shown here are already much smaller than in the scenario when physics informed neural networks were not used at all。

If GPUs are used as the hardware to run PNNs for plet modeling， their speedup grows even higher。

Here we've got orders of magnitude speed up on top of the previous one this way showcasing the ease of parallelizing the PNNs computations。

 which would not be as easy in case of conventional numerical methods。

Let's now conclude our presentation by summarizing some key findings which we have made in this research。

Mainly we have demonstrated that physics informed neural networks approach is suitableable for theorybased multiscale groundup modeling of the processes occurring in chemical reactors。

 we have demonstrated it for both microscopic scale where we have trained physics informed neural network to approximate the solutions of microkinetics equations and further demonstrated this at the scale of the catalytic palate。

 where this approach can be found capable of quickly providing the overall pelleate consumption rates for reactants at given conditions on the pellelet surface。

We further believe that both models represented here can be useful for creating the models of chemical reactors as a whole and probably even at some larger scales as well。

We know thank you for your kind attention to our work and we are open to answering your questions not only in the live chat。

 but also if you reach out to us by emails， Thank you。



![](img/3aa4c14aac3456673fd5b3bc445e7d0b_3.png)

![](img/3aa4c14aac3456673fd5b3bc445e7d0b_4.png)

![](img/3aa4c14aac3456673fd5b3bc445e7d0b_5.png)