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

## Lチカ

pico-examplesのリポジトリをClone

```sh
$ cd ~/Documents/pico
$ git clone https://github.com/raspberrypi/pico-examples.git
$ cd pico-examples
```

pico-ecamplesをビルド

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

BOOTSELボタンを押したままPCに接続

`blink.uf2`をドラッグ&ドロップ
