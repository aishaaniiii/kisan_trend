Hello and welcome to KisanTrend! 

This is the project submission for NASA Space Apps, for the 'Be An Earth System Trend Detective!'. 

Objectives: 
Choosing which data to monitor.

The first question to ask is what the aim is for this project: 

Explore trends in India that can be useful for farmers (or Kisan in Hindi). This was inspired by the SMAP satellite that I learnt about 5 years ago, and I will use data adjacent to it here. 

The data invovles:
- Root zone soil moisture from GLDAs. It let's us know how much water is available in soil (in draught this can be too little, while in Monsoon, soil can be too moist and rot the plants).
- Total precipitation rate. Similar to the one above, but this should us the Rainfall trend over farmland, which can be used for initial sowing times.
- Max 2m Air Temperature. Peak daytime heat at the crop canopy height. Too warm and the crops get crispy, too cold and they can die.
- NDVI, Vegetation health. This is a 'Greenness Index', measures how dense and healthy crops are from space, can be then connect to the trends in variables mentioned above and for future analysis. Also can be used to see how crops perform in rainy seasons versus seasons of draught.

For data the following was used: 
https://power.larc.nasa.gov/data-access-viewer/ 
<img width="606" height="693" alt="image" src="https://github.com/user-attachments/assets/cb837f4e-bfb7-47a6-b469-67eef4426dfe" />


How was the data parsed + analysed? 
- India experiences dramatic seasonal swings every year, due to Monsoon in July/August (known as Savan) or winter cooling. These would fog up the plot if we are trying to identify trends over several years, so they were excluded for this.
- Statistical Significance Testing: separates long-term environmental shifts from random year-to-year weather noise, each variables is evaluated using:
    - Ordinary least squares linear regression + t-test: fits a straight trend line through the deseasonalised anomalies to measure the slope (rate of change per year) and a 95% confidence interval. This checks whether the slope is significantly different from zero (i.e. is there a growing trend? ).
    - Mann-Kendall trend test, as suggested in the project description. A non-parametric rank based test, used in hydrology and climate science. A standard linear regression assumes that data follows the bell-curve, this method does not and is less sensitive to extremem weather outliers. It outputs a variable 'tau', from -1 to +1 and a p-value.
    - Interpreting results: a p-value < 0.05 (or of 95% confidence level) indicates that the trend is statistically significant, and unlikely to have occurred by random change.
 
Final Graph: 
<img width="3442" height="2237" alt="punjab_trends_summary" src="https://github.com/user-attachments/assets/2b71fc1d-85be-4ab5-bc01-4931e371b083" />




