# __Persian Named Entity Recognition Models Comparison__

This repo is a comparison between **bert-fa-zwnj** and **xlm-roberta**. These models are fine-tuned on either **ParsNer** or **SemEval** for NER task.

## Datasets
There was four popular datasets for NER task in Persian, and [Hooshvare Team](https://github.com/hooshvare/) introduced another dataset that is a mixture of three of them:
- [ARMAN](https://github.com/HaniehP/PersianNER), 
- [PEYMA](http://nsurl.org/2019-2/tasks/task-7-named-entity-recognition-ner-for-farsi/),
- [WikiANN](https://elisa-ie.github.io/wikiann/),
- [SemEval 2022: task 11 Persian dataset](https://multiconer.github.io/dataset), and
- [ParsNer](https://drive.google.com/uc?id=1fC2WGlpqumUTaT9Dr_U1jO2no3YMKFJ4) mixed NER dataset collected from ARMAN, PEYMA, and WikiANN

ParsNer tags:
>- DAT: Date
- EVE: Event
- FAC: Facility
- LOC: Location
- MON: Money
- ORG: Organization
- PCT: Percent
- PER: Person
- PRO: Product
- TIM: Time

SemEval tags:
> - PER: Names of people
- LOC: Location or physical facilities
- CORP: Corporations and businesses
- GRP: All other groups
- PROD: Consumer products
- CW: Titles of creative works like movie, song,
and book title

Statistics:

| Dataset |train | validation set | test set|
| - | - | - | - |
| ParsNer | 29,133 | 5,142 | 6,049 |
| SemEval - Fa |15,300 |	800 |	165,702 |

## Results' comparison on ParsNer dataset
These three models are fined-tuned on ParsNer train set and results are on ParsNer test set.


* __Pretrained model__: xlm-roberta-large

| - | precision | recall | f1-score |
| - | - | - | - |
| DAT | 0.76 | 0.81 | 0.78 |
| EVE | 0.86 | 0.97 | 0.91 |
| FAC | 0.84 | 0.99 | 0.90 |
| LOC | 0.95 | 0.94 | 0.95 |
| MON | 0.92 | 0.93 | 0.93 |
| ORG | 0.90 | 0.94 | 0.92 |
| PCT | 0.87 | 0.89 | 0.88 |
| PER | 0.97 | 0.98 | 0.97 |
| PRO | 0.87 | 0.98 | 0.92 |
| TIM | 0.82 | 0.91 | 0.86 |
| __micro__ | 0.93 | 0.95 | 0.94 | 16927 |
| __macro__ | 0.88 | 0.93 | 0.90 | 16927 |
| __weighted__ | 0.93 | 0.95 | 0.94 | 16927 |


* __Pretrained model__: xlm-roberta-base

| - | precision | recall | f1-score |
| - | - | - | - |
| DAT | 0.60 | 0.73 | 0.66 |
| EVE | 0.65 | 0.87 | 0.74 |
| FAC | 0.71 | 0.95 | 0.81 |
| LOC | 0.90 | 0.88 | 0.89 |
| MON | 0.85 | 0.86 | 0.85 |
| ORG | 0.81 | 0.89 | 0.85 |
| PCT | 0.79 | 0.87 | 0.83 |
| PER | 0.95 | 0.96 | 0.96 |
| PRO | 0.74 | 0.89 | 0.81 |
| TIM | 0.35 | 0.17 | 0.23 |
| __micro__ | 0.86 | 0.90 | 0.88 | 16927 |
| __macro__ | 0.73 | 0.81 | 0.76 | 16927 |
| __weighted__ | 0.86 | 0.90 | 0.88 | 16927 |


* __Pretrained model__: HooshvareLab/bert-fa-zwnj-base

| - | precision | recall | f1-score |
| - | - | - | - |
| DAT | 0.71 | 0.75 | 0.73 |
| EVE | 0.78 | 0.92 | 0.84 |
| FAC | 0.78 | 0.91 | 0.84 |
| LOC | 0.92 | 0.93 | 0.92 |
| MON | 0.83 | 0.82 | 0.82 |
| ORG | 0.87 | 0.90 | 0.88 |
| PCT | 0.90 | 0.88 | 0.89 |
| PER | 0.95 | 0.95 | 0.95 |
| PRO | 0.84 | 0.95 | 0.89 |
| TIM | 0.66 | 0.43 | 0.52 |
|__micro__ | 0.89 | 0.92 | 0.90 | 13979 |
|__macro__ | 0.82 | 0.84 | 0.83 | 13979 |
|__weighted__ | 0.89 | 0.92 | 0.90 | 13979 |


* __Entity comparison__ (f1-score)

|Entities| xlm-roberta-large | xlm-roberta-base | bert-fa-zwnj-base |
| - | - | - | - |
| DAT | 0.78 | 0.66 | 0.73 | 
| EVE | 0.91 | 0.74 | 0.84 | 
| FAC | 0.90 | 0.81 | 0.84 | 
| LOC | 0.95 | 0.89 | 0.92 | 
| MON | 0.93 | 0.85 | 0.82 | 
| ORG | 0.92 | 0.85 | 0.88 | 
| PCT | 0.88 | 0.83 | 0.89 | 
| PER | 0.97 | 0.96 | 0.95 | 
| PRO | 0.92 | 0.81 | 0.89 | 
| TIM | 0.86 | 0.23 | 0.52 | 


* __Weighted avg comparison__

| - | precision | recall | f1-score |
| - | - | - | - |
| __xlm-roberta-large__ | 0.93 | 0.95 | 0.94 | 16927 |
|__xlm-roberta-base__ | 0.86 | 0.90 | 0.88 | 16927 |
|__bert-fa-zwnj-base__ | 0.89 | 0.92 | 0.90 | 13979 |



## Results' comparison on SemEval dataset
These two models are fined-tuned on SemEval train set and results are on SemEval test set.


* __Pretrained model__: xlm-roberta-large

| - | precision | recall | f1-score |
| - | - | - | - |
| CORP | 0.56 | 0.56 | 0.56 |
| CW | 0.41 | 0.54 | 0.46 |
| GRP | 0.58 | 0.56 | 0.57 |
| LOC | 0.65 | 0.65 | 0.65 |
| PER | 0.70 | 0.72 | 0.71 |
| PROD | 0.60 | 0.61 | 0.60 |
| micro | 0.59 | 0.62 | 0.60 |
| macro | 0.58 | 0.61 | 0.59 |
| weighted | 0.60 | 0.62 | 0.61 |


* __Pretrained model__: bert-fa-zwnj-base

| - | precision | recall | f1-score |
| - | - | - | - |
| CORP | 0.51 | 0.56 | 0.53 |
| CW | 0.22 | 0.40 | 0.28 |
| GRP | 0.50 | 0.47 | 0.48 |
| LOC | 0.52 | 0.49 | 0.51 |
| PER | 0.56 | 0.64 | 0.60 |
| PROD | 0.48 | 0.47 | 0.47 |
| micro | 0.45 | 0.51 | 0.48 |
| macro | 0.46 | 0.51 | 0.48 |
| weighted | 0.47 | 0.51 | 0.49 |


* __Weighted avg comparison__

| - | precision | recall | f1-score |
| - | - | - | - |
| __xlm-roberta-large__ | 0.60 | 0.62 | 0.61 |
| __bert-fa-zwnj-base__ | 0.47 | 0.51 | 0.49 |


* __Entity comparison__ (f1-score)

|Entities| xlm-roberta-large | bert-fa-zwnj-base |
| - | - | - |
| CORP | 0.56 | 0.53 | 
| CW | 0.46 | 0.28 | 
| GRP | 0.57 | 0.48 | 
| LOC | 0.65 | 0.51 | 
| PER | 0.71 | 0.60 | 


