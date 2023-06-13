# Kaggle-Parkinsons-Freezing-of-Gait-Prediction

## Takoi's part

wip

## Hakubishin3's part

Go to ./hakubishin3 directory and do the following.

## Hardware

- Google Cloud Platform
    - ubuntu-2204-jammy-v20230524
    - a2-highgpu-1g (vCPU x 12, memory 85 GB)
    - 1 x NVIDIA Tesla A100
- Kaggle Notebook

## Data download

Download data to ./mnt/input/ from https://www.kaggle.com/competitions/tlvmc-parkinsons-freezing-gait-prediction/data .

## Environment

```
docker-compose up --build
```

## Step1: Prepare pseudo label dataset from unlabelled data

step1-1. exp222-defog-new-full-train-11epoch.ipynb
step1-2. notype-de-exp222.ipynb

This is done manually. First, rename the output file of the script notype-de-exp222.ipynb, which is submission.csv, to notype_targets_from_exp222.csv. Then, move it to the directory ./mnt/input.

## Step2: Training with pseudo label

- exp238-defog-add-notype-full-train-9epoch.ipynb
