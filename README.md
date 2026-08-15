# Fake News Detection — NLP & CNN Experiments

This repository contains **my NLP and deep-learning experiment work contributed to the collaborative [Fake News Detection](https://github.com/hosseindamavandi/Fake-News-Detection) project**.

It is intentionally scoped to my experimental work rather than presented as the complete team project. The original repository contains the integrated data-preparation, training, model, and inference pipeline.

## Project context

The team project explores AI approaches for classifying fake and real news, including neural-network, convolutional, and recurrent architectures. My work in this repository focuses on an NLP preprocessing pipeline and CNN classification experiments, including comparisons across several optimizers.

**Original collaborative project:**  
https://github.com/hosseindamavandi/Fake-News-Detection

**My GitHub account:**  
https://github.com/HoosseinRahimi

## My contribution

The notebooks in this repository document experiments around:

- combining real and fake news datasets and assigning class labels
- categorical encoding of article subjects
- text cleaning and normalization
- tokenization
- lemmatization and stemming with NLTK
- bag-of-words feature extraction with `CountVectorizer`
- train/test preparation
- 1D CNN classification with Keras
- dropout-based regularization
- confusion-matrix evaluation
- optimizer experiments using **Adam**, **Adamax**, **SGD**, and **Adadelta**

These notebooks are preserved as experiment snapshots from the development process. They are not intended to replace the final integrated implementation in the main project repository.

## Repository structure

```text
.
├── notebooks/
│   ├── README.md
│   └── optimizer_experiments/
│       ├── adam.ipynb
│       ├── adamax.ipynb
│       ├── sgd.ipynb
│       └── adadelta.ipynb
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Dataset

The collaborative project uses the **ISOT Fake News Dataset**. It contains real and fake news articles with fields such as title, text, subject, and publication date.

Dataset information:  
https://onlineacademiccommunity.uvic.ca/isot/2022/11/27/fake-news-detection-datasets/

The dataset itself is **not redistributed in this repository**. Download it from its original source and provide the `True.csv` and `Fake.csv` files locally when reproducing the experiments.

## Historical experiment result

One preserved Adam notebook records a test accuracy of approximately **77.45%** with a confusion matrix produced by the CNN experiment.

That number is included only as a historical development result. It should **not** be treated as a fully reproducible benchmark because the original notebook contains environment-dependent data paths and some experiment steps were created interactively in Google Colab.

For the final project-level model design, training setup, and reported results, refer to the original collaborative repository.

## Setup

Create a virtual environment and install the dependencies:

```bash
python -m venv .venv
```

Linux/macOS:

```bash
source .venv/bin/activate
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Then install the packages:

```bash
pip install -r requirements.txt
```

The historical notebooks use NLTK resources. Instead of downloading the entire NLTK collection, install only the resources required by the notebook you are reproducing, such as the tokenizer and WordNet data.

## Reproducibility notes

These notebooks were originally developed in Google Colab and still contain historical outputs. To reproduce an experiment:

1. Download the ISOT dataset from the original source.
2. Update the `True.csv` and `Fake.csv` paths in the selected notebook.
3. Install the dependencies from `requirements.txt`.
4. Install the required NLTK data packages.
5. Run the notebook from top to bottom in a clean environment.

Because these are historical experiment snapshots, package-version differences may affect results.

## Attribution and scope

This repository represents **my contribution and experiments within a team project**. It does not claim sole authorship of the complete Fake News Detection system.

For the full project, other contributors, final architecture, and integrated implementation, see:

https://github.com/hosseindamavandi/Fake-News-Detection

The original team repository and the dataset source should be cited when building on this work.

## Tech stack

- Python
- Pandas
- NumPy
- NLTK
- scikit-learn
- Keras / TensorFlow
- Jupyter / Google Colab

## License

See [LICENSE](LICENSE) for this repository's license terms. Third-party datasets and upstream project materials remain subject to their own licenses and terms.
