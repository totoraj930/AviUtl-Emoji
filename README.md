
# AviUtl-Emoji

AviUtlのテキストオブジェクトで絵文字を使えるようにするアニメーションスクリプトです。

## 動作確認環境

- AviUtl 1.10
- 拡張編集 0.92

### 推奨設定

- 最大画像サイズ: 大きめ
- キャッシュサイズ: 多め

### 共存確認

- [patch.aul](https://github.com/ePi5131/patch.aul) r28


## 使い方

0. 別途[rikky_module](https://hazumurhythm.com/wev/amazon/?script=rikkymodulea2Z)を導入している必要がります。
1. テキストオブジェクトのフィルタの一番上にアニメーション効果を配置して「絵文字.anm」を読み込みます
2. 絵文字を `{😀}` のように中括弧で囲みます。
    - 1文字ずつ囲む必要があります。
3. `{😀,1.1}` のようにコンマで区切ってサイズを指定することも出来ます。
4. `{"image.png"}` のようにパスを入力すると任意の画像も表示できます。
    - 画像は「絵文字.anm」と同一、またはその配下のフォルダにある必要があります。

### 例

```
AviUtlで{🤔}
{🤩,1.2}絵文字?!

{"image.png",1.4}画像も表示できる
```


## 仕様など

| 機能 | 個別オブジェクト | 単一 |
| ---- | ---- | ---- |
|縦書き|⚠|❌|
|文字寄せ|✅|✅|
|字間|✅|❌|
|行間|✅|✅|
|表示速度|✅|❌|
|制御文字|⚠|⚠|

## 既知のバグ(仕様)

### 表示がズレる

ある程度はズレないようにしたつもりですが、どうしても少しズレます。

### 縦書きがズレる

仕様です。

### 表示速度のズレ

1文字分遅れます。仕様です。

そもそも単一オブジェクトは対応していません。

### 制御文字が効かない or バグる

個別オブジェクト内で `<s50>` などは使わないようにしてください。

また処理の関係で `<#ff0000>` や `<p+50,+50>` なども動作が不安定です。

### 文字サイズが大きいとズレる

ズレの調整方法の関係でテキストオブジェクトが「最大画像サイズ」を越える場合ズレます。

最悪の場合表示されないです。

### レイヤーを重ねると絵文字が表示されない

「画像データのキャッシュ数」によっては表示されなくなります。

## License

### Twitter Emoji (Twemoji)

<https://github.com/twitter/twemoji/>

Copyright 2019 Twitter, Inc and other contributors

Code licensed under the MIT License: <http://opensource.org/licenses/MIT>

Graphics licensed under CC-BY 4.0: <https://creativecommons.org/licenses/by/4.0/>

### ソースコード

Copyright &copy; 2022 Reona Oshima (totoraj)  
This work is released under the MIT License.  
<http://opensource.org/licenses/mit-license.php>