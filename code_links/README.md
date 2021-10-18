# Links to useful code:
Feel free to add links to your own git-projects etc here. Please add a short description
## MetOs produced code

### NorESM related
- [setup_case_py](https://github.com/sarambl/setup_case_py) -- python based easy way to setup cases in NorESM.
  Idea is a one command program to setup a case with all the details stored in a *.ini file.
- [ERA_interim2noresm](https://github.com/sarambl/ERA_interim2noresm) -- package to download and regrid ERA-Interim to nudge format for NorESM.


### Reanalysis (ERA-Interim and ERA5)
- [download ERA-Interim](https://github.com/hannasv/MS/tree/master/download_reanalysis_data) -- scripts for downloading ERA interim can be found in directory [downloading_era_interim](https://github.com/hannasv/MS/tree/master/download_reanalysis_data/downloading_era_interim) and ERA5 in [download_ERA5](https://github.com/hannasv/MS/tree/master/download_reanalysis_data/download_ERA5). Inspired by [ECMWF's own instructions](https://confluence.ecmwf.int/display/WEBAPI/Access+ECMWF+Public+Datasets). 
- [download ERA5](https://github.com/franzihe/download_ERA5) -- for analysis, e.g. monthly means, hourly; for single level values and pressure level. As for now it downloads globally at 0.25 grid resolution. Can be adjusted to coarser grid and just a region.

### Regridding
- [regrid global data](https://github.com/franzihe/regrid_global_data) -- codes to e.g. regrid ERA5 or CMIP6 gridded data to a common grid for further analysis.

### Forecasts and weather observations
- [plot weathermaps from MEPS/AROME Arctic](https://github.com/franzihe/Weathermap) -- creates specific weathermaps for a chosen area. This can be adjustet to either use the _latest_ initialization or the _archived_ forecasts (change the input directory accordingly).
- [download Radiosonde data and create skewT plots](https://github.com/franzihe/Radiosonde) -- this includes code to download radiosonde observations from the University of Wyoming website (here Stavanger, station #01415). Code to plot a vertical profile of temperature in skewT from MEPS (_latest_ or _archived_ has to be adjusted). In addition, a code to plot a seasonal mean temperature profile of both, UWyoming data and MEPS archived data.

### Useful code produced by others
- [CMIP6-downloader python script](https://github.com/tloureiro/cmip6_downloader) -- The instructions are on the github repo, but you simply have to download the `cmip6_downloader.py` file and place it in the folder that you want the data to be downloaded into, and then run the script specifying what variables etc. you want downloaded. The script can run in the background, as opposed to manually downloading the wget scripts from the WCRP website.

e.g. TOA radiative fluxes from NorESM2-LM 
```
python3 cmip6_downloader.py --variable_id rsut,rlut,rsutcs,rlutcs --experiment_id historical --source_id NorESM2-LM --grid_label gn --variant_label r1i1p1f1 --frequency mon

```

