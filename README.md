
# Regression Datasets

This repository contains 15 datasets for regression tasks. Each dataset is organized into train, validation, test, and train+val (full data) folders.

## Data Organization

Each dataset is stored in the `data` folder, with the following structure:

```
data/
    dataset_name/
        train/
        validation/
        test/
        trainval/
```

### Dataset Split

The datasets are split using train-test splits with the following ratios:
- **Test**: 30%
- **Validation**: 10.5%

## Download

The datasets can be downloaded from [this link](https://www.dcc.fc.up.pt/~ltorgo/Regression/DataSets.html).

## Basic Dataset Information

| dataset             | instances | features | train_size | task       |
|---------------------|-----------|----------|------------|------------|
| Abalone             | 4177      | 12       | 2484       | regression |
| Ailerons            | 7154      | 42       | 4255       | regression |
| Auto-Mpg            | 398       | 102      | 236        | regression |
| Auto-Price          | 159       | 17       | 94         | regression |
| CaliforniaHousing   | 20640     | 10       | 12280      | regression |
| ComputerActivity    | 8192      | 23       | 4873       | regression |
| Elevators           | 9517      | 8        | 5661       | regression |
| FriedmanExample     | 40768     | 12       | 24256      | regression |
| Housing             | 506       | 15       | 300        | regression |
| Kinematics          | 8192      | 10       | 4873       | regression |
| Machine-Cpu         | 209       | 8        | 124        | regression |
| PoleTelecomm        | 5000      | 50       | 2975       | regression |
| Servo               | 167       | 14       | 98         | regression |
| triazines           | 186       | 62       | 110        | regression |
| WiscoinBreastCancer | 194       | 34       | 114        | regression |

## Loading Data

To load the datasets, you can use the following Python functions:

```python
import os
import joblib

def _load_data(path):
    return joblib.load(os.path.join(path, 'data.pkl'))

def load_UCIdata(cat_key, name_key, splits='train'):
    """
    Load UCI dataset.

    Parameters:
    cat_key (str): The category key of the dataset.
    name_key (str): The name of the dataset.
    splits (str): The data split to load ('test', 'train', 'validation', 'trainval').

    Returns:
    Data: The loaded data.
    """
    return _load_data(f'processed_data/{name_key}/{splits}')
```

### Example Usage

```python
# Example of loading training data for a dataset named 'dataset1'
train_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='train')

# Example of loading validation data for the same dataset
validation_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='validation')

# Example of loading test data for the same dataset
test_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='test')

# Example of loading train+validation data for the same dataset
trainval_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='trainval')
```

Feel free to explore and use these datasets for your regression tasks. Happy analyzing!
