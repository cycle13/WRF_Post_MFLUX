# WRF_Post_MFLUX
This Folder contains the code to compute the Vertically Integrated Moisture flux using WRF model output data.
The code "Calc_Daily_Monthly_fluxes.ncl" calclates Daily and Monthly averaged values of obtained after running "Calc_Moisture_FLux.ncl" code.
### Calc_Daily_Monthly_fluxes.ncl
The "Calc_Daily_Monthly_fluxes.ncl" files usage list of CTRL_MFC_YYYY_MM_DD.nc in an year and concatenate using NCO into a yearly file as MFLUX_WRF_CTRL_YYYY.nc. 
After reading the MFLUX_WRF_CTRL_YYYY.nc; the code computes the Monthly and daily average of MFC for every grid point over the entire domain. The Monthly and Daily files got created are (i) MFLUX_MONTHLY_YYYY_WRF.nc, (ii) MFLUX_DAILY_YYYY_WRF.nc

![equation](http://latex.codecogs.com/gif.latex?P%28s%20%7C%20O_t%20%29%3D%5Ctext%20%7B%20Probability%20of%20a%20sensor%20reading%20value%20when%20sleep%20onset%20is%20observed%20at%20a%20time%20bin%20%7D%20t)
