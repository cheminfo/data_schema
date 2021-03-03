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

- Any new markdown page must be added to the `README.md` file
