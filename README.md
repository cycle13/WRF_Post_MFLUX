# WRF_Post_MFLUX
This Folder contains the code to compute the Vertically Integrated Moisture fluxes using WRF model output data. The formula to compute the moisture flux is a follows.

The Atmospheric moisture balance is given by;

![Atmospheric Water Bdget equation](http://latex.codecogs.com/gif.latex?%7B%5Ccolor%7BBlack%7D%20%5Cfrac%7B%5Cpartial%20%7BW%7D%7D%7B%5Cpartial%20t%7D%7D%20%3D%20P%20-%20E%20-%20MFC%20&plus;%20RESW)

Where, terms on L.H.S. is water storage term. While on the R.H.S. we have,

precip (mm/day), 

Evapotranspiration, 

N(Soil Moisture+ Surface runoff + underground runoff), and ,

RSEW is residual

Using WRF 3 hourly 2D surface variables (PRECIP, LH, SMOIS, SROFF,UDROFF) the budget terms have been calculated for every hour and then accumulated on daily basis to obtain daily values.


The MFC has calculated using the following formula:

![MFC EQ1](http://latex.codecogs.com/gif.latex?MFC%20%3D%20-%5Cbigtriangledown.%28QV_%7Bh%7D%29%20%3D%20-V_%7Bh%7D.%5Cbigtriangledown%7BQ%7D%20-%20Q%5Cbigtriangledown.V_%7Bh%7D%2C)

![MFC EQ2](http://latex.codecogs.com/gif.latex?MFC%20%3D%20%5Cunderset%7Badvection%7D%7B%5Cunderbrace%7B%7D%7B-u%5Cfrac%7B%5Cpartial%20Q%7D%7B%5Cpartial%20x%7D%20-v%5Cfrac%7B%5Cpartial%20Q%7D%7B%5Cpartial%20y%7D%20%7D%7D%20-%20Q%5Cleft%20%28%20%5Cunderset%7Bconvergence%7D%7B%5Cunderbrace%7B%7D%7B%5Cfrac%7B%5Cpartial%20u%7D%7B%5Cpartial%20x%7D%20&plus;%5Cfrac%7B%5Cpartial%20v%7D%7B%5Cpartial%20y%7D%20%7D%7D%20%5Cright%20%29)

The file "Calc_Daily_Monthly_fluxes.ncl" calculates Daily and Monthly average values of moisture convergence/divenrgence fluxes obtained by running "Calc_Moisture_FLux.ncl" NCL code.

The "Calc_Moisture_Flux.ncl" file generates daily average moisture convergence/divergence fluxes unit ![unit for fluxes](http://latex.codecogs.com/gif.latex?%5Ctiny%20%7B%5Ccolor%7BRed%7D%20%5Cfrac%7Bkg%7D%7Bm%5E%7B2%7Ds%7D%7D).
The output files has been named as "CTRL_MFC_YYYY_MM_DD.nc".


### Calc_Daily_Monthly_fluxes.ncl
The "Calc_Daily_Monthly_fluxes.ncl" files usage yearly list of CTRL_MFC_YYYY_MM_DD.nc output file and concatenate them using NCO into a yearly file as MFLUX_WRF_CTRL_YYYY.nc.
The NCL sscript read the MFLUX_WRF_CTRL_YYYY.nc file; the code computes the Monthly and daily average of MFC for every grid point over the entire domain. The Monthly and Daily files created and named as 

(i) MFLUX_MONTHLY_YYYY_WRF.nc, 

(ii) MFLUX_DAILY_YYYY_WRF.nc
