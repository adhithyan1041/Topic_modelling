# The below text mining steps are carried out as part of the coding challenge.

## * Step1 : 
The given data is cleaned and standardized (the date fields and text fields are standardized) using open refine tool.
  
## * Step2 :
The given data is checked and removed if any duplicates values are present
  
## * Step3 : 
The given data is preprocessed so as to improve the efficiency of the NLP algorithms.
The below steps are carried out:
 * 1) Using regular expression to consider only the text values.
 * 2) The text fields are converted to lower case to avoid confusions of same word repeated (eg: The words Apple and apple will be considered as 2 seperate words by NLP algorithms)
 * 3) The words in the text fields are tokenized using Spacy library. I used spacy because it was more efficient in terms of speed and logic wise than NLTK.
 * 4) The stop words(like a, the etc) are removed using spacy library.
 * 5) The words are lemmatized (converting the words to its base form) using spacy library. 
 		
## * Step4 : 
The common words from the text field are identified using collections library and random 10 projects are visualized using wordcloud.
  
## * Step5 : 
The text column is topic modelled using Latent Direchlet Allocation algorithm and the underlying topics are identified and appended to the dataframe as topic_number (column name).
  
## * Step6 : 
The topic wise word distribution is visualised using pyLDAvis library. 
  
## * Step7 : 
For an example of how to use this data, A Logistic Regression model is created to predict the funding organization(topics column in the project dataset).
* 1) The project duration is calculated using the project start and end date.
* 2) The project duration,totalcost,topic_number and ecMaxcontribution are used as predictor variables
* 3) The data is divided into train and test set using train_test_split function.
  
## * Step8 : 
Similary, Linear regression model is created in order to predict the ecMaxcontribution amount provided the total cost,duration of the project and the topic number is given.
* Note: This was done as an example to show how can we use the topic modelling algorithm in this dataset. Some of the data cleaning steps (in this case, the numeric values in the topics column should be removed) has to be done to improve the accuracy of the model.
  
## * Step9 : 
Text Summarization of the objective is done using pegasus model abstractive text summarization algorithm using transformers library from hugging face.
I chose the abstractive method rather extractive method, Since the abstractive method understands the text better and summarizes on its own than using the same sentenses from the original texts like extractive method.
