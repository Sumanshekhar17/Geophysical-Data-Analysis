# Geophysical-Data-Analysis

**Assaignment 1**- 

The file monthly_in_situ_co2_mlo.xls contains monthly carbon dioxide concentrations based on continuous measurements taken at the Mauna Loa Observatory on the island of Hawaii. In this file Column 1 is year, Column 2 is month and Column 9 is monthly mean CO2 concentration.   This is famously known as the Keeling Curve.  The data show the inexorable rise in CO2 over time and also a seasonal variability in the CO2 concentration associated with the annual cycle of uptake and release of CO2 by terrestrial plants. Your assignment is to assess if there has been any change in the annual variations in the CO2 concentration over time.

 

1. Define the annual variation as the maximum annual value minus the minimum annual value from the raw data and calculate the mean annual variability during the first half of the record and compare that to the value from the second half of the record. Is the difference significant at the 95% confidence limits?
2. Remove the “noise” in the data associated with the long term rise in CO2 concentration. You can do this by fitting a polynomial to the data. Try a first order (linear), second order (quadratic) and higher order fits (maybe to 5th order) and describe how this changes your results.

Solution - https://github.com/Sumanshekhar17/Geophysical-Data-Analysis/blob/main/Keeling%20Curve%20Data%20-%20Statistical%20Analysis.ipynb


**Assaignment 2**-

1) If you had 1 million random time series—how many would be significantly correlated at the 95 percent confidence limit? How would you test this?

2) The MAT file KVK.mat. Download KVK.mat.contains hourly data of along channel flow (UA), winds (WE,WN), river discharge from the Passaic and Hudson (QP, QH) and tidal amplitude (AMP)

   a) How many data points are there? Using a lagged autocorrelation find out how many degrees of freedom there are.

   b)  Express the wind data as a complex number and find what wind angle has the largest response to sea level (HLOW) and the currents (UA).

   c) Calculate the zero-lag correlation matrix for this data set.

   d) Develop a multiple regression for the UA as a function of HLOW, QP, QH, WN,WE, AMP
