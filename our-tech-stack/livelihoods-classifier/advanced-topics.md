---
description: >-
  In this page we aim to give further details about the classes and functions
  located to the GItHub repository.
---

# Advanced Topics

## inference/linker.`py`

### class EntityLinker

Creates a pipeline of an entity recognition transformer and a sentence transformer for embedding text.

#### Initialization Parameters

entity\_model : str, default='tabiya/roberta-base-job-ner' Path to a pre-trained `AutoModelForTokenClassification` model or an `AutoModelCrfForNer` model. This model is used for entity recognition within the input text.

similarity\_model : str, default='all-MiniLM-L6-v2' Path or name of a sentence transformer model used for embedding text. The sentence transformer is used to compute embeddings for the extracted entities and the reference sets. The model 'all-mpnet-base-v2' is available but not in cache, so it should be used with the parameter `from_cache=False` at least the first time.

crf : bool, default=False A flag to indicate whether to use an `AutoModelCrfForNer` model instead of a standard `AutoModelForTokenClassification`. `CRF` (Conditional Random Field) models are used when the task requires sequential predictions with dependencies between the outputs.

evaluation\_mode : bool, default=False If set to `True`, the linker will return the cosine similarity scores between the embeddings. This mode is useful for evaluating the quality of the linkages.

k : int, default=32 Specifies the number of items to retrieve from the reference sets. This parameter limits the number of top matches to consider when linking entities.

from\_cache : bool, default=True If set to `True`, the precomputed embeddings are loaded from cache to save time. If set to `False`, the embeddings are computed on-the-fly, which requires GPU access for efficiency and can be time-consuming.

output\_format : str, default='occupation' Specifies the format of the output for occupations, either `occupation`, `preffered_label`, `esco_code`, `uuid` or `all` to get all the columns. The `uuid` is also available for the skills.

#### Calling Parameters

text : str An arbitrary job vacancy-related string.

linking : bool, default=True Specify whether the model performs the entity linking to the taxonomy.

### class FrenchEntityLinker

French version of the entity linker. In order to use, we need to rewrite the reference databases to the French version of ESCO.

## `inference/evaluator.py`

## class Evaluator(EntityLinker)

Evaluator class that inherits the Entity Linker. It computes the queries, corpus, inverted corpus and relevant docs for the [InformationRetrievalEvaluator](https://github.com/UKPLab/sentence-transformers/blob/master/sentence_transformers/evaluation/InformationRetrievalEvaluator.py), performs entity linking and computes the Information Retrieval Metrics.

### Initialization Parameters

entity\_type: str Occupation, Skill, or Qualification to determine the exact evaluation set to be used.

## `util/transformersCRF.py`

### class CRF(nn.Module)

Implemented from [here](https://github.com/lonePatient/BERT-NER-Pytorch/tree/master).

A class that creates a linear Conditional Random Field model.

### class AutoModelForCrfPretrainedConfig(PretrainedConfig)

Configuration class that inherits from [PretrainedConfig ](https://huggingface.co/docs/transformers/en/main_classes/configuration#transformers.PretrainedConfig)HuggingFace class.

### class AutoModelCrfForNer(PreTrainedModel)

A general class that inherits from [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) class. The model\_type is detected automatically.

model\_type: str Possible options include `BertCrfForNer`, `RobertaCrfForNer` and `DebertaCrfForNer.`

### class BERT\_CRF\_Config(PretrainedConfig)

Custom class used for configuring BERT for CRF.

### class BertCrfForNer(PreTrainedModel)

BERT-based CRF model that inherits from [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) class.

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel).

#### Forward Parameters

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) except for

`special_tokens_mask` default: None. We use this option from HuggingFace as a small hack to implement the special\_mask needed for CRF.

### class ROBERTA\_CRF\_Config(PretrainedConfig)

Custom class used for configuring RoBERTa for CRF.

### class RobertaCrfForNer(PreTrainedModel)

RoBERTa-based CRF model that inherits from [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) class.

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel).

#### Forward Parameters

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) except for

`special_tokens_mask` default: None. We use this option from HuggingFace as a small hack to implement the special\_mask needed for CRF.

### class DEBERTA\_CRF\_Config(PretrainedConfig)

Custom class used for configuring RoBERTa for CRF.

### class DebertaCrfForNer(PreTrainedModel)

RoBERTa-based CRF model that inherits from [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) class.

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel).

#### Forward Parameters

Same as [PreTrainedModel HuggingFace](https://huggingface.co/docs/transformers/en/main_classes/model#transformers.PreTrainedModel) except for

`special_tokens_mask` default: None. We use this option from HuggingFace as a small hack to implement the special\_mask needed for CRF.

## `util/utilfunctions.py`

### class Config

Configuration class for the [training hyperparameters](training.md#train-an-entity-extraction-model).

### class CPU\_Unpickler

A class that loads the tensors in the CPU.
