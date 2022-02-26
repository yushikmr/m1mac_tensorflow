# m1mac_tensorflow

m1搭載MacBookでのtensorflow環境の構築

# 構築手順

## 事前準備

anacondaとかminicondaとかをinstallしてcondaコマンドが使用できる状態にしておいてください

## tensorflow導入

レポジトリ内で以下のコマンドを実行

`conda env create -f enviroment.yml`

上記のymlファイルには

- tensorflow
- jupyter lab
が入っています。想定するpython versionは3.8です。

続いて

`conda activate m1mac_tensorflow`

でconda環境を有効にしてください

### m1用tensorflowの導入

以下のコマンドを実行してください
`pip install --upgrade --force --no-dependencies https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha3/tensorflow_addons_macos-0.1a3-cp38-cp38-macosx_11_0_arm64.whl https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha3/tensorflow_macos-0.1a3-cp38-cp38-macosx_11_0_arm64.whl`

`pip install --upgrade --force --no-dependencies`

で後続するurlにあるファイルのソースファイルからパッケージをインストールできます。m1用のtensorflowパッケージは現時点(2022/02/26)では
`https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha3/tensorflow_addons_macos-0.1a3-cp38-cp38-macosx_11_0_arm64.whl`が使用できます。

最新のバージョンはここを確認してください [guthubレポジトリ](https://github.com/apple/tensorflow_macos)

## jupyterで作成した仮想環境を実行できるようにする

以下のコマンドで作成した仮想環境をjupyter kernelに追加してください
`ipython kernel install --user --name=m1mac_tensorflow --display-name=m1mac_tensorflow`

## 環境の起動をtensorflowの使用

`jupyter lab`でjupyterlabを起動し、sample.ipynbを開いてください

select kernelでm1mac_tensorflowを選択すれば
`import tensirflow as tf`が実行できます。

