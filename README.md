#  Language Detector

A simple yet effective character-level n-gram based language detection tool trained on the [JRC-Acquis Multilingual Corpus](https://wt-public.emm4u.eu/Acquis/JRC-Acquis.3.0/). 
This project uses **Multinomial Naive Bayes** for classification and is capable of detecting English, German, Spanish, and French from plain text input.

##  Dataset

This project downloads and uses small portions of the **JRC-Acquis 3.0** corpus for the following languages:

- English (`en`)
- German (`de`)
- Spanish (`es`)
- French (`fr`)

Corpus files are extracted and loaded into memory using `os.walk`, and the data is stored as a Pandas DataFrame with columns:
- `text`: the raw text from a file
- `label`: the corresponding language

##  Model

The model pipeline consists of:

- **Preprocessing**: lowercasing and removing special characters.
- **Vectorization**: using `CountVectorizer` with character n-grams (`n=1–3`), a `min_df` of 5, and a `max_features` cap of 1000.
- **Classifier**: `MultinomialNB` from `sklearn`.

## Usage

Access Google Colab, create a new notebook and paste the file contents there. The loading time should run under 10 minutes, after that, the magic happens.


## Conclusion

This was a fun project that helped me grasp machine learning better and was fundamental for another, more advanced project I intend to push to github once I figure out the logistics. Very fun!
