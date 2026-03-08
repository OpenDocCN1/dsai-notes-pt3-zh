# 2025 Pytorch大会 ｜ Pytorch Conference 2025 p21 P21_闪电演讲-通过异步集合通信加速PyTorch_FSDP...-Nariaki_Tateiwa -BV1b8kRB6EJG_p21-

Hello， everyone。I'm a Nariyaki tawa and I'm from NTT。

 which is the Japanese telecommunicationss company。

I'm a researcher at that company and I'm studying about optimizing the distributed machine learnings network backend。



![](img/c26c0e728b4beb7959cf76da69b43ecf_1.png)

So today， I would like to talk about acc Pyto GFSTP by using Car network。



![](img/c26c0e728b4beb7959cf76da69b43ecf_3.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_4.png)

Now technologies。Okay， so here is a brief overview of FDP。So， FSDP is。



![](img/c26c0e728b4beb7959cf76da69b43ecf_6.png)

The a memory efficient para electronic method。And it positions model parameters and optimizational states across multiple per GPUus。



![](img/c26c0e728b4beb7959cf76da69b43ecf_8.png)

In FSCP， only required parameters are gatheredered。



![](img/c26c0e728b4beb7959cf76da69b43ecf_10.png)

Using all Ga collective communication before computing and it is unnecessary necessary parameters after a。



![](img/c26c0e728b4beb7959cf76da69b43ecf_12.png)

In addition， in backward， after computing， the FPSDP distributes gradients using reduced Qar。

 corrective communication。

![](img/c26c0e728b4beb7959cf76da69b43ecf_14.png)

After computing， and similarly there is unnecessary gradient after that。😊，And these two collectives。

Dominate the FSDP's workro of communication， so it is important to reduce these communications execution time for the speed up FSDP workro。



![](img/c26c0e728b4beb7959cf76da69b43ecf_16.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_17.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_18.png)

So this slide shows。The existing background schedule in FSDP。



![](img/c26c0e728b4beb7959cf76da69b43ecf_20.png)

So before training， in many cases， we split model into some SFTP modules。



![](img/c26c0e728b4beb7959cf76da69b43ecf_22.png)

For example， when we train transformer based model。

 we split it into some modules based on the transformer blockss。And in each module。

 we execute our to correct parameters and then。

![](img/c26c0e728b4beb7959cf76da69b43ecf_24.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_25.png)

Execut computation。 And finally， we execute video scatter to distribute compute gradient。😊。



![](img/c26c0e728b4beb7959cf76da69b43ecf_27.png)

And this all the Ga and computation and reduced Q process can be pipeline across multiple GP and multiple modules。

 for example， the moduleular2s or the Ga is executed before or moduleular3 to reduce Q to overlap the computation and all the Ga communication。



![](img/c26c0e728b4beb7959cf76da69b43ecf_29.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_30.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_31.png)

So our target in this talk is reducing this entire backward time。



![](img/c26c0e728b4beb7959cf76da69b43ecf_33.png)

So the key idea for that is the Hol paper which was accepted in theC24。



![](img/c26c0e728b4beb7959cf76da69b43ecf_35.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_36.png)

This paper proposes the idea that by combining overlap communication and network computing and Marchcast。

 we can reduce the entire backward time of the FSDP。



![](img/c26c0e728b4beb7959cf76da69b43ecf_38.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_39.png)

So。But to the best to open our knowledge， there was not any studies that evaluate this technique with the P to the FSDP and0。

 so we try do it。😊。

![](img/c26c0e728b4beb7959cf76da69b43ecf_41.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_42.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_43.png)

And I note that only overlap the communication is not enough to show reduce the communication time of overlapped。

 reduce scatter and all。😊，So we have to need to use internet computing and marcast together with O up。



![](img/c26c0e728b4beb7959cf76da69b43ecf_45.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_46.png)

So let me explain why it's in network computing and multi necessary to shorten the。



![](img/c26c0e728b4beb7959cf76da69b43ecf_48.png)

Exeecution time or the communication。

![](img/c26c0e728b4beb7959cf76da69b43ecf_50.png)

So collective communication time is mainly dependent on the longer of or received time of each end point associated with GPU。



![](img/c26c0e728b4beb7959cf76da69b43ecf_52.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_53.png)

And for example， in link algorithmism， this is a default algorithm in many creative communication。😊。



![](img/c26c0e728b4beb7959cf76da69b43ecf_55.png)

Each end point sense and receives。Sme data volume， dling both reduced scatter and all。

 so therefore if we overlap them it does not reduce the total communication time because the total the same data volume and receiving data volume is not changed。

😊。

![](img/c26c0e728b4beb7959cf76da69b43ecf_57.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_58.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_59.png)

But by using in computing， we can reduce the receiving data volume of reduced scatter。



![](img/c26c0e728b4beb7959cf76da69b43ecf_61.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_62.png)

So in network computing is a network technology that operates some computation operation into the network devices。

 such as a network switch， ormni and so on。

![](img/c26c0e728b4beb7959cf76da69b43ecf_64.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_65.png)

And summation in network switch is a typical example of network computing。

 and it can reduce reduce scattered out receiving volume to1 by and minus-1。



![](img/c26c0e728b4beb7959cf76da69b43ecf_67.png)

And where， at its a number of GPUus。

![](img/c26c0e728b4beb7959cf76da69b43ecf_69.png)

And this figure becomes to the half where the number of GPU is large enough。



![](img/c26c0e728b4beb7959cf76da69b43ecf_71.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_72.png)

And similarly， March gust on network device can also reduce the old gas send of data volume to 1 by and minus1。

 and finally we overlap these reduce kar and old gather， we can reduce the total as。



![](img/c26c0e728b4beb7959cf76da69b43ecf_74.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_75.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_76.png)

We can reduce the both total cent data volume and receiving data volume。

 so we can reduce the reduce S and all gas execution time by this overlap。



![](img/c26c0e728b4beb7959cf76da69b43ecf_78.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_79.png)

そ。Yeah， so we use by using overlap and internet computing and Matcast。

 we can reduce reduceq and or execution time up to half where the number of GPU is large enough。😊。



![](img/c26c0e728b4beb7959cf76da69b43ecf_81.png)

So this is a big reduction， so it is very efficient。😊。



![](img/c26c0e728b4beb7959cf76da69b43ecf_83.png)

When we apply it to the IPDP workro。So to realize this technique in the Pto GFSDP。

 we use these communication backyard setting as prototype。😊。

So we use two different communication libraries for each correctives。



![](img/c26c0e728b4beb7959cf76da69b43ecf_85.png)

So we use ania sharp for the scattera， and we use zero copy spin for all。



![](img/c26c0e728b4beb7959cf76da69b43ecf_87.png)

So NVD Sha provides someary network switch function and zerocopy spin provides independent UD Marchcast or Ga function。



![](img/c26c0e728b4beb7959cf76da69b43ecf_89.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_90.png)

And this zeropy spin is our thepy expansion of the existing spin libraries to speed up。



![](img/c26c0e728b4beb7959cf76da69b43ecf_92.png)

And we use UCCC communicationic library as interface of Sha and spine library。

Because UC can provide power correct looing and easy access to Sha and spin。But。When we use the UC。

 when we use UC as a back end or Python distribution directory。

It is not doesn't work because the UC backend queues correctives into the single stream。

 which is in the inner U backend and。Not overlaped that quality of communication。

So to avoid this contract， we use MPI as the backhand of Pyth distribution。

 then the core UCC from MPI。And we add some synchronization between MP corrects and cloud streams。So。

 of course， these states are ahoc， changing， ahoc design for。Experiment。

 and I think there is a more simple way to realize the love communication into the SDP training。😊。



![](img/c26c0e728b4beb7959cf76da69b43ecf_94.png)

Now by the way， with this setting， we can overlap this scatter and allga in the FSDP training without user code modification。

😊，So this is the experimental result using 10 individual GPUs， and we use GPU， their B C。

 border 100 GPU。So let's side of this right short， the micro benchmarkch result of reduced scatter and all together。

In this experiment， overlap overlap communication implement。Whats 22。5% faster than NAB and NICA。

 Sea Ken Sha execution， and NICAR is a de communication back used in the FSDP。

And the right side of this slide shows when we applied the overlap communication technique to the FSDP workload。

So all of the 3。7 billion models。So we achieved to improve 10。

7% faster by using overlapup communications。So and even with other settings。

 we observed a consistent improvement in back time of FSDP training。

 so our approach accelerates both micro benchmarkchmarks and layout training workers。

So this is a last slide of the takeaways。

![](img/c26c0e728b4beb7959cf76da69b43ecf_96.png)

Soう。By applying communication overlap。In network computing and Mat gas to FSCP。

 we achieved up to 10%% faster backward execution of FSCP workgroup。



![](img/c26c0e728b4beb7959cf76da69b43ecf_98.png)

Without user code modification。

![](img/c26c0e728b4beb7959cf76da69b43ecf_100.png)

So this technique is crucial to accelerate HP。So that's all from me。

 for thank you for your listening。

![](img/c26c0e728b4beb7959cf76da69b43ecf_102.png)

Yeah。

![](img/c26c0e728b4beb7959cf76da69b43ecf_104.png)

performanceformance。many you are offloading， really going above 100 tick。For the。

How are you able to consider what kind of schedule。



![](img/c26c0e728b4beb7959cf76da69b43ecf_106.png)

M my。上面取间脑上。Is that comfortable。

![](img/c26c0e728b4beb7959cf76da69b43ecf_108.png)

So first was what is the performance on the network bandwidth you're looking when on the smartne when you upload it。

 Yeah， what bandwidth you are able to see， What's the high end of the， What is the capacity of the。



![](img/c26c0e728b4beb7959cf76da69b43ecf_110.png)

Uload network smart chip。Oh approachship。 So the the you you say the。As。TheComp fraud to the。

A network switch。

![](img/c26c0e728b4beb7959cf76da69b43ecf_112.png)

Yeah， we use the IB Con network switch and why we use the Nvi NikA sharp plugingging and we use the Connect X as a Nik and so this its answer。

The reason I'm asking is like the D decay or anything youre using for uploadload that will kind of start I know。



![](img/c26c0e728b4beb7959cf76da69b43ecf_114.png)

It transport播放。Yeah。Only the only laser the network switches overload we used。Thank you。



![](img/c26c0e728b4beb7959cf76da69b43ecf_116.png)

Does this technique work with FSDP version 2 and1 or just one。



![](img/c26c0e728b4beb7959cf76da69b43ecf_118.png)

So， Chris。I can please。AndDoes this technique work with FSDP version 1 and2。



![](img/c26c0e728b4beb7959cf76da69b43ecf_120.png)

![](img/c26c0e728b4beb7959cf76da69b43ecf_121.png)

So we explain our explain in our explain， we use the E P Bu one。 Did this result is gained Bu one。

 and so we are。We apply this technique to the Bu 2 is now ongoing。 So this result is from the Ba one。



![](img/c26c0e728b4beb7959cf76da69b43ecf_123.png)

I have a similar question， does this work for other parallelism techniques like data parallel or model parallel？

Yeah， that's exactly yes。Yeah， this technique is August now all the other parallel strategies。

 for example the pipeline and data parallel and so on。

 so yeah this technology but this technology is only can fast。

 the FSDPs backward FFDP's a backward communication flow。😊，So if the a strategy can combine the FSDP。

 this technology can use these workload。

![](img/c26c0e728b4beb7959cf76da69b43ecf_125.png)

Thank you。