# Spam Email Checker

Detect spam and ham messages with a **machine-learning classifier**. The model
combines text preprocessing, TF-IDF vectorization, and logistic regression, and
is trained on a real ham/spam message dataset. After training, you can paste any
email text into the interactive prompt and get an instant classification.

![Python](https://img.shields.io/badge/Python-3.x-3776AB)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E)
![NLTK](https://img.shields.io/badge/NLTK-NLP-277A9F)
![pandas](https://img.shields.io/badge/pandas-data--analysis-150458)

## How it works

The classification pipeline:

1. **Clean** â€” remove non-word characters, lowercase the text
2. **Stem** â€” remove English stopwords and apply Porter stemming
3. **Vectorize** â€” convert text to a TF-IDF feature matrix (3,000 features)
4. **Classify** â€” logistic regression predicts spam vs not-spam

The dataset is split 80/20 for training and evaluation, and the script prints the
model's **accuracy** and a **classification report** on startup.

## Getting Started

### Requirements

Install the dependencies:

```bash
pip install pandas scikit-learn nltk
```

### Run the classifier

```bash
python Spam_Email_Detector/app.py
```

After training, paste an email (multi-line is fine) and finish with a line
containing just `END`. Type `exit` to quit:

```
Paste the email (multi-line is fine). On its own line type END to classify, or 'exit' to quit :
WINNER!! This is the last call to collect... 
END
Prediction: Spam
```

> **Note:** the script expects the dataset file `mail_data.csv` (columns
> `Category` + `Message`) â€” if it's not found, adjust the file path at the top of
> `app.py`.

## Dataset

The `Spam_Email_Detector` folder bundles:

- `mail_data.csv` â€” the labeled dataset used for training
- `spam.csv` â€” an additional sample of raw SMS messages

## Project structure

```
spam_email_checker_using_ML/
â””â”€â”€ Spam_Email_Detector/
    â”œâ”€â”€ app.py          # Training + interactive prediction
    â”œâ”€â”€ mail_data.csv   # Labeled training data
    â””â”€â”€ spam.csv        # Raw message samples
```

## License

This project is open-source and available under the [MIT License](LICENSE).