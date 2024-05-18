# Image Regression

by [Tony Assi](https://www.tonyassi.com/)

Image Regression model training and inference. Built with 🤗 and PyTorch.

## Installation
```bash
pip install -r requirements.txt
```

## Dataset

The model trained takes a 🤗 dataset id as input so your dataset must be uploaded to 🤗. It should have a column of images and a column of values (floats or ints). Check out [Create an image dataset](https://huggingface.co/docs/datasets/en/image_dataset) if you need help creating a 🤗 dataset. Your dataset should look like [tonyassi/sales1](https://huggingface.co/datasets/tonyassi/sales1)--but the values column can be named whatever you'd like.

## Usage

### Import 
```python
from ImageRegression import train_model, upload_model, predict
```

### Train model
- **dataset_id** 🤗 dataset id
- **value_column_name** column name of the dataset. these are the prediction values
- **test_split** test split of the train/test split
- **output_dir** the directory where the checkpoints will be saved
- **num_train_epochs** training epochs
- **learning_rate** learning rate
```python
train_model(dataset_id='tonyassi/sales1',
            value_column_name='sales',
            test_split=0.2,
            output_dir='./results',
            num_train_epochs=10,
            learning_rate=1e-4)

```
