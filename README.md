IMDb Movie Review Sentiment Analysis 🎬
Overview
This project explores IMDb movie reviews using Natural Language Processing (NLP). The goal is to clean raw review text, prepare it for analysis, extract simple text-based features, and convert reviews into numerical data using the Bag of Words technique.
I also use exploratory visualizations and Principal Component Analysis (PCA) to examine the review data and visualize it in two dimensions.
Objectives
Clean raw movie reviews using Python string operations and regular expressions.
Tokenize reviews and remove English stop words.
Extract character-length and word-count features.
Explore positive and negative reviews using histograms and word clouds.
Convert text into numerical features using Bag of Words.
Use PCA to reduce the sampled feature matrix to two dimensions for visualization.
Project Workflow
Data Loading and Inspection — load the dataset and inspect its rows, dimensions, columns, and data types.
Data Cleaning — lowercase text, trim whitespace, remove HTML tags and URLs, and remove punctuation and special characters. A helper function for expanding selected contractions is defined in the notebook, but it is not currently applied to the review column.
Text Preprocessing — tokenize reviews, remove English stop words, and join the remaining tokens into cleaned text.
Feature Extraction — calculate character length and token count, then compare these features across sentiment labels.
Exploratory Visualization — create word clouds for positive and negative reviews.
Vectorization — use `CountVectorizer` to represent reviews as numerical word-count vectors, keeping up to 5,000 features.
Dimensionality Reduction — apply PCA to a random sample of up to 2,000 reviews and plot the first two principal components.
Tools and Libraries
Python
Pandas
NumPy
Regular Expressions (`re`)
NLTK
Matplotlib
Seaborn
WordCloud
Scikit-learn (`CountVectorizer` and `PCA`)
Jupyter Notebook
Dataset
The notebook expects a dataset named `IMDB Dataset.csv` containing at least these columns:
`review` — the movie review text
`sentiment` — the sentiment label, such as `positive` or `negative`
Update the CSV file path in the notebook to match your local setup. If the dataset is not included in this repository, add a link to the dataset source here before publishing.
Key Steps Explained
Text Cleaning
Text is normalized with lowercase conversion and whitespace trimming. Regular expressions are used to remove HTML tags and URLs, and selected contractions are expanded. Punctuation and special characters are also removed.
Text Preprocessing
Reviews are split into word tokens using NLTK. English stop words are filtered out, and the remaining tokens are joined back into text for vectorization.
Feature Extraction and EDA
Character length and token count are calculated for each review. Histograms compare these features between positive and negative reviews. Word clouds provide a visual overview of frequent words in each sentiment group.
Bag of Words
`CountVectorizer(max_features=5000)` converts the cleaned reviews into a document-term matrix using up to 5,000 vocabulary features. Sentiment labels are encoded as `1` for positive and `0` for negative.
PCA Visualization
PCA reduces the vectorized representation of a random sample of up to 2,000 reviews to two components. A Seaborn scatter plot colors the points by sentiment to help visually inspect how the reviews are distributed.
Observations
Character length and word count alone do not clearly separate positive and negative reviews in the explored distributions.
Word clouds offer a quick visual comparison of frequent words in the two sentiment groups.
The PCA scatter plot provides a two-dimensional view of the sampled Bag of Words data. Any visible overlap or separation is exploratory and does not, by itself, measure sentiment-classification performance.
Current Scope and Limitations
This project focuses on text cleaning, exploratory analysis, feature extraction, vectorization, and visualization. It does not currently train or evaluate a machine-learning sentiment classifier.
PCA is applied to a random sample because converting the sparse Bag of Words matrix to a dense array can require substantial memory. The two-dimensional PCA plot is an exploratory visualization, not a classifier.
How to Run
Clone or download this repository.
Install the required libraries:
```bash
   pip install pandas numpy nltk matplotlib seaborn wordcloud scikit-learn jupyter
   ```
Place `IMDB Dataset.csv` at the path specified in the notebook, or update the path to its location.
Open Jupyter Notebook and run the cells in order.
If prompted, download the NLTK resources required for tokenization and stop-word removal.
Future Improvements
Compare additional text features.
Experiment with bigrams using `CountVectorizer`.
Try other text representation techniques.
Train and evaluate a sentiment-classification model in a future version.
---
Project focus: Learning and applying foundational NLP concepts through IMDb movie review data.
