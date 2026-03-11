# 【全集】佐治亚理工学院-GPU编程：视频与游戏-中英字幕-p24-Lecture-24---法向量变换--BV1GZfyBbEQn_p24-

So we've seen how to transform vertex positions Let's talk a little bit about how to transform normals So the positions will have a four-dimenional coordinate where we set that W to1 to facilitate translation normals we generally just think of as say starting at the origin and pointing now at a particular direction where in this case we're thinking about the origin as being a surface and if you normalize it to have unit length well then you have this sphere around the origin where your normal vector lives so transforming this normal at first glance may seem like just applying the rotation but not the translation that you would apply to the vertex position and that almost works but what can mess it up is scaling if you're scaling your XYz dimensions the same then that's fine you just apply that three by three upper left part of the transformation matrix that just handles the rotation。



![](img/4ce3542d73bb40e5067c97c1df12caab_1.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_2.png)

And uniform scaling in all of the mentions but you wind up leaving out the parts of the edge that are handling the translation What can mess this up is if you're scaling by different amounts in different directions and we can see what the problem is here If you do that you'll wind up with vectors that are no longer actually orthogonal to the underlying surface so you have to tweak things to make that happen Now this is something that will only show up as a problem if you're scaling differently in different directions and you might want to tell your level designers hey。

 just don't scale differently in different directions but at some point they will because what they're going to do is they're going to take one of your regular 3D objects put a different texture on it and then stretch it in some weird way to repurpose that 3D object and try to make it look like something else。



![](img/4ce3542d73bb40e5067c97c1df12caab_4.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_5.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_6.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_7.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_8.png)

For the purposes of this class， you don't have to understand the details of this derivation。

 you can just use the final result， but in case you're curious。

 I would like to talk about it a little bit so imagine we have some surface sitting here and T represents a point somewhere on that surface and we have an origin and t represents a point on that surface that at some point is passing through the origin now we imagine that we also have a normal vector that's orthogonal to the surface plane and what we would like to do is to transform the point in a slightly modified version of the usual way and then see what well need to transform the normal by in order to maintain this orthogonality in the final result。



![](img/4ce3542d73bb40e5067c97c1df12caab_10.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_11.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_12.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_13.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_14.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_15.png)

Well， what we're going to do is we're going to take this point on the plane and transform it with the upper left three by three part of the transformation matrix so we're doing the rotation and potentially nonisotroppic scaling meaning we might be scaling differently in different dimensions but we're not doing the translation at this point we're centering everything here on zero noticeice I'm using a row convention here and the reason I'm using a row convention even though unity uses a common convention is this is the convention used by the Wikipedia article where I found this math what we want to do is we want to take the normal and transform it by some matrix big W and we don't know what that matrix is yet we're going to find out but what we would like to have happen after we transform the plane however we transform it and maybe here's my new point t on the plane。



![](img/4ce3542d73bb40e5067c97c1df12caab_17.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_18.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_19.png)

I want to make sure that my normal vector is still orthogonal to it。

Pretend that I'm much better at drawing 3D things and that this makes sense。

 I realize that doesn't look very orthogonal。Anyway。

 those transformed vectors are going to be orthogonal to each other。

 it means that their dot product is zero and in this row convention I can get the dot product。

 the dot product of two vectors looks like the first vector times the transpose of the second vector so we can take the transpose and pull it inside the parentheses here when I pull it inside the multiplication the transpose lands on everything。

 but I also need to remember to flip the order here。



![](img/4ce3542d73bb40e5067c97c1df12caab_21.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_22.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_23.png)

Between the T and the M， and then once I've done that。

 I can just rearrange the parentheses a little bit because matrix multiplication is associative。



![](img/4ce3542d73bb40e5067c97c1df12caab_25.png)

If I need this to be zero。Well， I can say the original normal and tangent point vectors were orthogonal to each other that had a zero dot product。

 so what that means is that I could just set the stuff inside the parentheses here to the identity matrix and then I could just multiply both sides by this inverse of MTt and that tells me what my w is。

 so to transform a normal， you take the same matrix that you use to transform the vertices。

 you grab the upper left three by three part and then you take its inverse transpose。



![](img/4ce3542d73bb40e5067c97c1df12caab_27.png)

![](img/4ce3542d73bb40e5067c97c1df12caab_28.png)

As I mentioned before， if M just has rotation under those conditions。

 the inverse transform of that kind of matrix is just the transpose of the matrix。

 so then you could just say that W is equal M， but that's really only for that special case。

 to be on the safe side， it's a good idea to use this inverse transpose。



![](img/4ce3542d73bb40e5067c97c1df12caab_30.png)