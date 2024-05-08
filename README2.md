# Dataset Card for Norwegian Comma Benchmark (NCB)

Sentence-level evaluation of the comma placement abilities of large language models in Norwegian sentences.

## Dataset Description
The NCB corpus (version 0.1) is a collection of 840 human-written Norwegian sentence pairs. The sentences are manually collected from publicly available sources such as articles and governmental reports. The sentences aim to be representative of Norwegian non-fiction, in particular governmental prose. Each pair tests one Norwegian comma rule: one sentence is correctly punctuated, while the other contains faulty comma usage. The dataset tests both rules where there should be a comma and rules where there should not be a comma. 

- **Point of Contact:** [Hans Christian Farsethås](mailto:hans.farsethas@uib.no) and [Joakim Tjøstheim](mailto:joakimtjostheim@outlook.com)
- **Language:** Norwegian (bokmål)
- **License:** The data is distributed under a Creative Commons Attribution-NonCommercial licence (CC BY-NC 4.0). The licence is motivated by the need to block the possibility of third parties redistributing the original reviews for commercial purposes. Note that machine learned models, extracted lexicons, embeddings, and similar resources that are created on the basis of NoReC are not considered to contain the original data and so can be freely used also for commercial purposes despite the non-commercial condition.


## Uses
The data is intended to be used for testing and finetuning models for Norwegian sentence-level comma usage.

## Dataset Structure

### Data Instances
Each data instance contains the following features: correct, wrong and category. An instance from the dataset looks like the following:
```
{"correct": "Eva klatrer, og Ola går på ski.", "wrong": "Eva klatrer og Ola går på ski.", "category": 1}

```

### Data Fields

- 'Correct': a string containing the a Norwegian sentence with correct use of comma
- 'Wrong': a string containig the same Norwegian sentence with wrong use of comma
- 'Category': an integer indicating the rule tested by the pair of correct and wrong sentences.

### Norwegian comma rules

The model tests the following Norwegian comma rules:
```
  1. Det skal alltid være komma mellom helsetninger som er bundet sammen med sideordnende konjunksjoner
  2. Det skal alltid være komma mellom leddsetninger som er bundet sammen med sideordnende konjunksjoner
  3. Det skal alltid være komma etter en leddsetning som står først i en helsetning
  4. Det skal alltid være komma etter en innskutt leddsetning
501. Det skal alltid være komma før og etter apposisjoner som ikke befinner seg i slutten av, men inni en helsetning
502. Det skal alltid være komma før og etter tillegg som ikke befinner seg i slutten av, men inni en helsetning
503. Det skal alltid være komma før og etter innskudd
601. Det skal alltid være komma før apposisjoner som står til slutt i en helsetning
602. Det skal alltid være komma før tillegg som står til slutt i en helsetning
  7. Det skal ikke være komma når det til ett subjekt står to eller flere predikater forbundet med konjunksjon
  8. Det skal ikke være komma etter preposisjonsstyrte infinitiver og andre ikke-setningsformede ledd
  9. Det skal ikke være komma etter ufullstendige leddsetninger
 10. Det skal ikke være komma mellom leddsetninger hvor en leddsetning står som siste ledd i en annen leddsetning
 11. Det skal alltid være komma i en oppramsing dersom det ikke står noen konjunksjon
```


## Dataset Creation


### Curation Rationale

The sentences in the dataset are primarily curated to benchmark the performance of language models on Norwegian comma usage.

### Data Preparation

The sentences in the dataset are collected from actual documents. After collection, they are proofread and lightly edited to remove ambiguity and ensure they align with the specific rule being tested.

The dataset contains 60 sentence pairs for each rule. Thus, it is representative of the rules rather than of language in actual use.

## Generalizability

The dataset aims to be representative of Norwegian non-fiction, with an emphasis on governmental prose. The rules tested are the main syntactic comma rules. Other forms of comma usage, such as commas indicating sentence rhythm and cases where correct placement depends on the writer's intended meaning, are not emphasized.

### Personal and Sensitive Information

The data does not contain information considered personal or sensitive.


### Recommendations

Results obtained on this data might not generalize to texts from other domains or genres. Any biases in the sentiments expressed by the original review authors may carry over to models trained on this data.

### Dataset Creators and Curators
The Norwegian Comma Benchmark was created by Hans Christian Farsethås and Joakim Tjøstheim.


