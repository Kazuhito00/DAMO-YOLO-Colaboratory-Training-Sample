# DAMO-YOLO-Colaboratory-Training-Sample
https://user-images.githubusercontent.com/37477845/208217703-756cf5e8-df30-48ad-a164-798cc3b7539c.mp4

[DAMO-YOLO](https://github.com/tinyvision/DAMO-YOLO)をGoogle Colaboratory上で訓練しONNX形式のファイルをエクスポートするサンプルです。<br>
以下の内容を含みます。<br>
* データセット
* Colaboratory用スクリプト(環境設定、モデル訓練)
* ONNX推論サンプル

# Requirement
* opencv-python 4.5.5.64 or later ※推論サンプルを実施する場合のみ
* onnxruntime 1.12.0 or later ※推論サンプルを実施する場合のみ

# About annotation
Pascal VOC形式で出力したアノテーションデータを前提としています。<br>
ただし、ノートブック内で更にMS COCO形式変換しています。<br><br>

# Usage
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Kazuhito00/DAMO-YOLO-Colaboratory-Training-Sample/blob/main/DAMO_YOLO_Colaboratory_Training_Sample.ipynb)<br>
トレーニングはGoogle Colaboratory上で実施します。<br>
[Open In Colab]リンクからノートブックを開き、以下の順に実行してください。
1. condaインストール(conda install)<br>condacolab インストール後にセッション再起動でクラッシュしますが、インストールは成功しているため、以降の処理を続けて実行してください。<br>
After the installation, the session causes a crash, but the installation was successful, so please continue with the subsequent steps.
1. 必要パッケージインストール(install)
1. データセットダウンロード(Download Dataset)
1. Pascal VOC形式 を MS COCO形式へ変換(Convert Pascal VOC format to MS COCO format)
1. 学習データディレクトリ準備(Training data directory preparation)
1. DAMO-YOLO学習用コンフィグファイル生成
1. トレーニング
1. ONNXエクスポート
1. ダウンロード

# Demo
トレーニング後のONNXの動作確認用デモは以下です。
```
python demo.py --model=damoyolo_tinynasL20_T.onnx --movie=fish.mp4
```

# Author
高橋かずひと(https://twitter.com/KzhtTkhs)
 
# License 
DAMO-YOLO-Colaboratory-Training-Sample is under [Apache-2.0 License](LICENSE).
