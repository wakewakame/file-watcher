# file-watcher

ファイルの変更を監視するサンプル。
ファイルが連続で変更された場合は最後の変更のみを通知する。

# 使い方

```sh
cargo run <監視するファイルへのパス>
```

# TODO

最終的には以下のようなインターフェイスにしたい。

```
let code = file::open("main.js").unwrap();  // パス文字列からファイルを開く (存在しなければ作成する)
let code = file::dialog().unwrap();  // ダイアログを開いてファイルを開く

let text = code.read();  // ファイルを読み込む
code.write(text);  // ファイルに書き込む
code.open_dir();  // std::process::Command::new() でファイルの存在するフォルダを開く
code.watch(dur, callback);  // ファイルの変更を監視する
```

