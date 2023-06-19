# Python練習問題08. PythonからOSを操作する

## 設問1

カレントディレクトリの配下に存在する、拡張子が".py"のファイルをすべて絶対パスで表示してください。

## 設問2

各OSには、カレントディレクトリ直下に存在するファイルとディレクトリの一覧を表示するシェルコマンド（Windowsのコマンドプロンプトでは"dir"、Mac/Linuxのシェルでは"ls -l"）が存在します。このシェルコマンドをPythonから実行し、その出力からディレクトリ名のみを抽出して表示するプログラムを作ってください。

ヒント:OSのコマンドを実行するにはsubprocessモジュールを使用します。

### Windows(コマンドプロンプト)の```dir```コマンドの出力例

~~~cmd
C:\User\user\Desktop> dir
 ドライブ C のボリューム ラベルは OS です
 ボリューム シリアル番号は D2E6-15A9 です

 C:\Users\user\Desktop のディレクトリ

2022/12/21  10:01    <DIR>          .
2022/12/14  17:02    <DIR>          ..
2022/12/21  11:10               132 test.py
2022/12/14  11:13    <DIR>          testdir1
2022/12/14  11:15    <DIR>          testdir2
2022/12/14  11:15                 0 testfile1
2022/12/14  11:15                 0 testfile2
               4 個のファイル               6,033 バイト
               3 個のディレクトリ  29,918,003,200 バイトの空き領域

C:\User\user\Desktop> 
~~~

真ん中に\<DIR>とある行がディレクトリを表しているので、ここでプログラムを実行した場合の出力は、

~~~cmd
.
..
testdir1
testdir2
~~~

となります。

### Mac/Linuxの```ls -l```コマンドの出力例

~~~cmd
[root@localhost ~]# ls -l
total 3372
-rw-------.  1 root root    1475 Dec 22  2014 anaconda-ks.cfg
drwxrwxrwx. 18  500  500    4096 Dec 23  2014 click-2.0.1
-rw-r--r--.  1 root root 3423136 Sep 25  2011 click-2.0.1.tar.gz
-rw-r--r--.  1 root root     919 Sep  2 12:58 ping.py
-rw-r--r--.  1 root root     393 Sep  2 09:38 setip.py
-rw-r--r--.  1 root root     477 Sep  1 17:42 test.py
drwxr-xr-x.  2 root root    4096 Sep  2 13:12 testdir1
drwxr-xr-x.  2 root root    4096 Sep  2 13:12 testdir2
-rw-r--r--.  1 root root       0 Sep  2 13:12 testfile1
-rw-r--r--.  1 root root       0 Sep  2 13:12 testfile2
[root@localhost ~]# 
~~~

こちらも各行の先頭が'd'になっているものがディレクトリを表しているので、ここでプログラムを実行した場合の出力は、

~~~cmd
click-2.0.1
testdir1
testdir2
~~~

となります。
