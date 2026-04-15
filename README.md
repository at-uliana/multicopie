# MultiCoPIE: A Multilingual Corpus of Potentially Idiomatic Expressions

This repository contains MultiCoPIE - **Multi**lingual **C**orpus of **P**otentially **I**diomatic **E**xpressions. The corpus consinsts of figurative and literal instances of idiomatic expressions, originally designed for the task of PIE classification. For details, see [our paper](https://aclanthology.org/2025.mwe-1.8/) (Sentsova et al., MWE 2025).

## Files: corpus and metadata

The ZIP archive contains two TSV files: `corpus.tsv` and `metadata.tsv`.

The `corpus.tsv` file contains instances with potentially idiomatic expressions. An instance typically comprises a sentence with a specific idiomatic expressions (*target sentence*) and two surrounding sentences (*previous sentence*, *next sentence*). In few cases, one of the context sentences (*previous*, *next*) may be absent.

The `corpus.tsv` file has the following columns:
- `idiom ID`: unique idiom identifier
- `idiomatic expression`: potentially idiomatic expression
- `previous sentence`
- `target sentence`: sentence with the idiomatic expression
- `next sentence`
- `label`: 0 (literal instance) or 1 (figurative instance)
- `language`: CA (Catalan), IT (Italian), or RU (Russian)

The `metadata.tsv` file contains further information about each PIE in the corpus, such as part-of-speech of idiom head and equivalent (or similar) idiomatic expressions in English.

The `metadata.tsv` file has the following columns:
- `idiom ID`
- `idiomatic expression`
- `head part-of-speech`: part-of-speech of the idiomatic phrase
- `equivalent idiomatic expression in English`: corresponding English idioms with the same meaning; if several, they are separated by a semicolon (;)
- `equivalence type`: *identical*, *similar* or `NaN` (see Section 3.1 of the paper under *Cross-Lingual Lexical Overlap*)

## Annotation

### Instance-level annotation
Each instance is assigned a label: either 0 (literal usage of a PIE), or 1 (idiomatic usage of a PIE).

### Token-level annotation
Inside each instance, all lexicalized tokens of idiomatic expressions are annotated with tags `<idiom>` (opening tag) and `</idiom>` (closing tag). 
Many instances contain idiomatic expression other than the target one; these idiomatic expressions are annotated as well, using numbered tags (`<idiom2>...</idiom2>`, `<idiom3>...</idiom3>` etc).

## Further developments
The corpus is currently undergoing improvements. A new version will include a new English subcorpus, extended annotation as well as new idiomatic expressions and instances. Release date: summer 2026.

## Citation
> Uliana Sentsova, Debora Ciminari, Josef Van Genabith, and Cristina España-Bonet. 2025. MultiCoPIE: A Multilingual Corpus of Potentially Idiomatic Expressions for Cross-lingual PIE Disambiguation. In Proceedings of the 21st Workshop on Multiword Expressions (MWE 2025), pages 67–81, Albuquerque, New Mexico, U.S.A.. Association for Computational Linguistics.

