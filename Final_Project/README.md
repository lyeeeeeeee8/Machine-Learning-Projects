# NCTU Introduction to Machine Learning, Final Project
 


## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```

To download the dataset:
- train.csv
- test.csv
- sample_submission.csv

---
## Training

To train the model(s) in the paper, run this code:

```train
109550090_Final_train.ipynb 
```
This code will generate:
- Preprocessed data:
    - x_train.csv
    - x_test.csv  
- Model weights:
    - model1.pkl
    - model2.pkl
    - model3.pkl
> Please also download the *catboost_info* and *kuma_utils* directory
Training process:
- Train three models including:
    - Logistic regression
    - LightGBM model
    - Catboost gradient boosting
- Form an **ensemble model**:
    ```python
    prediction1 = clf_lr.predict_proba(x_test)[:,1] * 0.8
    prediction2 = clf_lgbm.predict_proba(x_test)[:,1] * 0.1
    prediction3 = clf_cat.predict_proba(x_test)[:,1] * 0.1
    prediction = prediction1 + prediction2 + prediction3 
    ```


---
## Testing

To test the model(s) in the paper, run this code:

```test
109550090_Final_inference.ipynb 
```
This code will generate: submission.csv <br>

---
## Pre-trained Models

You can download pretrained models here:

- [My model weights](https://drive.google.com/drive/folders/133Q6nIbBbRNKOXmOLry1SRMXh-gvySol?usp=sharing)

---
## Results

Our model achieves the following performance on :

[Kaggle-Tabular Playground Series-Aug 2022-Leaderboard](https://www.kaggle.com/competitions/tabular-playground-series-aug-2022/leaderboard)

| Model name         | Private Score  | Public Score |
| ------------------ |---------------- | -------------- |
| My  model   |     0.59112         |      0.59046       |

---
## Memo
I've tried another approach by using keras neural network. However, the performance wasn't good. I've also put the code in *keras_method* directory.
 
