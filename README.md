## Purpose and structure
This repository is dedicated to testing the comma placement abilities of large language models in Norwegian sentences. The repository includes the following files:

- [kommaregler.json](https://github.com/hans-chr-f/komma/blob/main/kommaregler.json): A dictionary of Norwegian comma rules, where keys are arbitrary integers and values are sentences describing each rule.
- [test.txt](https://github.com/hans-chr-f/komma/blob/main/test.txt): A list of sentences, each annotated with correct punctuation, followed by an integer that matches a key in the dictionary.
- [train.txt](https://github.com/hans-chr-f/komma/blob/main/train.txt): More sentences in the same format.

## Data format
Each line in test.txt includes one sentence. Lines that begin with '#' serve as comments. The placement of commas is marked by &lt;KOMMA&gt; where they are needed and &lt;IKKE&gt; where they are not. Each line containing &lt;KOMMA&gt; or &lt;IKKE&gt; can be split into two tests. For example:

Eva klatrer &lt;KOMMA&gt; og Ola går på ski. > 1
```
- Eva klatrer, og Ola går på ski.  --> Correct
- Eva klatrer og Ola går på ski.   --> Wrong
```
Møtet har begynt &lt;IKKE&gt; og varer i en time. > 7
```
- Møtet har begynt og varer i en time. --> Correct
- Møtet har begynt, og varer i en time. --> Wrong
```
Lines that do not contain &lt;KOMMA&gt; or &lt;IKKE&gt; will generate only one test. They are all marked with '> 99', indicating that they are correctly formatted without any commas.

## Fine tuning with explanations
The numbers following the '>' symbol, such as 1 or 7, represent keys in the dictionary of rules. These keys can be utilized to parse explanations for fine-tuning purposes.

Eva klatrer &lt;KOMMA&gt; og Ola går på ski. > 1

> - Eva klatrer, og Ola går på ski. --> Setningen har korrekt bruk av komma. Det skal alltid være komma mellom helsetninger som er bundet sammen med sideordnende konjunksjoner.
> - Eva klatrer og Ola går på ski. --> Setningen mangler et komma. Riktig bruk av komma er: «Eva klatrer, og Ola går på ski.» Det skal alltid være komma mellom helsetninger som er bundet sammen med sideordnende konjunksjoner.





