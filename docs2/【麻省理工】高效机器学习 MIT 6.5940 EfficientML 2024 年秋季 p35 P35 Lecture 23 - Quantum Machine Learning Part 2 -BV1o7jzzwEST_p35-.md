# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p35 P35 Lecture 23 - Quantum Machine Learning Part 2 -BV1o7jzzwEST_p35-

So today we are going to continue our lecture on the quantum machine learning and this is the part two。

 and in part one， we actually introduce on basics of the quantum computing， how the qubbits works。

 how we can implement different kinds of thequbits and also what are the basic gates and how to implement a very basic quantum classifier and also what is the status of the current quantum computing。

 for example， the noisy intermediate scale， the N era。

 and also how to perform some of the compilation on those N devices。And today。

 we' are going to further to introduce more details of the quantum learning。Specifically。

 we are going to introduce a parameterized quantum circuit or called P QC and also how to train those P QCs to finish some of the specific tasks like the quantum class classification and also how to perform noise aware training to improve the robustness and also reliability of the quantum parameterized quantum circuit。

And also we are going to introduce the library which is a Toch quantum library developer and my team to perform those quantum learning tasks。

 and finally we're going to introduce four different kinds of the architecture we can use。

 how can we choose the one with the highest reliability to do those quantum learning tasks。Okay。

 so for the first section， we are going to introduce some of basic this testonomy of the Pl approaches。

 So， we can have two dimensions。 One is the types of algorithm right so we can have a quantum algorithm or classical algorithm and also we have type of data。

 classical data or quantum data。 So in that case， we can separate this whole landscape into four regions。

 and on the top left corner that is the classical data classical algorithm and we already learn a lot of a lot of those different types of the classical efficient algorithms for classical in the previous lectures。

 and also we have those classical data， quantum algorithm。

 So that's how how we can use the power of quantum computing to process the classical inputs such as the images。

 and that's what we are going to introduce in this lecture。 and also for others。

 those quantum data classical algorithm。 Those are typically referring to how to perform the control of the quantum devices like how to。

Send different control signals to the qubits， how to do the calibration and also how to read out。

 And finally， we also have this quantum data quantum algorithm that means you can also process some of the quantum information。

 For example， we can use the qubs as a sensor right to sense some of the environment and then you want to decode what is the information we can get from the quantum quantum sensor quantum  cubits sensing。

 and then in that case we can use also quantum algorithm to process the quantum information。

 but in this lecture， we are mainly focusing on how to process the classical information classical data with the quantum algorithms。

 which is the the second line of the taxonomy。Alright， so first of all。

 we want to understand the concept of the parameterized quantum circuit。 So in the last lecture。

 we introduced in the quantum circuit， basically we have multiple stages we want to initialize the qubits and also then apply in different gates。

 And finally， we can do the measurement to obtain this classical outcome from the quantum quantum information qubits。

 So here is an example for the quantum circuit parameterized quantum circuit。

 we can see some of them has this yellow color， which contains those those parameters parameters or tunable values。

 So that means， for example， this Rx theta gate。 you actually can configure the rotation angle of this gate。

 And for different rotation angles， the actual effect of the gate will be also different。

And for other ones in the gray color， such as the C gate or the X gate or the H gate here。

 So those are the fixed gate。 So that means those are basically the ones that is performing the fixed fixed operation。

 So just like in the in the classical， we had multiple layers， right。

 Some of layers such as the convolution or the multi perception layers。 they have the ways to tune。

 However， they are also some down sampling layer， like the maxpoing or some other flatten layers。

 though they don't have any of the parameters to tune。

So one thing that we are carrying about this the property of the quantum circuit is the expressiveness or the expressivity。

 So we want to understand how expressive is the quantum circuit to represent arbitrary states。

 how the circuit can cover the hub space right So here actually the extent to which the states can generated from the circuit debate from the uniform distribution can be characterized as the expressivity expressivity of the quantum circuit。

 So here we can see two examples one is on the left。 The quantum circuit A。

 which has firstly a hammer gate and and also the rotation Z gate。 And on the right hand side。

 we have another circuit， which have one more operation or one more one more parameter。

 So we can firstly rotate on the Z basis with this R Z gate。 And then after that。

 we also apply R gate with the。Pter here。 So it is very intuitive that if we have more parametersers。

 right， for example， on the Russian side， we have a larger expressivity。

 which means we can represent more state in the in the whole hub space。

So how exactly can we visualize this， right？ So here on the top side。

 we can see the3 A when we actually changing the theta values here。

 we can see the coverage of the block sphere on the top right corner here is's actually a ring on the tropical here。

 And then for the circuit B here。 we we actually can have a more larger coverage of the whole space。

 because after we have a different combination， different random assignment of those theta and five values。

 we can have a coverage of the overall space。 So it's not just limited to a ring of this of this blocks sphere。

 So in that case， we can understand actually visually oriently the circuit B here has a better representation power compared to the3 A。

So in other words， actually， we can have a more rigorous definition of this expressivity。

 So here we have more examples。 The first one we have the idle circuit。

 which does nothing and also we have circuit A B to the arbitrary unitary rotation。

 So if here we actually we want to compare we want to understand what is the coverage of this whole space with this given quantum circuit。

 So here we are actually comparing the the circuit to some of the arbitrary state。

 which is called higher measure。 So here on the bottom side。

 the higher measure is actually measuring that for it's a uniform distribution。

 So that means for two arbitrary state in the hubber space。

 What would be the difference between those two states right So for example。

 we can do a sampling and then we can sample many different pairs in the whole space。

 and then we compute what is the difference between those two。 it can be a compute as the infidelity。

Between the two states， right in that case， we can imagine for a single qubits。

 that's actually uniform， right So because we can sample two states which are very close to each other。

 We can also sample two states are very far from from each other。

 So the distribution of that is actually arbitrary。

 And also if we want to evaluate the expressivity of a given circuit。

 And then the way we do that is that we can sample randomly sampled many different pairs that can be represent by the circuit。

 So specifically in order to do that， we can sample two different values of the Rz gate and then compute the fidelity of that。

 So in that case， we can also have another distribution shown in the in the yellow yellow distribution here。

 So in that case， we want to compare what is the K dirgs between this yellow distribution to the uniform distribution。

 You can imagine that if we have just idle circuit。

 And then no matter what we sample we always get the same state。

 and then the fidelity of that will be always one。 So in that case， theres。

A very large value or large probability in the first figure here。That we have 100% of one fiity here。

 and then in decades if we compute the divergence of this distribution to the higher measure。

 and then the value will be extremely large。And then if we have the arbitrary image here。

 and then if we just compute the distribution of this uniform sampled two space。

 and then we can know the fidelity of that can be very close to the uniform distribution。

 And then the c dirgence of this distribution to the uniform distribution。

 the higher measure will be very low。 So in that case， you can imagine the lower dec dirgence here。

 That means the higher the expresssivity of the quantum circuit。So besides this expressivity。

 we also want to understand what is the entanling capacity of the circuit。 So we want to know， like。

 say， given this circuit， whether we can entangle the states of two qubits。

 So here we can use a Vock performance measure to tell us or called the MW measure。

 So for the MW measure actually have a rank of0 to1。

 And if for an entangled state and then we can compute the MW measure at 0 and for for two four entangled state of two qubits。

 and then the MW measure would be one so。In that case。

 we can actually use an average NW measure to measure this entanling capacity capability of the quantum circuit。

So here we can firstly have a look at the many different kinds of the quantum of circuit structure。

 so for example the circuit one here we only have both gates on the each of the individual qubits right so there's no quantum of gaze between the two bits at all so in that case there is no entangling between any of the qubits because if you don't do any gates between the qubits how you can entangle those twos right。

So we can also see the Q circuit2 here， we have many of the syn gates between the QB4 to third。

 QB3 and QB3 to QB4， QB2 and also QB2 to QB1。RightAnd also we also have other circuit with the different structures so for other circuit we can always see that there are some integral in power between thequs。

 which means you can do the perform you can do this entangled state preparation using this quantum circuit。

So there are more circuits that can be constructed with different structures here。

So here we can actually leverage this MW measure to have a visualized plot of this enling capacity of of all the quantum circuit。

So here we have different colors first。 So different colors means that how many layers you can apply this block。

 For example， you can just apply a single block here。

 or you can apply multiple copies of the block to prepare those those entangled states right So first of all。

 we can see that for the circuit I1 on the left andmost corner。

 we can see that no matter how many layers you are you are using this quantum circuit。

 you are always not able to perform this entgling operation between the qubits，2 qubits。

 any of the twoqubits because there is no gate between any of the qubits here。

And also we can see another one is the quantum circuit 9 on the rightmost of the axis。

 So here we can see that actually， when we have a reasonable number of layers here。

 the entangling capacity of this kind circuit is very large because we actually have a lot of engling gate between those cur pairs。

 and then we can create an entangled states between other qus。Alright。

 so besides this en capacity so intuitive here， we actually want to have some quantum circuit that can have a large en in power because remember in the first lecture。

 we introduced that we want to encode actually a large space of data to the qubbits so only if we have a large en power between the qubits。

 we can leverage this large exponential hubber space if we're not able to entangle them together and then we cannot encode a large number of data all of qubits altogether。

So besides this expresssivity and also the enling capacity， we also have another measure。

 which is the hardware efficiency。 So in the last lecture， we introduce that this question。

So on Tuesday39。layerer one。不异。提嗰。月份给。Yeah， that's a great question。

 So here we can see that one interesting observation that actually with a very small number of layers here。

1，2 or three。 and then the enling power here is already one。

 So I think the value here is because of the randomness when we actually compute is under measure。

 So the larger the larger the number of copies of the layers。

 we have to sample more circuit to compute this measure。 So if we are not able to sample enough。

 that actually number is increasing。 So but short answer is that for the entanling capacity it is using one or two or three layers is large enough。

 but for the expressivity is always better to have more parameters to learn。Okay， great question。

Alright， so for the another aspect is the higher efficiency。

 So basically whether we want to implement those quantum circuit on the actual device。

 so we can see that for example， if we have five qubits with this topology。

 and then we also need to consider what is the architecture of a quantum circuit。

 whether we can perform those operations natively on those quantum gate quantum quantum circuit or quantum device。

 So the first question is whether the PqC design， consider the qubic connectivity。 For example。

 in the previous1， we can see that there is connect their connections between the neighboring qubits 0 to 11 to 2 and 2 to3。

 So in that case， we'd better to place those different qubits on the P0 P2 P and P1。

RightSo that case at least two of the gates can be directly compute。And also。

 we also need to consider whether the gates are native gates， right So for example here。

 the gates are the C gate， the control Z rotation gate。

 So in that case we also need to see what is the actually supported operation on the actual quantum device if the operation is not directly supported and then we have to perform a lot of transformation of the gate to decompose those on the circuit to the native operations and then decomposition process we will introduce also a lot of the overhead。

So those are the several aspects we have to consider when we actually construct those quantum circuit and。

 and for the encoding part， we also have multiple ways to encode the data to the quantum circuit。

 for example， consider。The classical data X which consist consisting of the M samples and each of them has n features So in that case。

 we need to encode each of the value or each of the vector to the quantum circuit to do the to do the processing with the encoding module。

 So there are multiple ways of encoding ways of encoding those different information to the cubits。

 So for example， we are going to introduce four different encoding methods。

 So the first one is called the basis encoding。 So that is very similar to the binary representation in the classical machines right So for example。

 if we have just one value number two， and then we have the binary representation of this value in the in the10。

 and then we can create a quantum state just representing this10 state。

 we have all the energy on the10 state。 However， it is not very efficient because we can only encode one data。

 say if the x here is is two。And then we have one0， but if the value is zero here。

 and then we just have all of the energy for this00 state。 and if the value here is three。

 we have to encode all information or all the energy to the one Wednesday state。So。

This is not very efficient for only one data point。 But if we have multiple data simultaneously。

 for example， we have the data set contains multiple values。 For example。

 a vector of two with a value 0 and also wave3。 And in that case。

 we actually can encode those data simultaneously because we are able to represent a multiple multiple values with a limited number of qubits。

 For example， here， we can create an entangle state， the 0，0 plus 1。

1 using the quantum circuit we introduced in the last lecture， Basically。

 we have the hand gate and also a syn gate。 And then we can create ent state between the0 state and also the 11 state。

And also， if we have multiple values further， we have 0，1 and3。

 We can also use a vector to have enough to have the same energy on all the all of the basically L of the sectors here from the 0。

0 to01 to the 11。So we also have other encoding， which is the amplitude encoding。

 So basically using this amplitude encoding is very straightforward。

 So we just want to encode this input vector to the state vector of the qubits right， So for example。

 if we have this input vector as 1000。 So this is the input vector。

 and then we know that with two qubits， we can actually create this vector with the length of four right So in that case。

 we can have a just the first vector， all of the energy will be on the first qubits。 In that case。

 we can create this 10，0 state。So。If we have another vector， which is the 00。80。20。6 and 0。4 45 here。

 we can also allocate energy of different states here to represent the ratio between different inputs。

 and then we can recover this input vector through the states of this quantum circuit。

 So in that case for n features， you can imagine that we only need a log two of n of the qubits because we are able to create a vector of two power of n with n qubits。

 So this is a very efficient encoding method。Yeah快损。Re。That's yeah that's a great question。

 So actually we required input the the length to be one。 So the overall the length for example。

 the norm two of each value squared and then something together， which we have one。 in that case。

 typically what we did is to do a normalization first， and then we have a normalizing factor。

 and then we can encode the remaining information to the  Qbits。

 So in that case we have to store the normalizing factor in a classical device。O。

For another one is the amplitude encoding another example here。 So basically， we can。

We have two values， and then similar to the previous one， we can configure them together。

 and then we can use this quantum circuit below to represent state。

 So the reason why I'm showing this quantum circuit is that although we are thinking that we have a large space to encode data。

 actually the actual encoding process is not very trie。

 So basically we have to construct a very complicated quantum circuit to prepare the quantum state from the all0 state。

 because initially all the quantum all the Qs will be initial to all0 state。

 And then that means the vector will be 1，0，0，0。 and how can you prepare this arbitrary state from this 10。

0 state， that is a large problem because we have to have a large number of gates in the middle to prepare the state that we want。

 For example， even if we want to just encode those four numbers。

 and then we can use we have to use a large number of gates to represent the state。Alright。

 so another one is called angle encoding。 so basically， we can encode。

Different data in the rotation angles of the QB gates。

 So here is an example on on the bottom right corner。 So basically if we have values。

 different values of the input data。 And then we can we can encode those values to the rotation angle of the gates。

 For example， we have this R gate for on each of the  Qbits。

 And then if the input vector is this0 pi over2 and pi。 in that case。

 we can just directly encode those values to the rotation angle of the QB0 and QB1 and  QB2。

 So in that case， this one， this way is very efficient because we don't have to perform any of the compilation process to to construct those communication circuit to do the state preparation。

 we can just directly input those values to the rotation angles of those gate。

And also there are also several other ways to encode data。

 So one way is called the arbitrary encoding。 So basically you can construct the combinations of those different previous encoding method。

 and then for example， we can firstly have these two layers of the rotation gate。

 and then we can perform some entanglements between the qubit using those signal gates。 and finally。

 we can use another layer of the several gates of the entangle gates to encode another remaining values in the classical vector。

 So that case， we can see that four this vector with in total 12 values。

 we can use those rotation angles on the bottom to perform this encoding of those input input data。

So after we have those encoding process， we need to perform the training of the primary quantum circuit。

 So basically the intuitive way to understand the previous encoding data is that for example。

 you have this in the classical we want to perform this image classification and then the first step will be performing some of the say denoing or some of the down sampling of a very large input image and and right after that you can apply those different layers of the trainable trainable different layers like col or some other layers to the input input image So just like here in the quantum device。

 the first step is to perform some preprocessing to encode the classical data to the Qs and then after that you can apply in different kinds of the parameterized quantum circuit to transform the input state to some of the target state to perform the classification or some other task。

So typically， the primary surgery training， they also use this data driven method。

 So basically we have a lot of parameters in in the trainable layer。

 and then we want to do this interpretative parameter updates according to to the objective function So basically we have this iterative loop。

 So we have some parameters initially， and then we can firstly compute。

 What is the objective function。 What is the cost function。 for example， for the classification cut。

 we can still use the cross thattropy loss， and then we can do the back propagation or some other optimizer to optimize those values to minimize this overall cost function。

So one way to do that is it's a fine different differentiated method。

 so basically we can just use this very， we can just have a small preturbation of input data values。

 and then we can compute the local derivative of those of that point。

 and then we can use this gradient to update the parameters。

So the accuracy actually really depends on what is the site how large is epsilon。

 because if you have a very large epsilon here and then the derivative of your computing is actually very different from the actual gradient。

 So for example， here， for the epsilon here very large to the very large epsilon here。

 and then the actual gradient to your computing is very different from the the gradient your computing is actually very different from the true gradient。

 So in that case， the problem of the final difference methods that you have to carefully it's like the epsilon value to compute gradients。

So in order to overcome this drawback， we also have another way to compute the analytical gradients for each of the quantum gates in the quantum circuit。

 So that is actually called the parameter shift rule。 So in the parameter shift rule。

 here is actually the overall overview of the parameter shift。

 So basically we have those different layers different gate in the quantum circuit。

 The way to compute the partial the gradients of this the loss function to this to this rotation angle or to this value is that you can add pi over2 to this value。

 And then actually the quantum circuit again， to compute the final loss function。

 And then you can this you can subject this。Howeverover two value from the original theta。

 And then you compute value again。 So the final gradients will be the same as the will be the true gradients or the true analytical gradients。

 So here we are going to do that expanded step by step。 So basically。

 we want to compute the gradient of theta here with regard to the F theta。 right。

 So the F theta here is actually the measurement outcome of this this qus， the first qus。

So we want to understand what is the gradient of partial F theta here over partial theta。

So in order to do that， we can shift the theta twice， right， So firstly。

 we can add pi over 2 to the theta， and then we can compute the function again。

 which is E F theta plus pi over 2。And then we can also shift the theta to another direction by pi over two。

 which is theta theta minus pi over2。 And then the actual gradient of those partial f theta over partial theta can be directly computed as F theta plus pi over2 subject F theta minus pi over two over2。

 So why is that the case。 So that seems to be not very intuitive， right， So。So， actually。

I'm listing the actual the proof of this process here in the slides。

 but I'm not going to show all the details of those process。

 So one very intuitive way to understand that is that for example。

 if we have we want to compute what is the gradient of the cosine function right So we know that if we compute the derivative of cosine。

 And then the function will be aine sine function right So that would be cosine theta plus over pi over2 So actually。

 when you shift the cosine function， this periodic function by pi over 2。

 that is actually align with the derivative function of this original function。

 So that's the intuitive understanding of how we can just shift the original value by pi over2 to compute gradients for this angle。

 Because as long as we are using those rotation angles because of the mathematical representation of those values。

 those cosine for example， if we are doing this rotation x and then we can always。

We can always distribute the decomposition for convert to the exponential representation。

 and then we can know that the base element of them is actually the cosine and sine functions。

 so that's why we can directly use those parameter shift rules to compute analytical gradients inside of the actual inside of the estimated gradients。

Okay， so basically we another way to do the gradienting computations is， of course， the back propag。

 which we are very familiar familiar with in the classical differently。

 So we can we can compute using the chain using the chain rule。

 we can compute gradients for each parameter on the whole computing path。

 So here actually we are we are doing some equipment to show that actually the using the back propag。

 we are of course getting the analytical gradients of those values。

 And then we can also verify whether our parameter shift rule Comp gradients align with the back propag。

 So here basically we can see there are there are two plot here。

 and on the top one here is actually showing two different two different。Greds here。

 So one is in the in the blue， which is the gradient computed by the by propagation。

 And also for another one is using the printer shift rule。

 So we can basically see that all of them are aligned to each other。

 So that means using the printer shift can can always give us the same result with the black propagation and which are the analytical gradients of the value。

So however， the bad propvocation， as you know， we have to understand， what is the。

We have to have the whole computing graph so we can do that on the classical classical device。

 so we can compute the first layer。 we know all the intermediate results。

 and then we can do the back propagation。 However， if we are computing that on the actual quantum quantum device。

 we cannot obtain the intermediate results So that's why actually the back propagation can only be done on the classical simulator because in that case we have the whole computing graph。

 however， on the actual quantum device， we are not able to obtain all the intermediate results。

 So that's why we cannot perform the actual back propag back propagation on the real device。

 So on the real device on the other hand， we can perform this parameter shift role。

 because on the real device for the parameter shift rule here。

 we actually don't require any of the intermediate results。

 We only require the final output from the device。 So that's the reason why we can always rely on this parameter shift role to compute gradients。

 but for the back propagation is only。Suable for the classicaltco simulators。So here we can see。

 as we say， it is doable to perform the primary shift on the actual device。

 So how exactly can we do that right， So for example， here we have the rotation X theta gate。

 So we want to understand what is the partial F over this partial theta value right So in marked by the yellow log here。

And then on the actual quantum device， so we can firstly perform this quantum circuit without the shift to obtain this firstly obtain the F function values。

 which is the original value。And then we can compute。

This classical part classical part of the forward forward loop。Because we can， for example。

 we want to perform this classification task and then from those F1， F2 all the way to F4。

 and then we want to perform， say the soft next function。

 and then we can compute the cross entropy loss according to the classification result。

 and then after that we can perform this bad propagation on the classical side because on the side we can always record the intermediateter result right so in that case we can we are able to obtain this partial loss over the partial F where F is actually the measurement outcome from the  Qbits。

And then on the actual device， we can perform this shift role， right。

 So because we want to we want to compute， what is the partial F over the partial theta。So the。

 so overall goal is to compute the partial loss over the partial theta。

 so we can use the chain rule to separate that to firstly partial loss over partial F and then partial F over partial theta。

 So using for this partial F over partial theta here。

 we can use the parameter shift rule we just introduced。RightSo in that case。

 we we can sum over those two four passes because of the sum principle。

 and then we can use the chain rule to compute the value for the overall partial loss over the partial theta。

 which is the the on the bottom right corner， which is actually using we can obtain this partial F over partial theta using the partial rule on point of device。

 and then the partial device， we have this partial loss over partial F。

 and then we can do the overall communication of partial loss over partial theta using this chain rule。

So after this competition we we can understand or we can obtain that what is the derivative of this theta value。

 what is the impact of the theta value to the final loss。

 and then we can update the theta according to over a goal。

 either there a classification task or some other generation tasks。也 question是。最近？不好意思。有个で。Anyways。

Yeah， so that's a really great point。 So you actually capture one of the fundamental challenge of the premier rule。

 which is the for each of the parameters analytically。

 we have to just ship that only value with all the others remain the same So that case。

 the number of actual certain run scale linear to number of parameters。

 So that's actually not very scalable。 So that's the reason why there actually many research。

 for example， we can do the sim simultane perturbation as the。 So which we introduce later。

 So we have some ways to approximate this process。 we don't have to rigorously remain keep the other values the same。

 but we can pertu a subset of all the parameters altogether。 So in that case。

 we can reduce the coefficient。 but in general the reason that's the case we have pay the linear cost to the number of parameters。

 So that's also the case for the classical deep learning also have the。scaling training costs。

 if have a really large number of funders in the classical near mass。

 but we have some way or some ongoing research trying to reduce the coefficient。

 reduce the scaling factor。O。All right， so here comes the we're going to introduce some of the training technique。

 including the SBSA we will also introduce actually just next slide。

 so the vanilla gradient descent is that for many different its。

 so this is just a very intuitive or very very conceptual plot so we want to make sure we reduce the loss function right for example we want to do the quantum classification we want to train those parameters until we converge to some of the target with the satisfactory accuracy。

And so just as we discuss， if we just do the， the， the circuit execution for each of the parameters and then。

The number of circuit1 will be two times n where n is the number of parameters， right。

 So in that case is very very costly processed to train all the parameters。 So in that case。

 they actually the algorithm called SA， which is simultaneous perturbation schastic approximationination。

 So the basic idea is that we can actually not we we don't have to just keep value value changed。

 we can actually change all the values altogether。 right So for example。

 we can pertu all of the parameters in the circuit altogether。

 and then we can obtain this value obtain this vector。

 which is the the F theta plus epsilon minus F theta minus epsilon。 So in that case。

 we can actually over assumption is that when we actually perturb all the parameters together。

 The value will be not very far away from the previous perturbation of。

only a small number value or even only one value， right So over the hope is that when you actually do this process。

The the new value on the on the top here is very close to only perturb one value。 So in that case。

 because we are changing a small， very small epsilom to each of the parameters。 So in that case。

 we can consider those two very close to each other。 and then we can use this and then however。

 after we compute this gradient。We will have a gradient for each of the parameter here using the SGSA because we will have a the vector。

 Some of the preturbation will be plus1。 Some of others will be-1。 right， So in that case。

 we can compute one single value gradient for each of the parameter and the magnitude of that value will be always the same。

 but direction for that value of each parameter will be different。

 Some of them is is on the positive direction。 Some others on the next direction。

 So that's how how we can perform this simaneous preion to compute the gradient of all the parameters in just one round of this forward process。

So here we can see what is the performance of this S P I A compared to the vanilla gradient descent。

 So basically， we have multiple multiple like curve here。

 So what the first one in the blue is the vanilla gradient descent。 right。

 So just using the using the back propagation were using this just using the this natural。

Is a fine different。 And then that will be the blue curve。 But using the SPSA。

 we can see that it's very close to the vanilla gradientingcent。

 And then we also have this quantum natural gradient。

 So that is in like case the performance of that one is the best。

 but the cost of that one is much larger than the vanilla gradientcent or SPSA。Okay。

 so there is another issue that I want to also introduce or mention a little bit。

 which is the barren plateau issue。 So in the classical。

 we know that after we stack in many layers of the neural。

 So there will be a gradient vanish problem because when we are doing too many layers of the back proag。

 and then the gradients of the first layer will be too small to update it will be too small to update meaningfully change the parameter values。

 So that's also there the similar case in the quantum circuit。

 So basically if we have a very large number of qubits。

 and then we have many different layers a large number of layers。

 And then the gradients of the first several layers will be also very small。

So here we can see that intuitive plus here， So the x axis is the number of qubits and y axis is the variance of the gradients so we can see that when we have a larger larger number of qubits。

 the variance of the gradients will be reducing exponentially So that's actually one of the the bottleneck or one of the ongoing charging point of the quantum machine models。

 which which means we don't have we cannot stack too many layers in the quantum circuit because of this vanish vanish gradient problem。

Okay， so and then here yeah， question。す状か。Yeah， that's a great question。

 So in the classical side classical， we have these residual connections the bypass right so we can directly have those different layers of the back propagation of the gradient all the all the way to the first layer。

 So actually there are some similar process in the quantum to adding this bypass layer to the quantum circuit。

 but in general they are not working greatly So the reason for that is actually on a quantum device we cannot copy the state of intermediate state to the later layers because we cannot directly there is a non cloning theoryem actually right here。

 So we cannot directly clone the state of all the qubits to a new set of qubits。

 So it's not like in the classical device。 It's very easy for you to clone one value or all the values of a layer and then bypass that to the final layer。

 but on the quantum device， you are not able to do the cloning of the qubits So that's why we。

Cannot create two copies of the state and then merge altogether in the later layers。So right。

 so in that case， the using the residual connection is not a solution or it's not a complete solution for the quantum learning right now。

Great question。O， so。Now we we can have a recap of the quantum classifier we just introduced in the previous lecture。

 So basically we have this encoder。 we can encode those pixels as the angles with this angle rotation angle encoding。

 and then we have those trainable layers， those unitary U3 layers。

 U3 is basically can arbitrary changing these states。

 And then also we have the controlled U3 gaze so we can train those parameters using the spPSA method or using the finite difference method。

 And then after that， we can do the measurement of thequbits and then do some of the post processing to obtain this classification results。

So here we can see basically this training process is also similar to the training process of this classroom neural。

 so if we have a here on the left side is visualization of this opposition process。

 we want to make sure we are going to the minimum process minimum places to come to that point to have a good prediction result。

So besides this classifier， actually there are also other tasks that we can use the parameterized quantum circuit。

 so one task we can do is actually the variational quantum eigens over so the basic task for this variational quantum eens over is to find what is the smallest eigenvalue given given the matrix right so that is for example。

 we can decompose that matrix to multiple multiple poly matrixrices and then we can measure that for multiple times and then the variational quantum eigens over is actually trying to prepare state which is the eigen state corresponding to the smallest eigenvalue so we can imagine that we can prepare the state and then evaluate what is the value。

 what is eigenvalue for that state and then we can always tunening the parameters in the quantum circuit to approach those final the final eigen state which has the smallest eigenvalue。

So finding the smallest eigvalue have a lot of applications。 For example。

 we can use that to find the ground energy of some molecule。

 We can represent the molecule Hamiltonian state。 we can represent the molecule feature with the Hamiltonian matrix。

 And then if you find the smallest eigvalue of the Hamiltonian matrix。

 That will be the smallest ground state energy。So that is that means that for the stable process。

 stable for example， if we want to understand what is the stable length of the bond between some some of the molecule。

 some of the item inside the molecule。 and then we can simulate or compute the energy for different distance。

 right So in that case， because of the because the country reactions will always go to the state which which has the smallest energy right So in that case。

 we can understand after this this country process。

 we will be the length of the bond between all of the items。

 So that is one of the application of the primaryized quantum circuit。

 So another one is the Q A or the quantum approximate algorithm。 So using the QA。

 we actually can find the solve the combinatorial organization tasks。 so。

So ensure those are some of the variational some of the PQC task。

 the classifier for the machinery task， the BQE for chemistry。

 or some of the QOA algorithm for the comb Or tasks。Okay， so let's continue to the section4。

 which is the noise aware entrepreneur。So， so we have introduced that how to construct the quantum circuit。

 So actually on the real device， there is a large impact of the noise were actually doing this noise gradient computation。

 So actually the noise can reduce this reliability of the complete ingredients significantly right So here we can see that there is a noise induced sky between those two curves。

 One curve in in in the blue is actually the classical training。

 which means we just simulate all of the process on the classical device。

 And then the red one here is actually showing the the actual actual partnership rule on the real device on the IBM quantum device。

 So we can see the accuracy of this evaluation process can be can be significantly reduced by this noise on the actual device。

 So how can we deal with that right So here we can we have a very interesting observation is that when we when the gradient。

itude is very small。 And then the relative error of that will be very large。

 So it's also very intuitive。 So imagine that if we have a very large gradient value。

 and then the noise on that noise is more unlikely to change the direction of those gradient。

 But if the gradient is very very small。 you can imagine only a small noise。

 a small perservrbation or real device will change the direction of the gradient。 So in that case。

 the overall idea that we can find those very small value of the gradients。

 and then we can prune those unreliable gradients during the training。

 we only use those reliable gradients to perform this primary updates。Right， so in that case， here。

We propose a method called this probability gradient pruning。

 so the basic idea is that before this pruning we we actually in each of the training step。

 we can always perform in the updates of all the parameters right so and however。

 using this gradient pruning we only perform those updates of those gradient those parameters with very reliable gradient。

So how can we know whether the gradient is reliable enough？ So actually。

 we just see what is the how large is the gradients that we computed from the this process， right。

 So specifically before this pruning process， we are updating all of the parametersers on the left hand side and using this gradient pruning。

 we are only updating a subset of the parametersers with the reliable gradient。

So in order to determine which subset of the gradients is reliable enough。

 we actually have a this iterative process at the window based method。

 so we can firstly have a accumulation window to accumulate the gradients of multiple steps to accumulate the absolute value of those gradient and then。

For example， we can accumulate for three steps to see how large are the gradients for each paners。

 And then we can do a sum of all of the absolute value of the gradients for each paner。

 and then we can do a sorting。 We only use those values。With a very large only use those gradients。

 with a large value to perform those pruning process。 And for those gradients， very small gradients。

 we will not use them to update the the parameters of the quantum circuit。

 So that's make sure that we are only using the reliable information to update the parameters。Okay。

 so we are。Actually comparing this QC trend using this probabilitybabil gradient pruning compared to the other ones。

 so basically we are able to improve around like5% to 10% of the accuracy on this four classification task using this probabilitybabilistic gradient pruning method。

And also， we can see that for this accuracy on this two fashion2 on the Sen Diego machine on the IBM device。

 we can achieve around  two x of the training time reduction because for those unreliable gradient。

 We not only， we don't use them。 And also， we actually don't have to compute them for for the from the first perspective。

 So we actually don't have to doing the computation for those un reliableable gradient。

 We only compute those reliable ones。So。Here we can see that the the。

Gre pruning for different times of the inferences。 So the axis here is the the number of inference we you we are doing on the real device to compute the parameter shift rule gradientance。

 And then the Y axis is the test loss。 So the loss is the lower the better。

 So we can see on the classical device。 There's no error at all。 So we can see the。

 the loss is always the lowest。 And then the the blue curve here is the Q C train。

 which means we are using the real device to perform the parameter shift rule。

 And then the because of the noise。 There will be a gap between the the ideal case to the the blue curve。

And for this quantum on training， we are able to close this gap to further push this curve to the to the ideal case to the green curve。

And also the on training here is actually also very scalable because we are not using any of the classical process during the whole training training pipeline。

 We are computing those gradients on the real device and then real quantum device and then update parameters。

 so imagine that if we're using the classical simulator and then the cost， for example。

 the runtime cost or the memory cost will be exponentially large when we have a large number of qubits because the the size of the same vector will increase exponentially to the number of qubits。

 but using the quantum device quantum device to training model。

 we don't have to pay the exponential increasing cost in terms of the runtime and also the memory。

🤧So here we can see the probabilitybabil pruning， we also compare to the deterministic pruning。

 So basically in the probabilitybabil pruning， we are using the magnitude of those values to determine which parameter has a larger probability to be pruned。

 but this process is not determinacy。 So that means we are not always or removing the parameter the gradients forever。

 we are having using the sampling method to sample those different values to prune。

 So that is also give us some advantage compared to the deterministic pruning method。

 around like 1% to 9% of the increase of the accuracy over the several different tasks。Alright。

 so were also actually developing a library which is called a Torch quantum library。

 which we are actually implementing all of the classical process using this Pytorrch framework。

 because all of us are very familiar with the machining process and we are using this Pytorch Py framework or Tensorflow if a Google Google。

Prefer the Google frameworks， and then actually Google have their own quantum framework。

 which is called the Tensorflow quantum。 But the patch we are actually developing the TQ framework。

 the To quantum framework。So we want to make sure the developing of these quantum machine models has a very good infrastructure to start with。

 right， So we we want to make sure the developing of those models have a fast speed and also very convenience to use and very easy probability between different frameworks among those common quantum Is and also scalable computation。

So and also we won't have those GPU acceleration process and also those density matric support and also different converters to other frameworks and also in the pipeth we know one of the advantage is the dynamic completion graph that we can have an intermediatetent results very easily and that can facilitate our debugging process。

So basically here， I'm just going to show a very simple example using the TQ framework to construct a quantum machine model。

 So basically basically this is very similar similar to constructing the classical neural networks。

 So we have this model， which is a。12 class of the N dot module。

 And then we can firstly instantiate a quantum device using the T Q dot quantum device。

 and we can specify how many  cubits with the number of wires。 And after that。

 we can also specify the encoder gate。 So remember， previously introduceds rotation angle encoding。

 So we can have those rotation X， rotation Y， and also all the other four layers， the R X， R， Y。

 R Z and R X。 And then we can also specify some of the trainable gate。For example。

 we have those rotation X gates to train right and also whether those have parameters or not。

 we can specify them in the in function。And also we have that is basically the construction of the model。

 And how can we use that， right So we also have this forward function。

 the same as the other classical pet models。 So basically we have this we want to first reset the quantum device vector reset this same vector。

 And then we can encode those classical pixels using those encoder layers right So just like the the diagram we're showing we have those different layers to encode the classical images。

 and then we can apply those trainable gates to different qubits。

 and then we can apply those nine trainable gate。 for example。

 some of the hammer gates or the S or the arbitrary unitry。

 we can apply some unitary gates arbitrary ones to the qubits。 And then finally， we can measure。

This we can have this measure process， the measurement function to measure the cubs device back to the classical values。

 right， And then after that， the x here will be purely classical value。 and then we can。

You can apply any of the your favorite classical layers。

 either is a MLP layer or some attention layer or any other ones after we obtain these values from the class from the quantum device on the classification classification side。

 And then finally， we can do this。We can perform this softm to obtain this final classification task。

 or either some up some you can also generate perform some generation tasks using this framework。

So basically as we introduce we have this quantum device supported as the TQ dot quantum device and also we can perform different ways。

 so just just like in the Pytor we have this Pyrch n do functional。

 we also have the Torch quantum dot functional similar to the quantum Py syntax。

And also we have another supported gate， supported way to perform the gate。

 we can instantiate the gates first， and then we can use that gate to process the value。

 the quant bias。And also we have we can perform this the third way of performing those skate is that you can directly initialize this quantum state。

 and then you can use the quantum state。 H to perform the gate。

So the underlying information of the TQ is actually using all of the data structure in the pys。

 right， So， for example， we are using the state will using the torch native operation。

 the torch zero to initialize and also all of the operations， all of the unit circuit。

 unit gate will also using the Py tensor。So in that case。

 you can imagine the classical simulation process or any of the quantum forward process will be fully differentiable。

 so we can very simply use all of the off the shelf optimizers provided by pety to optimize our quantum churn model parameters。

Alright， so we also provide some of the macros in the in the basically some of the macros in the。

The third in the framework， so we have this amplitude encoder。

 you can directly use the TQ dot amplitude encoding to call that and also TQ dot face encoder to call this angle encoding using those rotation values。

And also， of course， we have this supported way to convert those TQ models to other frameworks like the Kisket。

 so if we want to run those quantum circuit on the real quantum device provided by the IBM quantum platform。

 we can also use some of the some of the functions that we already bake in the TQ framework to directly write those converters。

 and then we also provide some of other functions to draw circuit or constructing some of the predefined layers and also different kinds of。

Different kinds of quantum machine models that are right in the library that we can directly use。

Welcome to check it out， I will now introduce all the details of the model so you can just go to Torchponum。

org or search Torchpon on Github to play with the library。Alright， so in the final section。

 we will introduce one example that we can use the TQ to perform some of the robust quantum circuit architecture search。

 So actually the quantum circuit architecture search is one of the fundamental challenge in quantum learning。

 So that's actually also the challenge in the classical deep learning。

 So I believe that in the previous lectures we are learning。

 we have learned some of the neuralarch search of the models。

 So you don't know how to how to construct model， which is that is the best suitable for the target task。

 So you can do some of the na method， the neuro architecture search to find the best model。

So that's also the case。 That's also the challenge for the quantum quantum machine learning。

 So basically you have a large design space。 you can perform many different kinds of the different kinds of the gate。

 for example， we have a many different types of the gates either the U3 gate or the node gate or Cn or you can have a different numbers of gates right can you can just put one layer or you can stack as many layers as you want and also the positions of the gate。

 It's also very different。 So if you're directly applying this U3 gate in the first layer or you can do some perturbation of the gate。

 So there's essentially a very large design space for us to explore。

 So how can we find the best quantum circuit to perform the target target task right So for example。

 if you want to perform those this kind of classification task。

 We will be the best best quantum circuit structure to start with and also what are the structure for some quantum generation。

So here we are going to introduce this framework called quantum nuts the quantum noise aware search to perform those search process。

 So of course， you can use any of the any of the naive search method that is already available or already widely use in the classical。

 For example， you can just list have a random search， right。

 So can you can have many of the different structures。

 And then you can train each of them According to our previous process。

 and then you can evaluate the performance of each of the quantum circuit on the real device to see which one is the best。

 However。If you are doing this search process， for example， you can have a many different。啊。

For example， you can have many different layers。the one嘅。Then you have one pen case for each other。

So。So in that case， you actually have many different combinations。

 you can just use one case on the first layer， two gate in the second one。Third。

 so there is actually a very large space right so one way you can do the search is you just train many different circuit。

 you can train one here。And then obtain a performance like  many0% of this word can another one。Here。

Many this one。Of accuracy。However， that way is not very efficient because you can imagine you have to train each of them to obtain the accuracy and then find the best one。

 So the goal of the quantum nu framework is actually whether we can just train once whether we can train a super of all of the all of the possible circuit。

 a super side of that here and just train once。 and then we can sample the parameters from that super circuit。

 and then directly evaluate on the real device to obtain the performance。

 So that's the basic idea behind the a quantum nu framework。 So you can train once but use many。

 So it's a similar to the classical like one single pass one shot of the nu method。

So there are actually four steps in in the framework。

 So the first one is that we can construct a super circuit right so we want to make sure the super circuit has a large enough representing power so we can construct say we have three layers here and then each layer has say four days over nine days and then we have maximum。

 we have nine layers。 and then we can after that， we want to train this super circuitcu。

 and then after training， we can do some a noise where this evolutionary search of this sub circuitrcuit and also the cube mapping。

 And then after we find this reliable circuit and then we can train this from scratch。

 And finally we can also perform this pruning method of those values。

So let's go through them one by one。 So the first one is the quantum super circuit and sub circuit。

 So as we just introduced。We want to construct we want to cover a large large enough design space。

 right So for example， the super circuit with this U 3 and C3 gates。

 So we have many different candidatesdies in the design space。

 Those are called a sub circuit right So during the training process。

 the reason why we are using a super circuit is that we can just do the training for this super circuit for one once。

呃，开始。So in this sense。輸出さ。Yeah， so the issue for the baron plateau is actually still there。

 but there are some of the actually this method is orthogonal to the quantum circuit structure that is can we can kind of solve the bar plateau issue So we are proposing that inside this design space。

 How can you find the most reliable circuit right， but you can start with design space that have a better immunity to to the bar plateau issue。

So or the short answer is that are this method cannot directly solve the bar plate。

 but we can firstly start with the design space that has a good property or we can during the search。

 we can evaluate the gradient to find those one without the bar plate issue so that can always be done during the search process。

So either you want to search a very reliable one or you want to search one without the very issue。

Okay， so let's continue。 So basically those when we are actually using the super circuit method。

 we want to make sure those sub circuitrit can inherit the the train values directly from this super circuit。

 So we don't have to train those values again。 So we just train the super circuit ones。

 And then we can use that for the evaluation of all all of the sub circuit in in the in the design space。

So in order to achieve that。 So you may wondering how can we do that。

 because those values are typically cannot be inhered to to by all of the sub circuit， right。

 because if we are training those individually and then the final value， for example。

 if if we train this several circuit individually， right even they have the same location of the case。

 they may have different values。 why we can directly inherit that。All of the sub circuit， right。

 So that is seems to be possible。 So so here actually we are introducing one heuristic to train this super circuit。

 right， So that is this sample and training process， right so。

For each the each of the sub each of the set， we actually can sample a sub circuit from this super circuit。

 We just sample subset during this training set， and then we only do one time of the parameters updating。

 for example， in the first training set， we can sample this structure and then update parameters inside this structure。

 and for the second step， we between we sample this structure。

 and then we continue to update the values。Right， so that is after enough number of training steps。

 we can imagine that all of the sub circuit in the in the super circuit are already undergoing the same number of training steps。

 right， So even though they are not the same level of accuracy compared to the train from scratch sub circuitit。

 they can still indicate what is the performance or the relative performance order between those all of the sub circuit。

 So here we can see a。We can see a quantitative result for that。

 So basically here on the X axis is the loss function for those sub circuitrit using those inherent parameters and y axis is the values is the ground truth。

 Basically the laws that we train from scratch。 So we can see a pretty good positive correlation between those two。

 So that means because we are just want to find the one with the best performance。

 So we are only carrying about the other preserving property between the sub circuitrcuit with the inherent parameters compared to the all of the sub circuitcuit train from scratch。

 So that case we only need to to make sure this correlation between those two are very。

 very large so。In that case， we can use this super circuit to facilitate the later search process so we can do the evolutionary search inside this this sub circuitrcuit。

 Basically， we can search for we can use a reinforce learning or any of the search engine your favorite search engine。

 and then we can sample the sub circuitrcuit from this super circuitcuit。

 and then we can evaluate the performance on the real device and then do this etly until we find the best sub circuitcuit。

So we are also as we learn in the first several lectures。

 we also have the pruning technique that is also applicable to the quantum churn domain。

 So basically some of the gate， after we train those sub circuitrit can be very close to0 So as we introduce in the previous previous last lecture。

 So if we have a value very close to0， and then the actual unitary matrix is actually a identity mapping between the input and output。

 So in that case， we actually don't have to perform the actual implementation of this gate。

 So if the value， for example， rotation of the zero degree and then the actual result will be same as the input。

 So in that case， we can also perform those interpretative pruning of those values very close to0。

 So basically we can find those we can do a search of those values or those gate close to0 have question。

Actually， I'm wondering why there is a stillalable， likely if there is a large number of children。

Yeah， that's a great question。 So basically we can do the。

 remember that we introduced the parameter shift rule in the last section right So the super circuit training process can always can also be done on be done on the on the real device right So we can use the parameter shift to train the super circuit。

 So all of the process。 The super circuit training。

 the sub circuit training and also the search can be done can be done on the point device。

 So that that's actually scale with the number of  Qs。Greatre question。Okay。

 so after that we can do this pruning process to remove those small value number。

 small value gate to make sure the final resulting circuit is most efficient containing the most essential essential message。

对。Alright， so there are also some some other search frameworks， for example。

 the one that using the machinery based predictor。 So basically。

 you can train a model to predict which sub circuitit has the best performance。

 right so we can use some graph neural networks to approximate the structure of the common circuit and then train a predictor on a real device。

And then there are also some other framework that directly encode the structure of the quantum circuit using a graph right So for example。

 if there are three different qubits， we can use a three row of the pixels to encode the data and also some other framework using the reinforced learning for the architecture search and then here we have this quantum computer on the top and then the action will be generate whether we want to add one more layer right so we can do that using a bottom up approach So whether you want to adding one more layer or reducing one more layer so there are action space and then you can evaluate the performance on the on the real device to generate the reward and also the observations and then you can feedback to the R agent to decide the next action。

And also there are some other work using the differentiable search and also some proxy based search。

 which Im not going to all the details， but welcome to check out those papers。So finally。

 a summary of today's lecture， we introduce the primaryized quantum circuit， the training process。

 how to do application using the simple classifiers and also how to improve the reliability using those noise where primary search。

 the TQ library and also how to find the most robust quantum architectures using this quantum nice framework All right so thank you very much for attention happy to take any questions Thank you and also have a nice thanks。

