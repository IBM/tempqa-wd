# Temporal question answering dataset for Wikidata: `Tempqa-wd`
`Tempqa-wd` is a wikidata-based dataset focused on temporal reasoning.
## Dataset details
`Tempqa-wd` is obtained by annotating questions in [TempQuestions](https://github.com/zhenjia2017/tequila) dataset (of size 1271) with the corresponding Wikidata SPARQL queries and Wikidata answers.
We removed the questions where wikidata answers were not present. The resulting subset of 839 questions is divided into dev and test set.

### Test set: 
The test set has 664 questions, where each question consist of the following attributes
1. `ID`: Question id is taken as it is from the TempQuestions dataset
2. `TEXT`: Question text is taken as it is from the TempQuestions dataset
9. `SPARQL`: Wikidata SPARQL queries
10. `ANSWERS`: Wikdata answers
11. `FREEBASE_ANSWERS`: Freebase answers are taken as it is from TempQuestions dataset
12. `TEMPORAL_SIGNAL`: Temporal relation between events present in question. These are taken as it is from TempQuestions dataset
13. `TYPE`: Question type taken as it is from the TempQuestions dataset
14. `DATA_SOURCE`: Source of the question taken as it is from TempQuestions dataset
15. `CATEGORY`: Complexity of the question in terms of temporal and non-temporal reasoning required to get the answer. There are three categories: `Simple`, `Medium` and, `Complex`
### Dev set:
Dev set has 175 questions, where each question consists of the following additional attributes along with attributes for question in the test set
1. `AMR`: AMR corresponding to the question text
1. `LAMBDA`: Lambda expression corresponding to the question text 
5. `ENTITIES`: Entities present in question. Each entity consists of:
    1. `SURFACEFORM`: Entity surface form
    2. `WIKIDATAID`: Entity Wikidata IRI 
7. `RELATIONS`: Relations present in question. Each relation consists of:
    1. `REFERENCE_EXPRESSION`: Reference variable corresponding to the sub-expression in `LAMBDA`
    2. `SUBJECT`: Wikidata IRI for the subject in sub-expression
    3. `PROP`: Wikidata IRI for the predicate in sub-expression
    4. `OBJECT`: Wikidata IRI for the object in sub-expression
    5. `IS_REIFIED`: `true` if Wikidata predicate is reified, `false` otherwise
    6. `IS_DATE`: `true` if the range of Wikidata predicate is date, `false` otherwise
8. `LAMBDA_KBSPECIFIC`: Lambda expression obtained from `LAMBDA` by replacing entity and relation surface forms with Wikidata specific entity and relation IRIs. 
