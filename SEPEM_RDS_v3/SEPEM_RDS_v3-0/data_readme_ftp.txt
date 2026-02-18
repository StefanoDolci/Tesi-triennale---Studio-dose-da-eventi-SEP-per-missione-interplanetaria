Description
===========

The data files in this archive contain carefully processed and cross-calibrated Solar Energetic Particle (SEP) H and He data derived from space-based measurements.
This Reference Data Set (RDS) may be freely used and modified but any publication or website making use of these data should include the following citation:
SEPEM Reference Data Set version 3.0, European Space Agency (2024).

This work has been carried out as part of successive contracts issued by the European Space Agency (ESA) aimed at building a system for plotting data, building and validating environmental models and derivation of effects pertaining to Solar Energetic Particles (SEPs), all of which were initiatives of the Space Environment and Effects section of ESA based at the European Space Research and Technology Centre (ESTEC) in the Netherlands:
http://space-env.esa.int/index.php/ESA-ESTEC-Space-Environment-TEC-EES.html
[Contract Numbers: 20162/06/NL/JD; 4000108377/12/NL/AK; 4000107025/12/NL/AK; 4000115930/15/NL/HK, 4000127129/19/NL/HK, 4000127282/19/NL/IB/gg]

The present Solar Energetic Particle Environment Modelling (SEPEM) system is operated by the Royal Belgian Institute for Space Aeronomy and available for registration and use by registered users here:
http://sepem.eu/
Or may alternatively be accessed via the ESA Space Weather Service Network portal:
https://swe.ssa.esa.int/
A description of the system and its functionalities is available in a peer-reviewed journal article [Crosby, N., et al. (2015), SEPEM: A tool for statistical modeling the solar energetic particle environment, Space Weather, 13, 406–426, doi:10.1002/2013SW001008].

Key persons in the development of this dataset include:
Daniel Heynderickx (DH Consultancy, Belgium)
Ingmar Sandberg (Institute of Accelerating Systems & Applications, Greece)
Piers Jiggens (European Space Agency, ESTEC, The Netherlands)
Osku Raukunen (Aboa Space Research Oy, Finland)
Juan Rodriguez (National Centers for Environmental Information, National Oceanic and Atmospheric Administration, U.S.A.)
Rami Vainio (University of Turku, Finland)
Sigiava Aminalragia-Giamini (Institute of Accelerating Systems & Applications, Greece)

Data has been processed from the NOAA Energetic Particles Sensor (EPS) (latterly named Energetic Proton, Electron and Alpha Detector (EPEAD)) and the High Energy Proton and Alpha Particles Detector (HEPAD), part of the Space Environment Monitor (SEM) package on-board GOES and earlier SMS satellites. The original NOAA data is available for download from here:
http://www.ngdc.noaa.gov/stp/satellite/goes/dataaccess.html
Data from the EPS(EPEAD) have been cross-calibrated to find the effective (mean) energy of each energy channel using data from the Goddard Medium Energy (GME) instrument on-board the IMP-8 spacecraft:
http://spdf.gsfc.nasa.gov/imp8_GME/GME_home.html
A description of this cross-calibration, and necessary corrections for spurious behaviour in the GME measurements, is available in a peer-reviewed research letters article [Sandberg, I., P. Jiggens, D. Heynderickx, and I. A. Daglis (2014), Cross calibration of NOAA GOES solar proton detectors using corrected NASA IMP-8/GME data, Geophys. Res. Lett., 41, doi:10.1002/2014GL060469.].
Data from the HEPAD have been assessed in terms of the energy dependence of the geometric factor to derive the bow-tie (mean) energy for each energy channel. A description of this bow-tie analysis is included in the Appendix available in a peer-reviewed journal article [Raukunen, O. et al. (2020), Very high energy proton peak flux model, Journal of Space Weather and Space Climate, 10, 24, doi: 10.1051/swsc/2020024].

The time range for Version 3.0 of the data set is from 1974-07-01 until 2017-12-31.

For more information please contact Piers Jiggens: Piers.Jiggens[at]esa.int


RDS v3.0 Data files
===============

The processed data set is composed of 18 text (.txt) files, for which:
- Caveats have been removed comprised primarily of data spikes which are more abundant in the earlier original data.
- Data gaps have been filled either by other EPS(EPEAD)/HEPAD data of by interpolation where they are short in duration or other data are unavailable.
- Mean energy values are provided for each energy channel (given below)
No further processing was performed on these data, i.e. the channels are the same as in the original files (see the table at the end of this file).

The P2-P7 H channels (P1 was not considered in the analysis) and the A1-A6 He channels into individual files identified by particle species and GOES spacecraft identifier. The file name format is <species>_<detector>_<spacecraft>.txt. GOES is shortened to ‘G’. There are:
- 7 EPS(EPEAD) H files (note that SMS 1 and 2 and GOES 1 and 2 are given in 2 single files)
- 7 EPS(EPEAD) He files (note that SMS 1 and 2 and GOES 1 and 2 are given in 2 single files)
- 4 HEPAD H files

The file format for both sets is the same with a header line followed by data records (always in 5-minute time resolution):
Column 1 contains the date and time in ISO format (yyyy-mm-dd HH:MM:SS) of the start of a measurement time bin
Columns 2-7(4) contain the differential fluxes [cm-2.s-1.sr-1.(MeV/nuc)-1] of the H/He channels with channel definitions and effective (mean) energies given below.

All data are comma-separated.

Timespan of data sets
-----------------------------

In order to build a contiguous time series of data, the following datasets were processed:
SMS01 (EPS): 1974-07-01 to 1975-10-31
SMS02 (EPS): 1975-02-01 to 1978-03-31
GOES01 (EPS): 1977-01-01 to 1977-07-31
GOES02 (EPS): 1977-08-01 to 1983-05-19
GOES05 (EPS): 1983-05-20 to 1987-03-24
GOES06 (HEPAD): 1983-05-20 to 1994-12-31
GOES07 (EPS): 1987-03-06 to 1996-08-31
GOES08 (EPS): 1995-01-01 to 2003-06-16
GOES08 (HEPAD): 1995-01-01 to 2003-06-17
GOES11 (EPS): 2000-07-01 to 2011-02-27 
GOES11 (HEPAD): 2003-06-16 to 2010-12-31
GOES13 (EPEAD): 2010-05-01 to 2017-12-31
GOES13 (HEPAD): 2010-05-01 to 2017-12-31

The P4 channel in the GOES01-02 data is corrupted, so this channel is set to NaN in the SEPEM_H_GOES01-02.TXT file.

All data files are contiguous in time, i.e. there are no data gaps, with only one exception: The GOES11 H and He data contain large gaps before 2003-06-20; the data before that date were kept nonetheless in order to maximise the overlap with GOES08 for comparison studies. Data from GOES12 has been used to in place of GOES11 data in the data files for EPS for the period from 2003-06-01 until 2003-06-21 (where GOES08 data is also missing) and thereafter the data is once more from the GOES11 satellite. It should be noted that background levels were used for the highest 2 energy EPS channels (P6 and P7) during this period due to missing channels in GOES12 data, the 3rd highest channel is also at background during this period, giving confidence this is valid. Accordingly, HEPAD energy channel fluxes can also be assumed to be at background throughout this time period and gaps in both GOES8 and GOES11 data sets have been filled with background values. The final helium channel (A6) is also filled with background levels during this time period.  

Data Processing from Original files
---------------------------------------------

The format of the GOES/SEM data files depends on the processing algorithms used for the individual spacecraft. Up to now, three formats have been used:
- 1974-1985: FITS (precursor spacecraft SMS01-02, GOES01-03, and the pre-1986 portion of the GOES05-06 data)
- 1986-2011: ASCII (GOES05-12)
- 2010-present: netCDF (GOES13-15)

The pre-1986 (binary) FITS files (one per month) contain successive records with 3 channel samples of 1 second each, where the channels vary over successive records. The time histories of the individual channels in each file were averaged over 5 minute intervals and output to new ASCII files in the same format as the 1986-2011 files (A and G files). As a consequence, an extra solar cycle of H, He, X-ray and magnetic field data has been made available.

The data files (H and He) for all spacecraft were ingested into a MySQL database; all subsequent analysis and processing was performed using the database tools available on the SEPEM server. The resulting individual data sets are available with API through ESA’s Open Data Interface (ODI) at:
https://spitfire.estec.esa.int/hapi/.
More information on ODI is available via the user guide:
https://spitfire.estec.esa.int/trac/ODI/
and the client software may be downloaded from:
https://essr.esa.int/project/odi-open-data-interface-client


Original energy channels for the individual GOES data files
===========================================================

H EPS/EPEAD channels (MeV)
---------------------------------------

    Spacecraft        P2       P3         P4         P5          P6           P7
    SMS01   4.0-6.0  6.0-10.0  18.0-38.0  40.0-500.0  84.0-150.0  150.0-500.0
    SMS02   4.0-6.0  6.0-10.0  18.0-38.0  40.0-500.0  84.0-150.0  150.0-500.0
    GOES01   4.0-6.0  6.0-10.0  18.0-38.0  40.0-500.0  84.0-150.0  150.0-500.0
    GOES02   4.0-8.0  8.0-16.0  16.0-36.0  36.0-500.0  80.0-215.0  215.0-500.0
    GOES05   4.2-8.7  8.7-14.5  15.0-44.0  39.0- 82.0  84.0-200.0  110.0-500.0
    GOES07   4.2-8.7  8.7-14.5  15.0-44.0  39.0- 82.0  84.0-200.0  110.0-500.0
    GOES08   4.0-9.0  9.0-15.0  15.0-40.0  40.0- 80.0  80.0-165.0  165.0-500.0
    GOES11   4.0-9.0  9.0-15.0  15.0-40.0  40.0- 80.0  80.0-165.0  165.0-500.0
    GOES13   4.2-8.7  8.7-14.5  15.0-40.0  38.0- 82.0  84.0-200.0  110.0-900.0

He EPS/EPEAD channels (MeV/nuc)
----------------------------------------------

    Spacecraft         A1       A2        A3          A4         A5           A6
    SMS01   4.0-10.0 10.0-16.0 18.0-56.0  71.0-150.0 167.0-245.0  340.0-392.0
    SMS02   4.0-10.0 10.0-16.0 18.0-56.0  71.0-150.0 167.0-245.0  340.0-392.0
    GOES01   4.0-10.0 10.0-16.0 18.0-56.0  71.0-150.0 167.0-245.0  340.0-392.0
    GOES02   3.2-10.0 10.0-16.0 16.0-60.0  85.0-182.0 156.0-228.0  326.0-412.0
    GOES05   3.8- 9.9  9.9-21.3 21.3-61.0  60.0-180.0 160.0-260.0  330.0-500.0
    GOES07   3.8- 9.9  9.9-21.3 21.3-61.0  60.0-180.0 160.0-260.0  330.0-500.0
    GOES08   4.0-10.0 10.0-21.0 21.0-60.0  60.0-150.0 150.0-250.0  300.0-500.0
    GOES11   4.0-10.0 10.0-21.0 21.0-60.0  60.0-150.0 150.0-250.0  300.0-500.0
    GOES13   3.8- 9.9  9.9-20.5 20.5-61.0  60.0-160.0 160.0-260.0  330.0-500.0

H HEPAD channels (MeV)
---------------------------------

    Spacecraft        P8          P9           P10
    GOES06   355-435  435-555  555-760
    GOES08   350-420  420-510  510-700
    GOES11   350-420  420-510  510-700
    GOES13   350-420  420-510  510-700

Effective energies obtained from the SEPCALIB cross calibration
===============================================================

H EPS/EPEAD channels (MeV)
---------------------------------------

    Spacecraft       P2     P3     P4     P5    P6     P7
    SMS01-02      4.282  6.561  29.59  52.96  150.7  440.8
    GOES01-02      4.347  7.233    -    34.20  78.29  278.5
    GOES05       6.348  11.01  17.56  46.54  103.8  213.6
    GOES07       6.591  11.15  21.54  49.98  102.4  214.4
    GOES08       6.214  10.74  18.65  47.82  105.6  152.9
    GOES11-13      6.643  12.61  20.55  46.62  103.7  154.6


He EPS/EPEAD channels (MeV/nuc)
----------------------------------------------

    Spacecraft           A1     A2     A3     A4     A5     A6
    SMS01-02, GOES01-02   1.558  2.417  5.849  23.76  38.95  75.00
    GOES05, GOES07   1.664  4.173  8.607  21.13  41.21  79.79
    GOES08, GOES11, GOES13   1.598  3.717  8.680  17.45  39.32  77.79

H HEPAD channels (MeV)
---------------------------------

    Spacecraft   P8  P9  P10
    GOES06   405  473 622
    GOES08   406  457  583
    GOES11   406  457  583
    GOES13   406  457  583
