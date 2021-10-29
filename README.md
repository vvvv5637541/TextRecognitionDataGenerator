# TextRecognitionDataGenerator
## Introduction
生成繁體中文文字圖像以供訓練。請參考[the official documentation](https://textrecognitiondatagenerator.readthedocs.io/en/latest/index.html).

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

也可增加其他Argumentation。

### Text skewing
只需要增加參數-k(設定角度)和-rk(0~設定角度)

```python run.py -c 300 -l cn -w 5 -k 5 -rk```

![photo_2021-10-29_09-41-36](https://user-images.githubusercontent.com/62441311/139359291-d5e62179-94e1-49dc-b9c7-21aa4f8a790a.jpg)

### Text blurring
增加`-bl` and `-rbl`參數來達到高斯模糊的效果。

![image](https://user-images.githubusercontent.com/62441311/139361673-7c1b2987-eda1-406e-8bc4-6624943765aa.png)

### Background
加入參數-b可挑選背景，gaussian noise (0)， plain white (1)， quasicrystal (2) 或 image (3)，

![image](https://user-images.githubusercontent.com/62441311/139359986-752d81e8-92d2-46f1-b098-b10c26ff8b96.png)

如選擇image (3)，將會從images/ folder隨機選擇圖片當作背景。

因我們想生成的是字詞顏色和背景顏色為互補色，在選擇plain white (1)時有做修改。

```python run.py -c 300 -l cn -l cn -i snt.txt --output_dir test --margins 0,0,0,0 --fit -b 1```

-i為欲生成哪些字詞的檔案，在snt.txt檔中存放欲生成的字詞。
--output_dir為欲輸出的資料夾。
--margins設定為0,0,0,0代表邊框和字的距離為0。
-b選擇1時，文字顏色和背景顏色為互補色。

![photo_2021-10-29_09-55-49](https://user-images.githubusercontent.com/62441311/139360533-96237a0f-c0c8-4897-8994-430f79edb51c.jpg)
![photo_2021-10-29_09-55-51](https://user-images.githubusercontent.com/62441311/139360537-42555d6c-7dca-4a1e-8895-5145a41ffe0f.jpg)

## Reference
[TextRecognitionDataGenerator](https://github.com/Belval/TextRecognitionDataGenerator)
