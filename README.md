# THIS IS OUR REIMPLEMENTATION SUBMISSION FOR ML Reproducibility Challenge 2020
## PyTorch *RE*implementation of "Learning Memory-guided Normality for Anomaly Detection"[`pdf`](https://arxiv.org/abs/2101.12382)

<p align="center"><img src="./MNAD_files/overview.png" alt="no_image" width="40%" height="40%" /><img src="./MNAD_files/teaser.png" alt="no_image" width="60%" height="60%" /></p>
This is the implementation of the paper "Learning Memory-guided Normality for Anomaly Detection (CVPR 2020)".

For more information, checkout the project site [[website](https://cvlab.yonsei.ac.kr/projects/MNAD/)] and the paper [[PDF](http://openaccess.thecvf.com/content_CVPR_2020/papers/Park_Learning_Memory-Guided_Normality_for_Anomaly_Detection_CVPR_2020_paper.pdf)].

## Dependencies
* Python 3.6
* PyTorch 1.1.0
* Numpy
* Sklearn

## Datasets
* USCD Ped2 [[dataset](https://github.com/StevenLiuWen/ano_pred_cvpr2018)]
* CUHK Avenue [[dataset](https://github.com/StevenLiuWen/ano_pred_cvpr2018)]
* ShanghaiTech [[dataset](https://github.com/StevenLiuWen/ano_pred_cvpr2018)]

These datasets are from an official github of "Future Frame Prediction for Anomaly Detection - A New Baseline (CVPR 2018)".

Download the datasets into ``dataset`` folder, like ``./dataset/ped2/``

## Training
* The training and testing codes are based on prediction method
```bash
git clone https://github.com/cvlab-yonsei/projects
cd projects/MNAD/code
python Train.py # for training
```
* You can freely define parameters with your own settings like
```bash
python Train.py --gpus 1 --dataset_path 'your_dataset_directory' --dataset_type avenue --exp_dir 'your_log_directory'
```
## wandb metric logs:
* Please filter by tags to find relevant logs. All runs on which scores have been benchmarked and reported are tagged. If a run is missing tags, we probably did not use the results from that run in our report. 
* Folders without expilicit dataset name are from ped2, i.e., ShanghaiTech and CUHK avenue models have explicit mentions of the dataset name in the folder. 
* Reconstruction task: https://wandb.ai/alchemi5t/mnad
* Prediction task:  https://wandb.ai/kevins99/mnad

## Pre-trained model and memory items {*Reimplemented models available here*}
* Download our pre-trained model and memory items <br>Link: [[model and items](https://drive.google.com/file/d/11f65puuljkUa0Z4W0VtkF_2McphS02fq/view?usp=sharing)]
* Note that, these are from training with the Ped2 dataset

## Reimplementation models on all datasets:
* Download benchmark and ablation study models<br>Link:(https://drive.google.com/drive/folders/1QPgl53Iv1u-m8KcevQLBYWbuGEWB1Ky_?usp=sharing)
* Download memory distribution supervision models<br>Link:(https://drive.google.com/drive/folders/1_k2xfV0rFZOMYRTs9tX55-3quwcZMYIU?usp=sharing)


## Evaluation
* Test the model with our pre-trained model and memory items
```bash
python Evaluate.py --dataset_type ped2 --model_dir pretrained_model.pth --m_items_dir m_items.pt
```
* Test your own model
* Check your dataset_type (ped2, avenue or shanghai)
```bash
python Evaluate.py --dataset_type ped2 --model_dir your_model.pth --m_items_dir your_m_items.pt
```

## Bibtex
```
@inproceedings{
menon2021re,
title={Re Learning Memory Guided Normality for Anomaly Detection},
author={Varun Menon and Kevin Stephen},
booktitle={ML Reproducibility Challenge 2020},
year={2021},
url={https://openreview.net/forum?id=vvLWTXkJ2Zv}
}

```
