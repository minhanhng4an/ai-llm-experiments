# Setup AI/LLM for Devs experiments locally

This repository contains the necessary setup instructions and environment configurations to run AI/LLM experiments locally.

## Setup

1. Fork/Clone the repository.
2. Install `miniforge3` to your local machine. Choose and download the installer for your machine type [HERE](https://github.com/conda-forge/miniforge).
3. Navigate to the cloned repository directory in your terminal:

```
cd ai-llm-experiments
```

4. Create a new conda virtually environment by running:

```
conda env create -f environment.yml
```

If you prefer another name for the environment, change `name` in `environment.yml` (Default: `codepath`)

5. Activate the new environment:

```
conda activate <environment_name>
```
6. Create two folders `notebooks` and `data`
```
mkdir notebooks
mkdir data
```
7. Download the notebooks from Google Colab as `.ipynb` and put them in `/notebooks`

8. Downloaded data could go to `/data`

## Running the notebooks locally

You can open the notebooks in your favorite IDE (I believe most of them support notebook now). I personally am using Cursor (it is a VSCode fork) to leverage its built-in AI features and have access to quality-of-life IDE features like declaration preview, better syntax highlighting,...

```
cursor ai-llm-experiments
```

or

```
code ai-llm-experiments
```

After you open the repository in Cursor/VSCode, you will be prompted to install the necessary extenstions for Python notebooks, make sure you have them installed.

Before you run your notebook, you will need to select a kernel. In Cursor/VSCode it is on the top right when opening a notebook. Make sure you select the environment you created earlier (For me it is `codepath (Python 3.10.12)`).

Since our dependencies like fastai already been installed, comment some unused steps in the notebook:

```python
# from google.colab import drive
from pathlib import Path

# # Mount Google Drive
# drive.mount('/content/drive')
```

```python
# Setup
# !pip install fastai
# !pip install fastbook

from fastbook import *
from fastai.vision.widgets import *
```

## Disclaimers

This setup was only tested on a Macbook M1 Pro (MacOS 14.4.1). While it tries to mimic the Python environment in Colab, there are potentally mismatched versions of some that might lead to inconsistent behaviour between the two environments (though I haven't experienced any).

Have fun!
