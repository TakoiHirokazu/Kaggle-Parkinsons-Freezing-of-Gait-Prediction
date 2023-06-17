# Kaggle-Parkinsons-Freezing-of-Gait-Prediction
The discription of this solution is available [here](https://www.kaggle.com/competitions/tlvmc-parkinsons-freezing-gait-prediction/discussion/416057).

# Takoi's part

Go to ./takoi directory and do the following.

## Hardware
- Google Cloud Platform
    - Debian 10.12
    - a2-highgpu-1g (vCPU x 12, memory 85 GB)
    - 1 x NVIDIA Tesla A100
## Data download
Download data to ./data/ from https://www.kaggle.com/competitions/tlvmc-parkinsons-freezing-gait-prediction/data .

## Environment

```
docker-compose up --build
```

## tDCSFOG

### Feature Engineering
Please run the following notebooks in th ./fe

- fe001_tdcsfog_base_feature.ipynb
- fe022_tdcsfog_1000.ipynb

### Training
Please run the following notebooks in th ./exp
- ex143_tdcsfog_gru.ipynb
- ex145_tdcsfog_gru_StartHesitation.ipynb
- ex146_tdcsfog_gru_Turn.ipynb
- ex147_tdcsfog_gru_Walking.ipynb
- ex182_tdcsfog_gru_StartHesitation_Turn.ipynb
- ex183_tdcsfog_gru_StartHesitation_Walking.ipynb
- ex184_tdcsfog_gru_Turn_Walking.ipynb

All models above were used for final submission.

## DeFOG

### Feature Engineering
Please run the following notebooks in th ./fe
- fe039_defog_base_feature.ipynb
- fe047_defog_5000.ipynb
- fe061_notype_5000.ipynb
- fe064_notype_10000.ipynb
- fe074_notype_15000.ipynb

### Training
Please run the following notebooks in th ./exp
- ex153_defog_gru.ipynb
- ex154_defog_gru.ipynb

### Making pseudo label(round1)
Please run the following notebooks in th ./exp
- ex153_defog_gru_inference_notype_10000.ipynb
- ex153_defog_gru_inference_notype_15000.ipynb
- ex154_defog_gru_inference_notype_15000.ipynb

Please run the following notebooks in th ./fe
- fe073_notype_pseudo_ex153_10000.ipynb
- fe075_notype_pseudo_ex153_15000.ipynb
- fe086_notype_pseudo_ex154_15000.ipynb

### Training with pseudo label(round1)
Please run the following notebooks in th ./exp
- ex175_defog_gru_pseudo.ipynb
- ex179_defog_gru_pseudo.ipynb
- ex204_defog_gru_pseudo.ipynb

### Making pseudo label(round2)
Please run the following notebooks in th ./exp
- ex175_defog_gru_inference_notype_15000.ipynb

Please run the following notebooks in th ./fe
- fe078_notype_pseudo_ex175_15000.ipynb

### Training with pseudo label(round2)
Please run the following notebooks in th ./exp
- ex185_defog_gru_pseudo2.ipynb

The following numbered models were used for the final submission
- ex153
- ex179
- ex185
- ex204


# Hakubishin3's part

Go to ./hakubishin3 directory and do the following.

## Hardware

- Google Cloud Platform
    - ubuntu-2204-jammy-v20230524
    - a2-highgpu-1g (vCPU x 12, memory 85 GB)
    - 1 x NVIDIA Tesla A100

## Data download

Download data to ./mnt/input/ from https://www.kaggle.com/competitions/tlvmc-parkinsons-freezing-gait-prediction/data .

## Environment

```
docker-compose up --build
```

## Step1: Prepare pseudo label dataset from unlabelled data

- Step1-1. exp222-defog-new-full-train-11epoch.ipynb
- Step1-2. notype-de-exp222.ipynb

## Step2: Training with pseudo label

- exp238-defog-add-notype-full-train-9epoch.ipynb

# Inference & Submit
https://www.kaggle.com/code/takoihiraokazu/cv-ensemble-sub-0607-1?scriptVersionId=132514119
