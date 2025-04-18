# M5Unified-WindowsNative-examples
Windows環境でM5Unifiedを動かすためのサンプル

# セットアップ

## Visual Studio Code
```
winget install Microsoft.VisualStudioCode --override "/VERYSILENT /NORESTART /MERGETASKS=!runcode,addcontextmenufiles,addcontextmenufolders,associatewithfiles,addtopath"
```
上記コマンドでいれるか、普通にVisual Studio Codeをインストールする。単に「winget install Microsoft.VisualStudioCode」でも問題ないが、この場合にはPathが追加されなかったり、右クリックからCodeで開くなどの機能が使えません。

### 拡張機能の設定
1. (必要であれば)日本語化
2. PlatformIOの追加

## MSYS2 + SDL2
```
winget install MSYS2.MSYS2
C:\msys64\usr\bin\pacman -S mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-gdb
C:\msys64\usr\bin\pacman -S mingw-w64-ucrt-x86_64-SDL2
```

通常のインストールよりは上記のコマンドを利用するのが確実です。
gccへのPathの追加は環境設定を変更か、Visual Studio Codeの起動時に設定するかをする必要があります。
このサンプルではVisual Studio Codeの起動時に設定しています。

## 実行方法
start.batを実行して起動させます。

```
set PATH=%PATH%;C:\msys64\ucrt64\bin
"C:\Users\%USERNAME%\AppData\Local\Programs\Microsoft VS Code\bin\code" .
```

start.batでは上記の処理を行っており、既存のpathにgccのあるC:\msys64\ucrt64\binを追加してからVisual Studio Codeを起動させています。
Visual Studio Codeの起動は通常はcode .で今いるディレクトを開くで起動するはずですが、サンプルでは念の為フルパスを指定しています。
