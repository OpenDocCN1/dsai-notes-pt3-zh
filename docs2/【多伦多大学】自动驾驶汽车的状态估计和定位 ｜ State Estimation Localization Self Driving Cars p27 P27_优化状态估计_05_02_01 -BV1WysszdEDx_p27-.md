# 【多伦多大学】自动驾驶汽车的状态估计和定位 ｜ State Estimation Localization Self Driving Cars p27 P27_优化状态估计_05_02_01 -BV1WysszdEDx_p27-

![](img/42298d2349fa6c0c36738d165f5e6cfb_0.png)

Most compelling ways to do state estimation really are some guys of an optimization。

 so you do a clever way to do a search of probably quite a high dimensional space that says given this stream of images of now and recently and all the things I've ever seen before。

 given this sensor data you write down a function which you wish to minimize and it can be proper complicated you know you've got the projection of features into images you've got laser that's got different reflection。

 you've got Doppler signals， say given all of that and all of the difficulties are having the association you would write the association problem。

 the data association problem as a minimization problem as well。

 given all of that solve this optimization problem proper fast to tell you an idea of where you could be or a set of places where you could be and then having uncertainty associated with that as well and that's an important point as well you need to be thinking。

About what you're unsure about as well， and that's important when you're going to come up for some planning decisions。

😊，And there are lots of algorithms that use optimization。

 I mean the simplest one that you will come across is probably least squares wouldn't necessarily recommend using raw least squares because the stuff that's an outlier least square spends all of its time worrying about rather than the stuff that makes sense so you put some outlier rejection on that there are things called ca filters which are again another minimum mean square error estimator that's online。

 there are big big batch optimizes that you might want to use as well。

 there are things called particle filters that you might want to use in all of these are looking for some maximal or a minima depending on how you pose it in a que in a happy world。

 your sensors are merrily releasing data to you， but you've got to expect that something's going to go wrong so you have to have this sense of introspection So you have to have some processes that are looking that say actually that stream of data there that's now anomalous it's not properly。

Exposed or some things just stopped working。But this also speaks at a higher level to the need to not just have one sense of modality as well。

 So if you had just one camera and that camera failed， that's going to be difficult for you。

 So you know you're talking to your vehicles oometry you're talking to some gyros。

 you' maybe got some laser and radars and any one of those failing you would then have sort already a backup but a complementary sensor that allows you to make an immediate plan about whether that's a critical error and then pull over and slow down and in a way your data fusion helps there as well so you might have 17 cameras and they're all giving you an idea of where you are。

 you might have a forward backward looking camera you might have several lasers that are indexing into a laser map so you would hope that you would not design it that you had a critical sensor that if that went down you have no idea what to do and then you're in big Dodo that would be a bad plan。



![](img/42298d2349fa6c0c36738d165f5e6cfb_2.png)

![](img/42298d2349fa6c0c36738d165f5e6cfb_3.png)