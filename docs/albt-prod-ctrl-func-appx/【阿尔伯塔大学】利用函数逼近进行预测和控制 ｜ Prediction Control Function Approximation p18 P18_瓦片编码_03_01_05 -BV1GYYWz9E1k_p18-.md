# 【阿尔伯塔大学】利用函数逼近进行预测和控制 ｜ Prediction Control Function Approximation p18 P18_瓦片编码_03_01_05 -BV1GYYWz9E1k_p18-

![](img/cbc640972bfd2355241dbf9082334446_0.png)

We previously talked about course coding， today let's look at a computationally efficient way to perform course coding。

 Tal coding。By the end of this video， you'll be able to explain how tile coding achieves both generalization and discrimination。

And understand the benefits and limitations of tau coding。

Tal codingd is a specific type of course coding。Talconing performs an exhaustive partition of the state space using overlapping grids。

This is perhaps best understood through an example。

Let's revisit our fish friend who lives in a two dimensional continuous state space， the pondnd。

Unlike coursese coding， which uses arbitrary shapes， tile coding uses squares。

What's the most convenient way to lay out a bunch of squares over a space， it's a grid。

Let's call this grid a T length。So far， using this is just state aggregation。

Larger tiles will result in increased generalization。

Although the ideal tile size depends on the specific problem。

 it's generally a good idea to use larger tiles。To improve the discriminative ability of our telecoding。

 we can put several talllings on top of each other。Each tiling is offset by a small amount。

 Offting each layer of tiling creates many small intersections。

 This results in better discrimination。In practice， it is useful to use a large number of tilings。

For one tiling， generalization only occurs within the square， but with multiple tilings。

 updates in this state generalized to these other states。



![](img/cbc640972bfd2355241dbf9082334446_2.png)

The generalization in this case is diagonal， if we had used random offsets。

 then the generalization would be more spherical and homogeneous。



![](img/cbc640972bfd2355241dbf9082334446_4.png)

This is discussed more in the textbook。Let's talk about how to control the generalization properties further。

We can do this by creating a grid of rectangles rather than squares。

An efficient way to do this is to scale each dimension of the state space。

The environment appears to have gotten squished here。Actually。

 layering squares over this squished environment is like laying rectangles over the unsquied environment。



![](img/cbc640972bfd2355241dbf9082334446_6.png)

By using rectangles， we can control the broadness of the generalization across each dimension of the state space。

Tile coding can represent a wide range of functions， but its utility does not end there。

Talcoding is also computationally efficient。Since grids are uniform。

 it's easy to compute which cell the current state is in。Due to its computational efficiency。

 tileco can be used to quickly run preliminary experiments in low dimensional environments。However。

 as the number of dimensions grows， the number of required tiles grows exponentially。As a result。

 it can be necessary to tall input dimensions separately。

Whether or not input dimensions can be treated independently depends on the specific problem。



![](img/cbc640972bfd2355241dbf9082334446_8.png)

In this video we talked about course coding and how it is a generalization of state aggregation。

 see you next time。