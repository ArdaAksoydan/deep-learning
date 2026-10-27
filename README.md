# Deep Learning (CENG506)

Coursework for CENG506 Deep Learning: Jupyter notebooks covering a single-neuron classifier, U-Net semantic segmentation and recurrent neural networks, plus the mitochondria dataset used for the segmentation homework.

## Contents

| Path | Description |
| --- | --- |
| `src/333078019_HW1.ipynb` | Homework 1: a single neuron with sigmoid activation (parameter initialization, cost and gradient, gradient descent) trained on the cat vs non-cat H5 dataset. |
| `src/333078019_HW3.ipynb` | Homework 3: U-Net binary semantic segmentation of mitochondria, with training curves and MeanIoU on the test set. |
| `src/333078019_HW4.ipynb` | Homework 4: forward propagation for a basic RNN and an LSTM, built with NumPy. |
| `src/rnn_utils.py` | Helper functions for Homework 4 (softmax, sigmoid, Adam initialization and updates). |
| `src/CENG506_Multiclass_Semantic_Segmentation.ipynb` | Lecture notebook: multiclass U-Net segmentation on the sandstone dataset. |
| `src/CENG506_HW3_Binary_SS.ipynb` | Homework 3 assignment brief. |
| `256x256_mitochondria/` | Dataset for Homework 3: 330 grayscale 256x256 TIFF images in `images/` and matching binary masks in `groundtruths/` (mask files carry a `groundtruth_` prefix). |

## Requirements

- Python 3.10 to 3.13
- Dependencies are listed in `pyproject.toml` and mirrored in `requirements.txt`: NumPy, SciPy, Matplotlib, Pillow, h5py, OpenCV, scikit-learn, TensorFlow (with Keras) and JupyterLab.

## Setup

With [uv](https://docs.astral.sh/uv/):

```bash
uv sync
uv run jupyter lab
```

With pip:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

## Running the notebooks

The notebooks were written for Google Colab. They mount Google Drive and read data from paths such as `/content/drive/MyDrive/CENG506/...`.

- **On Colab:** upload the notebook and put the datasets in the Drive folders the notebook expects.
- **Locally:** skip or delete the `google.colab` / `drive.mount(...)` cells and point the path variables at local files. For Homework 3, set `DATA_DIR = "../256x256_mitochondria"` (relative to `src/`). For Homework 4, replace the `execfile(...)` line with `from rnn_utils import *`.

The Homework 1 H5 files (`train_catvnoncat.h5`, `test_catvnoncat.h5`) and the sandstone dataset for the lecture notebook are not included in this repository.
