# TextRecognitionDataGenerator
## Introduction
生成繁體中文文字圖像以供訓練。
## Build Process
* 首先先下載pakage，就可以開始操作。

```pip install trdg```

並執行

```pip install -r requirements.txt```

安裝其他需要的pakage。
## Basic CLI
首先先cd進入trdg資料夾。
### 生成繁體中文圖像
如要隨機生成五個中文字的圖片，可簡單執行
```python run.py -c 300 -l cn -w 5```


![photo_2021-10-29_09-36-42](https://user-images.githubusercontent.com/62441311/139358891-81b9a986-00e5-45c0-a79d-78b2e656a006.jpg)

也可以設定其他Argumentation

###Text skewing
只需要增加參數-k(設定角度)和-rk(0~設定角度)

```python run.py -c 300 -l cn -w 5 -k 5 -rk)```

![photo_2021-10-29_09-41-36](https://user-images.githubusercontent.com/62441311/139359291-d5e62179-94e1-49dc-b9c7-21aa4f8a790a.jpg)

###Background

加入參數-b可挑選背景，gaussian noise (0)， plain white (1)， quasicrystal (2) 或 image (3)，

![image](https://user-images.githubusercontent.com/62441311/139359986-752d81e8-92d2-46f1-b098-b10c26ff8b96.png)

