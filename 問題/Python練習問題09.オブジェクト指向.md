# Python練習問題09. オブジェクト指向

## 設問1

以下の条件でクラスを作成してください。

- クラス名 BodySize
- 名前、身長、体重を表すインスタンス変数 name, height, weight
- 名前、身長、体重を引数にもつコンストラクタ

## 設問2

演習1で作成したBodySizeクラスを使って以下のように複数のインスタンスを用意します。ここから一番身長が高い人および一番体重が軽い人の名前を表示するプログラムを書いてください。

```python
hanamichi = BodySize('sakuragi', 189, 83)
kaede = BodySize('rukawa', 187, 75)
takenori = BodySize('akagi', 197, 93)
ryota = BodySize('miyagi', 168, 59)
hisashi = BodySize('mitsui', 184, 70)
```

## 設問3

先のBodySizeクラスにBMIと適正体重をタプルで返すメソッドbmi()を追加してください。BMIと適正体重は下記の計算式で求められます。それぞれ小数点第一位まで求めてください。

- BMI = 体重kg ÷ (身長m)^2
- 適正体重 = (身長m)^2 × 22

## 設問4

以下のように長方形を表すRectangleクラスを用意します。このクラスのコンストラクタでは長方形の幅と高さの２つの引数を受け取り、メソッドarea()でその面積を返します。このクラスを継承して正方形を表すクラスSquareを作成し、引数１つのコンストラクタで一辺の長さだけを受け取るようにしてください。

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

```

```python
>>> rectangle = Rectangle(3, 5)
>>> rectangle.area()
15
>>> 
```

## 設問5

組込み型のlistクラスを継承し、文字列(str)型だけを格納できるクラスStringListを作成してください。
以下のように使用します。

```python
>>> sl = StringList()
>>> sl.append('a')
>>> sl.append(1)    # 数値なので受け取らない
>>> sl.append('xxx')
>>> print(sl)
['a', 'xxx']
```
