# 吴恩达《生成对抗网络（Generative Adversarial Networks，GAN）》中英字幕 - P20：20_03_01_欢迎来到第三周.zh_en - GPT中英字幕课程资源 - BV1JC4y1T7vZ

Last week， you gave your G a little bit of an upgrade to generate images better。 This week。

 you'll explore another major issue with G training。

 and that's with a G generating the same thing each time。

 So G trained on all different dog breeds will only generate a golden retriever。

 And so that's obviously an issue and this issue happens because the discriminator improves。

 But it gets stuck between saying an image of a dog looks extremely fake or extremely real。

 and it's a classifier after all。 So it's encouraged to say。

 you know it's one real or zero fake as it gets better。 But in a single round of training。

 if the discriminator only thinks the generator's golden retriever looks real。

 even if it doesn't even look that real。 Then the generator will cling on to that golden retriever and only produce golden retrievers。

 So now when the discriminator learns that this golden retriever is fake and the next round of training。

 the generator won't know where to go because there's really nothing else it has in its arsenal of different images。

😊，And that's the end of learning， the end of learning is very， very bad for these networks。

And so digging one level deeper， this happens because of binary crossenttropy loss。

 where the discriminator is forced to produce a value between0 or 1。

 and even though there's an infinite number of decimal values between0 and1。

 it'll approach zero and1 as it gets better and so this week you'll be introduced to a new loss function that allows a discriminator to say negative4 or 100 any number between negative infinity and infinity which mitigates this problem and allows both networks to keep on learning just like you。

your assignment will be implementing this amazing GAN upgrade， so let's get started。

