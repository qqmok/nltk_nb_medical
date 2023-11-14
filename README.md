# nltk_nb_medical
## Problem
Goal of this exercise is to classify a given English text between medical and non-medical. A Naive Bayes Classifier was trained for this purpose. It takes a list of counted words (Bag of Words) of a given text and predicts a class (either medical or non-medical).
## Structure and Pipeline
The program can be devided into the following sections.
### Data Collection using MediaWiki
The program accesses articles form Wikipedia to compose its training corpus. Using the MediaWiki API, random articles can be fetched, while you can distinguish medical texts from non-medical ones by looking at the categories assigned to the article. This process will be repeated until a minimum amount of both medical and non-medical articles is reached.
### Data Preprocessing using NLTK
The gathered articles then go through a sequence of preprocessing methods. First a clean text is extracted form the HTML data of the aricles's page, which is then tokenized to obtain a list of words. After removing the stopwords, the words in the list are stemmed and lemmatized using NLTK. A Bag of Words is created by counting the words in the list, it receives a respective label depending on the class of the article so that it can be used for training the classifier.
### Training and Classification
After the preprocessing there will be a list of medical Bag of Words data and a list of non-medical Bag of Words data. Elements from both lists are then shuffled together to create the training and test set. Now the Naive Bayes Classifier from NLTK can be trained on the train set. After that the the classfier can be used to either classify new texts (in form of the preprocessed Bag of Words) or be tested on the test set to determine the accuracy of the classifier.
## Technologies
**MediaWiki API**: Retrieving text and annotations from Wikipedia

**NLTK**: Text processing and classification

**BeautifulSoup**: Replacement for the `clean_html()` method in NLTK
