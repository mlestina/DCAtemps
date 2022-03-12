# Analysis of temperature trends over the last 77 years in Washington DC (DCA airport)

Everyone is aware of global worming caused by the increased CO2 content and CH4 content in our atmosphere, the former being caused by 
the combustion of fossile fuels and the latter being caused by thawing of tundra and gas flares. It is also well known that the international 
community (i.e. the Paris Agreement of 2015) strives to limit global warming to about 1.5 Celsius degrees (i.e. 2.7 Fahrenheit degrees) 
as compared to pre-industrial levels.

This project looks at temperature changes at Washington, DC's Reagan National Airport (aka DCA) over the last 77 years. I graph out the 
average highs and average lows for each month over the 77 year period (24 graphs) to see if certain months have larger temperature increases than others,
and whether any patterns or conclusions can be drawn from the graphs. I also examine extreme highs and lows (i.e. winter lows and summer highs), 
and see whether global warming manifests in the frequency of extreme temperatures.

The data was imported from the National Centers for Environmental Information of NOAA (i.e. the National Weather Service).  For convienence, temperatures are in Fahrenheit.

Project starts off by graphing the average highs, the average lows and the average mean temperatures for the entire year:

![image](https://user-images.githubusercontent.com/28972117/158034746-2b0f4fcf-55ce-485e-b105-2e6bcad0d6b5.png)

It appears that temperatures overall increased by about 2.5 Fahrenheit degrees at DCA from the end of WW II to today, suggesting that Washington DC has approached the 2015 Paris Agreement limit of 2.7 Fahrenheit degrees.

![image](https://user-images.githubusercontent.com/28972117/158034792-92b25fe7-bf90-48b8-9a65-d7a924aa2b42.png)

daily highs seemed to increas only about 1.5 Fahrenheit degrees in this period

![image](https://user-images.githubusercontent.com/28972117/158034795-ac1b9214-ec46-4135-ac86-17a701897e62.png)

however daily lows seemed to hav increased about 3 Fahrenheit degrees over this 77 year period, suggesting that an outsized proportion of the global warming is reflected in the daily minimum temperatures
With that, I will now focus on the coldest months of the year for df3, that being Dec thru Feb. This presents a small problem because December is of a different year than Jan and Feb. I'll remedy this issue by adding a new column called 'season' to allow for December to be grouped in the same season as Jan and Feb of the next calendar year

I now proceed to calculate the average low temperature in Fahrenheit for each winter season of Dec 1 to Feb 28 for each season from 1945/1946 to 2021/2022 and print and then plot the results

![image](https://user-images.githubusercontent.com/28972117/158034861-e81f1635-3eed-40c7-9736-a2b3f8abb81a.png)

There seems to be a wide variance in the average winter seasnonal daily low temperature making it difficult to determine how much of an increase it had over the 77 year period. Even after applying a 7 year rolling average as in the above right graph, it is difficult to determine the increase of winter nightly average lows over the 77 year period.
Now, I will focus on the number of nightly lows each season that dropped below a certain threshold. I played around and it seamed that a threshold of 20F gave significant data

![image](https://user-images.githubusercontent.com/28972117/158034898-611866ce-5035-4469-a81a-354e5e7b81ec.png)

data and graphs above seemed to show a steady drop in the occurrences of winter nightly lows well below the norm. Due the the high fluctuation, a rolling mean is appied to the right graph to try to clarify the results.

![image](https://user-images.githubusercontent.com/28972117/158034915-de8399d2-82ee-4d04-836a-971577dcb176.png)

As can be seen above, the number of daily highs exceeding 90F has dramatically increased over the last 77 years, indicating that the warmer months at DCA are experiencing an outsized global warming effect
now I will calculate and plot the average nightly lows for each year for the coldest month of the year (January) and the warmest month of the year (July) to see how they compare

![image](https://user-images.githubusercontent.com/28972117/158034929-4b94ea58-60b0-4c82-ab16-3c27880cbbb8.png)

Suprisingly, it appears that the average nightly lows for July have increased as much or more overe the 77 year period as compared to the average nightly lows for January. It appears that I may have been focussed too much on the lack of extreme low temperatures as a manifestation of global warming in Washington DC. To the contrary, it is the warmer months in Washington DC that seem to exhibit and outsized increase of temperature over the 77 year period.
I will now plot the average low for each month and the average high for each month for each year for the 1945 to 2022 time frame. I will then use Seaborn's FacetGrid function to make a grid plot of these 24 graphs (12 months * min and max variants). This will involve a groupby call for each of Min and Max temps, a merging of these two dataframes, and the use of the FacetGrid function to make the 24 plots. Before merging, column names for TMAX and TMIX will each become 'temp', a flag column 'attr' will be formed that tells whether the temperature listed in the temp column is a high or a low temp.
The 24 graphs will show how the daily lows and the daily highs for each month have varied over the last 77 years. A horizontal graph will indicate no change in temperature, and an inclined graph will indicate warming thru the period. By placing all 24 plots side by side, comparison can easily be made as to which months and which attribute (daily temperature highs or lows) experienced the greatest increase in temperature.

![image](https://user-images.githubusercontent.com/28972117/158034938-3809f536-0c09-4171-b0b5-f53b188a0db7.png)

After spanning all 24 combinations (12 months by max or min temps), it seems that the warmer months (both for daily lows and daily highs) had an outsized increase in temperature as compared to other months. For example, the above graph shows how the daily temperatures of July and December have increased over the 77 year window. However many months show little change, like January and November. In general, summer months, seemed to have the greatest increase.

A second observation is that most graphs showed a significant increase over the last 10 or so years, the increase often being equal to or more than the previous 65 years. This shows that global warming may be accelerating, and that there is a positive reinforcement effect in place.

