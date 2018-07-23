# Jon Vail Horror Writers NLP

Date: **July 17, 2018**

Kaggle compitiotion "Spooky Author Identification"

https://www.kaggle.com/c/spooky-author-identification

## GOAL
Use classification models to identify the works of Mary Shelly, Edgar Allen Poe, and HP Lovecraft. I look use literary research to attempt to create features that can be used to identify one author from another. For example, using topic clustering, I could identify sentences that center around a certain theme and use that to create features that might be useful. Also looking at the structure of the sentence or if the sentence has a poetic meter. Stretch goals include adding more authors, and building a creator that will try to write sentences in the style of the different authors. Use train test split for cross validation and use test set for further evaluation on model performance.

## DATA

Train.csv
3 Columns 
1) ID (Index)
2) text (Quote)
3) Author (target)

Test.csv
2) Columns
1) ID (Index)
2) text (Quote)

No nulls present. Text seems clean. only oddity found during exploration is that opening quote marks will be present but not end quote marks and vice versa. Makes sence, but will make finding diologue difficult if I want to model off that.

## EDA 

EAP    0.403494
MWS    0.308698
HPL    0.287808

EAP most common words
said       245
little     192
say        188
time       178
man        171
great      164
did        144
long       144
having     131
day        128
eyes       125
head       125
like       121
length     119
far        114
mr         110
thought    110
left       107
way        103
old        100

HPL most common words
old        278
like       190
night      179
did        176
man        175
saw        165
time       165
things     164
came       152
house      140
men        140
great      138
thing      137
heard      122
strange    118
said       110
street     107
door       106
long       102
thought    102

MWS most common words
life       229
love       210
heart      183
did        177
raymond    176
eyes       174
time       163
man        155
said       148
day        139
death      137
mind       125
father     120
shall      117
like       113
night      109
saw        109
perdita    106
thought    100
nature      97

## MODELING

Multinomial logistic Regression

Accuracy

- Train .967
- Test .789

Log Loss

- Train .242
- Test .523

Feature Importance: Text

Random Forest

Accuracy

- Train .986
- Test .647

Log Loss

- Train .205
- Test 1.42

Feature Importance: Created Features

Ada Boosting

Accuracy

-Train .561
- Test .562

Log Loss

- Train 1.06
- Test 1.06

Feature Importance: Created and Text Features

## EVALUATION
Overall, Logistice Regression seems to work best, but overfitting prevents the model from performing to its best. More work would be needed to solve this problem. Once solved this method could be used to either expand this problem (Add more horror writers) or try to build model on different 
