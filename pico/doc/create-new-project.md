## 新規プロジェクト作成

プロジェクト用のディレクトリを作成する

```txt
# ディレクトリ構造
myproject
├── CMakeLists.txt
├── build
├── pico_sdk_import.cmake
├── pico_sdk_init.cmake
└── src
    └── main.cpp
```

`src/main.cpp`と`CMakeLists.txt`を自分で書く

`pico_sdk_import.cmake`と`pico-sdk-init.cmake`は`pico-sdk`からコピペしてくる

```sh
$ cp ~/Documents/pico/pico-sdk/external/pico_sdk_import.cmake /path/to/myproject
$ cp ~/Documents/pico/pico-sdk/pico_sdk_init.cmake /path/to/myproject
```

### ビルド

```sh
$ cd build
$ cmake ../
$ make
