# 2019年度 第四回 プログラミング講習会
## 今回の目標
1. for文が使えるようになる
2. while文が使えるようになる
3. 代入演算子が使えるようになる
## おまけ目標
- インクリメントとデクリメント  
- ほか言語のfor文について
## 付録
今までの構文まとめ

---
# 1. for文が使えるようになる
これもまずはコードを見てみましょう。(Githubでは41.pyです)
```py
print("かぞえます！")
for i in range(10):
   print(str(i) + "回目！")
print("おわり！")
```
これは、10回ループします。実際に書いて実行してみましょう。
> かぞえます！  
> 0回目！  
> 1回目！  
> 2回目！  
> 3回目！  
> 4回目！  
> 5回目！  
> 6回目！  
> 7回目！  
> 8回目！  
> 9回目！  
> おわり！  

およよ？0, 1, 2....という数え方ですね。  
実は、プログラムの世界では0から数えます。日本の年齢の数え方と一緒ですね！  
~~(だから彼女いない歴=年齢をすると0歳のとき彼女いた事になるんやで)~~  
Pythonのfor文は`for 変数名 in range(回数)`とすることで、指定した回数だけ繰り返し、iの中に何回ループしたかを記録してくれます！(もちろん0から数えることに注意)  
  
pythonのfor文はこれだけですごい簡単ですが、おまけ目標の「他の言語のfor文」についてなれることをおすすめします。単位的に。  

では試しに、1~nまでの数字の和(三角数といいます) を求めるプログラムを作ってみましょう。  
ここで、nはプログラム実行時に入力するものです。`n = int(input(">> "))`的なのを使います。  

ハイじゃ回答。(Githubでは42.pyです)
```py
n = int(input(">> "))

sum = 0
for i in range(n):
   sum = sum + (i+1)

print("1 から " + str(n) + " までの和は " + str(sum))
```
これを自力でできた人は、プログラミングの筋がかなりいいです。(現段階では難しめの問題だとおもいます)  
> ### 解説
> ```py
> n = int (input(">> "))
> ```
> 念のためもう一度解説すると、`input(">> ")`で「プログラム実行したときに文字列を読み取る」ものです。  
> しかし、このままでは「文字列(String)」として扱われているので、数字(Int)に変換します。  
> それが`int()`という形で書くキャストと呼ばれるものです。なので合わせて`int(input(">> "))`になります。  
> そしてその数字を `n` に代入しています。  
> つまり、入力した数字を `n` に代入しているということです。
> ```py
>  sum = 0
> ```
> `sum` という名前の変数を作って 0 を代入しています。数字なので 整数(int)型です。
> ```py
> for i in range(n):
>    sum = sum + (i+1)
> ```
> n回のループ処理を行うfor文です。  
> iには0, 1, 2.....というふうに数えられることに注意がいります。  
> `sum = sum + (i+1)` という式で、今`sum`に代入している値に加算します。  
> > 例えば、以下のコードを実行するとします(Githubでは43.pyです)
> > ```py
> > a = 3
> > print(a)
> > a = a + 2
> > print(a)
> > ```
> > すると
> > >3  
> > >5
> >
> > という出力が得られます。
>
> ただし、iは0, 1, 2.....というふうに数えるのに対し、  
> sumには1, 2, 3...という数字をどんどん足していきたいので
> `i+1`として足し算しています。  
> ```py
> print("1 から " + str(n) + " までの和は " + str(sum))
> ```
> 出力しているだけです。ただし、`n`や`sum`は整数(int)型なので、文字列(String)型に変換(=キャスト)してあげる必要があります。それが `str()` です。

# 2. while文を使えるようになる
こちらは簡単です。  
実際にコードを見てみましょう。(Githubでは43.pyです)  
```py
i = 0
while i<10:
   print(str(i) + "回目！")
   i = i+1
```
これを実行すると以下のようになります
> 0回目！  
> 1回目！  
> 2回目！  
> 3回目！  
> 4回目！  
> 5回目！  
> 6回目！  
> 7回目！  
> 8回目！  
> 9回目！  

whileのあとの条件式が True になっている(成立している)間じゅう繰り返す。という文です。  
for文では「何回だけ繰り返したい！」というときに使い、それ以外ではwhile文などとしてもいいでしょう  
また、for文は次回やる list と呼ばれるものとの相性が抜群に良いです  

では、上のプログラムを改造して「お皿が◯枚...」と1~9枚目まで出力し、最後に「1まいたりなぁ〜い」と出力するプログラムを作ってみましょう。  (for文でも作ってみましょう)  
1枚目から始めていることに注意が必要です  

早速答え。
while文の方です。(Githubでは44.pyです)
```py
i = 1
while i<10:
   print("お皿が" + str(i) + "枚....")
print("1まいたりなぁ〜い")
```
  
for文を用いた方の答えです。(Githubでは45.pyです。)
```py
for i in range(9):
   print("お皿が" + str(i+1) + "枚....")
print("1まいたりなぁ〜い")
```

Pythonの気持ちになって見てみると  
どちらも、if文と同様に「インデントをしっかりする」ことによってwhile / for文の中身かどうかを見分けています。  
何度も言いますが **インデントはしっかりしましょう**  

# 3. 代入演算子が使えるようになる
ぶっちゃけて言うと、「ある数に追加で足し算したい！」や「ある変数からこれ分だけ引きたい！」などのときに使います。百聞は一見に如かず。まず見てみましょう。  
```py
a = 10
a = a + 4
print(a)

#上と意味同じ
b = 10
b += 4
print(a)
```
`+=`を使うことで、少し短くなりました。これ滅茶便利なので覚えましょう。多分嫌でも覚えることになる。
足し算以外にも、引き算、かけ算、割り算もつかえます。  

| 代入演算子 | 同じ意味の文 | 意味 |
|:--:|:--:|:--:|
| a+=n | a = a+n | aにnを足す |
| a-=n | a = a-n | aからnを引く |
| a*=n | a = a*n | aにnをかける |
| a/=n | a = a/n | aをnで割る |

まあぶっちゃけて言うと`a 演算子= n`って書けばだいたい通用します(a<<=1みたいに。)  
Pythonではおまけ項目の「インクリメント」と「デクリメント」が存在しないため、これを多用することがおおいです。  

---
# おまけ：インクリメント と デクリメント
**※Pythonにはインクリメントとデクリメントがありません**
## インクリメント
`a+=1;` としたい場合には `a++;`または`++a;`と省略できます。
## デクリメント  
`a-=1`としたい場合には`a--;`または`--a;`と省略できます。

## ++a; と a++;の違い
C言語の以下の文の実行例で見てみましょう。まずは後置と呼ばれる方。
```c
#include <stdio.h>
void main(){
   int a = 0;
   while(a<10){
      printf("%d\n", a++); //aの値を出力する文
   }
}
```
出力結果は
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9  

一方で前置と呼ばれる方を見ていきましょう。
```c
#include <stdio.h>
void main(){
   int a = 0;
   while(a<10){
      printf("%d\n", ++a); //aの値を出力する文
   }
}
```
出力結果は
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9  
> 10  

となります。つまり、後置は「実行してから`a+=1;`をする」  
前置は「`a+=1;`をしてから実行する」という違いがあります。  
実行してから足し算するか、足し算してから実行するかの違いとなります。  
まあ、ぶっちゃけて言うとa++;さえ使えれば組み込みとかでない限り困ることはないでしょう。ちょいマニアックな内容でした。  

# おまけ：ほか言語のfor文について
百聞は一見に如かず。コード見てみましょう。 ~~(このことわざ多用しますねココ)~~  
全部同じ出力結果です。  
### Python
```py
for i in range(10):
   print(i)
```
### C
```c
#include <stdio.h>
void main(){
   int i;
   for(i=0; i<10; i++){
      printf("%d", i);
   }
}
```
### Java
```java
public class ForStatement{
   public static void main(String[] args){
     for(int i=0; i<10; i++){
        System.out.println(i);
     }
   }
}
```
### C#
```cs
using System;
namespace ForStatement
{
    class For 
    {
        static void Main() 
        {
            for(int i=0; i<10; i++){
               Concole.WriteLine(i);
            }
        }
    }
}
```
 出力
> 0  
> 1  
> 2  
> 3  
> 4  
> 5  
> 6  
> 7  
> 8  
> 9  

通常扱うような言語でのfor文は `for(初期化; 条件; 更新){}`という形になっているということが知っていただければそれで大丈夫です。  

以上、本日もお疲れちゃんでした。
次回はlistを扱うので、for文とかでてくるよん

# 付録：今までの構文まとめ
## if文
```py
if 条件式:
   文
elif 条件式:
   文
else:
   文
```
## for文
```py
for i in range(回数):
   文
```
## while文
```py
while 条件式:
   文
```