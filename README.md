# WRF_Post_MFLUX
This Folder contains the code to compute the Vertically Integrated Moisture fluxes using WRF model output data.

The file "Calc_Daily_Monthly_fluxes.ncl" calculates Daily and Monthly average values of moisture convergence/divenrgence fluxes obtained by running "Calc_Moisture_FLux.ncl" NCL code.

The "Calc_Moisture_Flux.ncl" file generates daily average moisture convergence/divergence fluxes ![unit for fluxes](http://latex.codecogs.com/gif.latex?%7B%5Ccolor%7BRed%7D%20%5Cfrac%7Bkg%7D%7Bm%5E%7B2%7Ds%7D%7D).
The output files has been named as "CTRL_MFC_YYYY_MM_DD.nc".


### Calc_Daily_Monthly_fluxes.ncl
The "Calc_Daily_Monthly_fluxes.ncl" files usage yearly list of CTRL_MFC_YYYY_MM_DD.nc output file and concatenate them using NCO into a yearly file as MFLUX_WRF_CTRL_YYYY.nc.
The NCL sscript read the MFLUX_WRF_CTRL_YYYY.nc file; the code computes the Monthly and daily average of MFC for every grid point over the entire domain. The Monthly and Daily files created and named as 

(i) MFLUX_MONTHLY_YYYY_WRF.nc, 

(ii) MFLUX_DAILY_YYYY_WRF.nc

![Atmospheric Water Bdget equation](http://latex.codecogs.com/gif.latex?%7B%5Ccolor%7BBlack%7D%20%5Cfrac%7B%5Cpartial%20%7BW%7D%7D%7B%5Cpartial%20t%7D%7D%20%3D%20P%20-%20E%20-%20MFC%20&plus;%20RESW)
