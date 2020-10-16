# title (`string`, )

- description: user-chosen title for the sample

# description (`string`, )

- description: free text HTML for any kind of description

# kind (`string`, )

- description: materials class
- possibleValues: catalyst, buffer, cellLine, RNA, DNA, molecule, peptide, protein

# name (`List<nameObject>`, )

- description of (non-)iupac names as `nameObjects`

## Proto: `nameObject` (Object, )

### value (string, )

- description: name of chemical

### iupac (boolean, )

- description: true if name is IUPAC-conform
