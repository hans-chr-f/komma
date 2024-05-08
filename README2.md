# Dataset Card for Norwegian Comma Benchmark (NCB)

Sentence-level evaluation of **???**

## Dataset Description
The NCB corpus (version 0.1) is a collection of 840 human-written Norwegian sentence pairs. 

The sentences are manually collected from publically available sources like articles, governmental reports and ... They aim to be representative of Norwegian non-fiction, in particular governmental prose. 

- **Point of Contact:** [Hans Christian Farsethås](mailto:hans.farsethas@uib.no)
- **Point of Contact:** [Joakim Tjøstheim](mailto:joakimtjostheim@outlook.com)

### Supported Tasks and Leaderboards


## Dataset Structure

### Data Instances
Each data instance contains the following features: correct, wrong and category. An example from dataset looks like the following:
```
{"correct": "Eva klatrer, og Ola går på ski.", "wrong": "Eva klatrer og Ola går på ski.", "category": 1}

```

### Data Fields

- 'correct': a string containing the a norwegian sentence with correct use of comma
- 'wrong': a string containen the same norwegian sentence with wrong use of comma
- 'category': an integer indicating the rule testet by the pair of correct and wrong sentences.

### Norwegian comma rules
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

## Additional Information

### Dataset Curators
The Norwegian Comma Benchmark was created by Hans Christian Farsethås and Joakim Tjøstheim

### Licensing Information

