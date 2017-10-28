---
layout: post
title: The Curse of Sunshine
tags: plotly python visualization regression
---

It is a common stereotype that warm European countries are less productive than colder ones. Many claim that hot and sunny days cause people to be lazy, and that in general things do not work that smoothly in 40º weather. But is this *actually* true? And conversely, does less sunshine and bad weather actually correlate with a better, healthier economy?

When you meet an Italian expat living in northern Europe and want to have some fun, ask them how they are finding the weather up there. Being one myself, I can tell you that there are few things we like to complain about more than how much we miss the Italian sun. Why, then, are so many of us southerners, used to the warm and lazy life, living in the cold North? Why are we so ready to give up good weather, only to spend our lives complaining about it? 

The answer to this is pretty simple: to get better education, financial security and brighter career prospects. But does it have to be this way? Do we *really* need to give up on sunshine to increase our likelihood of getting a job and be part of a healthy economy, when we move around the continent? 

Long story short....**yes**, pretty much. Turns out that countries kissed by the sun tend indeed to have worse economies. We may have all suspected that: Greece and Portugal were amongst the main victims of the recent crisis, while Italy and Spain are often in the financial newspapers for the worst reasons. But does this apply to other countries as well? I wanted to check whether there is a correlation when considering the whole continent – and turns out this is the case.

I will not try to explain *why* this is the case, but I decided to simply prove it with some simple regression and data visualization. I recently came across this [cool map](https://commons.wikimedia.org/wiki/File:Europe_sunshine_hours_map.png) on Reddit, so I decided to look at how **average sunshine hours** in European countries correlate with a country's economy, using two main indicators: GDP and unemployment rate.

To graph the data I used Python and [Plotly](https://plot.ly/). You can find the code and the (clean) dataset on [my Github](https://github.com/michetonu/europe_sunshine_economy). The graphs are interactive, and not ideal on mobile; you can find the PNG versions [here (GDP)](https://github.com/michetonu/europe_sunshine_economy/blob/master/gdp_sunshine.png?raw=true) and [here (unemployment)](https://github.com/michetonu/europe_sunshine_economy/blob/master/unemployment_sunshine.png?raw=true)

### 1: Gross Domestic Product (GDP) vs Sunshine Duration

While the GDP is not the only measure of a country's economy, it is nonetheless considered one of its best indicators. GDP represents the total value of goods and services produced in a country in a specific year; basically, it can be thought of as the size of a country's economy [[1]](http://www.investopedia.com/ask/answers/199.asp). The GDP per capita is further divided by the population of the country, thus proving a useful number which is independent on country size. I plotted the 2016 GDP per-capita figures for each European country against the total hours of sunshine. The GDP data was provided by the [International Monetary Fund](https://www.imf.org/external/pubs/ft/weo/2017/01/weodata/index.aspx), while the climate figures were obtained using a mixture of national and local sources pulled from the [Wiki page](https://en.wikipedia.org/wiki/List_of_cities_by_sunshine_duration). When a national average wasn't available, I took a mean of the available cities. I also decided to include the average yearly temperature in graph, as well as the total GDP as a reference. 

Here's what came out of it. Note: You can hover on each marker to see the data of the corresponding country.

<iframe width="800" height="500" frameborder="0" scrolling="no" src="//plot.ly/~michetonu/15.embed"></iframe>

A few interesting things can be noticed:

- There is a clear negative correlation between sunshine hours and a country's GDP per capita. 
- Countries with larger total GDP tend to be located above the trendline – meaning that for the same amount of sunshine, they are more productive.
- The UK is the only "big" economy which is underperforming. Everyone who complains about British weather seems to be totally justified.
- Thanks to its small size, Luxembourg has an extremely high GDP per capita, and it would have been an outlier regardless of the amount of sunshine.
- Most of the countries below the line are ex-members of the Eastern Bloc.
- For the same amount of sunshine hours, the average yearly temperature does not seem to correlate with GDP.

*Disclaimer:* some countries (e.g. Cyprus, Slovakia, Russia) were not included because the climate data seemed too unreliable. Apologies.

### 2: Unemployment vs Sunshine Duration

I then decided to use unemployment as my independent variable. We have all heard about the high unemployment rates in Spain, Greece and Italy – all places famous for their sunny weather. But how do the other countries fare? I decided to only look at EU members, since unemployment data for ex-Eastern Bloc countries seem to vary hugely and unpredictably, due to historical and political reasons (e.g. <1% in Belarus, but close to 45% in Bosnia Herzegovina). The fact that the EU has stricter, common employment and welfare laws makes any correlation with external factors (in this case, sunshine hours) both more likely and more useful to draw some conclusions. I also included youth unemployment as a colour scale, to spot any possible patterns. All unemployment data was taken from [Eurostat](http://ec.europa.eu/eurostat/statistics-explained/index.php/Unemployment_statistics).

<iframe width="800" height="500" frameborder="0" scrolling="no" src="//plot.ly/~michetonu/17.embed"></iframe>

A few striking observations can be made here as well:

- There is a **positive** correlation between unemployment and sunshine. That means that countries *below* the trend line tend to have more people employed than what would be expected given their yearly share of sun.
- Italy has a very high rate of youth unemployment given its relatively small distance from the trend line.
- Conversely, Malta –once again– is capitalizing on the most amount of sunshine in the continent by showcasing a fantastic low unemployment rate.
- Luxembourg, this time, is perfectly in line with expectations; so is the UK.
- Bonus: the data points for France, Croatia, and Italy make up the french flag.

### Conclusions?

With some very simple regression and data visualization we confirmed a few stereotypes about European countries. Nations which receive less sunshine during the year tend to have a lower GDP per capita, and higher unemployment rate. We could also see that those countries that are "underperforming", given their share of sunshine, are mostly those who historically have had less chance to develop a strong and stable economy. Interestingly, when I used precipitation data (rainfall) instead of sunshine duration, there was almost no correlation. It is therefore likely that it is not the case of bad weather promoting economic growth, but rather *too much good weather* hindering it. 

But let's be careful – correlation does not necessarily imply causation. Do *siestas* really affect a country's productivity? Does the possibility of going to the beach 6 months a year make you less willing to look for a job? We can't draw those type of conclusions from just a couple of graphs, but it's fun to speculate. 

I'll leave you with a last piece of advice: if you want lots of sunshine, low unemployment, and a decently healthy economy, you should probably move to Malta.
