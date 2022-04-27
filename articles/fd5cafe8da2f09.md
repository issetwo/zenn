---
title: "Swift : コレクション（集合）を使う"
emoji: "🦔"
type: "tech"
topics: ["ios", "swift"]
published: true
---

# はじめに
以下の人を対象に書いています。
- Swiftをあまり触ったことのない方
- Setの使い方を知りたい方

# 環境
この記事の情報は以下のバージョンで動作確認しています。
- Xcode 12.3 (12C33)
- Swift 5.3.2

# 集合とは（Set）
**順序を管理しないコレクションで、同じ型をユニークな値を格納**します。
順序を意識しないユニークな値をコレクションで管理したい場合は、配列ではなく集合の方が適しています。

**値を登録するには 型がHashableプロトコルに準拠**している必要があります。Hashableプロトコルは整数のハッシュ値を提供し、一意なユニークな値として扱いたい場合に使用するプロトコルです。標準ライブラリの多くの型はデフォルトでHashableに準拠していますが、独自のクラスを使用する場合は準拠するようにしてください。

# 生成（空）
空の集合を生成する場合の実装例です。
変数の型を指定しなくても生成が可能です。
```swift
// 例１
var persons: Set<String> = Set<String>()

// 例２
var persons2: Set = Set<String>()

// 例３
var persons3 = Set<String>()
```

# 生成（初期値あり）
初期値を入れた集合を生成する場合の実装例です。
こちらも変数の型を指定しなくても生成が可能です。
```swift
// 例１
var persons4: Set<String> = ["Yamada", "Tanaka", "Okabe"] // 型指定あり

// 例２
var persons5: Set = ["Yamada", "Tanaka", "Okabe"] // 型指定なし
```

# 値を追加
集合に値を追加する場合の実装例です。
既に集合に追加してある値は重複して追加できません。
```swift
// "Suzuki"を追加
persons.insert("Suzuki")
```

# 値を削除
集合から指定した値を削除する場合の実装例です。
```swift
// "Suzuki"を削除
persons.remove("Suzuki")
```

# 繰り返し処理
繰り返して処理を行う場合の実装例です。
```swift
// 集合を生成
var persons: Set<String> = ["Yamada", "Tanaka", "Okabe"]

// 繰り返し処理
for person: String in persons {
   // デバッグ出力
   print(person)
}
```

# 値の存在確認
集合に追加した値が存在するかチェックする実装例です。
```swift
// 集合を生成
var persons: Set<String> = ["Yamada", "Tanaka", "Okabe"]

// "Kai"が存在するか取得
let isExist: Bool = persons.contains("Kai")

// デバッグ出力
print(isExist)
```

# 値の個数取得
集合に追加した値がいくつあるのか個数を取得する実装例です。
```swift
// 集合を生成
var persons: Set<String> = ["Yamada", "Tanaka", "Okabe"]

// 値の個数取得
let count: Int = persons.count

// デバッグ出力
print(count)
```

# 空かどうか取得
集合が空かどうか取得する実装例です。
```swift
// 集合を生成
var persons: Set<String> = ["Yamada", "Tanaka", "Okabe"]

// 空かどうか取得
let isEmpty: Bool = persons.isEmpty

// デバッグ出力
print(isEmpty)
```

# 最後に
今回はよく使う集合の使い方について解説しました。
昨日追加により新しい機能が追加された場合は、本記事に追記したいと思います。