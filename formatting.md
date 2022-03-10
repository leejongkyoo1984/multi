# フォーマティング (Formatting)
フォーマッティング問題は重要ではありませんが、最も議論の通りです。人々はそれぞれ異なるフォーマットスタイルを適用するかもしれませんが、誰もが同じスタイルに固執し、もはやそれを必要としなくなり、フォーマットのトピックにあまり気にしないでください。問題は長く、規則的なスタイルガイドなしでいかにこのユートピアにアクセスできるかである。


Goでは、私たちは新しいアプローチを取り、マシンに大部分のフォーマット問題を処理させることができます。 `gofmt`プログラム（ `go fmt`としても使用できます。これはソースファイルではなくパッケージレベルで実行されます）はGoプログラムを読み、標準スタイルのインデントと垂直整列、維持、そして必要に応じてコメントを再フォーマットします。ソースを出す。


例えば、Goでは、構造体のフィールドに書かれた注釈を整列するのに気を使う必要はありません。 `Gofmt`が代わってくれるだろう。以下を見てみましょう。

```go
type T struct {
    name string // name of the object
    value int // its value
}
```

`gofmt`は各列を次のようにソートします

```go
type T struct {
    name    string // name of the object
    value   int    // its value
}
```


標準パッケージのすべてのGoコードは `gofmt`でフォーマットされています。


いくつかのフォーマッティングの詳細が残っているが、これを非常に簡単に要悪してみると次のようになる。


インデント

>インデントにはタブを使用し、 `gofmt`はデフォルトでタブを使用します。書く必要がある場合にのみスペースを使用してください。

一行の長さ

> Goは一行の長さに制限がありません。長さが長くなるのを心配しないでください。行の長さが長すぎると感じる場合は、別のタブを持ってインデントして包みます。

かっこ

> GoはCとJavaに比べて少数の括弧が必要です。制御構造（ `if`、 `for`、 `switch`）の文法には括弧はありません。また、演算子優先順位階層が単純で明確である。以下を見てみましょう。

```go
x<<8 + y<<16
```

他の言語とは異なり、スペースの使用が意味するところが大きい。