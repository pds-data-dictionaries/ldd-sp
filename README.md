# Spectral Discipline Dictionary

The Spectral Discipline Dictionary provides classes used to define the spectral characteristics of light spectra 
(frequency, wavelength, wavenumber, or energy).

## Steward

The current steward for this dictionary, and your primary point of contact for questions and requests, is Anne Raugh (@acraugh),
located at the Small Bodies Node at the University of Maryland.

## Namespace

The namespace for the Spectral Discipline Dictionary is:

    http://pds.nasa.gov/pds4/sp/v1
    
and the reserved abbreviation is "**sp:**".

## Schemas

The schemas needed for creating, validating, and working with the Spectral Dictionary classes are in the [build/release](build/release) directory.
Unless you are familiar with GitHub, though, it's probably easier to download the file set you want from 
the [PDS Data Dictionaries](https://pds.nasa.gov/datastandards/dictionaries) page. Look for the "Spectral Discipline Dictionary". Other spectral/spectrum
dictionaries are _not_ the same thing.

## Entry Points

There is a single wrapper class defined for the Spectral Dictionary. All other classes are contained within it.  
You must use the wrapper class to access the **sp:** namespace content:

    <sp:Spectral_Characteristics>
    ...
    </sp:Spectral_Characteristics>
    
The ```<sp:Spectral_Characteristics>``` class should be placed in the ```<Discipline_Area>``` of your product label.    

## Documentation

User documentation for the Spectral Discipline Dictionary is maintained on the SBN PDS4 wiki:

https://sbnwiki.astro.umd.edu/wiki/Filling_Out_the_Spectral_Dictionary_Classes

## Examples

Code samples demonstrating how to use various features of the Spectral Discipline dictionary are in the [examples](examples) directory.

## Version Summaries

The ([Change Log](ChangeLog.md)) begins with version 1.1.0.0 and provides more details.

- [1.0.0.0](src/archive/1.0.0.0): A complete re-design of the prototype dictionary
- [1.1.0.0](src/archive/1.1.0.0): Upgrades as suggested by early adopters
- [1.2.0.0](src/archive/1.2.0.0): Minor upgrades to make for more uniform use of features across arrays and tables
- [1.3.0.0](src/archive/1.3.0.0): Added support for energy (X-ray) spectra; cleanup of some internal details
- [1.3.1.0](src/archive/1.3.1.0): Bugfix to remove spurious error message in the case of Table_Delimited data

## Builds

The Spectral Dictionary (LDD) is built for each version of the [PDS4 Information Model](https://pds.nasa.gov/datastandards/documents/).
The build process insures compatiblity of the LDD with the core information model. The ```build/release``` directory tree is 
where you will find the XSD Schema and Schematron files needed to use the Spectral Dictionary classes in labels. There is one
directory for each release of the PDS IM.

The table below shows the versions of the IM for which each version of the Spectral Dictionary is supported. The first
column links to the specific [build/](build) directory in this repository.

Spectral Dictionary Version | v1.0.0.0 | v1.1.0.0 | v1.2.0.0  | v1.3.0.0 | v1.3.1.0
--------------------------- | -------- | -------- | --------  | -------- | --------
[IM 1700 (1.7.0.0)](build/release/1.7.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x: | :x: | :x:
[IM 1800 (1.8.0.0)](build/release/1.8.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x: | :x: | :x:
[IM 1900 (1.9.0.0)](build/release/1.9.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x: | :x: | :x:
[IM 1A00 (1.10.0.0)](build/release/1.A.0.0) | :heavy_check_mark: | :heavy_check_mark: | :x: | :x: | :x:
[IM 1A10 (1.10.1.0)](build/release/1.A.1.0) | :heavy_check_mark: | :heavy_check_mark: | :x: | :x: | :x:
[IM 1B00 (1.11.0.0)](build/release/1.B.0.0) | :x: | :heavy_check_mark: | :heavy_check_mark: | :x: | :x:
[IM 1C00 (1.12.0.0)](build/release/1.C.0.0) | :x: | :heavy_check_mark: | :heavy_check_mark: | :x: | :x:
[IM 1D00 (1.13.0.0)](build/release/1.D.0.0) | :x: | :x: | :heavy_check_mark: | :heavy_check_mark: | :x:
[IM 1E00 (1.14.0.0)](build/release/1.14.0.0) | :x: | :x: | :x: | :heavy_check_mark: | :x:
[IM 1F00 (1.15.0.0)](build/release/1.15.0.0) | :x: | :x: | :x: | :heavy_check_mark: | :x:
[IM 1G00 (1.16.0.0)](build/release/1.16.0.0) | :x: | :x: | :x: | :heavy_check_mark: | :heavy_check_mark:

The [test/](test/) subdirectory contains test labels, a *Validate* tool 
configuration file, and the validation report for the test labels.  These are used for regression testing of the schema 
files.  The ```test/``` files are not needed to use the Spectral Dictionary for developing labels.

> If you need a back-port of a specific version of the Spectral Dictionary to an earlier IM that is not currently supported,
> please contact the dictionary steward, @acraugh, or raise an Issue in the [PDS4 Issue Repo](https://github.com/pds-data-dictionaries/PDS4-LDD-Issue-Repo/issues/new/choose).

## Source

The source file for each version of the Spectral Discipline Dictionary is in the [src/archive/](src/archive) subdirectory for the 
corresponding Spectral Dictionary version. This source file, also known as the "Ingest_LDD" file for the root document 
structure used, is heavily annotated so it can be used as a set of working examples for other dictionary writers.


# Contribute

Have a bug or feature request? Create an entry in the [PDS4 Issue Repo](https://github.com/pds-data-dictionaries/PDS4-LDD-Issue-Repo/issues/new/choose).


# Support

See the [PDS4 Local Data Dictionaries (LDDs) page](https://pds-data-dictionaries.github.io/) *SUPPORT* topics for more information 
on how to report issues, request new features, and otherwise contact the dictionary stewards.
