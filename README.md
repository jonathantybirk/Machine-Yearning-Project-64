# machineyearningproject

Project Description: Musical Instrument Sound Classifier

Overall Goal: The goal of this project is to build a machine learning model that can classify audio files of musical instruments, identifying the specific instrument being played. Initially, the model will recognize four instruments: guitar, drums, violin, and piano, using a dataset of sound clips. This tool could be a useful as a base model in music recognition apps.

Framework: We will use PyTorch for model development, leveraging either transformers or CNNs. Transformers are suitable for sequential data like raw audio, while CNNs can be used for spectrograms if needed. Additionally, we plan to fine-tune a pre-trained model (e.g., from AudioSet or VGGish) to speed up training and improve accuracy.

Data: The dataset we will use is the Musical Instruments Sound Dataset from Kaggle. See https://www.kaggle.com/datasets/soumendraprasad/musical-instruments-sound-dataset.
It contains:
Guitar: 700 samples
Drums: 700 samples
Violin: 700 samples
Piano: 528 samples
The dataset is split into training, validation, and test sets, with the validation set being used for real-time model evaluation during training, and the test set for final performance evaluation once we are satisfied with the model's results.

Modeling Process: The training process will be divided into three phases:

Training Phase: We will train the model using the training set while continuously validating it on a validation set during each iteration to monitor performance.
Validation Phase: During training, the model will be validated on the validation set to fine-tune hyperparameters and prevent overfitting.
Testing Phase: Once we are satisfied with the results from the validation phase, we will evaluate the model on the test set to measure its final performance.
Our Extra Product Design Ideas (we need more words help :c ): The final product could include a user interface that allows users to upload their own audio recordings, with the model predicting the instrument played. We know this is wildly out of the scope of this course, but maybe the clips uploaded could somehow automatically be added to the dataset for a better model. Anyway, this interface would then display the prediction along with some kind of confidence score. 

## Project structure

The directory structure of the project looks like this:
```txt
├── .github/                  # Github actions and dependabot
│   ├── dependabot.yaml
│   └── workflows/
│       └── tests.yaml
├── configs/                  # Configuration files
├── data/                     # Data directory
│   ├── processed
│   └── raw
├── dockerfiles/              # Dockerfiles
│   ├── api.Dockerfile
│   └── train.Dockerfile
├── docs/                     # Documentation
│   ├── mkdocs.yml
│   └── source/
│       └── index.md
├── models/                   # Trained models
├── notebooks/                # Jupyter notebooks
├── reports/                  # Reports
│   └── figures/
├── src/                      # Source code
│   ├── project_name/
│   │   ├── __init__.py
│   │   ├── api.py
│   │   ├── data.py
│   │   ├── evaluate.py
│   │   ├── models.py
│   │   ├── train.py
│   │   └── visualize.py
└── tests/                    # Tests
│   ├── __init__.py
│   ├── test_api.py
│   ├── test_data.py
│   └── test_model.py
├── .gitignore
├── .pre-commit-config.yaml
├── LICENSE
├── pyproject.toml            # Python project file
├── README.md                 # Project README
├── requirements.txt          # Project requirements
├── requirements_dev.txt      # Development requirements
└── tasks.py                  # Project tasks
```

## Downloading the data set
A Google Cloud Bucket is used for data version control. Reach out to a contributer to get authorized for access.
Run `dvc pull` to fetch the newest data from the remote storage.


Created using [mlops_template](https://github.com/SkafteNicki/mlops_template),
a [cookiecutter template](https://github.com/cookiecutter/cookiecutter).
