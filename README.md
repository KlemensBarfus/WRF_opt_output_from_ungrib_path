# WRF_opt_output_from_ungrib_path
WRF usually does not provide a path variable that describes where to store output from the ungrib routine
like the variable "opt_output_from_geogrid_path" in namelist.wps. For some environments like supercomputers with limited space
for the home directory where source code is stored and workspaces for the data, such a variable could be helpful.
Replacing the original 
