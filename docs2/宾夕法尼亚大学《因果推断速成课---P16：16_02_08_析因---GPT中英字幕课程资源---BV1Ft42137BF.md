# 宾夕法尼亚大学《因果推断速成课程｜A Crash Course in Causality》中英字幕 - P16：16_02_08_析因准则.zh_en - GPT中英字幕课程资源 - BV1Ft42137BF

![](img/b854017b04e3b8e625b57d49e107dca3_0.png)

Hi， in this video， we're going to talk about an alternative criterion。

 the disjunctive cause criterion。So the objective is to understand what the criterion is。

And given a da， how to use it to identify a set of variables to control for。

Imagine that you're interested in selecting variables to control for in an analysis。

So one method for doing that is what's known as the disjunctive cause criterion。 There。

 you'll select the set of variables that are causes of the exposure， the outcome， or both。

And from the set of variables， what we really mean is all observed variables。

 So imagine that you have a lot of variables in your data set and you want to know which of these variables should you control for。

 So it's possible that there are unobserved variables。That you of course， cannot control for。

So the advantage of this method is that you do not have to know the whole causal graph。

 you simply have to be able to identify which variables affect the exposure or the outcome。

So one property of this criterion is that if there exists a set of observed variables that satisfy the back door path criterion。

 then the set of variables selected based on the disjunctive cost criterion will be sufficient to control for confounding。

 So as long as。On a given day， there's a set of observed variables that you can use to control for confounding。

Then selecting the variables that are causes of exposure or the outcome are both will also be sufficient to control for confounding。

So to illustrate， let's consider an example where we have three observed pretreatment variables that we'll call M。

W and V。And let's imagine that there's also some unobserved pre treatmentatment variables， U1 and U2。

 So in practice， of course， there would be typically many more observed variables and far more than just two unobserved variables。

 But we're just going to keep things simple and say there are three observed variables and two unobserved variables。

So， of course， it's impossible to control for the unobserved variables directly in an analysis。 Now。

 suppose we also know that W and V are causes of either A， Y or both。

And let's assume that M is not a cause of either A or Y。

There's a number of things you could do then to select variables to control for。

You could draw a da and then use the backdo path criterion to select some set of variables。

 But here we're going to imagine that we actually don't know what the dag is。

 but we might have some information about the variables。

So one thing you could do is just use all pre treatmentrement covariates。

So you could kind of what some people might view as plain itself safe， if you could just decide， oh。

 I'm going to control for everything。 So in this example， that would be controlling for M，W and V。

 so。You could think of this as one way to select variables， which is just use everything you have。

Alternatively， you could use a disjunctive cause criterion， and in this case。

 that would be just W and V， because on the previous slide。

 we noted that we're assuming that W and V are causes of either the treatment or outcome or both。

So what we're going to do in the next few slides is look at some hypothetical diggs and see which of these criterion would be sufficient to control for confounding in those different situations。

So here's one example where you see the true D。And in this day。

 you can see that V and W are causes of either A or y or both。

 and you can also see that M does not affect either A or Y。

 so that meets the definitions we had on the previous slide。

So we're imagining that this is a true egg。And then if you use the criterion where you use all pre treatmentatment covariates。

 in that case， we control for MW and V， you'll see that that does satisfy the back dooror path criterion。

Because there's only one backdoor path from A to Y。 and that's through V and W。

 and we block that path。 So that's fine。 So those variables are sufficient to control for confounding。

If you look at the second one here， where you use a dejunctive cross criterion。

 we simply control for W and V。We don't include M because that's not a cause of A or Y。 Well。

 it turns out that also satisfies the backdo path criterion because we are blocking that one back dooror path from A to Y by controlling for W and V。

So here's an alternative true De where there are， again。

 three variables that we might want to control for VM and W。In this case。

 we actually don't need to control for any variables because there's no unblocked back door paths from A to Y because there's a collision at M。

 So technically， you wouldn't have to control for any variables here。

 but if you do control for all pre treatmentment covariates， which is M W and V。That's fine。

 It will satisfy the backdoor path criterion because even though when we condition on M。

 it opens a path between V and W， we're blocking that path by controlling for V and W。

 So there's no problem there and similarly the dejunctive cause criterion also is fine it controls for W and V。

 It doesn't condition on the collider， doesn't create any new confounding。

 and so either of these would work in this example。

So here's another hypothetical dig where you see that W affects A V affects y。

 and then there's a variable M that doesn't affect A or y at all。

 but then here we have two unmeasured variables U and Y and I use these dash arrows just as a reminder that we don't observe u1 and U2。

 So those are not variables that we can control for。 And again。

 we can note that we actually don't need to control for anything in this dig because the only backdoor path from a to y has a collision at M。

So because there's a collider there， there's no unblocked backdoor path from A to Y。

 So we don't actually need to control for anything。 but if you didn't know the dag。

 then you wouldn't know that that's true。 So suppose because you don't know what the da is。

 you decide you're go into control for MW and V。 In other words。

 you control for all pretreatment covariates。In that case。

 you would not satisfy the back door path criterion。And again。

 the reason being is because you control fall for M。And there's a collision at M。

 and that opens a path between U1 and U2。 and therefore you can go from a to U1 to U2 to Y。

 So there is confounding on this graph if you control for M。

So using all pretreatment covariates in this case would end up creating confounding when there was none。

 and so you wouldn't be controlling for confounding with that criterion。

But if you use a disjunctive cross criterion where you just control for W And V here。

 it does satisfy the back dooror path criterion。 We didn't control for and therefore。

 we didn't open a path between the Us。In this example。

 the true drag is one such that there is no way to satisfy the backdoor path criterion just by controlling for the observed variables。

 And so we'll illustrate that here where we have W and V both affect Y。

 And then there's two unmeas variables。 U1 and U2。 And then there's also a variable M。

 but that doesn't affect anything。 So M is just an independent variable。

 And so what we'll see here is that in general。If you can only control for observed variables and not unobserved ones。

 you'll see that there's a path from a to Y that goes through W， but there's also a collision at W。

 And so because there's a collision at W that opens a path from U1 to U2。 So if we control for W。

There's a path from U1 to U2。And then you could get from A to Y using that back dooror path。

 And so in this case， if you select all pre treatmentment covariates。

 M W and V that won't satisfy the back door path criterion because， again。

 you open up this path from U1 to U2 that allows for a to be associated with Y in a non causal way。

And similarly， if you just control for W and V using the dejunctive cause criterion。

 you also won't satisfy the backdoor path criterion。 So in this example。

 there's no set of variables that you could control for that would satisfy the backdoor path criterion。

 So in that case， there's nothing you could do。 There's no set of observed variables that would solve the problem。

 and therefore， the disjunctive cause criterion is also not going to work。

So to summarize a disjunctive cost criterion， it's not always going to select the smallest set of variables。

 as we saw earlier where， in some cases， it would select variables in situations where you didn't even need to control for anything。

 But it's conceptually simple in that you're just listing variables that are causes of treatment or outcome or both。

And it's guaranteed to select a set of variables that are sufficient to control for confounding as long as such a set exists。

 so as long as your data set contains a set of observed variables that are sufficient to control for confounding。

And importantly， you also have to correctly identify all of the observed causes of A and Y。

 So there's an additional burden there that you have to know something about the causal structure。

 so you don't have to know the entire causal graph。

 but you do have to know something about the relationship between these variables so that you can list variables that are causes of A or Y。

So now that we have ideas on how to select variables to control for。

 then we need to think about how do we actually go about controlling for them。

 so some general approaches for doing that include matching and inverse probability of treatment waiting。

 and so these and other methods will be discussed in future videos。

