# TESS_research
Useful scripts and data files comparing Fermi/LAT &amp; TESS coverages

List of Files:
TESS_Fermi_exp_results.txt 
- Results of the iPython notebook
- Will be updated as new Mission Weeks are planned

TESS_exp_check.ipynb
- iPython notebook that does all the work
- Starts with a given weeekly Fermi FT2 (spacecraft) file and the wtv-blazars-names.csv data file
- Determines which TESS segment is active based on START, STOP times of FT2 file
  - Times are expressed in Fermi Mission Elapsed Time (MET) as that is how the FT2 files are formatted
  - The xtime webtool can easily convert between several time formats:
    https://heasarc.gsfc.nasa.gov/cgi-bin/Tools/xTime/xTime.pl
- Determines which blazars in wtv-blazars-names.csv are visible in the current segment(s)
- Creates an all-sky exposure map & calculates the exposure received by each blazar that TESS is observing in the given epoch
- Results presented as a fraction of average exposure, e.g...
  - During Fermi MW 530, TESS was observing S1 for the entire week 
  - The average exposure over the whole sky was 5.04717e+07 seconds
  - The source QSO B0506-612 was in the TESS field of view during this time, and its exposure was 1.34 times the average exposure, or 6.7632078e7 seconds. 
- Note that in some weeks, such as MW 531, we were rocked mostly to the Northern sky and thus had very little overlap with TESS observations. In MW 533 we rocked back to the south and got ~double the exposure on target visible to TESS

wtv-blazars-names.xls
- Modifid version of the Excel spreadsheeet that Sara sent out earlier.
- Added object name as first column
  - Name preference was given to 3FGL catalog designations, when available
  - I wasn't able to find a source at 258.523002,-20.463447, so I just dubbed it 'Unknown 1714-2027' for now
  
wtv-blazars-names.csv
- Same content as the .xls version, but in comma-separated format for easier reading by python (and other) scripts

expMap/
- Directory containing the exposure maps, corresponding to each block entry in the results file.
