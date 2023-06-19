# Python練習問題08. PythonからOSを操作する

## 設問1

カレントディレクトリの配下に存在する、拡張子が".py"のファイルをすべて絶対パスで表示してください。

### 解答(設問1)

~~~python
import os

for cur, dirs, files in os.walk("."):
    for file in files:
        if file.endswith(".py"):
            print(os.path.abspath(file))

~~~

---

## 設問2

各OSには、カレントディレクトリ直下に存在するファイルとディレクトリの一覧を表示するシェルコマンド（Windowsのコマンドプロンプトでは"dir"、Mac/Linuxのシェルでは"ls -l"）が存在します。このシェルコマンドをPythonから実行し、その出力からディレクトリ名のみを抽出して表示するプログラムを作ってください。

### 解答(設問2)

#### Windowsの場合

~~~python
import re
import subprocess

# シェルコマンド
cmd = ["dir"]

# コマンドの出力を文字列で取得する場合は、オプションでcapture_output=True, text=Trueを指定する
# Windowsで、ファイルの実行ではなくdir等のシェルコマンドを実行する場合はshell=Trueを指定する
result = subprocess.run(cmd, capture_output=True, text=True, shell=True)

# 出力を行ごとに分割する
lines = result.stdout.splitlines()

# 年月日から始まる行だけを対象とするために、正規表現を利用する
p = re.compile("\d{4}/\d{2}/\d{2}")
for line in lines:
    # 年月日から始まる行の場合
    if p.match(line):
        words = line.split()
        # <DIR>がある行がディレクトリを示す
        if (words[2] == '<DIR>'):
            # ディレクトリ名に空白があると複数単語に分かれるので、それらを空白で連結しなおして出力する
            print(' '.join(words[3:]))
~~~

#### Mac/Linuxの場合

~~~python
import subprocess

# シェルコマンド
cmd = ["ls" "-l"]

# コマンドの出力を文字列で取得する場合は、オプションでcapture_output=True, text=Trueを指定する
result = subprocess.run(cmd, capture_output=True, text=True)

# 出力を行ごとに分割する
lines = result.stdout.splitlines()

for line in lines:
    # 'd'から始まる行が対象
    if line[0] == 'd':
        words = line.split()
        # ディレクトリ名に空白があると複数単語に分かれるので、それらを空白で連結しなおして出力する
        print(' '.join(words[8:]))
~~~

---
