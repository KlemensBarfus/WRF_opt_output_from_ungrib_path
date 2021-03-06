# WRF_opt_output_from_ungrib_path
NEW: the solution mentioned in the post below only works for ungrib.exe but not e.g. for ecmwf_calc_p.exe or for metgrid.exe. From my point of view the invention of the variabele opt_output_from_ungrib_path in namelist.wps would be still helpful. In case you use WRF4.3, just let me know: modified routines exist. 

~~(NEW: checking WRF related webcontent for this issue, I found this solution: https://forum.mmm.ucar.edu/phpBB3/viewtopic.php?f=32&t=9706&p=18979&hilit=opt_output_from_ungrib_path#p18979 -> setting the path in 'prefix' of the ungrib section of namelist.wps, making all changes from below obsolete.)~~

WRF usually does not provide a path variable that describes where to store output from the ungrib routine
like the variable "opt_output_from_geogrid_path" in namelist.wps. For some environments like supercomputers with limited space
for the home directory where source code is stored and workspaces for the data, such a variable could be helpful.
Replacing the original files with files from this repository before compiling WPS will provide the path variable "opt_output_from_ungrib_path" directly after "opt_output_from_geogrid_path" in namelist.wps.

Replace:  
- gridinfo_module.F with geogrid_gridinfo_module.F in WPS4.2.1/geogrid/src/ and rename it to gridinfo_module.F   
- process_domain_module.F in WPS4.2.1/metgrid/src/
- gridinfo_module.F in WPS4.2.1/metgrid/src/ with metgrid:gridinfo_module.F and rename it to gridinfo_module.F  
- datint.F in WPS4.2.1/ungrib/src/  
- file_delete.F in WPS4.2.1/ungrib/src/  
- read_namelist.F in WPS4.2.1/ungrib/src/  
- rrpr.F in WPS4.2.1/ungrib/src/  
- ungrib.F in WPS4.2.1/ungrib/src/
- output.F in WPS4.2.1/ungrib/src/  
- avg_tsfc.F in WPS4.2.1/util/src/ (and avgtsfc_ECHAM.F if needed)  
- gridinfo_module.F with util_gridinfo_module.F in WPS4.2.1/util/src/ and rename it to gridinfo_module.F   
- calc_ecmwf_p.F in WPS4.2.1/util/src/


