# Training

Train your entity extraction model using PyTorch.

First, activate the virtual environment as explained [here](getting-started.md#dep).

### Train an Entity Extraction Model

Configure the necessary hyperparameters in the config.json file. The defaults are:

```json
{
    "model_name": "bert-base-cased",
    "crf": false,
    "dataset_path": "tabiya/job_ner_dataset",   
    "label_list": ["O", "B-Skill", "B-Qualification", "I-Domain", "I-Experience", "I-Qualification", "B-Occupation", "B-Domain", "I-Occupation", "I-Skill", "B-Experience"],
    "model_max_length": 128,
    "batch_size": 32,
    "learning_rate": 1e-4,
    "epochs": 4,
    "weight_decay": 0.01,
    "save": false,
    "output_path": "bert_job_ner"
}
```

To train the model, run the following script in the `train` directory:

```sh
python train.py
```

The training script is based on the [official HuggingFace token classification tutorial](https://huggingface.co/docs/transformers/en/tasks/token_classification).

### Train an Entity Similarity Model

Configure the necessary hyperparameters in the `sbert_train` function in the sbert\_train.py file:

```python
sbert_train(model_id='all-MiniLM-L6-v2', dataset_path='your/dataset/path', output_path='your/output/path')
```

To train the similarity model, run the following script in the `train` directory:

```sh
python sbert_train.py
```

The dataset should be formatted as a CSV file with two columns, such as 'title' and 'esco\_label', where each row contains a pair of related textual data points to be used during the training process. Make sure there are no missing values in your dataset to ensure successful training of the model. Here's an example of how your CSV file might look:

| title                   | esco\_label                 |
| ----------------------- | --------------------------- |
| Senior Conflict Manager | public institution director |
| etc                     | etc                         |

More information can be found [here](datasets.md#entity-similarity).
