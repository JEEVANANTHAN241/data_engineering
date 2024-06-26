# BBC Article Classification

This project aims to preprocess and vectorize the BBC article dataset for text classification tasks using natural language processing (NLP) techniques.

# Dataset

The dataset used in this project is the BBC article dataset, which consists of articles from the BBC news website, categorized into different topics. The dataset is provided in a zip file named `data.zip`, containing a folder named `BBC_articles`. Inside this folder, there are text files named as `articleID_category`, where `articleID` is a unique identifier, and `category` is the topic of the article.

# Data Structuring

The first step of the project is to structure the data by creating a CSV file named `bbc_articles.csv` with the following columns:

* `article_id`: Unique identifier for each article.
* `text`: Text content of the article.
* `category`: Category or topic of the article.

This CSV file is generated by reading the text files in the `BBC_articles` folder and extracting the necessary information.

# Data Preprocessing

The next step involves preprocessing the text data to prepare it for feature extraction and model training. The preprocessing steps include:

1. Tokenization: Splitting the text into individual words or tokens using the NLTK library.
2. Preprocessing:
   * Removing numerals from the text.
   * Converting the text to lowercase.
   * Removing punctuation.
   * Lemmatization: Reducing words to their base or root form using the WordNet lemmatizer from NLTK.
3. Removing stopwords: Eliminating common words like "the", "a", "and", etc., which provide little or no semantic value.

# Feature Extraction

After preprocessing, the text data is converted into numerical features using the TF*IDF (Term Frequency*Inverse Document Frequency) vectorization technique. The TF*IDF vectorizer from scikit*learn is used with a maximum of 10,000 features, which selects the 10,000 most frequent terms based on their TF*IDF scores across the dataset.

The resulting numerical features and corresponding category labels are stored in a new CSV file named `vectorized_dataset.csv`. To reduce the file size, the floating*point precision of the numerical features is limited to 4 decimal places using the `float_format` parameter when saving the CSV file.

# Usage

To run the project, follow these steps:

1. Ensure you have the required dependencies installed, including Python, pandas, NLTK, scikit*learn, and any other necessary libraries.
2. Extract the `data.zip` file to obtain the `BBC_articles` folder.
3. Run the provided Python script, which will perform the following tasks:
   * Create the `bbc_articles.csv` file.
   * Preprocess the text data.
   * Extract numerical features using TF*IDF vectorization.
   * Save the vectorized dataset as `vectorized_dataset.csv`.
4. The `vectorized_dataset.csv` file can then be used for training machine learning models for text classification tasks.

Note: The Python script and any additional instructions or requirements for running the code are provided separately.
