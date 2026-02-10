# IBM数据科学专业证书课程2：《数据科学工具》open-source-tools-for-data-science（中英字幕） - P26：25_GitHub分支管理.zh_en - GPT中英字幕课程资源 - BV1np4y1V7Sn

In this video， you will learn how to create and merge a branch using the Gitthub web interface。

 A branch is a snapshot of your repository to which you can make changes。

 It is a copy of the master branch and can be used to develop and test changes to the workflow before merging it back to the master branch In Git and Gitthub。

 There is a main branch。

![](img/71747b1f5cd2668e906ae8877908130c_1.png)

![](img/71747b1f5cd2668e906ae8877908130c_2.png)

![](img/71747b1f5cd2668e906ae8877908130c_3.png)

![](img/71747b1f5cd2668e906ae8877908130c_4.png)

![](img/71747b1f5cd2668e906ae8877908130c_5.png)

The main branch， which is called master， is the one with deployable code and the official working version of your project。

 It is meant to be stable， and it is always advisable。

 never to push any code that is not tested to the master。

 Many times we want to make changes to the code and workflow in the master branch。

 That is when we create a copy of the master branch。 Let's call it child branch。

 We will then create a copy of the workflow to the child branch。 in the child branch。

 changes and experiments are done。 We will build and make edits， test the changes。

 And when we are satisfied with the changes。 We will merge it back to the master branch where we prepare the model for deployment。

 We can see that all of this is done outside of the main branch and until we merge。

 changes will not be made to the workflow before we branch to ensure that changes done by one member。

 do not impede or affect the flow of work of the other members， multiple。😊。



![](img/71747b1f5cd2668e906ae8877908130c_7.png)

![](img/71747b1f5cd2668e906ae8877908130c_8.png)

Branches can be created and merged appropriately to the master after the workflow is properly tested and approved to create branches in Gitthub。

 Let's look at this repository。 There is currently one branch in the repository。

 I want to make some changes， but I don't want to alter the master in case something goes wrong。

 We will create a branch To do that。 We will click the drop down arrow and create a new branch。

 Let's name it child branch， and then we will click enter。



![](img/71747b1f5cd2668e906ae8877908130c_10.png)

![](img/71747b1f5cd2668e906ae8877908130c_11.png)

![](img/71747b1f5cd2668e906ae8877908130c_12.png)

![](img/71747b1f5cd2668e906ae8877908130c_13.png)

![](img/71747b1f5cd2668e906ae8877908130c_14.png)

![](img/71747b1f5cd2668e906ae8877908130c_15.png)

The repository now has two branches， the master and the child branch。

 You can check this by selecting child branch in the branch selector drop down list。

 Whatever was in the master branch was copied to the child branch。

 but we can add files to the child branch without adding any files to the master branch。



![](img/71747b1f5cd2668e906ae8877908130c_17.png)

![](img/71747b1f5cd2668e906ae8877908130c_18.png)

![](img/71747b1f5cd2668e906ae8877908130c_19.png)

![](img/71747b1f5cd2668e906ae8877908130c_20.png)

To add a file， make sure child branch is selected in the branch selector drop down list。

 Click on create new file in the space provided， name the file。 We will name it Test child dot Pi。

 and then we will add a few lines of code。 We will print the statement inside child branch。



![](img/71747b1f5cd2668e906ae8877908130c_22.png)

![](img/71747b1f5cd2668e906ae8877908130c_23.png)

![](img/71747b1f5cd2668e906ae8877908130c_24.png)

At the bottom of the screen， we will see a section called commitit new file。

 commitit messages are very important， as it helps to keep track of the changes that were made。

 It is important to add a descriptive commit message so that the other team members can understand it Here we will add a commit message。

 createate test child dot Pi。 Then we will commit the new file。

 The file gets added to only the child branch。 We can check this by going to the master branch by clicking master from the branch selector menu。

 And here we can see that the new file is not added to the master branch。



![](img/71747b1f5cd2668e906ae8877908130c_26.png)

![](img/71747b1f5cd2668e906ae8877908130c_27.png)

![](img/71747b1f5cd2668e906ae8877908130c_28.png)

![](img/71747b1f5cd2668e906ae8877908130c_29.png)

![](img/71747b1f5cd2668e906ae8877908130c_30.png)

![](img/71747b1f5cd2668e906ae8877908130c_31.png)

![](img/71747b1f5cd2668e906ae8877908130c_32.png)

After we have created the new file tested and made sure that it is up to standards。

 we then want to merge the changes in the child branch to reflect in the master branch to merge these changes。

 we will first have to create a poll request。 Also known as a PR。

 a poll request in simple terms is a way to notify other team members of your changes and edits and ask them for review so they can be pulled or merged into the master branch。

 Po requests are the heart of collaboration on Github。 When you open a poll request。

 youre proposing your changes and requesting that someone review and pull in your contribution and merge them into the target branch。

 Po requests show the differences of the content from both branches to open a poll request and see the differences between the branches。

 click on the compare and pull request button。 If you scroll down to the bottom of the screen。

 you will see something like this that show。

![](img/71747b1f5cd2668e906ae8877908130c_34.png)

![](img/71747b1f5cd2668e906ae8877908130c_35.png)

![](img/71747b1f5cd2668e906ae8877908130c_36.png)

![](img/71747b1f5cd2668e906ae8877908130c_37.png)

![](img/71747b1f5cd2668e906ae8877908130c_38.png)

![](img/71747b1f5cd2668e906ae8877908130c_39.png)

the difference between both branches as you can see on the screen。

 it shows that one file has been changed and the file has two additions。

 which are the two lines we added to the file and zero deletions。



![](img/71747b1f5cd2668e906ae8877908130c_41.png)

![](img/71747b1f5cd2668e906ae8877908130c_42.png)

![](img/71747b1f5cd2668e906ae8877908130c_43.png)

We will now create the pull request， add the title and an optional comment for the pull request。

 Click create pull request to create the pull request。

 You can assign team members to review and approve pull requests。



![](img/71747b1f5cd2668e906ae8877908130c_45.png)

![](img/71747b1f5cd2668e906ae8877908130c_46.png)

On the next page， you will see this image。 If you are okay with the changes。

 click on merge pull request and click confirm。 You will get a confirmation that the pull request has been successfully merged。

 You can now delete the branch if you no longer need to make any edits or add new information。 Now。

 the child branch has completely merged with the master branch。 You can check the master branch。

 and we can now see it contains the test child dot pi file。

 You should now be familiar with how to create and merge branches using the Web interface。



![](img/71747b1f5cd2668e906ae8877908130c_48.png)

![](img/71747b1f5cd2668e906ae8877908130c_49.png)

![](img/71747b1f5cd2668e906ae8877908130c_50.png)

![](img/71747b1f5cd2668e906ae8877908130c_51.png)

![](img/71747b1f5cd2668e906ae8877908130c_52.png)

![](img/71747b1f5cd2668e906ae8877908130c_53.png)

![](img/71747b1f5cd2668e906ae8877908130c_54.png)

![](img/71747b1f5cd2668e906ae8877908130c_55.png)