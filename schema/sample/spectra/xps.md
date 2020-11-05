- xps (array<object>): x-ray photoelectron spectroscopy:
  - instrument (object):
    - model (string)
    - manufacturer (string)
    - software (string)
    - serialNumber (string)
  - jcamp (object):
    - filename
  - method (string)
  - peaks (array<object>):
    - be (number, eV): binding energy in eV
    - fwhm (number, eV)
    - intensity (number)