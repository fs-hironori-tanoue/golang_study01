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
@size[1.2em](ダウンロード)
@snapend
@snap[south]
https://golang.org/dl/
@snapend
---
@snap[north]
### 2.構成と実行
@snapend
- Hello, World!
- Goのコマンド
- パッケージと構成
- パッケージのテスト
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
$go run hello.go
Hello, World!
```
@[1](go run [ファイル名]で実行) |
@[2](実行結果の表示) |
---
@snap[north]
### Goのコマンド
@snapend
```
$go run hello.go
$go build hello.go
$go fmt hello.go
$go test hellog.go
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
│       ├── elephant.go  
│       ├── monkey.go  
│       └── rabbit.go  
└── main.go  
```
@[1](アプリケーションと同名のディレクトリ) |
@[6](直下にmainパッケージ定義用の「main.go」) |
@[2](独自に定義するパッケージのディレクトリを作成) |
@[3-5](独自定義したパッケージのソースファイルを配置) |
---?code=src/zoo/animals/elephant.go
@snap[north]
### パッケージと構成
@snapend
zoo/animals/elephant.go
---?code=src/zoo/animals/monkey.go
@snap[north]
### パッケージと構成
@snapend
zoo/animals/monkey.go
---?code=src/zoo/animals/rabbit.go
@snap[north]
### パッケージと構成
@snapend
zoo/animals/rabbit.go
---?code=src/zoo/main.go
@snap[north]
### パッケージと構成
@snapend
zoo/main.go
@[5](独自定義したパッケージをインポート) |
@[9-11]([パッケージ].[関数]で実行) |
---
@snap[north]
### パッケージと構成
@snapend
```
$go run main.go  
Grass  
Banana  
Carrot  
```
@[1](zooフォルダ直下で「go run」を実行) |
@[2-5](animals パッケージの関数が呼び出される) |
---
@snap[north]
### パッケージのテスト
@snapend
```
zoo  
├── animals  
│       ├── animals_test.go  
│       ├── elephant.go  
│       ├── monkey.go  
│       └── rabbit.go  
└── main.go  
```
@[3](「[パッケージ名]_test.go」というファイルを追加) 
---?code=src/zoo/animals/animals_test.go
@snap[north]
### パッケージのテスト
@snapend
@[4](標準パッケージの testing をインポート) |
@[7](「Test + 関数名」でテスト対象の関数で定義) |
@[8](テスト結果の予想) |
@[9](テストの実行) |
@[11-13](テスト失敗時の例外出力) |
---
@snap[north]
### パッケージのテスト
@snapend
```
$go test ./animals
ok      _/Users/hiro_tan_00/workspace/golang_study01/src/zoo/animals    (cached)
```
@[1](zooフォルダ直下で「go test [パッケージ名]」を実行) |
@[2](テスト結果が表示される) |
---
@snap[north]
### 3.言語の基本
@snapend
- 文(Statement)
- 変数の定義
- データ型
- 関数定義
- 制御構文
---?code=src/hello2/hello.go
@snap[north]
### 文(Statement)
@snapend
文(Statement)はセミコロン(;)  
によって区切られる。  
ただし、省略可能  
---?code=src/statement/statement.go
@snap[north]
### 文(Statement)
@snapend
(コンパイル前)
---?code=src/statement/statement2.go
@snap[north]
### 文(Statement)
@snapend
@[1](文末にセミコロンを挿入) |
@[3-5](文末が「,」「{」の場合はセミコロンを挿入しない) |
@[7-10](文末にセミコロンが挿入されコンパイルエラー) |
---
@snap[north]
### 変数の定義
@snapend
```
var n int
var x, y. z int
var (
  x, y int
  name string
)
i := 1
b := true
s := "abc"
```
@[1](var で変数を定義) |
@[2](カンマ区切りでまとめて定義も可能) |
@[3-6](()で囲うことでまとめて定義も可能) |
@[7-9](「:=」で初期値を代入しての定義が可能) |
---?code=src/package/package.go
@snap[north]
### 変数の定義
@snapend
@[7](関数定義外に定義された変数はパッケージ変数となる) |
@[11](「n=101」と出力される) |
---
@snap[north]
### データ型
@snapend
```
var b bool
var i int
var i8 int8
var i16 int16
var i32 int32
var i64 int64
var ui uint
var ui8 uint8
var ui16 uint16
var ui32 uint32
var ui64 uint64
var ptr uintptr
```
@[1](論理値) |
@[2-6](符号付き整数値) |
@[7-11](符号なし整数値) |
@[12](ポインタ用符号なし整数) |
---
@snap[north]
### データ型
@snapend
```
var f32 float32
var f64 float64
r := '松'
s := "abc"
r := `
abc
efg
hij
`
```
@[1](浮動小数点(Java:float)) |
@[2](浮動小数点(Java:double)) |
@[3](rune型(C言語のChar型)) |
@[4](string型) |
@[5-9](RAW文字列リテラル(複数行に渡る文字列)) |
---
@snap[north]
### データ型
@snapend
```
a := [5]int{1, 2, 3, 4, 5}
fmt.Printf("%v\n", a[0])
b := [...]int{6, 7, 8. 9. 10}
```
@[1](「[n]データ型{初期値}」で定義) |
@[2](配列は0からの範囲で指定(「1」と出力)) |
@[3](「...」で要素数の省略も可能) |
---
@snap[north]
### データ型
@snapend
```
var x interface{}
x = 1
x = 3.13
x = '松'
x = "文字列"
x = [...]int{1, 2, 3, 4, 5}
```
@[1](型名に「interface{}」で定義) |
@[2-6](あらゆるデータ型との互換性がある) |
---
@snap[north]
### 関数定義
@snapend
```
func plus(x, y int) int {
  return x + y
}

func hello() {
  fmt.Println("Hello!")
}

func div(a, b int) (int, int) {
  q := a / b
  r := a % b
  return q, r
}
```
@[1](func [関数名]( [引数の定義] [戻り値型] ) |
@[5](戻り値がない場合は省略) |
@[9](複数の戻り値の指定も可能) |
---
@snap[north]
### 制御構文
@snapend
```
for {
}
for i := 0; i < 10; i++ {
}
```
@[1-2](無限ループ) |
@[3-4](0-9のループ) |
---
@snap[north]
### 制御構文
@snapend
```
fruits := [3]string{"Apple", "Banana", "Cherry"}
for i, s := range fruits {
  fmt.Printf("fruits[%d]=%s¥n", i, s)
}
```
@[2](for [インデックス], [配列の要素] := range [配列型]) |
@[3](「fruits[0]=Apple・・・」と出力される) |
---
@snap[north]
### 制御構文
@snapend
```
if x == 1 {
} else if x == 2 {
} else {
}
```
@[1](条件式(x == 1)合致した場合に処理される) |
@[2](最初の条件式に合致しない場合に判定される) |
@[3](どれにも合致しない場合に処理される) |
---
### おわり
