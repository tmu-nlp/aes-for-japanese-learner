# Automated Essay Scoring System for Nonnative Japanese Learner

> [!WARNING]
> This repository is archived and no longer maintained.
> `requirements.txt` pins the old library versions (e.g. TensorFlow 1.x, PyTorch 1.1, scikit-learn 0.21) that are required to load the pre-trained models below.
> These versions have known security vulnerabilities.
> Use them only in an isolated environment (e.g. a container or a dedicated virtual machine) and only with trusted input and model files.

To clone this repository together with the required `bert-japanese`:

```
git clone --recurse-submodules https://github.com/reo11/aes-for-japanese-learner
```

## Download our pre-trained models
Please download our pre-trained model from [here](https://drive.google.com/file/d/11N6hnSaZiG0jHLJYBNvryoxHrArG6xr8/view?usp=sharing)
and set a directory name `trained_models`.

## Predicting scores with pre-trained models
You can predict the score by executing the following code.
```
python predict_with_**.py [input.csv]
```
When executing `LSTM` and `BERT` models, it is better to use GPU as follows.
```
CUDA_VISIBLE_DEVICES=0 python predict_with_**.py [input.csv]
```

## Input format
The input csv format of essays must be as follows:

|text_id|prompt|text|
|:---:|:---:|:---:|
|ex1|...|...|
|ex2|...|...|

## Output format
The output csv format is as follows:

|text_id|holistic|content|organization|language|
|:---:|:---:|:---:|:---:|:---:|
|ex1|3|3|3|3|
|ex2|4|4|4|4|