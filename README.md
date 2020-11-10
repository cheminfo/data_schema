# Data schema

This repository contains a description of the data schema using for the cheminfo ELN.
It is also the place where changes to the schema are discussed.

## Table of contents

- reaction

  - [reaction](./reaction/reaction.md)
  - [products](./reaction/products.md)
  - [reagents](./reaction/reagents.md)

- sample
  - [general](./sample/general.md)
  - [identifier](./sample/identifier.md)
  - [image](./sample/image.md)
  - [video](./sample/video.md)
  - [stock](./sample/stock.md)
  - [misc](./sample/misc.md)
  - spectra
    - [chromatogram](./sample/spectra/chromatogram.md)
    - [cyclicVoltammetry](./sample/spectra/cyclicVoltammetry.md)
    - [dynamicAdsorptionAnalysis](./sample/spectra/dynamicAdsorptionAnalysis.md)

## Guidelines

- Entries typically have the following format: `name (type, unit): Description.`
- For objects or array of objects the format is as follows

```
- arrayOfObjectExample (array<object>):
  - key1 (string): Description of key1
  - key2 (number, K): This is temperature
```
