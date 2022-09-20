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
