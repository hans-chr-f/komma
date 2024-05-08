# Dataset Card for Norwegian Comma Benchmark (ncb)
# Dataset Card for Norwegian Comma Benchmark

## Dataset Description
- **Point of Contact:** [Hans Christian Farsethås](mailto:hans.farsethas@uib.no)
- **Point of Contact:** [Joakin Tjøstheim](mailto:joakimtjostheim@outlook.com)

### Dataset Summary

The SNLI corpus (version 1.0) is a collection of 570k human-written English sentence pairs manually labeled for balanced classification with the labels entailment, contradiction, and neutral, supporting the task of natural language inference (NLI), also known as recognizing textual entailment (RTE).

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


## Additional Information

### Dataset Curators
The Norwegian Comma Benchmark was created by Hans Christian Farsethås and Joakim Tjøstheim

### Licensing Information
