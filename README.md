# Data schema

This repository contains a description of the data schema using for the cheminfo ELN.
It is also the place where changes to the schema are discussed.

## Table of contents

- [reaction](./reaction)
  - [reaction](./reaction.md)
  - [products](./products.md)
  - [reagents](./reagents.md)

## Guidelines

- Entries typically have the following format: `name (type, unit): Description.`
- For objects or array of objects the format is as follows

```
- arrayOfObjectExample (array<object>):
  - key1 (string): Description of key1
  - key2 (number, K): This is temperature
```
