# **COVID-19 and Global Happiness: A Brief Investigation**
**By: David Carzis, Remy Oktay, Eric Ragan, Daniel Weston, and Paul Zdankiewicz**

## **Problem Understanding: Was it worth it?**

Confronting the COVID-19 pandemic placed an enormous burden on
governments across the planet. A novel virus, it spread with prodigious
speed and forced governments across the globe to institute some of the
strictest lockdowns humanity has seen. Never before has the global
community been so united–our shared history is abound with strife in the
most challenging times, instead of cooperation. Government officials
placed the well-being of society above all else.

Being the most stringent actions ever taken, lockdown measures did
**not** come without serious costs to the individual. As discussed in
the [World Happiness Report
(WHR)](https://worldhappiness.report/ed/2021/social-connection-and-well-being-during-covid-19/),
psychological and physical health declined–a universal phenomenon that
will reverberate for decades to come. Individuals became significantly
more unsatisfied with life and experienced higher rates of depression,
anxiety, and other mental ills. In short, the isolation gnawed at the
sanity of our population’s most vulnerable. As lockdowns have subsided,
cited studies in the same report indicated a stabilization in these
rates; however the scars remain.

Under these assumptions, the initial investigation we will seek to
pursue can be surmised as one simple question: was it worth it? Did the
personal turmoil thrust upon millions of people save a significant
number of lives? Were stricter lockdowns, which undoubtedly degraded
mental health more severely, more effective at preventing death and
prompting vaccination? 

Lockdowns have largely been receding in use over recent months after a
wave of cases in Winter ’21-’22; however a few countries have gone as
far to reimplement strict lockdown protocols. Dissatisfaction and social
rebellion against these measures have only grown more prolific since the
pandemic’s beginning–enlarging from a vocal minority to a steadfast
majority. Once we understand how (and if) the policy impacted happiness, we will turn
our attention to focus on social attitudes that diluted the
effectiveness of measures taken across the globe. 

Our general topic, **Global Happiness and Social Attitudes with
COVID-19,** may provide extremely valuable insights for policymakers as
they work to craft more efficient policy for future pandemics. We seek
to examine different attitudes gauged in the World Happiness Data beyond
simple happiness (such as perception of freedom, corruption, government
trust) and see if these factors relate to vaccine rates and happiness levels
witnessed throughout the pandemic. If we can begin to glimpse into the
fundamental attitudes that impacted the effectiveness of stringent
measures, policymakers may be better prepared for the next crisis to
heighten the success of emergency policy.

## **Data Understanding**

### **Our World in Data**

We used [data on
COVID-19](https://www.kaggle.com/datasets/mathurinache/world-happiness-report)
from Our World in Data (OWID), an online source that informs the public
about diseases as well as topics like poverty, hunger, and inequality.
OWID has compiled daily data on the spread of COVID-19 in most countries
since late February 2020, including the number of new and total cases,
deaths, tests, vaccinations and boosters, an index that measures the
stringency of COVID-19 restrictions in the country, population, GDP per
capita, Human Development Index, and life expectancy.

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 9%" />
<col style="width: 63%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Variable</th>
<th style="text-align: center;">Type</th>
<th style="text-align: center;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;">Location</td>
<td style="text-align: center;">Nominal</td>
<td style="text-align: center;">Country</td>
</tr>
<tr class="even">
<td style="text-align: center;">Year</td>
<td style="text-align: center;">Ordinal</td>
<td style="text-align: center;">Year</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Total cases</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Total cases of COVID-19 that have been recorded in the country</td>
</tr>
<tr class="even">
<td style="text-align: center;">Total deaths</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Total deaths from COVID-19 that have been recorded in the country</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Population</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Population of the country</td>
</tr>
<tr class="even">
<td style="text-align: center;">Median age</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Median age in the country</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Life expectancy</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Life expectancy in the country</td>
</tr>
<tr class="even">
<td style="text-align: center;">New cases (annual)</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Total cases of COVID-19 that were recorded in the country during the year</td>
</tr>
<tr class="odd">
<td style="text-align: center;">New deaths (annual)</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Total deaths from COVID-19 that were recorded in the country during the year</td>
</tr>
<tr class="even">
<td style="text-align: center;">New people vaccinated smoothed (annual)</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Total number of people who received their first COVID-19 vaccine in the country during the year</td>
</tr>
<tr class="odd">
<td style="text-align: center;">New vaccinations (annual)</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Number of COVID-19 vaccines administered in the country during the year</td>
</tr>
<tr class="even">
<td style="text-align: center;">Stringency index (annual)</td>
<td style="text-align: center;">Interval</td>
<td style="text-align: center;">A measure of how strict a country’s lockdown measures were during the year</td>
</tr>
</tbody>
</table>

OWID itself uses various sources to find data for these different
variables. Information on cases and deaths come from Johns Hopkins
University’s COVID-19 Data Repository. Information on tests and
vaccinations come from various official reports, which are specified for
each country (for example, U.S. data comes from the Department of Health
and Human Services and French data is from France’s National Public
Health Agency). Information on other variables is collected from sources
such as the United Nations and World Bank.

In order to compare this data with the data from the World Happiness
Report, we converted it to annual values. Our new dataset had one
observation for each country in 2020 and one in 2021. Some variables,
such as the number of new cases in a country, were summed across all
days, but other variables, such as the stringency index, needed to be
averaged to reflect the fact that summation would not provide any
insight. We then merged this new dataset with the World Happiness
Report’s data from 2020 and 2021.

### World Happiness Report

Our [happiness
data](https://github.com/owid/covid-19-data/tree/master/public/data/vaccinations)
comes from the World Happiness Report, which uses global survey data to
report how people evaluate their own lives. The world happiness report
is a yearly report of around 150 countries that has just reached its
10th anniversary. The report also includes a way to predict a country’s
happiness using log GDP per capita, social support, healthy life
expectancy, freedom to make life choices, generosity, and perceptions of
corruption. We utilized data posted to Kaggle from the years 2018-2021,
where 2018-19 will be used to gauge any difference in happiness levels
pre- and post-Covid. 

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 1%" />
<col style="width: 92%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: center;">Variable</th>
<th style="text-align: center;">Type</th>
<th style="text-align: center;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;">Country name</td>
<td style="text-align: center;">Nominal</td>
<td style="text-align: center;">Name of country the data is collected from.</td>
</tr>
<tr class="even">
<td style="text-align: center;">Year</td>
<td style="text-align: center;">Interval</td>
<td style="text-align: center;">The year the data is calculated for.</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Happiness Score</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">The national average response to the Gallup World Poll (GWP) question of life evaluations. The question is “Please imagine a ladder, with steps numbered from 0 at the bottom to 10 at the top. The top of the ladder represents the best possible life for you and the bottom of the ladder represents the worst possible life for you. On which step of the ladder would you say you personally feel you stand at this time?”</td>
</tr>
<tr class="even">
<td style="text-align: center;">Log GDP per capita</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">GDP per capita is the total monetary or market value of all the finished goods and services produced within a country’s borders divided by the population. Log GDP per capita means that every step up the y-axis is an identical percent change in real GDP per capita. Plotting things in natural logs we can see the percent increases, rather than the absolute increases.</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Social Support</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">The national average of the binary responses (either 0 = no or 1 = yes) to the GWP question “If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?”</td>
</tr>
<tr class="even">
<td style="text-align: center;">Healthy life expectancy</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">Healthy life expectancies at birth are based on the data extracted from the World Health Organization’s Global Health Observatory data.</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Freedom to make life choices</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">The national average of responses to the GWP question “Are you satisfied or dissatisfied with your freedom to choose what you do with your life?”</td>
</tr>
<tr class="even">
<td style="text-align: center;">Generosity</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">The residual of regressing national average of response to the GWP question “Have you donated money to charity in the past month?” on GDP per capita.</td>
</tr>
<tr class="odd">
<td style="text-align: center;">Perceptions of Corruption</td>
<td style="text-align: center;">Ratio</td>
<td style="text-align: center;">The national average of the survey responses to two GWP questions: “Is corruption widespread throughout the government or not?” and “Is corruption widespread within businesses or not?” The overall perception is just the average of the two 0 or 1 responses. In case the perception of government corruption is missing, the perception of business corruption is used as the overall perception. The corruption perception at the national level is just the average response of the overall perception at the individual level.</td>
</tr>
</tbody>
</table>

## **Data Exploration**

To begin exploring, we consider how to distribution of happiness may, or
may not have changed as a result of the pandemic. The World Happiness
Report indicated that many people did suffer mental issues, however we
seek to validate their claim and whether it holds significance. To test
the claim, we created the difference in happiness across all countries
between 2019 and 2020, and 2019 and 2021 respectively–we will run a
one-sample t-test on this country-by-country differenced data.

Happiness (pre-COVID-19)

![](/gh_images/Histogram%20of%20Happiness%20(Pre-COVID-19)%20-%20Screenshot.jpg)

Happiness (during COVID-19)

![](/gh_images/Histogram%20of%20Happiness%20(Post-COVID-19)%20-%20Screenshot.jpg)

While these graphs seem to indicate that happiness did not significantly
change between the two periods, we will also perform a t-test on the
difference between the happiness scores of the periods. If we did not
use differenced data, we would have to perform a paired t-test.

<table>
<thead>
<tr class="header">
<th style="text-align: center;">Value Being Tested</th>
<th style="text-align: center;">P-value</th>
<th style="text-align: center;">Significant?</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: center;">Difference Between 2019 and 2020 Mean Happiness</td>
<td style="text-align: center;">0.557</td>
<td style="text-align: center;">No</td>
</tr>
<tr class="even">
<td style="text-align: center;">Difference Between 2019 and 2021 Mean Happiness</td>
<td style="text-align: center;">0.237</td>
<td style="text-align: center;">No</td>
</tr>
</tbody>
</table>

The results of the t-tests are insignificant. We can not conclude
happiness has shifted in any direction since the pandemic began;
however, we find that the mean happiness level is relatively stable
across both periods, with happiness levels rising throughout the
pandemic by a very small (insignificant) amount. In the face of this, it
is prudent to consider any other correlations that exist between the
data features. To visualize this, we will construct a correlation
matrix.

![](/gh_images/Heatmap%20of%20Correlations%20(Total%20Data)%20-%20Screenshot.jpg)

The above correlation plot visualizes any relations between the Covid
data and World Happiness data between 2020-21. This particular graph
does not indicate any noticeable relations, but we will also present the
individual correlation plots for individual years to possibly identify
any differences between the specific years.

Correlation plot for 2020:

![](/gh_images/Heatmap%20of%20Correlations%20(2020)%20-%20Screenshot.jpg)

Correlation plot for 2021:

![](/gh_images/Heatmap%20of%20Correlations%20(2021)%20-%20Screenshot.jpg)

The individual years do not present a much different picture than the
holistic view, unfortunately. While happiness and COVID-19 do not appear
to have a meaningful connection on a global scale in this dataset, we
still seek to provide insights for government officials that can be
useful in improving the well-being of their citizens. To this end, we
continue by exploring the qualities that impact happiness within the
World Happiness Report dataset. By seeing what makes a country happier,
other countries may be able to mirror these general guidelines in order
to collectively increase happiness and make the “insignificant”
difference “significant” even in trying times.

Using the correlation matrices, we present some of the more interesting
correlations that presented themselves that may be useful for
governments to learn from.

![](/gh_images/Scatterplot%20of%20Happiness%20vs.%20Corruption%20-%20Screenshot.jpg)

While not a linear fit, a nonlinear correlation may exist in this model.
Either way, the general message is clear–if more citizens perceive their
country as corrupt (a corruption index value closer to 1), then
happiness is bound to decline; meanwhile, citizens who believe their
governments above-board generally grade higher happiness scores.

Next, we consider happiness and how an individual perceives their
individual freedom as a country’s citizen.

![](/gh_images/Scatterplot%20of%20Happiness%20vs.%20Freedom%20-%20Screenshot.jpg)

The strongest correlation yet has been found. While a seemingly obvious
thing, this quality is integral to making any citizen happy. Far too
often we get lost in the minute details and fail to consider the big
picture. As Americans, it is a privelege we take for granted, but for
many others it is a gift that would drastically increase the quality of
their lives under government oppression.

In fact, the freedom to make life decisions is also shown to positively
correlate with life expectancy, which in turn positively correlates to
happiness score. The longer people live, the more interconnected
families become and heighten life satisfaction–therefore it is integral
that despite the lack of statiscial evidence between covid and
happiness–governments protect the health and safety of its citizens from
a pandemic that ravages its population and slashes its life expectancy.

![](/gh_images/Scatterplot%20of%20Life%20Expectancy%20vs.%20Freedom%20-%20Screenshot.jpg)

![](/gh_images/Scatterplot%20of%20Life%20Expectancy%20vs.%20Corruption%20-%20Screenshot.jpg)

These scatter plots make it clear that life expectancy is negatively
impacted in a country where government corruption is abound (at least as
perceived by its citizens, and in a nonlinear fashion) and that freedom
is positively correlated to life expectancy. To drive the relation home,
we will visualize the relation between life expectancy and the happiness
score.

![](/gh_images/Scatterplot%20of%20Happiness%20vs.%20Corruption%20-%20Screenshot.jpg)

We will revisit these relations in a later linear machine learning
model. In the meantime, we also wish to consider one last possible
connection between happiness and COVID-19, that also has the possiblity
of impacting life expectancy: vacciantions in coountries across the
globe. To consider this possible relation, we will utilize the “new
vaccinations” from only 2021 since vaccines only began to be
administered in late 2020 for a select few countries.

![](/gh_images/Scatterplot%20of%20Happiness%20vs.%20New%20People%20Vaccinated%20Per%20Capita%20(2021).png)

From initial 2021 data, we can surmise a positive relation between more vaccines per capita (a normalized version of the "new_people_vaccinated_smoothed_Y") and happiness. This follows our general intution that countries that work to ensure a higher life expectancy (say via national vaccination campaigns), the more happy that society is as familial units coexist for longer periods of time.

## **Machine Learning Algorithm**

To capitalize on the relation between this newly discovered
relationship, we construction a Linear Regression algorithm to ascertain
a numeric relationship between our target variable, happiness scores,
and new vaccinations per capita in each country. It is important to note
that this algorithm will only be able to use 2021 data contained with
the “t21” dataframe given that this was the first year vaccinations were
widely available to the general public.

![](/gh_images/ML%20-%20Happiness%20vs.%20New%20Vaccinations%20-%20Screenshot.jpg)

The optimal degree of polynomial to include in the model is degree 3,
which minimzed the model’s cost function. From this model, we can see a
clear, positive trend where the more new vaccinations per capita in
2021, the happier its citizens were. This general idea relates closely
to the EDA findings above: a longer life expectancy contributes to a
happier populace. By allowing families to lengthen generational ties, a
higher life satisfaction is likely to result and provide support needed
during especially trying times–including pandemics.

Additionally, we seek to delineate a predictive relationship between
life expectancy and another feature–the strongest relation we see is
between an individual’s perceived “freedom of choice”. We investigate
this relaton up next, but first we must update the dataset to remove a
single observation who did not report life expectancy.

![](/gh_images/ML%20-%20Life%20Expectancy%20vs.%20Freedom%20-%20Screenshot.jpg)

The resulting model ran optimally, with the lowest cost function, at a
degree 2 polynomial; however, the cost function is still relatively high
, suggesting that the model is highly biased. Despite having one of the
strongest relationships, it is likely that better explanatory variables
exist, which would form a better model. In terms of our output, however,
the upwards trend is clear–the more free a citizen feels in their own
country, the higher the predicted life expectancy becomes.

This may create an interesting area of contention, as many have placed
“freedom of speech” and “new vaccinations” at odds with each other, as
companies and governments across the globe have mandated vaccines. The
regulations have spurred many protests as citizens advocate for their
“freedom of choice.” It will be interesting to see how this contrast may
play out in the coming years as more data becomes publicly available.

## **Conclusion and Future Studies**

As we conclude our cursory, exploratory analysis of the COVID-19 dataset
and World Happiness Report dataset, we determined that happiness did not
significantly shift globally between 2019 and 2020-21, contradicting the
generally accepted principle that global happiness plunged throughout
the pandemic. Without discrediting the personal struggles faced by many
over the past 2 years, the insignificant results may seem to suggest a
“slowing” rather than a complete reversal of happiness trends.

In pursuit of investigating what governments can do to recover that
trend we surmise a general goal they can achieve, which is particularly
poignant in these volatile times: prioritize the health of your
citizens. We found countries with higher life expectancies had happier
citizens, a feat aided by widespread vaccination campaigns to counter
the pandemic. Governments must double down on these efforts.

We also foudn clues of insitutional features governments can seek to
refine as they try to work for the people–one such feature is promoting
a freer society in which citizens can live. If citizens are fearful or
in an oppressive government, etc., life expectancies in those countries
are found to be lower–governments shoudl prioritize reorganizing and
strengthening their insitutions that ensure individual liberties. Doing
so will only fortify a citizen’s ability to thrive in society and push
for the collective betterment (through longer life expectancies), which
in turn increase long run happiness.

In the future, additional research may seek to rigorously expand and
find new features beyond our dataset. We found the happiness metric and
associated data to be somewhat limiting as we got deeper into analysis
and more comprehenisve and detailed data may be more useful. Moreover,
it would be beneficial to allow additonal data over the coming years to
be recorded and return to this topic, and additionally focus on one
country across a plethora of features instead of an expansive, global
comparison. Refining focus further may provide more insight than
annualized, global data could provide.

Our Google Colaboratory file can be accessed
[here](https://colab.research.google.com/drive/1Me2gdZBcbn0M2oz2uZt-WJ4FPCjxo8UX#scrollTo=WoMZdh6XpPOC).

## More Information

### IO Page

-   Our IO page can be accessed here.

### Videos

-   Tutorial
-   Presentation

### Data Sources

-   [World Happiness Report
    data](https://github.com/owid/covid-19-data/tree/master/public/data/vaccinations)

-   [Our World in Data
    data](https://www.kaggle.com/datasets/mathurinache/world-happiness-report)

### Acknowledgements

-   [World Happiness
    Report](https://worldhappiness.report/ed/2021/social-connection-and-well-being-during-covid-19/)
