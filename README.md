# Data schema

This repository contains a description of the data schema using for the cheminfo ELN.
It is also the place where changes to the schema are discussed.

## Table of contents

- reaction

  - [reaction](./schema/reaction/reaction.md)
  - [products](./schema/reaction/products.md)
  - [reagents](./schema/reaction/reagents.md)

- sample

  - [general](./schema/sample/general.md)
  - [identifier](./schema/sample/identifier.md)
  - [image](./schema/sample/image.md)
  - [misc](./schema/sample/misc.md)
  - [physical](./schema/sample/physical.md)
  - [safety](./schema/sample/safety.md)
  - [stock](./schema/sample/stock.md)
  - [video](./schema/sample/video.md)

  - spectra

    - [chromatogram](./schema/sample/spectra/chromatogram.md)
    - [cyclicVoltammetry](./schema/sample/spectra/cyclicVoltammetry.md)
    - [dynamicAdsorptionAnalysis](./schema/sample/spectra/dynamicAdsorptionAnalysis.md)
    - [differentialCentrifugalSedimentation](./schema/sample/spectra/differentialCentrifugalSedimentation.md)
    - [differentialScanningCalorimetry](./schema/sample/spectra/differentialScanningCalorimetry.md)
    - [elementalAnalysis](./schema/sample/spectra/elementalAnalysis.md)
    - [hgPorosimetry](./schema/sample/spectra/hgPorosimetry.md)
    - [ir](./schema/sample/spectra/ir.md)
    - [isotherm](./schema/sample/spectra/isotherm.md)
    - [iv](./schema/sample/spectra/iv.md)
    - [mass](./schema/sample/spectra/mass.md)
    - [nmr](./schema/sample/spectra/nrm.md)
    - [raman](./schema/sample/spectra/raman.md)
    - [thermogravimetricAnalysis](./schema/sample/spectra/thermogravimetricAnalysis.md)
    - [uv](./schema/sample/spectra/uv.md)
    - [xps](./schema/sample/spectra/xps.md)
    - [xrd](./schema/sample/spectra/xrd.md)
    - [xrf](./schema/sample/spectra/xrf.md)
    - [xray](./schema/sample/spectra/xray.md)

  - biology

    - [antibody](./schema/sample/biology/antibody.md)
    - [cellLine](./schema/sample/biology/cellLine.md)
    - [nucleic](./schema/sample/biology/nucleic.md)
    - [peptidic](./schema/sample/biology/peptidic.md)

## Conventions

- Entries typically have the following format: `name (type, unit): Description.`
- For objects or array of objects the format is as follows

```
- arrayOfObjectExample (array<object>):
  - key1 (string): Description of key1
  - key2 (number, K): This is temperature
```

- For categorical variables, specify the allowed categories instead of the type, e.g. `kind ("a,b,c"): compound class`
- For many values, `unit` objects of the following form are used:

```
unitObject:
  - SI (number): value in SI units
  - unit (string): default unit that is shown to the user
```

- For instruments, the metadata is recorded in an object of the following form

```
instrumentObject:
    - model (string)
    - manufacturer (string)
    - software (string)
    - serialNumber (string)
```

- For spectra, there is also the `source` which can be specified with

```
source (object):
    - type (experiment|simulation|literature)
    - name (str): e.g., aiidalab.materialscloud.org
    - uuid (str): e.g., the UUID of the node of the object in AiiDAlab or the UUID of the data in some other database
    - doi (str)
    - url (str)
```

- In some cases, there might be derived properties. Those should be grouped under `derivedProperties`

- Any new markdown page must be added to the `README.md` file

### Spectra

Spectra are typically converted into [JCAMP-DX](http://jcamp-dx.org/) files. We store all user metadata using `##$` labels.
That is, even though there is a global, IUPAC defined, label for `TEMPERATURE` we will store the temperature using a `##$` to keep all metadata consistent.

## package metadata

To be able to automatically curate an overview of all the tools we add standardized metadata to the `package.json` file under the `info` key.
We use the following keys:

- `logo` (`string`): link to an image, ideally from the [cheminfo/font repository](https://github.com/cheminfo/font)
- `domain` (`array<string>`): array of "tags" to allow for easy filtering. We currently use "Materials Science", "Physical Chemistry", "Organic Chemistry", "Machine Learning", "Data Processing"
- `technique` (`object`): we use this to clarify what experimental technique the package is built for. For this, we reference the [Chemical Methods Ontology](https://www.ebi.ac.uk/ols/ontologies/chmo) and the [IUPAC gold book](https://goldbook.iupac.org)
  - name (string): name of the technique
  - chmo (string): identifier in the chemical methods ontology
  - iupac (string): doi link to the entry in the IUPAC gold book
- functionality (object): We use this to describe the functionality of the package. That is, the file types it can deal with or tags for the analysis techniques it can perform:
  - fileType (array<object>): For every filetype the library supports, add an entry here
    - extension (str): extension without dot
    - manufacturer (str): the maintainer/developer/supplier of the file. For chemical data that usually is an instrument manufacturer
    - example (str): link to an example of the file so users can compare this with their own file
- techniques (array<str>): List of analysis/processing techniques the package supports

An example is:

```json
"version" : "",
"name": "",
"description": "",
"cheminfo": {
    "logo": "https://raw.githubusercontent.com/cheminfo/font/master/src/tga/assignment.svg",
    "domain": [
      "Physical Chemistry",
      "Materials Science"
    ],
    "technique": {
      "name": "TGA",
      "chmo": "0000690",
      "iupac": "https://doi.org/10.1351/goldbook.T06324"
    },
    "functionality": {
      "fileTypes": [
        {
          "extension": "txt",
          "manufacturer": "TA Instruments",
          "example": "https://raw.githubusercontent.com/cheminfo/tga-spectrum/master/testFiles/TAInstruments.txt"
        },
        {
          "extension": "csv",
          "manufacturer": "Perkin Elmer",
          "example": "https://raw.githubusercontent.com/cheminfo/tga-spectrum/master/testFiles/perkinElmer.csv"
        },
        {
          "extension": "txt",
          "manufacturer": "Perkin Elmer",
          "example": "https://raw.githubusercontent.com/cheminfo/tga-spectrum/master/testFiles/perkinElmer_tga4000.txt"
        },
        {
          "extension": "jcamp",
          "manufacturer": "cheminfo",
          "example": "https://raw.githubusercontent.com/cheminfo/tga-spectrum/master/testFiles/ntuples.jdx"
        }
      ]
    }
  }
```
