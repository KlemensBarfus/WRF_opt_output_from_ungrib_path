# WRF_opt_output_from_ungrib_path
WRF usually does not provide a path variable that describes where to store output from the ungrib routine
like the variable "opt_output_from_geogrid_path" in namelist.wps. For some environments like supercomputers with limited space
for the home directory where source code is stored and workspaces for the data, such a variable could be helpful.
Replacing the original files with files from this repository before compiling WPS will provide the path variable "opt_output_from_ungrib_path" directly after "opt_output_from_geogrid_path" in namelist.wps.

Replace:  
gridinfo_module.F with geogrid_gridinfo_module.F in WPS4.2.1/geogrid/src/ and rename is to geogrid_gridinfo_module.F 
process_domain_module.F in WPS4.2.1/metgrid/src/  
datint.F in WPS4.2.1/ungrib/src/  
file_delete.F in WPS4.2.1/ungrib/src/  
read_namelist.F in WPS4.2.1/ungrib/src/  
rrpr.F in WPS4.2.1/ungrib/src/  
ungrib.F in WPS4.2.1/ungrib/src/
avg_tsfc.F in WPS4.2.1/util/src/ (and avgtsfc_ECHAM.F if needed)
gridinfo_module.F with util_gridinfo_module.F in WPS4.2.1/util/src/


