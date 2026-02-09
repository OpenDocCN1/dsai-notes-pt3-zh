# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P13：12_连接GitHub和RStudio.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

Now that we have both ourSt and Gitt up on your computer and a GitHub account。

 it's time to link them together so that you can maximize the benefits of using ourSt and your version control pipelines to link ourSt and Git in our studio。

 go to Tool， then global options， then Git/sVn sometimes the default path to the Git executable is not correct。

 Con that Git。ex resides in the directory that ourSt has specified if not。

 change the directory to the correct path otherwise。

 click OK or apply ourSt and Git are now linkeded。

![](img/b1de7e2815dcef47ba3039880054d742_1.png)

![](img/b1de7e2815dcef47ba3039880054d742_2.png)

![](img/b1de7e2815dcef47ba3039880054d742_3.png)

Now， to link our studio to GitHub in that same ourSt option window。

 click Create our SAP and when this completes， click Close following this in that same window again。

 click for you public key and copy the string of numbers and letters close this window you have now created a key that is specific to you which we will provide to GitHub so that it knows who you are when you commit a change from within our studio。



![](img/b1de7e2815dcef47ba3039880054d742_5.png)

To do so， go to GiHub。com log in if you are not already， and go to your account settings there。

 go to SSH and GPG Keys and click new SSH key。

![](img/b1de7e2815dcef47ba3039880054d742_7.png)

Paste in the public key you have copied from ourSt into the keybox and give it a title related to ourSt。

 confirm the addition of the key with your GitHub password GitHub and RSt are now linked from here we can create a repository on Gitthub and link to ourSt to do so。

 go to GitthHub and create a new repository by going to your profile， repositories and new。



![](img/b1de7e2815dcef47ba3039880054d742_9.png)

![](img/b1de7e2815dcef47ba3039880054d742_10.png)

Name your new test repository and give it a short description， click Create Repoitory。

 copy the URL for your new repository。

![](img/b1de7e2815dcef47ba3039880054d742_12.png)

In our studio， go to fileile new project， select versionion control。

 select Giter versionion control software， paste in the repository URL from before。

 select the location where you would like the project store it， when done， click on Create project。

 doing so will initialize a new project， link to the GitHub repository and open a new session of our studio。



![](img/b1de7e2815dcef47ba3039880054d742_14.png)

![](img/b1de7e2815dcef47ba3039880054d742_15.png)

Create a new our script by going to file， new file， our script。

 and copy and paste the following code， print parenthesis quoteThis file was created within our studio。

 end quotecloed parenthesis， and then on a new Li paste， print parenthesis。

 quote and now it lives on GitthHub， end quotecloed parenthesis， save the file。

 note that when you do so， the default location for the file is within the new project directory you created earlier。



![](img/b1de7e2815dcef47ba3039880054d742_17.png)

Once that is done， looking back at ourSt in the Git tab of the Environ Quadrant。

 you should see your file you just created， click the checkbox under stage to state your file。



![](img/b1de7e2815dcef47ba3039880054d742_19.png)

Click commitmit a new window should open that lists all of the changed files from earlier。

 and below that shows the differences in the staged files from previous versions in the upper quadrant in the commit message box。

 write yourself a commit message， click commit close the window。



![](img/b1de7e2815dcef47ba3039880054d742_21.png)

So far you have created a file， saved it， staged it。

 and committed it if you remember your version control lecture。

 the next step is to push your changes to your online repository。

 push your changes to the GitHub repository， go to your GitHub repository and see that the commit has been recorded。

 you've just successfully pushed your first commit from within our studio to GitHub。



![](img/b1de7e2815dcef47ba3039880054d742_23.png)

In this lesson， we linked it in ourSt so that our studio recognizes you are using it as your version control software following that we linked our studio to GitHub so that you can push and pull repositories from within our studio。

 to test this， we created a repository on GitHub， linked it with a new project within our studio。

 created a new file， and then staged， committed， and push the file to your GitHub repository。



![](img/b1de7e2815dcef47ba3039880054d742_25.png)