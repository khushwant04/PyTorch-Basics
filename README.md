# PyTorch Basics

Notebooks I wrote while learning PyTorch fundamentals, from tensors to a small CNN. They follow the structure of Daniel Bourke's [Learn PyTorch for Deep Learning](https://github.com/mrdbourke/pytorch-deep-learning) course, and `helper_function.py` comes from that course.

## Learning index

| # | Notebook | Topics | Data |
| --- | --- | --- | --- |
| 1 | [`Tensor's.ipynb`](Tensor's.ipynb) | Creating tensors, dtypes, attributes (shape/dtype/device), arithmetic and matrix multiplication, aggregation, reshape/stack/squeeze/permute, indexing, NumPy interop, reproducibility, GPU | none |
| 2 | [`pytorch_workflow.ipynb`](pytorch_workflow.ipynb) | End-to-end workflow: synthetic linear data, train/test split, an `nn.Module` with manual parameters, then the same with `nn.Linear`, training and testing loops, `torch.inference_mode()`, saving and loading a `state_dict` | synthetic |
| 3 | [`Neural Network Classification.ipynb`](Neural%20Network%20Classification.ipynb) | Binary classification on `make_circles`, linear vs non-linear models, hand-written ReLU and sigmoid, multi-class classification on `make_blobs`, `torchmetrics` | scikit-learn toy data |
| 4 | [`Computer_Vision.ipynb`](Computer_Vision.ipynb) | `torchvision.datasets`, `DataLoader`, a linear baseline, a model with non-linearity, a TinyVGG-style CNN, how `Conv2d` and `MaxPool2d` work, functionised train/test steps, a confusion matrix (`torchmetrics` + `mlxtend`), saving the best model | FashionMNIST |
| 5 | [`Custom_dataset.ipynb`](Custom_dataset.ipynb) | Downloading an image dataset, walking the directory tree, visualising a sample image (started, not finished) | pizza / steak / sushi subset of Food-101 |

### FashionMNIST results

These are test-set results printed in `Computer_Vision.ipynb`, after 3 epochs per model:

| Model | Test accuracy |
| --- | --- |
| `FashionMNISTModelV0` (linear) | 83.4% |
| `FashionMNISTModelV1` (linear + ReLU) | 75.0% |
| `FashionMNISTModelV2` (CNN) | 88.0% |

## Repository layout

```
*.ipynb               The notebooks above
helper_function.py    Plotting, accuracy, timing and data-download helpers (from the course)
models/               Saved state_dicts from notebooks 2 and 4
data/                 FashionMNIST raw files and the pizza_steak_sushi image set
```

## Running

```bash
git clone https://github.com/khushwant04/PyTorch-Basics.git
cd PyTorch-Basics
pip install -r requirements.txt jupyter
jupyter notebook
```

The datasets in `data/` are already in the repository. `torchvision` and the download helper would fetch them again if they were missing. A GPU is optional.

## License

Apache-2.0. See [LICENSE](LICENSE).
