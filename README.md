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
  - [video](./schema/sample/video.md)
  - [stock](./schema/sample/stock.md)
  - [misc](./schema/sample/misc.md)
  - spectra
    - [chromatogram](./schema/sample/spectra/chromatogram.md)
    - [cyclicVoltammetry](./schema/sample/spectra/cyclicVoltammetry.md)
    - [dynamicAdsorptionAnalysis](./schema/sample/spectra/dynamicAdsorptionAnalysis.md)

## Guidelines

- Entries typically have the following format: `name (type, unit): Description.`
- For objects or array of objects the format is as follows

```
- arrayOfObjectExample (array<object>):
  - key1 (string): Description of key1
  - key2 (number, K): This is temperature
```
