# surfs_up

## Overview and Purpose

The purpose of this analysis is to analyze temperature statistics in Oahu for June and December in order to determine if opening a surf and ice cream shop business year-round is sustainable. To do this analysis, we used the SQLalchemy library in Python and obtained data from a SQLite database that had the temperature information. 


## Results

Here is the summary information for the temperatures in June: 

![june](https://github.com/tylerfallon/surfs_up/blob/main/june_temps.png?raw=true)

Here is the summary information for the temperatures in December:

![dec](https://github.com/tylerfallon/surfs_up/blob/main/dec_temps.png?raw=true)

- Analyzing the data, it can be seen that there are more recorded temperatures in June (1700) than in December (1517). 

- The average temperature in June was higher than the average temperature in December. June had an average temperature of 74.944118 degrees while December had an average temperature of 71.041529 degrees. 

- December has a wider distribution of temperature data compared with June. This can be seen by comparing the Standard Deviations of the data and looking at the 25%, 50%, and 75% values. December's temperature data had a standard deviation of 3.745920, while June's temperature data had a standard deviation of 3.257417. 

## Summary

After analyzing the data, it can be determined that the weather in June is better for the ice cream shop to be open due to a higher average temperature, higher maximum/minimum temperatures, and a lower standard deviation in the temperature data. However, the difference is not that large between the two opposing months, so it should not have a huge impact on the ability to open a shop. 

In order to have more data to make a decision, we could take into account information such as the precipitation levels for each month, as varying levels of rain could affect operations. 

To obtain the precipitation information for the month of June, I would use the query:

`session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()`

To obtain the precipitation information for the month of December, I would use the query:

`session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()`
