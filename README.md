# Fake News Detection in Filipino
This repository contains data and models from our paper **Localization of Fake News Detection via Multitask Transfer Learning** (Cruz et al., 2020), published in the [LREC 2020 Proceedings](http://www.lrec-conf.org/proceedings/lrec2020/index.html).

# Datasets
* **Fake News Filipino Dataset** ~~[`download`](https://s3.us-east-2.amazonaws.com/blaisecruz.com/datasets/fakenews/fakenews.zip)~~ [`huggingface`](https://huggingface.co/datasets/jcblaise/fake_news_filipino)\
*Low-Resource Fake News Detection Corpora in Filipino*\
The first of its kind. Contains 3,206 expertly-labeled news samples, half of which are real and half of which are fake.

# Pretrained Models
All pretrained models used in the study are available in [this](https://github.com/jcblaisecruz02/Filipino-Text-Benchmarks) repository.

# Getting started

Parse Tagalog fake news dataset into a pandas dataframe object for ease of use.

```
from datasets import load_dataset
import pandas as pd

dataset_dict = load_dataset("jcblaise/fake_news_filipino", trust_remote_code=True)

dataset = dataset_dict['train']

labels = []
articles = []
for data in dataset:
    labels.append(data['label'])
    articles.append(data['article'])

df = pd.DataFrame({
    "articles": articles,
    "labels": labels
})
```

# Citation
If you found our work useful, please make sure to cite!

```
@inproceedings{cruz2020localization,
  title={Localization of Fake News Detection via Multitask Transfer Learning},
  author={Cruz, Jan Christian Blaise and Tan, Julianne Agatha and Cheng, Charibeth},
  booktitle={Proceedings of The 12th Language Resources and Evaluation Conference},
  pages={2596--2604},
  year={2020}
}
```

```
@article{evaluating2019cruz,
  title={{Evaluating Language Model Finetuning Techniques for Low-resource Languages}},
  author={Cruz, Jan Christian Blaise and Cheng, Charibeth},
  journal={arXiv preprint arXiv:1907.00409},
  year={2019}
}
```
