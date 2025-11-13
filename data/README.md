# data/

Store your dataset files in this folder. Suggested filenames:

- `data/dataset.csv` — primary CSV for analysis
- `data/sample.csv` — small sample for fast iteration

Guidelines:

- If your dataset is large, don't commit it to Git. Add the filename to `.gitignore` (example below) and keep data on Google Drive, S3, or a separate storage service.
- For Colab, either upload the file to the notebook session, use a raw GitHub URL, or mount Google Drive and point to `drive/MyDrive/...`.

Quick examples

- Load local CSV in notebook:

```python
import pandas as pd
df = pd.read_csv('data/dataset.csv')
```

- Load from GitHub raw URL (works in Colab):

```python
url = 'https://raw.githubusercontent.com/USERNAME/REPO/BRANCH/path/to/data/dataset.csv'
df = pd.read_csv(url)
```

- Mount Google Drive in Colab and load:

```python
from google.colab import drive
drive.mount('/content/drive')
df = pd.read_csv('/content/drive/MyDrive/path/to/dataset.csv')
```

Example `.gitignore` entry to add to the repo root if you don't want to commit datasets:

```
# Ignore local datasets
/data/*
!data/.gitkeep
```
