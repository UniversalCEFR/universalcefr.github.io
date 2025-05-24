# UniversalCEFR: Enabling Open Multilingual Research on Language Proficiency Assessment

UniversalCEFR is a largescale, multilingual, multidimensional dataset comprising of texts annotated according to the [CEFR (Common European Framework of Reference)](https://www.coe.int/en/web/common-european-framework-reference-languages/level-descriptions). The collection comprises of a total of **505,807 CEFR-labeled texts** annotated according to the in **13 languages** in **4 scripts** (Latin, Arabic, Devanagari, and Cyrillic).

 - English (en)
 - Spanish (es)
 - German (de)
 - Dutch (nl)
 - Czech (cs)
 - Italian (it)
 - French (fr)
 - Estonian (et)
 - Portuguese (pt)
 - Arabic (ar)
 - Hindi (hi)
 - Russian (ru)
 - Welsh (cy)

To enable open research in both automated readability and language
proficiency assessment, UniversalCEFR comprises curated from educational and learner-oriented resources, standardized into a unified data format to support consistent processing, analysis, and modeling across tasks and languages.

### Standardised Format 
To ensure interoperability, transformation, and machine readability, adopted **standardised JSON format** for each CEFR-labeled text. These fields include the source dataset, language, granularity (document, paragraph, sentence, discourse), production category (learner or reference), and license.

| **Field**         | **Description**                                                                                                                                                                                                                                                                                       |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`           | The unique title of the text retrieved from its original corpus (`NA` if there are no titles such as CEFR-assessed sentences or paragraphs).                                                                                                                                                         |
| `lang`            | The source language of the text in ISO 638-1 format (e.g., `en` for English).                                                                                                                                                                                                                         |
| `source_name`     | The source dataset name where the text is collected as indicated from their source dataset, paper, and/or documentation (e.g., `cambridge-exams` from Xia et al., 2016).                                                                                                                             |
| `format`          | The format of the text in terms of level of granularity as indicated from their source dataset, paper, and/or documentation. The recognized formats are the following: [`document-level`, `paragraph-level`, `discourse-level`, `sentence-level`].                                                   |
| `category`        | The classification of the text in terms of who created the material. The recognized categories are `reference` for texts created by experts, teachers, and language learning professionals and `learner` for texts written by language learners and students.                                         |
| `cefr_level`      | The CEFR level associated with the text. The six recognized CEFR levels are the following: [`A1`, `A2`, `B1`, `B2`, `C1`, `C2`]. A small fraction (<1%) of text in UniversalCEFR contains unlabelled text, texts with plus signs (e.g., `A1+`), and texts with no level indicator (e.g., `A`, `B`). |
| `license`         | The licensing information associated with the text (e.g., `CC-BY-NC-SA` or `Unknown` if not stated).                                                                                                                                                                                                                         |
| `text`            | The actual content of the text itself.  


## The UniversalCEFR Data Directory

| Corpus Name      | Lang (ISO 638-1)   | Format                                               | Category       | Size    | Annotation Method   | Expert Annotators   | Distinct L1                                                                                                        | Inter-Annotator Agreement     | CEFR Coverage   | License                                                       | Resource                                                                           |
|:-----------------|:------------------------|:-----------------------------------------------------|:---------------|:--------|:--------------------|:--------------------|:-------------------------------------------------------------------------------------------------------------------|:------------------------------|:----------------|:--------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| cambridge-exams  | en                      | document-level                                       | reference      | 331     | n/a                 | n/a                 | n/a                                                                                                                | n/a                           | A1-C2           | CC BY-NC-SA 4.0                                               | \citet{xia-etal-2016-text ,                                                        |
| elg-cefr-en      | en                      | document-level                                       | reference      | 712     | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2, plus     | CC BY-NC-SA 4.0                                               | \citet{breuker2022cefr ,                                                           |
| cefr-sp          | en                      | sentence-level                                       | reference      | 17,000  | manual              | 2                   | n/a                                                                                                                | r = 0.75, 0.73                | A1-C2           | CC BY-NC-SA 4.0                                               | \citet{arase-etal-2022-cefr ,                                                      |
| elg-cefr-de      | de                      | document-level                                       | reference      | 509     | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2           | CC BY-NC-SA 4.0                                               | \citet{breuker2022cefr ,                                                           |
| elg-cefr-nl      | nl                      | document-level                                       | reference      | 3,596   | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2, plus     | CC BY-NC-SA 4.0                                               | \citet{breuker2022cefr ,                                                           |
| icle500          | en                      | document-level                                       | learner        | 500     | manual              | 28                  | ur, pa, bg, zh, cs, nl, fi, fr, de, el, hu, it, ja, ko, lt, mk, no, fa, pl, pt, ru, sr, es, sv, tn, tr | Rasch kappa = -0.02           | A1-C2, plus     | CC0 1.0                                                       | \citet{thwaites2024crowdsourced ,                                                  |
| cefr-asag        | en                      | paragraph-level                                      | learner        | 299     | manual              | 3                   | fr                                                                                                                 | Krippendorf alpha = 0.81      | A1-C2           | CC BY-NC-SA 4.0                                               | \citet{tack-etal-2017-human ,                                                      |
| merlin-cs        | cs                      | paragraph-level                                      | learner        | 441     | manual              | multiple            | hu, de, fr, ru, pl, en, sk, es                                                                                  | n/a                           | A2-B2           | CC BY-SA 4.0                                                  | \citet{boyd-etal-2014-merlin ,                                                     |
| merlin-it        | it                      | paragraph-level                                      | learner        | 813     | manual              | multiple            | hu, de, fr, ru, pl, ,  en, sk, es                                                                                  | n/a                           | A1-B1           | CC BY-SA 4.0                                                  | \citet{boyd-etal-2014-merlin ,                                                     |
| merlin-de        | de                      | paragraph-level                                      | learner        | 1,033   | manual              | multiple            | hu, de, fr, ru, pl, ,  en, sk, es                                                                                  | n/a                           | A1-C1           | CC BY-SA 4.0                                                  | \citet{boyd-etal-2014-merlin ,                                                     |
| hablacultura     | es                      | paragraph-level                                      | reference      | 710     | manual              | multiple            | n/a                                                                                                                | n/a                           | A2-C1           | CC BY NC 4.0                                                  | \citet{vasquez-rodriguez-etal-2022-benchmark ,                                     |
| kwiziq-es        | es                      | document-level                                       | reference      | 206     | manual              | multiple            | n/a                                                                                                                | n/a                           | A1-C1           | CC BY NC 4.0                                                  | \citet{vasquez-rodriguez-etal-2022-benchmark ,                                     |
| kwiziq-fr        | fr                      | document-level                                       | reference      | 344     | manual              | multiple            | n/a                                                                                                                | n/a                           | A1-C1           | CC BY NC 4.0                                                  | Original ,                                                                         |
| caes             | es                      | document-level                                       | learner        | 30,935  | computer-assisted   | multiple            | pt, zh, ar, fr, ru                                                                                                 | n/a                           | A1-C1           | CC BY NC 4.0                                                  | \citet{vasquez-rodriguez-etal-2022-benchmark ,                                     |
| deplain-web-doc  | de                      | document-level                                       | reference      | 394     | manual              | 2                   | n/a                                                                                                                | Cohen kappa = 0.85            | A1,A2,B2,C2     | CC-BY-SA-3, ,  CC-BY-4, ,  CC-BY-NC-ND-4, ,  save\_use\_share | \citet{stodden-etal-2023-deplain ,                                                 |
| deplain-apa-doc  | de                      | document-level                                       | reference      | 483     | manual              | 2                   | n/a                                                                                                                | Cohen kappa = 0.85            | A2-B1           | CC-BY-SA-3, ,  CC-BY-4, ,  CC-BY-NC-ND-4, ,  save\_use\_share | \citet{stodden-etal-2023-deplain ,                                                 |
| deplain-apa-sent | de                      | sentence-level                                       | reference      | 483     | manual              | 2                   | n/a                                                                                                                | n/a                           | A2-B2           | By request                                                    | \citet{stodden-etal-2023-deplain ,                                                 |
| elle             | et                      | paragraph-level, ,  document-level                   | learner        | 1,697   | manual              | 2                   | n/a                                                                                                                | n/a                           | A2-C1           | CC BY 4.0                                                     | \citet{vajjala-rama-2018-experiments ,                                             |
| efcamdat-cleaned | en                      | sentence-level,,  paragraph-level                    | learner        | 406,062 | manual              | n/a                 | br, zh, tw, ru, sa, mx, de, it, fr, jp, tr                                                                      | n/a                           | A1-C1           | Cambridge                                                     | \citet{geertzen2013automatic, ,  \citet{shatz2020refining ,  \citet{huang2017ef  , |
| beast2019                       | en                                                   | sentence-level | learner | 3,600               | manual              | multiple                                                                                                           | n/a                           | n/a             | A1-C2                                                         | CC BY SA NC 4.0                                                                    |
| peapl2           | pt                      | paragraph-level                                      | learner        | 481     | manual              | n/a                 | zh, en, es, de, ru, fr, ja, it, nl, ar, pl, ko, ro, sv                                                  | n/a                           | A1-C2           | CC BY SA NC 4.0                                               | \citet{martins2019corpus ,                                                         |
| cople2           | pt                      | paragraph-level                                      | learner        | 942     | manual              | n/a                 | zh, en, es, de, ru, fr, ja, it, nl, ar, pl, ko, ro, sv                                                  | n/a                           | A1-C1           | CC BY SA NC 4.0                                               | \citet{mendes-etal-2016-cople2 ,                                                   |
| zaebuc           | ar                      | paragraph-level                                      | learner        | 214     | manual              | 3                   | en                                                                                                                 | Unnamed kappa = 0.99          | A2-C1           | CC BY SA NC 4.0                                               | \citet{habash-palfreyman-2022-zaebuc ,                                             |
| readme           | ar, en, fr, hi, ru   | sentence-level                                       | reference      | 9,757   | computer-assisted   | 2                   | n/a                                                                                                                | Krippendorf kappa = 0.67,0.78 | A1-C2           | CC BY SA NC 4.0                                               | \citet{naous-etal-2024-readme ,                                                    |
| apa-lha          | de                      | document-level                                       | reference      | 3,130   | n/a                 | n/a                 | n/a                                                                                                                | n/a                           | A2-B1           | Public                                                        | \citet{spring-etal-2021-exploring ,                                                |
| learn-welsh      | cy                      | document-level, ,  sentence-level,,  discourse-level | reference      | 1,372   | manual              | n/a                 | n/a                                                                                                                | n/a                           | A1-A2           | Public                                                        | Original                                                                         |

### Accessing UniversalCEFR

## Model Evalution Paradigms

### Feature-Based Models


### Finetuning Models


### Descriptor-Based Prompting


### Model Predictions

## Join the UniversalCEFR Initiative

### Motivation

### Initiators and Collaborators


### Contact

### Citation
> Written with [StackEdit](https://stackedit.io/).
