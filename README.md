# Spectral Discipline Dictionary

The Spectral Discipline Dictionary provides classes used to define the spectral characteristics of light spectra 
(frequency, wavelength, or wavenumber).

## Namespace

The namespace for the Spectral Discipline Dictionary is:

    http://pds.nasa.gov/pds4/sp/v1
    
and the reserved abbreviation is "**sp:**".

## Entry Points

There is a single wrapper class defined for the Spectral Dictionary. All other classes are contained within it.  
You must use the wrapper class to access the **sp:** namespace content:

    <sp:Spectral_Characteristics>
    ...
    </sp:Spectral_Characteristics>
    
The ```<sp:Spectral_Characteristics>``` class should be placed in the ```<Discipline_Area>``` of your product label.    

## Documentation

User documentation for the Spectral Discipline Dictionary is maintained on the SBN PDS4 wiki:

http://sbndev.astro.umd.edu/wiki/Filling_Out_the_Spectral_Dictionary_Classes

## Versions

- [1.0.0.0](src/1.0.0.0): A complete re-design of the prototype dictionary
- [1.1.0.0](src/1.1.0.0): Upgrades as suggested by early adopters
- [1.2.0.0](src/1.2.0.0): Minor upgrades to make for more uniform use of features across arrays and tables ([Change Log](src/1.2.0.0/README.md))

## Builds

The Spectral Dictionary (LDD) is built for each version of the [PDS4 Information Model](https://pds.nasa.gov/pds4/doc/im/).
The build process insures compatiblity of the LDD with the core information model. This is the directory tree where you will
find the XSD Schema and Schematron files needed to use the Spectral Dictionary classes in labels.

The table below shows the versions of the IM for which each version of the Spectral Dictionary is supported. The first
column links to the specific [build/](build) directory in this repository.

Spectral Dictionary Version | v1.0.0.0 | v1.1.0.0 | v1.2.0.0  
--------------------------- | -------- | -------- | --------
[IM 1700 (1.7.0.0)](build/1.7.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1800 (1.8.0.0)](build/1.8.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1900 (1.9.0.0)](build/1.9.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1A00 (1.10.0.0)](build/1.A.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1A10 (1.10.1.0)](build/1.A.1.0) | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1B00 (1.11.0.0)](build/1.B.0.0) | :x: | :heavy_check_mark: | :heavy_check_mark:
[IM 1C00 (1.12.0.0)](build/1.C.0.0) | :x: | :heavy_check_mark: | :heavy_check_mark:

The build directories for each version also contain ```Test/``` subdirectories that contain test labels, *Validate* tool 
configuration files, and the validation report for the test labels.  These are used for regression testing of the schema 
files.  The ```Test/``` files are not needed to use the Spectral Dictionary for developing labels.


## Source

The source file for each IM build is provided in the corresponding [src/](src) directories for each Spectral Dictionary version. The source file, also known as the "Ingest_LDD" file for the document structure used, for the Spectral Dictionary is heavily annotated so it can be used as a set of working examples for other dictionary writers.
