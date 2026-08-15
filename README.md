# Fake News Classification: NLP & CNN Experiments

An experimental natural-language-processing project for classifying real and fake news articles with a 1D convolutional neural network (CNN).

The repository contains multiple notebook experiments that keep the same general text-classification workflow while comparing different neural-network optimizers, including **Adam**, **Adamax**, **SGD**, and **Adadelta**.

> This repository is currently private and represents an experimental/learning workflow rather than a packaged production model.

## Experiment Workflow

The notebooks cover a pipeline similar to:

1. Load separate real-news and fake-news CSV datasets.
2. Add binary class labels and combine the datasets.
3. Clean text with regular expressions and lowercase normalization.
4. Tokenize text with NLTK.
5. Apply lemmatization and stemming.
6. Convert text into numerical features and padded sequences.
7. Split the data into training and test sets.
8. Train a Keras `Sequential` model containing `Conv1D`, pooling, dense, and dropout layers.
9. Evaluate the classifier with loss, accuracy, predictions, and a confusion matrix.
10. Repeat the experiment with different optimizers to compare training behaviour.

## Tech Stack

- Python
- NumPy
- Pandas
- NLTK
- scikit-learn
- TensorFlow / Keras
- Jupyter Notebook / Google Colab

## Repository Structure

```text
nlp-project/
├── Accurasy tests/        # Legacy folder name kept to preserve notebook history
│   ├── Adam
│   ├── Adamax
│   ├── SGD
│   └── adadelta
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

The files in `Accurasy tests/` are legacy Colab notebook JSON files stored without the usual `.ipynb` extension. They are preserved as-is rather than being renamed or rewritten just for presentation, because they contain historical experiment output.

## Dataset Setup

The news datasets are **not included** in the repository. The notebooks expect separate real-news and fake-news CSV files with fields such as:

- `title`
- `text`
- `subject`
- `date`

The existing notebook cells contain empty placeholders similar to:

```python
true_data = pd.read_csv("")
fake_data = pd.read_csv("")
```

Set those paths to your local or Colab dataset files before running an experiment.

## Environment

Create a virtual environment and install the dependencies:

```bash
python -m venv .venv
```

**Windows**

```bash
.venv\Scripts\activate
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

Then install:

```bash
pip install -r requirements.txt
```

## NLTK Note

The legacy notebooks call:

```python
nltk.download("all")
```

That downloads the complete NLTK data collection and is much heavier than this project normally needs. For a future cleanup, it would be better to request only the resources actually used by the preprocessing pipeline, such as the tokenizer and WordNet resources required by the installed NLTK version.

## Model

The inspected CNN experiment uses a structure based on:

- `Conv1D`
- `MaxPooling1D`
- `Flatten`
- dense hidden layer with ReLU
- dropout regularization
- softmax output layer

The optimizer is changed between experiment files so their training behaviour can be compared under a similar model structure.

## Reproducibility Caveats

The notebooks were created as Colab experiments and are not yet a fully reproducible benchmark suite. In particular:

- dataset paths must be supplied manually
- dataset files are not versioned here
- notebook outputs come from historical runs
- random seeds and a single shared train/test split should be fixed before treating optimizer results as a controlled comparison
- software versions were not pinned in the original experiments

Because of those limitations, historical accuracy values should be treated as experiment outputs, not as a rigorous optimizer ranking.

## Good Next Steps

- convert the legacy experiment files to standard `.ipynb` notebooks
- extract shared preprocessing/model code into reusable Python modules
- download only required NLTK resources
- fix random seeds and reuse the same split across optimizers
- record metrics in a single comparison table
- add precision, recall, F1 score, and confusion-matrix plots
- save experiment configuration and model metadata

## License

See [`LICENSE`](LICENSE).