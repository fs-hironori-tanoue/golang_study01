---?image=images/techjin.jpg&size=cover&opacity=20
## Go言語勉強会
### 第1回 入門編
#### TD-Unit Hironori Tanoue
---
@snap[north]
### 目次
@snapend
1. はじめに
2. 構成と実行
3. 言語の基本
---
@snap[north]
### 1. はじめに
@snapend
- Go言語とは
- C言語との比較
- ダウンロード
- インストール
---
@snap[north]
### Go言語とは
@snapend
- Google社によって開発 |
- コンパイル型言語 |
- マルチプラットフォーム |
- オブジェクト指向ではない |
---
@snap[north]
### C言語との比較
@snapend
- ガベージコレクターのサポート |
- 並列処理のネイティブサポート |
- 改良されたC言語 |
---?image=images/go_download.png&size=55% 55%
@snap[north]
### ダウンロード
@snapend
@snap[south]
https://golang.org/dl/
@snapend
---
@snap[north]
### インストール
@snapend
- @fa[apple fa-lg] パッケージインストーラー
- @fa[windows fa-lg] MSIインストーラー
---
@snap[north]
### 2.構成と実行
@snapend
- Hello, World!
- Goのコマンド
- パッケージと構成
---?code=src/hello/hello.go
@snap[north]
### Hello, World!
@snapend
@[1](Goでは何らかのパッケージに属する必要がある) |
@[3-5](プログラムで使用するパッケージを指定) |
@[7-9](メイン処理はmain関数で定義)
---
@snap[north]
### Hello, World!
@snapend
```
$ go run hello.go
Hello, World!
```
@[1](go run [ファイル名]で実行) |
@[2](実行結果の表示) |
---
@snap[north]
### Goのコマンド
@snapend
```
$ go run hello.go
$ go build hello.go
$ go fmt hello.go
$ go test hellog.go
```
@[1](ビルド & 実行) |
@[2](ビルドのみ) |
@[3](ソースコード整形) |
@[4](テストコード実行) |
---
@snap[north]
### パッケージと構成
@snapend
```
zoo  
├── animals  
│   ├── elephant.go  
│   ├── monkey.go  
│   └── rabbit.go  
└── main.go  
```
@[1](アプリケーションと同名のディレクトリ) |
@[6](直下にmainパッケージ定義用のmain.go) |
@[2-5](独自に定義するパッケージのディレクトリ) |
---?code=src/zoo/animals/elephant.go
@snap[north]
### パッケージと構成
@snapend
パッケージ名がディレクトリ名になるようファイルを構成する
---?code=src/zoo/animals/monkey.go
@snap[north]
### パッケージと構成
@snapend
パッケージ名がディレクトリ名になるようファイルを構成する
---?code=src/zoo/animals/rabbit.go
@snap[north]
### パッケージと構成
@snapend
パッケージ名がディレクトリ名になるようファイルを構成する
---?code=src/zoo/main.go
@snap[north]
### パッケージと構成
@snapend
@[5](独自定義したパッケージを指定) |
@[9-11]([パッケージ].[関数]で実行) |
---
@snap[north]
### パッケージと構成
@snapend
```
$ go run main.go  
Grass  
Banana  
Carrot  
```
@[1](zooフォルダ直下で go run を実行) |
@[2-5](animalsパッケージの関数が呼び出される) |
---
### おわり
