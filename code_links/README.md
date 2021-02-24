# Links to useful code:
Feel free to add links to your own git-projects etc here. Please add a short description
## MetOs produced code

### NorESM related
- [setup_case_py](https://github.com/sarambl/setup_case_py) -- python based easy way to setup cases in NorESM.
  Idea is a one command program to setup a case with all the details stored in a *.ini file.
- [ERA_interim2noresm](https://github.com/sarambl/ERA_interim2noresm) -- package to download and regrid ERA-Interim to nudge format for NorESM.


### ERA5
- [download ERA5](https://github.com/franzihe/download_ERA5) -- for analysis, e.g. monthly means, hourly; for single level values and pressure level. As for now it downloads globally at 0.25 grid resolution. Can be adjusted to coarser grid and just a region.

### Regridding
- [regrid global data](https://github.com/franzihe/regrid_global_data) -- codes to e.g. regrid ERA5 or CMIP6 gridded data to a common grid for further analysis.

### Forecasts and weather observations
- [plot weathermaps from MEPS/AROME Arctic](https://github.com/franzihe/Weathermap) -- creates specific weathermaps for a chosen area. This can be adjustet to either use the _latest_ initialization or the _archived_ forecasts (change the input directory accordingly).
- [download Radiosonde data and create skewT plots](https://github.com/franzihe/Radiosonde) -- this includes code to download radiosonde observations from the University of Wyoming website (here Stavanger, station #01415). Code to plot a vertical profile of temperature in skewT from MEPS (_latest_ or _archived_ has to be adjusted). In addition, a code to plot a seasonal mean temperature profile of both, UWyoming data and MEPS archived data.



