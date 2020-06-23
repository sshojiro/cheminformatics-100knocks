# ケモインフォマティクス100本ノック

ケモインフォマティクス入門用の例題集です。

## 環境構築
1. AnacondaあるいはMinicondaをインストールしましょう。
1. [Windows] [Windows Git Bash](https://gitforwindows.org/)をダウンロードしてGit Bashを使えるようにしましょう。その後で`echo HELLO WORLD!`と実行してみましょう。
1. [Mac] Homebrewをインストールしましょう。様々なソフトを簡単にインストールできるようになります。まずは`brew install git`を実行しましょう。

## データの読み込み・保存
1. RDKitでファイルを読み込みましょう。
1. pandasでcsvファイルを読み込みましょう。
1. DeepChemのデータセットをダウンロードしてみましょう。
1. ZINCデータベースからデータをダウンロードしてみましょう。
1. ChemSpiderデータベースからデータをダウンロードしてみましょう。
1. ChEMBLからヒスタミン阻害剤の化合物を取り出しましょう。IG50の値を元に`正例:負例=50:50`になるようにデータ分割をしましょう。
1. 各種データ形式（Molファイル、SDFファイル、SMILES、SMARTS、InChi）の比較をして、表現できるものとできないものをまとめましょう。

## Bashを使ったデータ成形
1. SDFファイル中の化合物をBashコマンドで数えてください。
1. ファイルのエンコーディング（Shift-JIS, UTF-8, etc.）を確認しましょう。
1. 複数のSDFファイル中の化合物をBashコマンドで数えてください。
1. ChEMBLからアッセイデータをダウンロードして、ファイル名を簡単な略称に変換しましょう。

## 記述子取得
1. 化合物セットに対してRDKit記述子（200次元）を取得しましょう。

## 化合物可視化
1. フィンガープリントを可視化しましょう（RDKit version>=2019.09）。
1. 化合物セットに対するRDKit記述子をPCAして可視化しましょう。
1. 化合物セットをRDKit記述子に直してから、GTMで可視化しましょう。GTMライブラリは`pip install git+https://github.com/sshojiro/ugtm`でインストールし利用できます。

## Scikit-Learnを使った機械学習
1. SMILESをRDKit記述子に変換してみましょう。
1. train_test_splitを使ってデータ分割をしましょう。
1. sklearn.model_selection.GridSearchCVを使ってパラメータ調整をし、sklearn.svm.SVRによる物性値予測モデルを構築しましょう。
1. 水溶解度データに対するRandomForestRegressor, SVRの予測精度を比較してみましょう。
1. 水溶解度データに対するIsolationForest, OneClassSVMによる異常サンプル検出率を確認しましょう。
1. [Stackingモデル](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.StackingRegressor.html#sklearn.ensemble.StackingRegressor)などのensembleモデルを構築しましょう。

## モデル解釈
1. 水溶解度データに対してLASSOを実行して重要な変数を確認しましょう。
1. PLSのVIP、T2、Qを調べて実装しましょう。
1. RandomForestモデルを構築して各変数の寄与率を確認しましょう。
1. [SHAP](https://github.com/slundberg/shap)の式を理解し、RandomForestの結果について実行してみましょう。
1. SVM、SVRの微分を取って変数の寄与を確認しましょう。
1. 数値微分によりGPRの変数の寄与(GPR-SA)を計算してみましょう。

## フィンガープリントと構造類似度
1. Morganフィンガープリントをハッシュ化有り／無しで取得しましょう。
1. タニモト係数、ダイス係数、シンプソン係数を定義しましょう。
1. タニモト係数、ダイス係数、シンプソン係数を計算しヒートマップを描いてみましょう。
1. タニモト係数などの指標を使って距離行列を計算しt-SNEによる可視化をしましょう。
1. 分子骨格(Scaffold)を取り出し可視化しましょう。

## 構造生成
1. 単結合で化合物を結合する関数を書きましょう。
1. BRICSアルゴリズムを使って構造を取り出しましょう。
1. [Chemical VAE](https://github.com/aspuru-guzik-group/chemical_vae)を使って化合物を取り出しましょう。

## 最適化
1. ベイズ最適化により水溶解度を最大化するプログラムを書いてみましょう。指標はPI、EI、UCBと変更して収束の様子を確認しましょう。

## 証明系
1. PCAを導出して実装しましょう。
1. PLSを導出して実装しましょう。
1. カーネル法でPCA、PLSを実装しましょう。
1. カーネルk-Means法を実装しましょう。