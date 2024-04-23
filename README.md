## Purpose and structure
Repository for a prototype testing the abilities of large language models to punctuate Norwegian sentences, with a particular emphasis on comma placement. The repository includes the following files:

- [kommaregler.json](https://github.com/hans-chr-f/komma/blob/main/kommaregler.json): A dictionary of Norwegian comma rules, where keys are arbitrary integers and values are sentences describing each rule.
- [test.txt](https://github.com/hans-chr-f/komma/blob/main/test.txt): A list of sentences, each annotated with correct punctuation, followed by an integer that matches a key in the dictionary.
- train.txt: More sentences in the same format.

## Data format
Each line in test.txt includes one sentence. Lines that begin with '#' serve as comments. The placement of commas is marked by <KOMMA> where they are needed and <IKKE> where they are not. Each line containing <KOMMA> or <IKKE> can be split into two tests. For example:

Eva klatrer <KOMMA> og Ola går på ski. > 1
```
- Eva klatrer, og Ola går på ski.  --> Correct
- Eva klatrer og Ola går på ski.   --> Wrong
```
Møtet har begynt <IKKE> og varer i en time. > 7
```
- Møtet har begynt og varer i en time. --> Correct
- Møtet har begynt, og varer i en time. --> Wrong
```

## Fine tuning with explanations

ChatGPT
The numbers following the '>' symbol, such as 1 or 7, represent keys in the dictionary of rules. These keys can be utilized to parse explanations for fine-tuning purposes.
Eva klatrer <KOMMA> og Ola går på ski. > 1

> - Eva klatrer, og Ola går på ski. --> Setningen har korrekt bruk av komma. Det skal alltid være komma mellom helsetninger som er bundet sammen med sideordnende konjunksjoner.
> - Eva klatrer og Ola går på ski. --> Setningen mangler et komma. Riktig bruk av komma er: «Eva klatrer, og Ola går på ski.» Det skal alltid være komma mellom helsetninger som er bundet sammen med sideordnende konjunksjoner.





