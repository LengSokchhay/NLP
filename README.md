README: Dinosaur Wikipedia Text Analysis and Language Modeling

-------------------------------------------------------------------------------------------------------------- 

Overview
This project analyzes text data from the Wikipedia page on Dinosaurs and builds a language model using N-gram modeling techniques. The language models implement both back-off and interpolation methods to predict word sequences. This repository showcases preprocessing, tokenization, statistical modeling, and text generation.

Features
Text Extraction: Downloads the Wikipedia page content for "Dinosaur".
Text Cleaning: Cleans raw Wikipedia text by removing special characters, citations, URLs, and redundant spaces.
Tokenization: Splits the cleaned text into sentences and tokenizes sentences into words.
Train-Test Split: Divides tokenized data into training, validation, and testing datasets.
N-Gram Model Building: Builds a 4-gram (sequence of four consecutive tokens) statistical language model using:
Backoff Probabilities for predicting the probability of sequences when encountering unknown events.
Interpolated Probabilities with smoothing for better handling of rare sequences.
Perplexity Calculation: Measures the model's performance on unseen data using perplexity, a standard language model evaluation metric.
Text Generation: Generates sample text using back-off and interpolation probabilities as part of a statistical prediction mechanism.

-------------------------------------------------------------------------------------------------------------- 


Dependencies
This project relies on:

wikipedia-api: To fetch Wikipedia page data for "Dinosaur".
nltk: For tokenization and sentence processing.
pandas: For data analysis and visualization.
re (regular expressions): To clean and preprocess text data.
Install these dependencies using pip:

bash
Copy code
pip install wikipedia-api nltk pandas

-------------------------------------------------------------------------------------------------------------- 

Getting Started
1. Extract Wikipedia Data
The script fetches the Wikipedia page for Dinosaur and saves the raw text to data2/wiki_dataset.txt. The raw data extraction step relies on the Wikipedia API.

2. Preprocess Text
The preprocessing removes:

Citations like [1].
URLs.
Parenthetical information.
Excessive formatting and whitespace.
The cleaned text is saved to data2/cleaned_wiki_text.txt.

3. Tokenization and Split
Tokenizes sentences and splits the data into training, validation, and test sets (train_set.txt, val_set.txt, test_set.txt). Tokenization relies on nltk.

4. Language Model Creation
Using tokenized text, a 4-gram statistical language model is trained with two methods:

Backoff Modeling: Predicts sequences using fallback probabilities when data is unseen.
Interpolation Modeling: Combines probabilities over different N-grams using a weighted smoothing factor.

-------------------------------------------------------------------------------------------------------------- 

Evaluation
The code computes Perplexity, a metric to evaluate how well the model predicts sequences on unseen data. Lower perplexity indicates better performance.

1. Backoff Model: Estimates probability based on the fallback sequence probabilities.
2. Interpolation Model: Combines multiple levels of probabilities with smoothing.
Both models' results are printed, e.g.:

python
Copy code
pp_lm1: 45.2
pp_lm2: 30.4

-------------------------------------------------------------------------------------------------------------- 


Text Generation
The code can generate sequences based on predictions made by the trained statistical models. Text is generated by predicting sequences of tokens using:

The backoff model.
The interpolation model.
Sample outputs are generated and displayed.


-------------------------------------------------------------------------------------------------------------- 

Directory Structure
bash
Copy code
project/
│
├── data2/
│   ├── wiki_dataset.txt            # Raw Wikipedia text extraction.
│   ├── cleaned_wiki_text.txt      # Preprocessed text from Wikipedia.
│   └── wiki_article/
│       ├── train_set.txt          # Training data.
│       ├── val_set.txt            # Validation data.
│       └── test_set.txt           # Testing data.
│
├── main_script.py                 # Script running the entire pipeline.
├── models.py                     # Functions for language modeling.
└── README.md                     # This file.

-------------------------------------------------------------------------------------------------------------- 


How to Run
Setup: Ensure all dependencies are installed:
bash
Copy code
pip install wikipedia-api nltk pandas
Execute the script:
bash
Copy code
python main_script.py
Review Results:
The script will download the Wikipedia article on Dinosaur.
Preprocess and tokenize text data.
Train a 4-gram language model and compute perplexity scores.
Generate example text using the backoff and interpolation models.

-------------------------------------------------------------------------------------------------------------- 
Credits

Wikipedia API: Data source for dinosaur knowledge extraction.
NLTK Tokenizer: Tokenization and preprocessing functionality.
Pandas & Regular Expressions: Used for data cleaning and statistical analysis.
License
This project is licensed under the MIT License. Use it freely for research, learning, and exploration.