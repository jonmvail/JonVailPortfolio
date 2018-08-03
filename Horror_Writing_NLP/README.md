# Jon Vail Horror Writers NLP
![alt text](https://github.com/jonmvail/JonVailPortfolio/blob/master/Horror_Writing_NLP/Images/free-vector-edgar-allen-poe-clip-art_105943_Edgar_Allen_Poe_clip_art_hight.png)

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

In the training data, the text leaned more heavily towards Edgar Allan Poe as opposed to the other authors, but not to a major degree. There is the possibility for issues with majority classes, but because there are more then 2 classes and the difference is not severe, the risk is limited and will not be focused on in the first modeling attempt.

**Data Distrobution**
- EAP    0.403494
- MWS    0.308698
- HPL    0.287808


![alt text](https://github.com/jonmvail/JonVailPortfolio/blob/master/Horror_Writing_NLP/Images/POE.png)


**EAP most common words**
1) said       245
2) little     192
3) say        188
4) time       178
5) man        171
6) great      164
7) did        144
8) long       144
9) having     131
10) day        128
11) eyes       125
12) head       125
13) like       121
14) length     119
15) far        114
16) mr         110
17) thought    110
18) left       107
19) way        103
20) old        100

![alt text](https://github.com/jonmvail/JonVailPortfolio/blob/master/Horror_Writing_NLP/Images/HP.png)


**HPL most common words**
1) old        278
2) like       190
3) night      179
4) did        176
5) man        175
6) saw        165
7) time       165
8) things     164
9) came       152
10) house      140
11) men        140
12) great      138
13) thing      137
14) heard      122
15) strange    118
16) said       110
17) street     107
18) door       106
19) long       102
20) thought    102

![alt text](https://github.com/jonmvail/JonVailPortfolio/blob/master/Horror_Writing_NLP/Images/MS.png)


**MWS most common words**
1) life       229
2) love       210
3) heart      183
4) did        177
5) raymond    176
6) eyes       174
7) time       163
8) man        155
9) said       148
10) day        139
11) death      137
12) mind       125
13) father     120
14) shall      117
15) like       113
16) night      109
17) saw        109
18) perdita    106
19) thought    100
20) nature      97

## Feature Engineering
The following features were created using nltk. Individual features were standardized before being added to the feature union. 

**Parts of Speech**
(Parts of speech were standardized by what percentage of words in the sentence are that part of speech)
- Noun Fraction
- Adverb Fraction
- Adjectives Fraction
- Future Tense Verb Fraction
- Present Tense Verb Fraction
- Past Tense Verb Fraction

**Sentiment Intensity Analyser**
- Compound (using nltk's sentiment analysis tool, the compound gives a since of how positive or negative a sentence is)

**Other**
- Word Count (What is the wordcount of the sentence)
- Question (Does the text end in a question mark)
- Highest Syllables (what is the highest syllable word in the sentence)

## MODELING

**Multinomial logistic Regression**

Accuracy

- Train .967
- Test .789

Log Loss

- Train .242
- Test .523

**Feature Importance: Text**
The majority of the feature importance relies on the individual words as opposed to the features that were created from the text vectorizing. 

**Random Forest**

Accuracy

- Train .986
- Test .647

Log Loss

- Train .205
- Test 1.42

**Feature Importance: Created Features**
The features that had the highest importance in the random forest are those that were created by me

**Ada Boosting**

Accuracy

- Train .561
- Test .562

Log Loss

- Train 1.06
- Test 1.06

**Feature Importance: Created and Text Features**
Adaboosting showed a mix of the vectorized text and created features as importance

## EVALUATION
Overall, Logistice Regression seems to work best, but overfitting prevents the model from performing to its best. More work would be needed to solve this problem. Once solved this method could be used to either expand this problem (Add more horror writers) or try to build model on different 
