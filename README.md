# WRF_Post_MFLUX
This Folder contains the code to compute the Vertically Integrated Moisture flux using WRF model output data.
The code "Calc_Daily_Monthly_fluxes.ncl" calclates Daily and Monthly averaged values of obtained after running "Calc_Moisture_FLux.ncl" code.
### Calc_Daily_Monthly_fluxes.ncl
The "Calc_Daily_Monthly_fluxes.ncl" files usage list of CTRL_MFC_YYYY_MM_DD.nc in an year and concatenate using NCO into a yearly file as MFLUX_WRF_CTRL_YYYY.nc. 
After reading the MFLUX_WRF_CTRL_YYYY.nc; the code computes the Monthly and daily average of MFC for every grid point over the entire domain. The Monthly and Daily files got created are (i) MFLUX_MONTHLY_YYYY_WRF.nc, (ii) MFLUX_DAILY_YYYY_WRF.nc
