- [円形開口でのフラウンフォーファー回折](#円形開口でのフラウンフォーファー回折)
- [ベッセル関数の定義](#ベッセル関数の定義)
- [母関数](#母関数)
  - [定義](#定義)
  - [フィボナッチ数列](#フィボナッチ数列)
- [ベッセル関数の導出](#ベッセル関数の導出)
  - [テイラー展開](#テイラー展開)
  - [ローラン展開](#ローラン展開)
  - [ベッセル関数](#ベッセル関数-1)

## 円形開口でのフラウンフォーファー回折

- 入力面での振幅分布 $u _ 1(\rho, \varphi)$
- 出力面での振幅分布 $u _ 2(r, \theta)$

で表されるとき**円形開口でのフラウンフォーファー回折**は

$$
u _ 2=\int _ {0}^{a} \rho d \rho \bigr(\int _ {0}^{2\pi} e^{-i\frac{kr}{z} \rho \cos{(\varphi-\theta)}} d \varphi \bigl)
$$

となります.今まで光学の勉強をしてきてこの後ろの積分は既知のものとして受け入れてきたが今回はこれについて調べます.

## ベッセル関数の定義

ベッセル関数は**母関数** $e^{\frac{x}{2}(t-\frac{1}{t})}$

を $t=0$ の周りで**ローラン展開**したときに

$$
e^{\frac{x}{2}(t-\frac{1}{t})} = \sum _ {n=-\infty}^{\infty} J _ n(x) t^n
$$

のように現れる係数 $J _ n(x)$ として定義されています.(他の定義の方法もありますが難しいです.)

[余談]

フリードリヒ・ヴァルヘルム・ベッセルはドイツの数学者,天文学者で貿易関連の会社に就職しました.それにともない惑星の軌道運動に関するケプラー方程式を解析的に解くためにベッセル関数が導入しました.天文学にも精通しており月にある大きなクレーターにベッセルと名前が付けられています.またベッセルは大学教育を受けていませんでした.

## 母関数

工学でのラプラス変換や物理学でのフーリエ変換は扱いにくい対象をひとまずラプラスやフーリエの世界で考えてそこで四則演算などの計算しやすい操作をした後,逆のラプラス,フーリエ変換をすることで解を求めていると解釈できます.もっと身近なところでは波をオイラーの公式により複素数表示にして計算を楽にし,最後に実部をとるということもこれに該当すると思います.母関数もこのようなもので,数列を母関数という世界で考えてなにかしらの操作をした後,もとの数列の世界に戻すものだと解釈できます.

### 定義

数列 ${a _ n} (= a _ 0, a _ 1, a _ 2 \cdots)$ に対して

$$
f(x) = a _ 0 + a _ 1x + a _ 2x^2 + \cdots = \sum _ {k=0}^{\infty} a _ k x^k
$$

としたときの $f(x)$ を**母関数**と言います.

例えば $1, 2, 4, 8, 16, \cdots$ という数列なら

$$
f(x) = 1 + 2x + 4x^2 + 8x^3 + \cdots
$$

ですがこれは初項 $1$ 公比 $2x$ の等比数列であるので

$$
f(x) = \frac{1}{1 - 2x}
$$

となります.

### フィボナッチ数列

上記で定義した母関数の有用性はいまいちつかめないので母関数を使うことで**フィボナッチ数列**の一般項を求められることを示します.

フィボナッチ数列は

$$
{F _ n} (= 1, 1, 2, 3, 5, 8, \cdots)
$$

のような数列でそれぞれの項が1個前と2個前の項を足したものになっています.つまり

$$
F _ {n+2} = F _ {n+1} + F _ n \quad (F _ 0 = F _ 1 = 1)
$$

となっています.簡単のため各項を $F _ n$ のままフィボナッチ数列を書くと母関数は

$$
f(x) = F _ 0+F _ 1x + F _ 2x^2 + F _ 3x^3 + \cdots \quad (3.1)
$$

となりますが $(3.1)$ に対して $x,x^2$ をそれぞれかけたものを考えると

$$
xf(x) = F _ 0x+F _ 1x^2 + F _ 2x^3 + F _ 3x^4 + \cdots \quad (3.2) \newline
x^2f(x) = F _ 0x^2+F _ 1x^3 + F _ 2x^4 + F _ 3x^5 + \cdots \quad (3.3)
$$

となります.これらに対して $(3.1)-(3.2)-(3.3)$ を考え $x$ の次数で並べると

$$
(1-x-x^2)f(x) = F _ 0+(F _ 1-F _ 0)x + (F _ 2-F _ 1-F _ 0)x^2 + (F _ 3-F _ 2-F _ 1)x^3 + \cdots
$$

となりますが

$$
F _ {n+2} = F _ {n+1} + F _ n \newline
F _ {n+2} - F _ {n+1} - F _ n = 0
$$

であるので

$$
(1-x-x^2)f(x) = 1
$$

のように定数項以外は消えます.つまり

$$
f(x) = \frac{1}{1-x-x^2}
$$

となります.これが先ほど言った母関数の世界での操作に対応しています.あとはこれをもとの数列の世界に戻せばよく

$$
\begin{aligned}
f(x) &= \frac{1}{(1-\alpha x)(1-\beta x)} \newline
&= \frac{\alpha}{\alpha-\beta}\frac{1}{1-\alpha x}+\frac{\beta}{\beta-\alpha}\frac{1}{1-\beta x}
\end{aligned}
$$

とおくと

$$
\alpha = \frac{1\pm \sqrt{5}}{2} \newline
\beta = \frac{1\mp \sqrt{5}}{2}
$$

であるので

$$
f(x) = \frac{1}{\sqrt{5}}\frac{1+\sqrt{5}}{2}\frac{1}{1-\frac{1+\sqrt{5}}{2}x}-\frac{1}{\sqrt{5}}\frac{1-\sqrt{5}}{2}\frac{1}{1-\frac{1-\sqrt{5}}{2}x}
$$

と母関数を表すことができます.これを和の形で表せば

$$
f(x)=\frac{1}{\sqrt{5}}\Bigl(\frac{1+\sqrt{5}}{2}+\frac{1+\sqrt{5}}{2}\frac{1+\sqrt{5}}{2}x+\frac{1+\sqrt{5}}{2}\frac{1+\sqrt{5}}{2}\frac{1+\sqrt{5}}{2}x^2+\cdots\Bigr) \newline
-\frac{1}{\sqrt{5}}\Bigl(\frac{1-\sqrt{5}}{2}+\frac{1-\sqrt{5}}{2}\frac{1-\sqrt{5}}{2}x+\frac{1-\sqrt{5}}{2}\frac{1-\sqrt{5}}{2}\frac{1-\sqrt{5}}{2}x^2+\cdots\Bigr)
$$

となるので母関数の定義よりフィボナッチ数列の一般項は

$$
F _ n=\frac{\Bigl(\frac{1+\sqrt{5}}{2}\Bigr)^{n+1}-\Bigl(\frac{1-\sqrt{5}}{2}\Bigr)^{n+1}}{\sqrt{5}}
$$

となります.このように母関数を通してフィボナッチ数列の一般項を求めることができました.

## ベッセル関数の導出

### テイラー展開

$f(x)$ を $x=a$ の周りでの**テイラー展開**すると

$$
f(x) = \sum _ {n=0}^{\infty} \frac{f(a)^{(n)}}{n!}(x-a)^n
$$

となりますが複素数の世界でも $a$ の周り(**※ただし微分可能な点**)のテイラー展開を考えたいです.コーシーの積分公式とグルサの公式というものから導出されるらしいですがここでは結果だけ書くと

$$
\begin{aligned}
f(z) &= \sum _ {\infty}^{n=0} \frac{1}{2\pi i} \oint _ {C}^{} \frac{f(w)}{(w-a)^{n+1}}dw(z-a)^n \quad (4.1) \newline
&= \sum _ {\infty}^{n=0} \frac{1}{n!}\frac{n!}{2\pi i} \oint _ {C}^{} \frac{f(w)}{(w-a)^{n+1}}dw(z-a)^n \quad (4.2)
\end{aligned}
$$

となります. $(4.2)$ の形にすると複素関数のテイラー展開も実関数のテイラー展開と似たように考えられます.つまり

$$
f(a)^{n}
$$

と

$$
\frac{n!}{2\pi i} \oint _ {C}^{} \frac{f(w)}{(w-a)^{n+1}}dw
$$

が対応しています.これは複素数 $z = x+1y$ を $0$ に近づけるときは $x,y$ の2個の自由度があるためにこのような違いがあると考えています.

### ローラン展開

次に $a$ が微分不可能な場合を考えます.これも詳細は理解していませんが

$$
f(z) = \sum _ {n=-\infty}^{\infty} \frac{1}{2\pi i} \oint _ {C}^{} \frac{f(w)}{(w-a)^{n+1}}dw(z-a)^n \quad (4.3)
$$

$(4.3)$ は $(4.2)$ と比べて和の範囲が負の無限大に広がっているのでこの展開式は先ほどの複素関数のテイラー展開の拡張版といえそうです.これを**ローラン展開**と言います.

### ベッセル関数

ベッセル関数は

$$
e^{\frac{x}{2}(t-\frac{1}{t})} = \sum _ {n=-\infty}^{\infty} J _ n(x) t^n
$$

と定義していたのでこれは $t=0$ の周りで $e^{\frac{x}{2}(t-\frac{1}{t})}$ をローラン展開できればベッセル関数が求まるということになります.

まず

$$
e^{\frac{x}{2}(t-\frac{1}{t})} = e^{\frac{xt}{2}}e^{-\frac{x}{2t}}
$$

と分けてそれぞれをマクローリン展開します.計算すると

$$
e^{\frac{xt}{2}} = \sum _ {k=0}^{\infty} \frac{1}{k!} \Bigl(\frac{xt}{2}\Bigr)^k
$$

と

$$
e^{-\frac{x}{2t}} = \sum _ {l=0}^{\infty} \frac{1}{l!} \Bigl(-\frac{x}{2t}\Bigr)^l
$$

になります.ひとまずそれぞれの関数をマクローリン展開したものの積が元の関数をマクローリン展開したものと等しいことを受け入れると

$$
\begin{aligned}
e^{\frac{x}{2}(t-\frac{1}{t})} &= \sum _ {k=0}^{\infty} \frac{1}{k!} \Bigl(\frac{xt}{2}\Bigr)^k \sum _ {l=0}^{\infty} \frac{1}{l!} \Bigl(-\frac{x}{2t}\Bigr)^l \newline
&= \sum _ {k=0}^{\infty}\sum _ {l=0}^{\infty} \frac{(-1)^l}{k!l!}t^{k-l}\Bigl(\frac{x}{2}\Bigr)^{k+l}
\end{aligned}
$$

となります. $n=k-l$ とおくと

$$
e^{\frac{x}{2}(t-\frac{1}{t})} = \sum _ {n=-\infty}^{\infty}\sum _ {l=0}^{\infty} \frac{(-1)^l}{(n+l)!l!}\Bigl(\frac{x}{2}\Bigr)^{n+2l}t^n
$$

ときれいな形になります.つまり

$$
J _ n(x) = \sum _ {l=0}^{\infty} \frac{(-1)^l}{(n+l)!l!}\Bigl(\frac{x}{2}\Bigr)^{n+2l}
$$

となります.今はフラウンフォーファー回折にでてくる積分の形で表したいので $t=e^{i\varphi}$ とすると左辺は

$$
\begin{aligned}
e^{\frac{x}{2}(e^{i\varphi}-e^{-i\varphi})} &= e^{ix\sin{\varphi}} \newline
&= \cos{(x\sin{\varphi})}+i\sin{(x\sin{\varphi})} \quad (4.4)\newline
\end{aligned}
$$

となります.ベッセル関数も同様に考えると

$$
\begin{aligned}
\sum _ {n=-\infty}^{\infty} J _ n{x}e^{in\varphi}
&=
J _ 0(x)+J _ 1(x)e^{i\varphi}+J _ 1e^{-i\varphi}+\cdots \newline
&=
J _ 0(x)+2(J _ 2(x)\cos{2\varphi} + J _ 4(x)\cos{4\varphi}+\cdots) \newline
&\quad +2i(J _ 1(x)\sin{\varphi}+J _ 3(x)\sin{3\varphi}+\cdots) \quad (4.5)
\end{aligned}
$$

となります.ただし

$$
J _ {-n}(x)e^{im\varphi} = (-1)^nJ _ n(x)
$$

という性質を使いました.次に $(4.4), (4.5)$ の実部と虚部を比べます.

実部は

$$
\cos{(x\sin{\varphi})} = J _ 0(x)+2\sum _ {n=1}^{\infty}J _ {2n}(x)\cos{(2n\varphi)} \quad (4.6)
$$

虚部は

$$
\sin{(x\sin{\varphi})} = 2 \sum _ {n=1}^{\infty}J _ {2n-1}(x)\sin{((2n-1)\varphi)} \quad (4.7)
$$

となります.ここで $(4.6)$ の両辺に $\frac{\cos{(n\varphi)}}{2\pi}$ をかけて $0 \rightarrow 2\pi$ で積分をとると,三角関数の直交性より

$$
\frac{1}{2\pi} \int _ {0}^{2\pi} \cos{(x\sin{\varphi})}\cos{(n\varphi)} = J _ n(x)
$$

を得ます.ただし $x$ が偶数の時のみ.(奇数の場合は $0$ .)

同様に虚数部に対して今度は $\frac{\sin{(n\varphi)}}{2\pi}$ をかけて $0 \rightarrow 2\pi$ で積分すると

$$
\frac{1}{2\pi} \int _ {0}^{2\pi} \sin{(x\sin{\varphi})}\sin{(n\varphi)} = J _ n(x)
$$

を得ます.ただし $x$ が奇数の時のみ.(偶数の場合は $0$ .)

まとめると

$$
\begin{aligned}
J _ n(x) &= \frac{1}{2\pi} \int _ {0}^{2\pi} \bigl(cos{(x\sin{\varphi})}\cos{(n\varphi)}+\sin{(x\sin{\varphi})}\sin{(n\varphi)}\bigr)d\varphi \newline
&= \frac{1}{2\pi} \int _ {0}^{2\pi} \cos{(n\varphi-x\sin{\varphi})}d\varphi
\end{aligned}
$$

となります.ここで天下り的ですが $n=0$ のとき,つまり $J _ 0(x)$

$$
J _ 0(x) = \frac{1}{2\pi} \int _ {0}^{2\pi} \sin{(x\sin{\varphi})}d\varphi = 0
$$

であることを用いて

$$
J _ 0(x) = \frac{1}{2\pi} \int _ {0}^{2\pi} \Bigl(\cos{(x\sin{\varphi})}-i\sin{(x\sin{\varphi})}\Bigr)d\varphi
$$

と表します.( $0$ であるので引いたとしても結果に影響を与えないです.)これを計算すると

$$
\begin{aligned}
J _ 0(x) &= \frac{1}{2\pi} \int _ {0}^{2\pi} \Bigl(\cos{(x\sin{\varphi})}-i\sin{(x\sin{\varphi})}\Bigr)d\varphi \newline
&=\frac{1}{2\pi} \int _ {0}^{2\pi} e^{-i(x\sin{\varphi})}d\varphi \newline
&= \frac{1}{2\pi} \int _ {-\frac{\pi}{2}}^{\frac{3\pi}{2}} e^{-i(x\sin{(\varphi+\frac{\pi}{2})})}d\varphi \newline
\therefore J _ 0(x)&= \frac{1}{2\pi} \int _ {0}^{2\pi}e^{-i(x\cos{\varphi})}d\varphi
\end{aligned}
$$

とフラウンフォーファー回折に出てくる積分が得られました.実際に円形開口での回折の計算をすると

$$
\begin{aligned}
u _ 2 &= \int _ {0}^{a} \rho d \rho \bigr(\int _ {0}^{2\pi} e^{-i\frac{kr}{z}\rho \cos{(\varphi-\theta)}} d \varphi \bigl) \newline
&= \int _ {0}^{a} \rho d \rho 2\pi J _ 0\bigl(\frac{kr\rho}{z}\bigr) \newline
&= \frac{2\pi}{\frac{kr}{z}}\int _ {0}^{a} \frac{kr\rho}{z} J _ 0\Bigl(\frac{kr\rho}{z}\Bigr)d\rho
\end{aligned} 
$$

ここでベッセル関数の漸化式

$$
\frac{d}{dx}\bigl(x^{n+1}J _ {n+1}(x)\bigr) = x^{n+1}J _ n(x)
$$

を用いれば $n=0, x=\frac{kr\rho}{z}$ として

$$
\begin{aligned}
\frac{d}{d\bigl(\frac{kr\rho}{z}\bigr)}\bigl(\frac{kr\rho}{z}J _ {1}\Bigl(\frac{kr\rho}{z}\Bigr)\bigr) &= \frac{kr\rho}{z}J _ 0\Bigl(\frac{kr\rho}{z}\Bigr) \newline
\leftrightarrow \frac{kr\rho}{z}J _ 1\Bigl(\frac{kr\rho}{z}\Bigr) &= \int _ {0}^{\frac{kr\rho}{z}} \frac{kr\rho'}{z}J _ 0(\rho') \quad \Bigl(\frac{kr\rho}{z} = \rho' \Bigr)
\end{aligned}
$$

となります.最終的に出力面の振幅分布は

$$
\begin{aligned}
u _ 2 &= \frac{2\pi}{\frac{kr}{z}}\frac{1}{\frac{kr}{z}} \int _ {0}^{\frac{kra}{z}} \frac{kr\rho'}{z}J _ 0(\rho')d\rho' \newline
&= \frac{2\pi}{\frac{kr}{z}}\frac{1}{\frac{kr}{z}}\frac{kr}{z}aJ _ 1\Bigl(\frac{kra}{z}\Bigr) \newline
\therefore u _ 2 &= 2\pi a^2 \frac{J _ 1\bigl(\frac{kra}{z}\bigr)}{\frac{kra}{z}} \newline
\end{aligned}
$$

となる.
