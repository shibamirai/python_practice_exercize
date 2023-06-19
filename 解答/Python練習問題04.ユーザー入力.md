# Python練習問題04. ユーザー入力

## 設問1

コマンドライン引数で与えた2つの整数の和を表示するプログラムadd.pyを作ってください。引数が2つ以外の場合はエラー表示をして終了してください。

### 解答(設問1)

add.py

```python
import sys

args = sys.argv
if len(args) != 3:
    sys.exit("引数は2つ指定してください")

print(int(args[1]) + int(args[2]))

```

### 実行例

```sh
> python add.py 3 5
8
```

---

## 設問2

標準入力(コンソール)から名前を入力すると"こんにちは ***入力した名前*** さん"と表示するプログラムhello.pyを書いてください。名前は繰り返し入力でき、exitと入力されると終了するようにしてください。

```python
> python hello.py
Tom
こんにちは Tom さん
鈴木
こんにちは 鈴木 さん
exit
>
```

### 解答(設問2)

hello.py

```python
while True:
    name = input()
    if name == 'exit':
        break
    print('こんにちは ' + name + ' さん')

```
