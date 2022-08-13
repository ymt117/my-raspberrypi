## 開発環境

- Manjaro linux
- fish shell

## 開発環境構築

コンパイラのインストール

```sh
$ sudo pacman -S arm-none-eabi-gcc arm-none-eabi-newlib
```

SDKのリポジトリをClone

```sh
$ mkdir -p ~/Documents/pico
$ cd ~/Documents/pico
$ git clone https://github.com/raspberrypi/pico-sdk.git
$ cd pico-sdk
$ git submodule update --init
```

パスを通す

```sh
$ echo "set -gx PICO_SDK_PATH ~/Document/pico/pico-sdk" >> ~/.config/fish/config.fish
$ source ~/.config/fish/config.fish
```

picotoolのリポジトリをCloneしてビルド

```sh
$ git clone https://github.com/raspberrypi/picotool.git
$ cd picotool
$ mkdir build
$ cd build
$ cmake ../
$ make
```

## Lチカ

pico-examplesのリポジトリをClone

```sh
$ cd ~/Documents/pico
$ git clone https://github.com/raspberrypi/pico-examples.git
$ cd pico-examples
```

pico-examplesをビルド

```sh
$ mkdir build
$ cd build
$ cmake ../
```

blinkをビルド

```sh
$ cd blink
$ make
```

## 書き込み

### 方法1

BOOTSELボタンを押したままPCに接続とストレージとして認識される

`blink.uf2`をドラッグ&ドロップ

### 方法2

picotoolを使う

```sh
$ sudo ~/pico/picotool/build/picotool load ./blink.uf2
$ sudo ~/pico/picotool/build/picotool reboot
```

## VSCodeの設定

拡張機能のインストール

- marus25.cortex-debug
- ms-vscode.cmake-tools
- ms-vscode.cpptools

VSCodeでプロジェクトのディレクトリを開く

コンパイラに「GCC <Version> arm-none-eabi」（<Version>にはバージョン番号が入る）を選択する
