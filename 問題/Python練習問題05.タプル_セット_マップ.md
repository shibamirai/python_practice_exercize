# Python練習問題05. タプル/組(tuple)、セット/集合(set)、マップ/辞書(map)

## 設問1

AさんとBさんのスキルをそれぞれskill_a, skill_bとして下記のように表しました。

~~~python
skill_a = {'Java', 'PHP', 'C', 'Python'}
skill_b = {'PHP', 'JavaScript', 'Java', 'Python'}
~~~

1. AさんとBさんに共通するスキルをskill_aとskill_bを使って表してください。(ヒント：積集合)
1. 同様にBさんしかもたないスキルを表してください。

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

---

## 設問3

以下のように、引数で与えた英語の文章中に出現する単語（空白文字で区切られたひとかたまりの文字列を単語としてください。句読点も含みます）およびその出現数を表示する関数word_countを書いてください。

~~~python
>>> word_count('so many men, so many minds.')
{'so': 2, 'many': 2, 'men,': 1, 'minds.': 1}
~~~

---

## 設問4

演習3の関数を改造し、引数の英語の文章から最頻出単語とその回数を返す関数most_frequent_word_countを作成してください。最頻出単語が複数ある場合はそのうちのどれか１つで構いません。

~~~python
>>> most_frequent_word_count('so many men, so many minds.')
('so', 2)
~~~
