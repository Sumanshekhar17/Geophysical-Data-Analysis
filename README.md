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
   
   
**Assaignment 3**-
This exercise is to compute EOFs of the zonal (east-west) component of wind stress in the equatorial Pacific using monthly average data from the Seawinds scatterometer instrument on the QuikSCAT https://www.jpl.nasa.gov/missions/quick-scatterometer-quikscatLinks to an external site. satellite.

I’d like you to write this as a MATLAB Live Script or Jupyter notebook with plot output inline and using markup text to write your geophysical interpretation of the data.

When you’re done, export your work to a pdf to upload to Canvas. I’m not going to re-run your code but want to see what you did. Pythoneers: you may upload your Jupyter notebook to https://notebooksharing.space/Links to an external site. and submit the link for me to view your analysis (make sure the link works).

Get the data
Part of this exercise is finding and downloading the data.

Go to the NOAA ERDDAP server at: http://coastwatch.pfeg.noaa.gov/erddap/griddapLinks to an external site.

Click Advanced Search and then in the Full Text Search for Datasets box at top left enter the search string wind stress.

Look for the entry that is QuikSCAT global science quality monthly data.

Click the graph link in the table for this data set and begin making your data selection.

You can move the sliders for latitude and longitude, or type the numbers you want, to zoom in on the equatorial Pacific … something like approximately ± 20 or ± 25 in latitude and roughly 145 to 285 in longitude.

Click the button Redraw the graph.

When you are happy with the spatial subset, click Data Access Form (above the browse plot image). Your lon/lat selection has carried over, but now select a time range. Start from 2001-01-01 (last time I looked there were a couple of bad months in 2000).

Stop! This is a lot of data at 0.125-degree lon/lat intervals. You have the option to select only every, say, 3rd or 4th data point by entering a value in the Stride column for latitude and longitude.

From the list of Grid Variables choose only taux (zonal wind stress). Remember you’ll want the coordinates as well.

Under File type, select how you want to receive the data. For Python you’re probably going to want NetCDF. For MATLAB you can also read NetCDF, though you may also select “.mat – Download a MATLAB binary file” and click Submit.

The dataset should download to your computer.

Now you have your data. When you load the data file the data will be probably be in a structure named something like erdQSstressmday.

You may see an extra “singleton” dimension corresponding to “altitude” which is not relevant. Squeeze this dimension out to get rid of it so you have data in three dimensions.

Note – there is a button Just generate the URL. You can bookmark or copy/paste that link to share with colleagues. It saves all the information of your data selection. You could write some code to read this URL directly into your workspace (in MATLAB using websave; Python experts … impress me by showing how to do this for extra credit). Why read directly into thre workspace? Well, if you do it this way you could actually make the lon/lat subset an input parameter to your script to build a modified download URL, allowing you to automate EOF calculations for an arbitrary subdomain (and time range) of the global ocean without downloading intermediate files.

Analysis - Follow the steps we followed in class:
Write your code from scratch, line by line, so you understand what each step does. Don’t just copy my in-class demo code making just a few substitutions.

The QuikScat data have NaNs where there is land. Change them to zero. For extra credit you can go back and do something smarter than this later.

Watch out! There might be some bad data with wild values or occasional NaNs. Deal with them.

You might want to blank out the data in the Gulf of Mexico, but this is not essential. The MATLAB function inpolygon used with a shape selected using ginput would be a nifty way of finding those points and zeroing them out.

Rearrange the data into a 2-D data matrix with dimensions space by time.

Remove the time mean from each time series. Don’t worry about removing a fit to the seasonal cycle – it should come out of the analysis. I will show ways to fit harmonic cycles in a later lecture.

Compute the EOFs by Singular Value Decomposition (SVD).

For modes 1, 2 and 3, plot the spatial mode pattern and its associated time series.

Please show a date on the time axis. In MATLAB convert time to a datenum or datetime so you can label the time axis with datetick. The Metadata link on the ERDDAP page will show you how to interpret the time units. Python probably does this automatically from the NetCDF file attributes.

Note and/or plot how much of the data variance is explained by each mode.

Make some interpretation of the dynamics you observe in terms of El Nino, the seasonal cycle, or other climate variability processes.

Even more extra credit: Test the significance of your modes.
