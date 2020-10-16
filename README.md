# Data schema

This repository contains a description of the data schema using for the cheminfo ELN.
It is also the place where changes to the schema are discussed.

## Guidelines

- For every field you should specify the fieldname, datatype as heading and a description in a syntax like

```
## temperature (number, K)
  - description: temperature at which the - measurement was performed
```

For categorical variables use `possibleValues`

```
## kind (string, )
  - description: specifies the materials class
  - possibleValues: catalyst, buffer, cellLine, RNA, DNA, molecule, dna, peptide, protein
```

This syntax is readable and still allows us to convert the schema with minimal effort into a JSON Schema.

- The unit that is specified here, should be the SI unit that is appropriate for this datatype, if the quantity is unitless, leave the field empty.
- The table of contents in this `README` will be generated automatically with a GitHub actions.
- For each spectrum type, create a new Markdown file.
- If you want to define a prototype object, prefix the heading with Proto
 
## Table of Contents

<!-- filetree -->

 - [README.md](./README.md)
   - **sample/**
     - [general.md](./schema/sample/general.md)
     - [identifier.md](./schema/sample/identifier.md)
     - **spectra/**
       - [pxrd.md](./schema/sample/spectra/pxrd.md)

<!-- filetreestop -->
