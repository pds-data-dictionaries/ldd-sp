## Changes from v1.2.0.0 to 1.3.0.0

### Added support for energy spectra

Spectral bin type can now be described as "energy" for spectra having bins defined in eV. 
All spectral-type attributes (like the <bin_width_\*>) now have an "energy" alternative,
(e.g., <bin_width_energy>).  Regression test files were updated with a class to exercise the new
bin type.

Note that energy spectral units require the presence of the *Units_of_Energy* unit class,
which was only introduced in IM build 1.12.0.0 (1C00 schemas). Therefore, this version of the
**Spectral Discipline Dictionar** cannot be back-ported to IM versions earlier than 1.12.0.0.

### Change Log move

This change log was moved out of the *src/* tree up to the root of the repo, and renamed from 
"README.md" to "ChangeLog.md".

### Fixed internal compliance issue with optional and nillable attributes

In keeping with PDS LDD design best practices, attribute that were defined as "nillable" but
no longer *required* to be present in any class had the nillable option removed from their 
definitions. This should be transparent to users.

### Use of DD_Associate_External

Where before a notational kludge was used to reference the <Internal_Reference> and 
<Local_Internal_Reference> classes in the *pds:* namespace, now the new <DD_Associate_External>
class is used in the souce *Ingest_LDD* file to make that association to an external namespace.
This should be transparent to users.

### Added license info

The Apache 2.0 license has been added to the repo

---
## Changes from v1.1.0.0 to v1.2.0.0

### <Uniformly_Sampled> Table Support

Upgraded support for tables in the <Uniformly_Sampled> class by recognizing two special values 
of <axis_name>: **Row**, for use with uniformly sampled spectral tables (where each row is a 
single bin of the spectrum); and **Field**, for use with tabulated spectra (where each row is
an entire spectrum and the bins are in successive columns).

### <Uniformly_Sampled>/<axis_name> now required

The <axis_name> attribute of the <Uniformly_Sampled> class is now required in all cases. Formerly
it was required for arrays, but assumed to be equivalent to the new **Row** value for all tables.

### Added Table Support to <Axis_Bin_Set>

The <axis_name> attribute in <Axis_Bin_Set> also recognizes the special values **Row** and **Field**
for use with table spectra.  This class may now be used to explicitly define bins for spectral 
tables and tabulated specta.
### Moved <Bin_Width_Constant> class

The <Bin_Width_Constant> class was moved under the <Spectral_Lookup> class to serve as an alternate
means of determining bin widths where a lookup is not available.  All other cases provide a "constant"
alternative already, and the class was unusable as originally implemented, since all other classes
define bin centers and widths concurrently.

### <bin_width_*> is nillable

The various unit-specific instances of <bin_width_*> have all been made nillable, to cover the
case where bin width is not known. Note that, because of a quirk of the implementation, units
must still be specified.  So, for example, to declare that a wavelength spectrum has unknown
bin widths, use this construct:

     <bin_width_wavelength unit="nm" xsi:nil="true" nilReason="unknown"/>
     
### Removed <original_bin_number>

This attribute was a carry-over from PDS3, where it appears to have been added to the dictionary
for the support of a single atypical mission instrument.  It has been removed.

### Updated Test Labels

The test labels have been updated to include test cases for use of <Uniformly_Sampled> and 
<Axis_Bin_Set> with tabular data, and nil bin widths.