---
date: 2018-04-11
slug: forecasting-competitions
title: "A history of forecasting competitions"
mathjax: true
categories:
  - forecasting
  - reproducible research
  - time series
---

Prediction competitions are now so widespread that it is often forgotten how ground-breaking they were when first held, and how influential they have been over the years.

While [Kaggle](http://kaggle.com) competitions and the [KDD cup](http://www.kdd.org/kdd-cup) are well-known, similar competitions have been held for many, many years. To keep this history manageable, I will only consider time series forecasting competitions here.

### Newbold & Granger (1974)

The earliest non-trivial study of time series forecast accuracy was probably Newbold & Granger (JRSSA, 1974), involving 106 time series. Although they did not invite others to participate, they did start the discussion on what forecasting methods are the most accurate for different groups of time series. They used a scaled version of MSE to compare the results. The article was published along with some discussion, which reveals some of the erroneous thinking of the time.

One important feature of the results was the empirical demonstration that forecast combinations improve accuracy. Yet one discussant (GJA Stern) stated
> The combined forecasting methods seem to me to be non-starters ... Is a combined method not in danger of falling between two stools?

Another (Maurice Priestley) said
>The authors' suggestion about combining different forecasts is an interesting one, but its validity would seem to depend on the assumption that the model used in the Box-Jenkins approach is inadequate---for otherwise, the Box-Jenkins forecast alone would be optimal.

This reveals a view commonly held (even today) that there is some single model that describes the data generating process, and that the job of a forecaster is to find it. This seems patently absurd to me, and George Box famously dismissed it saying ["All models are wrong but some are useful"](https://en.wikipedia.org/wiki/All_models_are_wrong).

There is also a strong bias against automatic forecasting procedures. For example, Gwilym Jenkins says
>  The fact remains that model building is best done by the human brain and is inevitably an iterative process.

Subsequent history has shown that to be untrue provided enough data is available.


### Makridakis M-competitions

As far as I know, the first true time series forecasting competition was organized by Spyros Makridakis and Michèle Hibon who put together a collection of 111 time series and invited expert time series analysts to produce forecasts. The resulting JRSSA paper caused quite a stir, and the discussion published along with the paper is entertaining, and at times somewhat shocking.

Maurice Priestley was in attendance again and was clinging to the view that there was a true model waiting to be discovered:
>I do not believe that it is very fruitful to attempt to classify series according to which forecasting techniques perform "best". The performance of any particular technique when applied to a particular series depends essentially on (a) the model which the series obeys; (b) our ability to identify and fit this model correctly and (c) the criterion chosen to measure the forecasting accuracy.

To which, Makridakis and Hibon replied
> There is a fact that Professor Priestley must accept: empirical evidence is in *disagreement* with his theoretical arguments.

Many of the discussants seem enamoured with ARIMA models.
> It is amazing to me, however, that after all this exercise in identifying models, transforming and so on, that the autoregressive moving averages come out so badly. I wonder whether it might be partly due to the authors not using the backwards forecasting approach to obtain the initial errors. --- *W.G. Gilchrist*

> I find it hard to believe that Box-Jenkins, if properly applied, can actually be worse than so many of the simple methods --- *Chris Chatfield*

> Why do empirical studies sometimes give different answers? It may depend on the selected sample of time series, but I suspect it is more likely to depend on the skill of the analyst and on their individual interpretations of what is meant by Method $X$ ... these authors are more at home with simple procedures than with Box-Jenkins. --- *Chris Chatfield*

Again, Makridakis & Hibon responded:
> Dr Chatfield expresses some personal views about the first author ... It might be useful for Dr Chatfield to read some of the psychological literature quoted in the main paper, and he can then learn a little more about biases and how they affect prior probabilities.

As a result of this paper, researchers started to:

 * consider how to automate forecasting methods;
 * study what methods give the best forecasts;
 * be aware of the dangers of over-fitting;
 * treat forecasting as a different problem from time series analysis.


Makridakis \& Hibon followed up with a new competition in 1982:

 *  1001 series
 *  Anyone could submit forecasts (avoiding the charge of incompetence)
 *  Multiple forecast measures used.




### M-competition}

\structure{Main findings\hfill\small (taken from Makridakis \& Hibon, 2000)}

 *  Statistically sophisticated or complex methods do not necessarily provide more accurate forecasts than simpler ones.
 *  The relative ranking of the performance of the various methods varies according to the accuracy measure being used.
 *  The accuracy when various methods are being combined outperforms, on average, the individual methods being combined and does very well in comparison to other methods.
 *  The accuracy of the various methods depends upon the length of the forecasting horizon involved.




### Makridakis and Hibon (2000)

``The M3-Competition is a final attempt by the authors to settle the accuracy issue of
various time series methods\dots\ The extension involves the inclusion of more methods/ researchers (in particular in the areas of neural networks and expert systems) and more series.''

 *  3003 series
 *  All data from business, demography, finance and economics.
 *  Series length between 14 and 126.
 *  Either non-seasonal, monthly or quarterly.
 *  All time series positive.
 *  M\&H claimed that the M3-competition supported the findings of their earlier work.
 *  However, best performing methods  far from ``simple''.




### Makridakis and Hibon (2000)}\fontsize{12.5}{14.3}\sf

\structure{Best methods:}
\begin{block}{Theta}
\begin{itemize}
 *  A very confusing explanation.
 *  Shown by Hyndman and Billah (2003) to be average of linear regression and simple exponential smoothing with drift, applied to seasonally adjusted data.
 *  Later, the original authors claimed that their explanation was incorrect.




 *  A commercial software package with an unknown algorithm.
 *  Known to fit either exponential smoothing or ARIMA models using BIC.





The ["M" competitions](https://en.wikipedia.org/wiki/Makridakis_Competitions) organized by Spyros Makridakis have had an enormous influence on the field of forecasting. They focused attention on what models produced good forecasts, rather than on the mathematical properties of those models. For that, Spyros deserves congratulations for changing the landscape of forecasting research through this series of competitions.

[Makridakis & Hibon, (JRSSA 1979)](http://www.jstor.org/stable/2345077) was the first serious attempt at a large empirical evaluation of forecast methods. It created heated discussion, and was followed by the M-competition comprising 1001 time series that participants were invited to forecast. The results were published in [Makridakis et al (JF 1982)](https://doi.org/10.1002/for.3980010202)

The M2 competition focused on different issues and involved a much smaller data set, but with richer contextual information about each series.

Twenty years after the first competition, the M3 competition was held, involving 3003 time series. Unfortunately, many of the algorithms used are not discussed in sufficient detail to replicate the results, but the resulting comparisons are published in [Makridaks & Hibon, (IJF 2000)](https://doi.org/10.1016/S0169-2070(00)00057-1). The M3 data have continued to be used since 2000 for testing new time series forecasting methods. In fact, unless a proposed forecasting method is competitive against the original M3 participating methods, it is difficult to get published in the IJF.

sMAPE

Now, almost 20 years later again, Makridakis is organizing the M4 competition. Details are available at [https://www.m4.unic.ac.cy/](https://www.m4.unic.ac.cy/). This time there are 100,000 time series -- surely enough to ensure any differences in accuracy between methods are statistically significant. Astute readers might recall an aborted attempt at an M4 competition a few years ago. For various reasons, that never got off the ground.

sMAPE/MASE

MIS

Since the M3 competition, I have talked to Spyros a few times about what a new competition should look like. My view is that it should not jd.ust be a repeat of old competitions with larger data sets, but should look at new features of forecasting, or new types of data.




For more details about the M4 competition see [this post](/hyndsight/m4competition/) or go to the [M4 website](https://www.m4.unic.ac.cy/).


Unfortunately, once again only annual, quarterly and monthly data are included. Given the widespread availability of more frequent data these days, this seems anachronistic, and limits comparisons to relatively simple seasonal methods. I would have liked to see daily and hourly data included, so that multiple seasonal patterns could be present in some of the time series.

It does not appear that there will be multiple submissions allowed over time, with a leaderboard tracking progress (as there is, for example, in a Kaggle competition). This is unfortunate, as this element of a competition seems to lead to much better results. See my paper on [The value of feedback in forecasting competitions](/publications/kaggle/) with George Athanasopoulos for a discussion. I am disappointed that this feature does not appear to be part of the plans for the M4 competition.

Despite my misgivings, I hope this competition will produce some useful results that guide future forecasting research. At the very least, a large collection of 100,000 time series will provide a much needed replacement for the M3 data which have been "done to death" over the years.

### Tourism forecasting

George Athanasopoulos

Focused on one domain

Predictor variables included

Time series data publicly available, but not predictor information

Kaggle feedback paper

tscompdata??

### Transportation

Similar idea -- Tcomp

Never published, but data still available

### Global Energy Forecasting Competitions (GEFCom)

Tao Hong

IJF

Criteria

2014: Participants provide full forecast distributions by submitting the percentiles from 1% to 99%, and a probability scoring method (CrPS) used for evaluation.  Even if we just stick to intervals, at least we could have a range of probability coverages (e.g., 50%, 80%, 95%, 99%) to give some more detailed idea of the forecast distribution in each case.

Probabilistic scoring

### Wikipedia

??/
