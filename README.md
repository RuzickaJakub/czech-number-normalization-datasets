# Czech number normalization datasets

This repository contains two datasets for the Czech number normalization task -
Wikipedia and News. The annotation manual provided to human annotators is also
included. Note that the manual is in Czech, as the Czech data was annotated.
Datasets were created to evaluate the Bachelor Thesis at the Faculty of
Mathematics and Physics, Charles University. The link to the university digital
repository will be added after the Thesis is published there.

## Dataset formats

Each dataset is a zip archive consisting of two files. The text file (`.txt`)
contains the original sentences - one per line. The JSON file (`.json`) contains
sentence annotations for all the sentences in the text file.

Each sentence annotation has the following fields:

- dataset_name : str
  - Name of the dataset the sentence belongs to.
- sentence_id : int
  - Index of the original sentence in the text file.
- sentence_state : str
  - State signifying whether the sentence is Annotated, Proposed or Approved.
    This is not important for the accompanying datasets, as all sentences are
    already Approved.
- original_sentence : str
  - Text of the original sentence.
- normalized_sentence : str
  - Text of the fully normalized sentence.
- tokens : List[Token]
  - List of all tokens that need normalization.

For completeness, we also provide the token structure:

- text : str
  - The original text to be normalized.
- normalized_text : str
  - The normalization of the original text.
- type : str
  - Corresponding semiotic class.
- begin : int
- end : int
  - The span of the token in the original sentence.
- children : List[Token]
  - Also, nested annotations are allowed, but these were not used during the
    presented datasets annotation.

## Wikipedia

The Wikipedia dataset contains 1469 sentences with 2548 tokens needing
normalization. The number of tokens per annotated class can be found in the
table below.

## News (Czech Radio)

The Czech Radio dataset contains 398 sentences with 599 tokens needing
normalization. The number of tokens per annotated class can be found in the
table below.

| Semiotic Class | Wikipedia # of tokens | News # of tokens |
| -------------- | --------------------- | ---------------- |
| **Total**      | **2548**              | **599**          |
| Cardinal       | 1207                  | 367              |
| Ordinal        | 234                   | 58               |
| Decimal        | 31                    | 39               |
| Date           | 291                   | 48               |
| Time           | 16                    | 15               |
| Measure        | 209                   | 5                |
| Money          | 16                    | 5                |
| Roman          | 49                    | 2                |
| Telephone      | 0                     | 0                |
| Score          | 15                    | 32               |
| WithSuffix     | 22                    | 2                |
| Identifier:    | 22                    | 7                |
| Mixed          | 99                    | 6                |
| Range          | 113                   | 3                |
| Math           | 5                     | 0                |
| Chemistry      | 18                    | 2                |
| Abbreviation   | 152                   | 5                |
| Acronym:       | 0                     | 0                |
| URL            | 2                     | 3                |
| Email          | 0                     | 0                |
| Pathname       | 0                     | 0                |
| Ignored        | 0                     | 0                |
| Verbatim       | 0                     | 0                |
| Other          | 0                     | 0                |
