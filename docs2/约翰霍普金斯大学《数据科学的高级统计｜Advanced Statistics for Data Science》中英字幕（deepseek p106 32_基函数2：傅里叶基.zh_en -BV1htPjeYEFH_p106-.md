# 约翰霍普金斯大学《数据科学的高级统计｜Advanced Statistics for Data Science》中英字幕（deepseek p106 32_基函数2：傅里叶基.zh_en -BV1htPjeYEFH_p106-

So we were talking about instances where the design matrix X was ortho theormal。

 I had ortho theormal columns so that x transpose x was the identity matrix。

Let's talk about some of the most famous cases where this happens。Easily。

 the biggest one is so called Fourier basis。So in the ferier basis， the column of the X。

Our trigoometric， so imagine if your Y is a time series。

And then the columns of x are trigoometric terms， basically signss and cosines。

Different periods from slow。嗯。Low varying signals to really high frequency signals。

Toward the end of the x matrix。So what this means。Is that the coefficients associated from a least squares fit from these basis elements。

In my observed time series Y， the coefficients are just the inner product。Of these specific columns。

 let's say X I is column I from X。And why。And so the。Transformation that takes y to the collection。

Of these basis elements， in other words， that takes y to x transpose y。

That transformation is called the Fourier transformation or the discrete Fourier transformation。

 In fact it can be done faster than this calculation。

 it can be done capitalizing on some of the redundancies and trigoometric relationships it can be done faster to result in the so-called fast discrete Fourier transform what you get with the Fourier transform。

Is each coefficient is the amount of sort of of the signal that's correlated with a signine or a cosine term of that frequency。

 so as an example if I had，A signal that looked like this。So it looks like。

Maybe a signine term and a cosine term。Of a slow variation s term and a high frequency term added together。

 then those two terms， the coefficients associated with those two terms will wind up having big coefficients when we do x transpose y。

So when we want to reconstruct the signal again， that's just summation， right， the basis elements。

Times， the inner product。Of the the x's and the Ys so we can do tricks， for example。

 if we want to reconstruct the signal but only omit only include those terms that are very low frequency so for example。

 if we want this big rolling term but we want to get rid of the high frequency information。

 we might do what is called a low pass filter so we would let the low frequency terms through and would we would filter out the high frequency terms。

 so this would amount to just in our reconstructed signal here only adding those components associated with the low frequency terms in the basis。

And conversely， we might want to just capture the high frequency stuff and filter out the low frequency stuff。

 so in this sum we would just take the high frequency terms and omit the others and then the reconstructed signal would have filtered out the low frequency information。

So again， this all boils down to least squares。Just like we've been studying， however。

 I think it's fair to say that signal processors tend to think of this in a different way。

 but it's nice to put this very important concept， Fourier analysis in the domain of least squares。

 which we've been talking about in this class。The second basis that I would mention to discuss a little bit is so called wavelet bases and wavelet bases are similar to Fourier bases they're an orthonormal basis that have some nice properties associated with them。

And there is a discrete wavelelet transform just like there's a discrete fur transform。

 but it's actually able to get the transform faster than if。

You were to do it by calculating each of these inner products by themselves。Again。

 the Fourier basis and the wavelet basis， though， to really discuss them。

 we'd have to get into the nitty gritty of the construction of the bases。

 So I think I'm going to only then cover really in a little bit more detail。

 only one of the three cases， that's a little bit more statistical。

 One of the three most important cases of orthoormal bases。 That's a little bit more statistical。

 And that's so calledled principle component bases。 So in the next lecture。

 we're going to talk about a particularly important version of a basis where x transpose X equals I。

