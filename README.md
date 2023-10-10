# VEC

Visual and Embodied Concepts evaluation benchmark. EMNLP 2023 Main Conference. 

For `shape`, `material` and `color` task, there is an object and corresponding two options for the given property, e.g., `chair is made of wood instead of jade`.

For `mass`, `temperature`, `hardness`, `size` and `height` task, the pair is consists of two items and a relation label, e.g., `red lego brick is more light-weight than a hammer` 

You can easily load the dataset from Huggingface Datasets API:


```python
from datasets import load_dataset


data = {}

for task in ['color', 'size', 'shape', 'height', 'material', 'mass', 'temperature', 'hardness']:
    data[task] = load_dataset("tobiaslee/VEC", task)


print(data['material']['test'][0])
# instance
# {'obj': 'chair', 'positive': 'wood', 'negative': 'jade', 'relation': 'material'}
# meaning:  chair is made of 

print(data['mass']['test'][0])
# {'obj1': 'red lego brick', 'obj2': 'hammer', 'relation': 'mass', 'label': 0} 
# meaning:  red logo brick is more light-weight than hammer.
# label=0 indicates`<`  while label=1 indicates `>` 
```




## Citation


If you found this benchmark, please kindly cite our paper:

```latex
@article{li2023vec,
  title={Can Language Models Understand Physical Concepts?},
  author={Li, Lei and Xu, Jingjing and Dong, Qingxiu and Zheng, Ce and Liu, Qi and Kong, Lingpeng and Sun, Xu},
  journal={arXiv preprint arXiv:2305.14057},
  year={2023}
}
```
