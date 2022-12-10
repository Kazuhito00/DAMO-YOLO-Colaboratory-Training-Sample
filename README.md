# ⚠Attention⚠
試験的な内容のリポジトリです。<br>
いくつかのIssueの内容を暫定対応しています。<br>
* https://github.com/tinyvision/DAMO-YOLO/issues/24<br>発生条件：詳細不明<Br>→おそらくデータセット数が少ない時にMosaicのデータ拡張でエラーが発生<br>暫定対応：damo/dataset/datasets/mosaic_wrapper.py にエラー処置を追加
* https://github.com/tinyvision/DAMO-YOLO/issues/39<br>発生条件：詳細不明<Br>→ファインチューニング時にデータ拡張を有効にするとLossが0になり学習が進まない？<br>暫定対応：self.train.no_aug_epochs を総エポック数と同一値に設定
* ファインチューニング時にクラス数を変更するとモデル構築に失敗する<br>暫定対応：ファインチューニング元のクラス数から変更しないように、VOC→COCO変換時に"categories"を80クラスになるよう不要なクラスで埋める

# DAMO-YOLO-Colaboratory-Training-Sample
<img src="https://user-images.githubusercontent.com/37477845/206830834-0fedef1b-b465-4ac6-8dfb-2adb10051e51.gif" width="40%"><br>

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
1. 暫定修正
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
YOLOX-Colaboratory-Training-Sample is under [Apache-2.0 License](LICENSE).


