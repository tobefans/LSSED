# LSSED
The dataset of the paper "LSSED: A Large-Scale Dataset and Benchmark for Speech Emotion Recognition".

## Dataset
In view of copyright reasons, researchers who are interested in applying for this dataset, please read and sign the license (EULA.pdf) carefully and send it to Prof. Xing by email.

## Pre-trained models
Our pre-trained models are released [here](https://mailscuteducn-my.sharepoint.com/:f:/g/personal/202010102065_mail_scut_edu_cn/EqZ614QxHUdKrzLcFMXi1nUBVvDOS9UKfgI4pesE73vM_A?e=9B3gTS) (password: SCUTLAB626). It contains three versions of PyResNet, with ResNet50, ResNet101 or ResNet152 as the backbone respectively.

The import and use of the pre-trained model are as follows:
```
model = torch.load('path_to_model.pth')
output = model(input)
```
These pre-trained models can be directly applied to the classification task of four kinds of emotions, including "Angry(0)", "Neutral(1)", "Happy(2)" and "Sad(3)".
If the user needs to perform other emotion recognition or related speech downstream tasks, then fine-tuning is necessary.
The user can replace the fully connected layer classifier of the last layer of the model called "fc".
```
model_ft = torch.load('path_to_model.pth')
num_fc_ftr = model_ft.fc.in_features
model_ft.fc = nn.Linear(num_fc_ftr, num_class)
```

## Contact
Prof. Xing: xfxing@scut.edu.cn

Dr. Fan: weiquan.fan96@gmail.com
