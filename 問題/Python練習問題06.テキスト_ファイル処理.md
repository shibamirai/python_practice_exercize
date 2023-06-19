# Python練習問題06. テキスト/ファイル処理

## 設問1

以下のCSV形式のテキストデータから、教科ごとの生徒の平均点を算出してください。

```python
text = '''名前, 国語, 数学, 英語
鈴木, 80, 70, 75
佐藤, 60, 80, 90
山田, 92, 60, 90
伊藤, 70, 95, 82'''
```

## 設問2

テキストファイルをコピーするプログラムfilecopy.pyを作ってください。original.txtというテキストファイルがある場合、```python filecopy.py original.txt destination.txt```のように使用して、original.txtと同じ内容のdestination.txtファイルを作成します。

## 設問3

演習2で作ったプログラムを改造し、```python filecopy.py -n original.txt destination.txt```というようにように、実行時にオプション引数```-n```をつけるとコピー時に行番号も書き出すようにしてください。このとき行番号は最後の行の桁数にあうように0詰めしてください（全部で20行なら01～20、1000行なら0001～1000）。たとえば以下のようになります。

original.txt（aからzまで１行に１文字ずつ書かれている場合)

```text
a
b
c
（中略）
x
y
z
```

destination.txt

```text
01 a
02 b
03 c
（中略）
24 x
25 y
26 z
```
