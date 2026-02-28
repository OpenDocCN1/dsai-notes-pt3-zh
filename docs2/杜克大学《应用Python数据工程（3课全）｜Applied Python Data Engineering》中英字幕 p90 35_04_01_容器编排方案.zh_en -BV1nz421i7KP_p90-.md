# 杜克大学《应用Python数据工程（3课全）｜Applied Python Data Engineering》中英字幕 p90 35_04_01_容器编排方案.zh_en -BV1nz421i7KP_p90-

![](img/df1b089656bcbb595ba70b86435f938d_0.png)

Here we have several different options on managing containerbased deployment services。

 but they have a lot of similarity。 So in this scenario you could be in a cloudbased developmentment。

 maybe you're in AWS cloud9 or you're in the Google cloud development environmentment in a cloud workstation or potentially in Github and as you're developing。

 you can test things locally build containers， but then eventually as you go to production。

 you'll go through and push this through a build system。 So in the case of Gitthub。

 it could be Github actions in the case of AWS it could be AWS build system but the idea here is these containers get pushed to a container registry and typically if you're in a cloud provider you'll use your cloud provider's container registry。

 but you also could use other public registries like Docker hubub and then from here there's a managed container service and there's lots of different options for managed container services。

 typically someone would want to use the highestle service that's possible。

That's efficient in terms of cost and so in terms of AWS。

 instead of you going to maybe a virtual machine and's setting up your own cluster。

 you could actually use a managed Kubernetes cluster with AWS EKS。

 likewise you could use an alternative like a homegrown container orchestration service with AWS ECS and there's a lot of services in AWS that communicate with this。

Other cloud platforms， it's kind of a similar thing。 If you go to Google Cloud， you go to GkeE。

 For example， you could push something directly into the managed Kubernetes service because it'll be much easier since they're going to manage that service for you or you could even use a very highleve service like Google Cloud run where it's actually trivial to deploy something to Kubernetes because you have a container and you just run one command and it pushes it into production。

 So in general， this is the overlay that you should expect when dealing with cloudbased systems。

 and typically you do not want to deploy things through your own self-managed Kubernetes cluster。

 you want to actually let the other experts do the heavy lifting for you。



![](img/df1b089656bcbb595ba70b86435f938d_2.png)