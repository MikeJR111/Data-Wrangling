## Introduction:
Text documents, such as reviews, are usually composed of topically coherent text data, which
within each topically coherent data, one would expect that the word usage demonstrates more
consistent lexical distributions than that across the data-set. A linear partition of texts into topic
segments can be used for text analysis tasks, such as passage retrieval in IR (information
retrieval), document summarization, recommender systems, and learning-to-rank methods.

## Task 1: Parsing Text Files

extracting data from semi-structured text files. Each student is provided with a data-set that contains
information about reviews from a retail company users on its products

Each text file contains information about the reviews, i.e., “reviewer ID”, “product ID”, “reviewer name”,
“number of helpful flags”, “review date”, “review text”, and the “review summary”. Your
task is to extract the data from the text file and transform the data into a XML format with the
following elements:
1. users: this tag wraps all the users
2. user: this tag wraps all the reviews from a particular user and keeps the meta data for
each user such as the latest review date and its username.
3. reviews: wraps all the reviews of a specific user
4. review: for each user, this tag wraps the product ID, review text, review date,
review_helpful info, and review summary of the user review

### Purpose

* Designing efficient regular expressions in order to extract the data from your textual
dataset

* Storing and submitting the extracted data into an XML file.


## Task2:  Text Pre-Processing

converting the extracted data
into a numeric representation. In this task, you are required to write Python code to preprocess a
set of articles about user reviews and convert them into numerical representations 

1. Generate the corpus vocabulary with the same structure as sample_vocab.txt. Please
note that the vocabulary must be sorted alphabetically.
2. For each unique date (articles come with a date at their title), generate the sparse
representation (i.e., doc-term matrix) of the Excel file according to the structure of the
sample_countVec.txt. The review texts and the review summaries of the same date
must be concatenated before converting to the vector representation. The order of
concatenation is not important for us (e.g., assuming “review1” and “review2” are both
written on the same day, then you can either do review1+review2 or review2+review1).

### steps:

1. The word tokenization must use the following regular expression,
"[a-zA-Z]+(?:[-'][a-zA-Z]+)?"
2. The context-independent and context-dependent stopwords must be removed from
the vocabulary.
○ For context-independent, The provided context-independent stop words list (i.e,
stopwords_en.txt) must be used.
○ For context-dependent stopwords, you must set the threshold to more than
ceil(Number_of_days / 2).
3. Tokens should be stemmed using the Porter stemmer.
4. Rare tokens (with the threshold set to less than 10 days (i.e. 10 unique dates)) must
be removed from the vocab.
5. Creating the sparse matrix using countvectorizer.
6. Tokens with a length less than 3 should be removed from the vocab.
7. First 200 meaningful bigrams (i.e., collocations) must be included in the vocab using
PMI measure.
8. Calculate the vocabulary containing both unigrams and bigrams.
