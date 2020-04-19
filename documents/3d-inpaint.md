[3D Photography using Context-aware Layered Depth Inpainting](https://shihmengli.github.io/3D-Photo-Inpainting/) を試した記録。。

## Links
- [論文: 3D Photography using Context-aware Layered Depth Inpainting](https://drive.google.com/file/d/17ki_YAL1k5CaHHP3pIBFWvw-ztF4CCPP/view)
- [Github](https://github.com/vt-vl-lab/3d-photo-inpainting)

## anaconda

[インストール手順](https://www.python.jp/install/anaconda/macos/install.html)にしたがって[Anaconda](https://www.anaconda.com/distribution/) をインストールし.

`~/opt/anaconda3/` にインストールされた。

`https://anaconda.org/` からパッケージを探すことができる。

## wget

wgetコマンドを使えるようにしておく。下記の手順にしたがってhomebrewを使ってインストールする。

https://webkaru.net/dev/mac-wget-command-install/

```bash
brew install wget
```

## packages

pipでrequirements.txtの内容をインストールしてもcondaで認識されなかった。（pythonとanacondaを関連づける必要がある？）
pythonのシェルではimportできるのにanacondaの環境では`ImportError : No module named 'package'`のエラーになった。
condaでインストールしなおしたが、conda環境に慣れていないため、pipでパッケージを揃えることにした。
（transforms3dだけcondaでインストールしてもimportできなかった。）

ImportErrorになったパッケージ

### vispy

### cv2

```
pip3 install opencv-python
```

conda環境だとライブラリとのバージョン不整合のエラーが発生した。 [参考](https://github.com/ContinuumIO/anaconda-issues/issues/1266)

> Incompatible library version when installing opencv via conda

### moviepy

### transforms3d

### yaml

```
pip3 install pyyaml
```

## CUDA

> RuntimeError: Attempting to deserialize object on a CUDA device but torch.cuda.is_available() is False. If you are running on a CPU-only machine, please use torch.load with map_location='cpu' to map your storages to the CPU.

> AssertionError: Torch not compiled with CUDA enabled

torchはGPUまたはCPUを利用して実行できる。GPUを使う場合にはCUDA(クーダ)というGPU向け並列コンピューティングが必要になる。
CUDAが有効でない状態でCUDAを使おうとすると上記のエラーが発生する。

スクリプト内でCUDAを使おうとしている箇所を修正して対応。

```　
device = torch.device('CPU')
```

(この問題はconda環境だと発生しないのかもしれない。condaで環境を作る場合にはcudatoolkitをインストールする)



