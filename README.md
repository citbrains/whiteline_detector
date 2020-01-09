# whiteline_detector

### サーバーでの白線の学習手順

1. 自分のPC内にある白線の学習データファイル(.jpgと\_label.png)をzipファイルにする。
```
zip -r ~.zip 学習データファイル名
```

2. サーバーに1で作ったzipファイルを転送。(whiteline2019/whiteline_detector/ までzipファイルを移動)
```
scp 1で作ったzipファイル名 サーバーのIPアドレス:ファイルを置くディレクトリ
```

3. 展開する。

```
unzip 展開したいファイル名
```

4. wldetection2.ipynbにて88行目を変更。
```python
jpgfiles = glob.glob('ここを書き換える(4で展開したファイル名に)/*.jpg')
```

5. jupyter上で実行

6. 学習回した後「〜.npz」というファイル名が出来ている。

7. サーバーの端末上で下記を入力すると、ファイルがある場所が表示されるのでコピーしておく。
```
realink -f 6で出来たファイル名
```

### 自分のPCに出来た重みを持ってくる方法

下記を入力して自分のPCに持ってくる。(.は今自分がいるディレクトリという意味)
```
scp サーバーのIPアドレス:7でコピーしたものを貼り付ける .
```



### 重みの保管場所

2019年: http://www.hayashibara-lab.it-chiba.ac.jp/robocup/DeepLearning/2019/
