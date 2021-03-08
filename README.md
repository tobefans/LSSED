# LSSED
The dataset of the paper "LSSED: A Large-Scale Dataset and Benchmark for Speech Emotion Recognition".

## Dataset
In view of copyright reasons, researchers who are interested in applying for this dataset, please contact Prof. Xing or Dr. Fan by email.

## Pre-trained models
Our pre-trained models are released [here](https://onedrive.live.com/?authkey=%21ACsmcyDUBU%5FJqOQ&id=B2C03030A7C7F63F%211204&cid=B2C03030A7C7F63F). It contains three versions of PyResNet, with ResNet50, ResNet101 or ResNet152 as the backbone respectively.

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
