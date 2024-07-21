# UCI-regression-data
This repository contains processed UCI dataset for regression tasks

Regression Datasets
This repository contains 15 datasets for regression tasks. Each dataset is organized into train, validation, test, and train+val (full data) folders.

Data Organization
Each dataset is stored in the data folder, with the following structure:

bash
Copy code
data/
    dataset_name/
        train/
        validation/
        test/
        trainval/
Dataset Split
The datasets are split using train-test splits with the following ratios:

Test: 30%
Validation: 10.5%
Download
The datasets can be downloaded from this link.

Basic Dataset Information
Dataset Name	Number of Instances	Number of Features
Dataset1	Number of Instances	Number of Features
Dataset2	Number of Instances	Number of Features
...	...	...
Dataset15	Number of Instances	Number of Features
Loading Data
To load the datasets, you can use the following Python functions:

python
Copy code
import os
import joblib

def _load_data(path):
    return joblib.load(os.path.join(path, 'data.pkl'))

def load_UCIdata(cat_key, name_key, splits='train'):
    """
    Load UCI dataset.

    Parameters:
    cat_key (str): The category key of the dataset.
    name_key (str): The name key of the dataset.
    splits (str): The data split to load ('test', 'train', 'validation', 'trainval').

    Returns:
    Data: The loaded data.
    """
    return _load_data(f'processed_data/{name_key}/{splits}')
Example Usage
python
Copy code
# Example of loading training data for a dataset named 'dataset1'
train_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='train')

# Example of loading validation data for the same dataset
validation_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='validation')

# Example of loading test data for the same dataset
test_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='test')

# Example of loading train+validation data for the same dataset
trainval_data = load_UCIdata(cat_key='regression', name_key='dataset1', splits='trainval')
