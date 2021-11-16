# openVINO のお試しプログラム類

## ディレクトリ構成

| ディレクトリ        | 内容                                                                 |
|---------------------|----------------------------------------------------------------------|
| images              | テスト用画像保存用                                                   |    
| models              | 各ツールキット用モデル格納用                                         |  
| models/_IR          | openVINO用モデルコンバート結果格納用                                 |  
| models/_models      | openVINO用モデルコンバート元データダウンロード用/tensorflow用モデル  |  
| models/_onnx        | onnx-runtime用モデルコンバート元データダウンロード用                 |  
| models/onnx         | onnx-runtime用モデルコンバートスクリプト実行ディレクトリ             |  
| models/ov           | openVINO用モデルコンバートスクリプト実行ディレクトリ                 |  
| onnx                | onnx-runtimeでSSDを実行する                                                        |
| ov                  | openVINOでSSDを実行する                                                        |
| tf                  | tensorflowでSSDを実行する                                                        |


## openVINO
以下あたりを参考にopenVINOをインストール  
<https://ippei8jp.github.io/memoBlog/2020/06/16/openVINO_ubuntu_2.html>  
<https://ippei8jp.github.io/memoBlog/2020/10/18/openVINO_ubuntu_3.html>  


## tensorflow
以下の手順で仮想環境を準備  
```
# 仮想環境の作成
pyenv virtualenv 3.8.11 tf2
pyenv local tf2
pip install --upgrade pip setuptools wheel

# tensorflowとopenCVをインストール
pip install tensorflow
pip install opencv-python
```

## onnx-runtime
以下の手順で仮想環境を準備  
```
# 仮想環境の作成
pyenv virtualenv 3.8.11 onnx
pyenv local onnx
pip install --upgrade pip setuptools wheel

# onnx-runtimeとopenCVをインストール
pip install onnxruntime
pip install opencv-python

# tensorflowモデルからのコンバートを行う場合は以下もインストールする
pip install tensorflow
pip install tf2onnx
```


onnx-runtime用モデルコンバートに使用する元モデルは
openVINO用モデルのコンバートで使用したモデルのうちの、tensorflowモデルを使用している。  
onnx-runtime用モデルのコンバートはopenVINO用モデルのコンバートを行ってから実行するか、  
手動でtensorflow用モデルをダウンロードし、
コンバートスクリプトの元ファイルのディレクトリを変更して実行してください。  
