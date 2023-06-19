# Python練習問題05. タプル/組(tuple)、セット/集合(set)、マップ/辞書(map)

## 設問1

AさんとBさんのスキルをそれぞれskill_a, skill_bとして下記のように表しました。

~~~python
skill_a = {'Java', 'PHP', 'C', 'Python'}
skill_b = {'PHP', 'JavaScript', 'Java', 'Python'}
~~~

1. AさんとBさんに共通するスキルをskill_aとskill_bを使って表してください。(ヒント：積集合)
1. 同様にBさんしかもたないスキルを表してください。

### 解答(設問1)

1. AさんとBさんに共通するスキルをskill_aとskill_bを使って表してください。(ヒント：積集合)

    ~~~python
    >>> skill_a = {'Java', 'PHP', 'C', 'Python'}
    >>> skill_b = {'PHP', 'JavaScript', 'Java', 'Python'}
    >>> skill_a & skill_b
    {'Java', 'Python', 'PHP'}
    ~~~

1. 同様にBさんしかもたないスキルを表してください。

    ~~~python
    >>> skill_b - skill_a
    {'JavaScript'}
    ~~~

---

## 設問2

簡易的な電話帳を作成してください。実行するとコンソール入力待ちになり、"set 名前 電話番号"と入力して登録、"get 名前"とするとその名前とセットで登録された電話番号を表示します。登録されていない名前が入力された場合は"登録がありません"と出力し、処理を継続させてください。"exit"と入力するとプログラムを終了します。以下のようなイメージです。

~~~python
set Tom 090-xxxx-xxxx
set John 080-yyyy-yyyy
get Tom
090-xxxx-xxxx
get John
080-yyyy-yyyy
get Mike
登録がありません
exit
>>> 
~~~

### 解答(設問2)

~~~python
>>> tel_dict = dict()
>>> while True:
...     words = input().split()
...     if words[0] == 'set' and len(words) == 3:
...         tel_dict[words[1]] = words[2]
...     elif words[0] == 'get' and len(words) == 2:
...         if words[1] in tel_dict:
...             print(tel_dict[words[1]])
...         else:
...             print('登録がありません')
...     elif words[0] == 'exit':
...         break
...     else:
...         print('不正な入力です')
... 
set Tom 090-xxxx-xxxx
set John 080-yyyy-yyyy
get Tom
090-xxxx-xxxx
get John
080-yyyy-yyyy
get Mike
登録がありません
exit
>>> 
~~~

---

## 設問3

以下のように、引数で与えた英語の文章中に出現する単語（空白文字で区切られたひとかたまりの文字列を単語としてください。句読点も含みます）およびその出現数を表示する関数word_countを書いてください。

~~~python
>>> word_count('so many men, so many minds.')
{'so': 2, 'many': 2, 'men,': 1, 'minds.': 1}
~~~

### 解答(設問3)

~~~python
def word_count(text):
    words = text.split()
    wc_dict = {}
    for word in words:
        if word not in wc_dict: 
            wc_dict[word] = 1
        else:
            wc_dict[word] += 1
    print(wc_dict)

~~~

---

## 設問4

演習3の関数を改造し、引数の英語の文章から最頻出単語とその回数を返す関数most_frequent_word_countを作成してください。最頻出単語が複数ある場合はそのうちのどれか１つで構いません。

~~~python
>>> most_frequent_word_count('so many men, so many minds.')
('so', 2)
~~~

### 解答(設問4)

~~~python
def most_frequent_word_count(text):   
    words = text.split()
    wc_dict = {}
    for word in words: 
        if word not in wc_dict:
            wc_dict[word] = 1
        else:
            wc_dict[word] += 1
    most_frequent_word = words[0]
    for word in wc_dict:
        if wc_dict[word] > wc_dict[most_frequent_word]: 
            most_frequent_word = word 
    return (most_frequent_word, wc_dict[most_frequent_word])

~~~
