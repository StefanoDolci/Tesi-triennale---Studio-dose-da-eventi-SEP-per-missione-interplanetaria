Description
===========

The data files in this archive contain carefully processed and cross-calibrated Solar Energetic Particle (SEP) Hand He data derived from space-based measurements.
This dataset may be freely used and modified but any publication or website making use of these data should include the following citation:
SEPEM Reference Data Set version 3.1, European Space Agency (2024).

This work has been carried out as part of successive contracts aimed at building a system for plotting data, building statistical models and derivation of effects of Solar Energetic Particles (SEPs) [ESA/ESTEC/Contract Nos: 20162/06/NL/JD; 4000108377/12/NL/AK; 4000107025/12/NL/AK; 4000115930/15/NL/HK], all of which were initiatives of the Space Environment and Effects section of the European Space Agency (ESA):
http://space-env.esa.int/index.php/ESA-ESTEC-Space-Environment-TEC-EES.html.

The present Solar Energetic Particle Environment Modelling (SEPEM) system is operated by the  Belgian Institute for Space Aeronomy and available for registration and use by registered users here:
http://dev.sepem.oma.be/
A description of the system and its functionalities is available in a peer-reviewed journal article [Crosby, N., et al. (2015), SEPEM: A tool for statistical modeling the solar energetic particle environment, Space Weather, 13, 406–426, doi:10.1002/2013SW001008].

Key persons in the development of this dataset include:
Daniel Heynderickx (DH Consultancy, Belgium)
Ingmar Sandberg (Institute of Accelerating Systems & Applications, Greece)
Piers Jiggens (European Space Agency, ESTEC, The Netherlands)

Data has been processed from the NOAA Energetic Particles Sensor (EPS), part of the Space Environment Monitor (SEM) package on-board GOES and earlier SMS satellites. The original NOAA data is available for download from here:
http://www.ngdc.noaa.gov/stp/satellite/goes/dataaccess.html
These data have been cross-calibrated to find the effective (mean) energy of each energy bin using data from the Goddard Medium Energy (GME) instrument on-board the IMP-8 spacecraft:
http://spdf.gsfc.nasa.gov/imp8_GME/GME_home.html
A description of the (SEPCALIB) cross-calibration is available in a peer-reviewed research letters article [Sandberg, I., P. Jiggens, D. Heynderickx, and I. A. Daglis (2014), Cross calibration of NOAA GOES solar proton detectors using corrected NASA IMP-8/GME data, Geophys. Res. Lett., 41, doi:10.1002/2014GL060469.].

The time range for Version 2.1 of the data set is from 1974-07-01 until 2015-12-31. New data will be added on a regular basis.

For more information please contact Piers Jiggens: Piers.Jiggens[at]esa.int


Change history
==============

13 Dec 2016: v2.1: background subtraction was applied to the H reference dataset SEPEM_H_reference.txt

21 Apr 2016: v2.0: H reference dataset SEPEM_H_reference.txt without background subtraction, He reference dataset SEPEM_He_reference.txt with background subtraction


Data files
==========

The archive contains two sets of files:
- cross-calibrated and merged H and He datasets: SEPEM_H_reference.txt and SEPEM_He_reference.txt
- the individual GOES data files where data spikes have been removed and data gaps were filled.

The file format for both sets is the same: a header line followed by comma separated data records, where the first column is the ISO standard time stamp of the start of a measurement time bin (always 5 minutes) and the remaining columns are the differential fluxes [cm-2.s-1.sr-1.(MeV/nuc)-1] in individual channels.

All data are comma-separated.


Individual spacecraft files
---------------------------

The format of the GOES/SEM data files depends on the processing algorithms used for the individual spacecraft. Up to now, three formats have been used:
- 1974-1985: FITS (precursor spacecraft SMS01-02, GOES01-03, and the pre-1986 portion of the GOES05-06 data)
- 1986-2011: ASCII (GOES05-12)
- 2010-present: netCDF (GOES13-15)

The pre-1986 (binary) FITS files (one per month) contain successive records with 3 channel samples of 1 second each, where the channels vary over successive records. The time histories of the individual channels in each file were averaged over 5 minute intervals and output to new ASCII files in the same format as the 1986-2011 files (A and G files). As a consequence, an extra solar cycle of H, He, X-ray and magnetic field data is now available.

The 5 minute resolution data files (H and He) for all spacecraft were ingested into a MySQL database; all subsequent analysis and processing was performed using the database tools available on the SEPEM server. In order to build a contiguous time series of data, the following datasets were processed (removal of data spikes and gap filling): SMS01, SMS02, GOES01, GOES02, GOES05, GOES06, GOES07, GOES08, GOES11, GOES13. The P2-P7 H channels (P1 was not considered in the analysis) and the A1-A6 He channels into individual files identified by particle species and GOES spacecraft identifier. The P4 channel in the GOES01-02 data is corrupted, so this channel is set to NaN in the SEPEM_H_GOES01-02.TXT file.

No further processing was performed on these data, i.e. the energy bins are the same as in the original files (see the table at the end of this file).

Column 1 contains the date and time in ISO format: yyyy-mm-dd HH:MM:SS
Columns 2-7 contain the differential fluxes [cm-2.s-1.sr-1.(MeV/nuc)-1] of the H (He) channels with channel definitions and effective (mean) energies given below.

All data files are contiguous in time, i.e. there are no data gaps, with one exception. The GOES11 H and He data contain large gaps before Jun 2003; the data before that date were kept nonetheless in order to maximise the overlap with GOES08.


Reference dataset files
-----------------------

The data for the individual spacecraft (or spacecraft pairs when time coverage is spare) were then cross-calibrated with IMP8/GME data as described above. Finally, the spectra for each time stamp were re-binned into a set of 11 (8) logarithmically spaced energy channels for H (He). The re-binned data are available in the files SEPEM_H_reference.txt and SEPEM_He_reference.txt, at continuous 5 minute time intervals without time gaps or NaNs.

Column 1 contains the date and time in ISO format: yyyy-mm-dd HH:MM:SS

Columns 2-12 (2-9) contain the differential fluxes [cm-2.s-1.sr-1.(MeV/nuc)-1] of the H (He) channels defined as follows:

Column 2 (Ch1): 6.01 MeV.nuc-1 (nominal bin: 5.00-7.23 MeV.nuc-1)
Column 3 (Ch2): 8.70 MeV.nuc-1 (nominal bin: 7.23-10.46 MeV.nuc-1)
Column 4 (Ch3): 12.58 MeV.nuc-1 (nominal bin: 10.46-15.12 MeV.nuc-1)
Column 5 (Ch4): 18.18 MeV.nuc-1 (nominal bin: 15.12-21.87 MeV.nuc-1)
Column 6 (Ch5): 26.30 MeV.nuc-1 (nominal bin: 21.87-31.62 MeV.nuc-1)
Column 7 (Ch6): 38.03 MeV.nuc-1 (nominal bin: 31.62-45.73 MeV.nuc-1)
Column 8 (Ch7): 54.99 MeV.nuc-1 (nominal bin: 45.73-66.13 MeV.nuc-1)
Column 9 (Ch8): 79.53 MeV.nuc-1 (nominal bin: 66.13-95.64 MeV.nuc-1)
Column 10 (Ch9): 115.0 MeV.nuc-1 (nominal bin: 95.64-138.3 MeV.nuc-1)
Column 11 (Ch10): 166.3 MeV.nuc-1 (nominal bin: 138.3-200.0 MeV.nuc-1)
Column 12 (Ch11): 244.2 MeV.nuc-1 (nominal bin: 200.0-289.2 MeV.nuc-1)
In the above effective mean energies of the particles are given first followed by the nominal energy bin limits in parentheses.

Note: a background subtraction was performed on the re-binned He data (not on the H data) as the background noise in the last two or three He channels in the GOES/SEM data is very high. This explains why the minimum value in the reference He dataset is zero, while all values in the reference H dataset are greater than zero.



Original energy channels for the individual GOES data files
===========================================================

H channels (MeV)
----------------

    Spacecraft        P2       P3         P4         P5          P6           P7
 SMS01-02, GOES01   4.0-6.0  6.0-10.0  18.0-38.0  40.0-500.0  84.0-150.0  150.0-500.0
    GOES02-03       4.0-8.0  8.0-16.0  16.0-36.0  36.0-500.0  80.0-215.0  215.0-500.0
    GOES05-07       4.2-8.7  8.7-14.5  15.0-44.0  39.0- 82.0  84.0-200.0  110.0-500.0
    GOES08-12       4.0-9.0  9.0-15.0  15.0-40.0  40.0- 80.0  80.0-165.0  165.0-500.0
    GOES13-15       4.2-8.7  8.7-14.5  15.0-40.0  38.0- 82.0  84.0-200.0  110.0-900.0


He channels (MeV)
-----------------

    Spacecraft         A1       A2        A3          A4         A5           A6
 SMS01-02, GOES01   4.0-10.0 10.0-16.0 18.0-56.0  71.0-150.0 167.0-245.0  340.0-392.0
    GOES02-03       3.2-10.0 10.0-16.0 16.0-60.0  85.0-182.0 156.0-228.0  326.0-412.0
    GOES05-07       3.8- 9.9  9.9-21.3 21.3-61.0  60.0-180.0 160.0-260.0  330.0-500.0
    GOES08-12       4.0-10.0 10.0-21.0 21.0-60.0  60.0-150.0 150.0-250.0  300.0-500.0
    GOES13-15       3.8- 9.9  9.9-20.5 20.5-61.0  60.0-160.0 160.0-260.0  330.0-500.0



Effective energies obtained from the SEPCALIB cross calibration
===============================================================

H channels (MeV)
----------------

    Spacecraft       P2     P3     P4     P5    P6     P7
     SMS01-02      4.282  6.561  29.59  52.96  150.7  440.8
    GOES01-02      4.347  7.233    -    34.20  78.29  278.5
      GOES05       6.348  11.01  17.56  46.54  103.8  213.6
      GOES07       6.591  11.15  21.54  49.98  102.4  214.4
      GOES08       6.214  10.74  18.65  47.82  105.6  152.9
    GOES11-13      6.643  12.61  20.55  46.62  103.7  154.6


He channels (MeV/nuc))
----------------------

    Spacecraft           A1     A2     A3     A4     A5     A6
 SMS01-02, GOES01-02   1.558  2.417  5.849  23.76  38.95  75.00
    GOES05-07          1.664  4.173  8.607  21.13  41.21  79.79
    GOES08-13          1.598  3.717  8.680  17.45  39.32  77.79