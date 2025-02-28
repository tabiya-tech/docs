# Getting Started

## Installation

Prerequisites\\

* A recent version of [git](https://git-scm.com/) (e.g. ^2.37 )
* [Python 3.10 or higher](https://www.python.org/downloads/)
*   [Poerty 1.8 or higher](https://python-poetry.org/)

    > Note: to install Poetry consult the [Poetry documentation](https://python-poetry.org/docs/#installing-with-the-official-installer)

    > Note: Install poetry system-wide (not in a virtualenv).
* [Git LFS](https://git-lfs.github.com/)

#### Using Git LFS

This tool uses Git LFS for handling large files. Before using it you need to install and set up Git LFS on your local machine. See https://git-lfs.com/ for installation instructions.

After Git LFS is set up, follow these steps to clone the repository:

```shell
git clone https://github.com/tabiya-tech/tabiya-livelihoods-classifier.git
```

If you already cloned the repository without Git LFS, run:

```shell
git lfs pull
```

#### Install the dependencies <a href="#dep" id="dep"></a>

**Set up virtualenv**

In the **root directory** of the backend project (so, the same directory as this README file), run the following commands:

```shell
# create a virtual environment
python3 -m venv venv

# activate the virtual environment
source venv/bin/activate
```

```shell
# Use the version of the dependencies specified in the lock file
poetry lock --no-update
# Install missing and remove unreferenced packages
poetry install --sync
```

> Note: Install the dependencies for the training using:
>
> ```shell
> # Use the version of the dependencies specified in the lock file
> poetry lock --no-update
> # Install missing and remove unreferenced packages
> poetry install --sync --with train
> ```

> Note: Before running any tasks, activate the virtual environment so that the installed dependencies are available:
>
> ```shell
> # activate the virtual environment
> source venv/bin/activate
> ```
>
> To deactivate the virtual environment, run:
>
> ```shell
> # deactivate the virtual environment
> deactivate
> ```

Activate Python and download the NLTK punctuation package to use the sentence tokenizer. You only need to download `punkt` it once.

```shell
python <<EOF
import nltk
nltk.download('punkt')
EOF
```

#### Environment Variable & Configuration

The tool uses the following environment variable:

* `HF_TOKEN`: To use the project, you need access to the HuggingFace 🤗 entity extraction model. Contact the administrators via \[tabiya@benisis.de]. From there, you must create a read access token to use the model. Find or create your read access token [here](https://huggingface.co/settings/tokens). The backend supports the use of a `.env` file to set the environment variable. Create a `.env` file in the root directory of the backend project and set the environment variables as follows:

```dotenv
# .env file
HF_TOKEN=<YOUR_HF_TOKEN>
```

> ATTENTION: The .env file should be kept secure and not shared with others as it contains sensitive information.

## QuickStart Guide

## Inference Pipeline

The inference pipeline extracts occupations and skills from a job description and matches them to the most similar entities in the ESCO taxonomy.

### Usage

First, activate the virtual environment as explained [here](getting-started.md#dep).

Then, `start python interpreter in the root directory` and run the following commands:

Load the `EntityLinker` class and create an instance of the class, then perform inference on any text with the following code:

```python
from inference.linker import EntityLinker
pipeline = EntityLinker(k=5)
text = 'We are looking for a Head Chef who can plan menus.'
extracted = pipeline(text)
print(extracted)
```

After running the commands above, you should see the following output:

```js
[
  {'type': 'Occupation', 'tokens': 'Head Chef', 'retrieved': ['head chef', 'industrial head chef', 'head pastry chef', 'chef', 'kitchen chef']},
  {'type': 'Skill', 'tokens': 'plan menus', 'retrieved': ['plan menus', 'plan patient menus', 'present menus', 'plan schedule', 'plan engineering activities']}
]
```

### French version

You can use the French version of the Entity Linker using the following code:

```python
from inference.linker import FrenchEntityLinker
pipeline = FrenchEntityLinker(entity_model = 'tabiya/camembert-large-job-ner', similarity_model = 'intfloat/multilingual-e5-base')

text = 'Nous recherchons un chef de cuisine capable de planifier les menus.'
extracted = pipeline(text)
print(extracted)
```

You should see the following output:

```javascript
[
  {'type': 'Occupation', 'tokens': 'chef de cuisine', 'retrieved': ['chef de cuisine', 'chef de marque', 'chef mécanicien', 'chef cuisinier/cheffe cuisinière', 'chef de train']}, 
  {'type': 'Skill', 'tokens': 'planifier les menus', 'retrieved': ['planifier les menus', 'présenter des menus', 'établir les menus des patients', 'préparer des plannings', 'préparer des plats préparés']}
]
```

### Running the evaluation tests

Load the `Evaluator` class and print the results:

```python
from inference.evaluator import Evaluator

results = Evaluator(entity_type='Skill', entity_model='tabiya/roberta-base-job-ner', similarity_model='all-MiniLM-L6-v2', crf=False, evaluation_mode=True)
print(results.output)
```

This class inherits from the `EntityLinker`, with the main difference being the `'entity_type'` flag.

{% hint style="warning" %}
If you want to run evaluations on custom datasets, you will need to make modifications to the `_load_dataset` function, located on the `evaluation.py` file. Please refer to the original evaluation datasets as described [here](datasets.md). If you have any trouble, please open an issue on [GitHub](https://github.com/tabiya-tech/tabiya-livelihoods-classifier/issues).
{% endhint %}

### Minimum Hardware

* 4 GB CPU/GPU RAM

The code runs on GPU if available. Ensure your machine has CUDA installed if running on GPU.
