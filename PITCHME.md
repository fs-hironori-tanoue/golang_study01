## Go言語勉強会
### 第1回 入門編
#### TD-Unit Hironori Tanoue
---
@title[目次]
@snap[north]
### 目次
@snapend
### 目次
1. はじめに
2. プログラムの構成と実行
3. 言語の基本
---
@snap[north]
### 1. はじめに
@snapend
- Go言語とは
- C言語との比較
- 開発環境
+++
@snap[north]
### Go言語とは
@snapend
- Google社によって開発 |
- コンパイル型言語 |
- マルチプラットフォーム |
- オブジェクト指向ではない |
+++
@snap[north]
### C言語との比較
@snapend
- ガベージコレクターのサポート |
- 並列処理のネイティブサポート |
- 改良されたC言語 |
+++
@snap[north]
### 開発環境
@snapend
#### Goのダウンロード
https://golang.org/dl/
![images/go_download.png](images/go_download.png)
+++
@snap[north]
### 開発環境
@snapend
#### インストール
- OS X 環境  
fa[apple]
パッケージを使用して通常のインストールを実行する。
- Windows 環境  
fa[windows]
MSIインストーラーよりインストールを実行する。
---
@snap[north]
### 2.プログラムの構成と実行
@snapend
- Hello, World!
- プログラムの実行
- ああああ
- ああああ
+++?code=hello/hello.go
@snap[north]
### Hello, World!
@snapend
@[1](Goでは何らかのパッケージに属する必要がある) |
@[3-5](プログラムで使用するパッケージを指定) |
@[7-9](メイン処理はmain関数で定義) |
---
@snap[north]
### プログラムの実行
@snapend

---
### おわり
