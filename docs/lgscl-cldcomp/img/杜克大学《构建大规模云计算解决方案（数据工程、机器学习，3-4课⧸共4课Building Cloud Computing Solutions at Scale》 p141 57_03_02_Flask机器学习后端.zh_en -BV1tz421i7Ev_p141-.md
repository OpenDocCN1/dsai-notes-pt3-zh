# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p141 57_03_02_Flask机器学习后端.zh_en -BV1tz421i7Ev_p141-

![](img/fac98dde3cce1d221e37e17400c97e32_0.png)

Let's say you were going to build a machine learning company from scratch。 So how would you do this。

 would you， was what would be the minimum amount of stuff you would need to build。

 You could probably build something with a flask gap。 So so let's even call this。 let's say。Fask。嗯。

El backend。Like a real back end So what would be the endpoints you would need to build， I would say。

You first， you would need to have an authentication endpoint。

 so this endpoint would make sure that someone has an account and that could go to。

 let's say cgognito。Or you could go to Firebase or whatever cug。Cognito。There we go， AW Carognito。

 so can authenticate， make sure you have an account， okay， great， it lets you in。

 you would also maybe have an off。An endpoint here as well， our authorization endpoint。Authorization。

And so this one would say also with Cgognito， is it would tell you what resources you can access like so this would be。

 I don't know。Admin， right， you could say， okay， the admin can access everything and then I would build like a predict。

In point。And so this predicting point， what it could do is it could accept。

 let's just take the handwriting， right， it takes images。

It accepts images and it predicts inside of the image it returns back。

To the user or return back a payload that says the the digit name right so it could be like name。1。

 right， and and that's pretty much， I don't know， maybe log out something like this。

 So so you could build out just like four endpoints here and you have this back end and you could build out this this this prediction back end service so you can people can sign up well。

 I guess you maybe do the register right so you have another endpoint that's register so it could be you know。

 again with Cognito。Register。 So， okay， I want to register for your service that predicts my handwriting。

 I want to authenticate once I've registered。Now I'm a registered user okay。

 what can I access oh grid， I can access the predict route and then you do it。

 you do the prediction and then you log out that could be a very。

 very simple you know backend for production service and then once you've got that set up I would say phase so this is step one。

Then I would say step two。Would be that I would use Postman first， I would not build a web service。

 I would not build the single page web app or Flask gap。My personal advice do not do that。

 do something like postman， make sure does it work， right， like can I actually call it？Um。

And also implicit to this step one here is I'll just put that we're doing continuous delivery right so we already talked about how important this is is that every time you're doing the code it automatically tests。

 itll linkss the code， tests it。This is what I would focus on， which is a little bit of work。

I would make sure that this works if you can do this then step three would be okay you got the web service working now you can finally build the front end and then the front end would be whatever you want in fact maybe even you don't care about you know the web even some some companies don't do this I think wechat right is like。

Like every time I use WeChat， it doesn't even let me do anything on the web。

 they just do mobile first， like maybe you just do mobile right and you just go mobile first or whatever you but whatever it is you want to do。

Then the mobile or the web。

![](img/fac98dde3cce1d221e37e17400c97e32_2.png)

Would call in step 2。

![](img/fac98dde3cce1d221e37e17400c97e32_4.png)