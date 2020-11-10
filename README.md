# Data schema

This repository contains a description of the data schema using for the cheminfo ELN.
It is also the place where changes to the schema are discussed.

## Table of contents

- reaction

  - [reaction](./data_schema/reaction/reaction.md)
  - [products](./data_schema/reaction/products.md)
  - [reagents](./data_schema/reaction/reagents.md)

- sample
  - [general](./data_schema/sample/general.md)
  - [identifier](./data_schema/sample/identifier.md)
  - [image](./data_schema/sample/image.md)
  - [video](./data_schema/sample/video.md)
  - [stock](./data_schema/sample/stock.md)
  - [misc](./data_schema/sample/misc.md)
  - spectra
    - [chromatogram](./data_schema/sample/spectra/chromatogram.md)
    - [cyclicVoltammetry](./data_schema/sample/spectra/cyclicVoltammetry.md)
    - [dynamicAdsorptionAnalysis](./data_schema/sample/spectra/dynamicAdsorptionAnalysis.md)

## Guidelines

- Entries typically have the following format: `name (type, unit): Description.`
- For objects or array of objects the format is as follows

```
- arrayOfObjectExample (array<object>):
  - key1 (string): Description of key1
  - key2 (number, K): This is temperature
```
