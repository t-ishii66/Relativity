# 場所の違うベクトルをどう比べるか

## はじめに

前の文書「計量は時空の物差し」では、平面を極座標で表すと、

$$
ds^2
=
dr^2+r^2d\theta^2
$$

となることを見た。

これは直交座標で書いた、

$$
ds^2
=
dx^2+dy^2
$$

と同じ平面を表している。

極座標では計量成分が場所によって変わる。しかし、その変化だけを見ても、座標の選び方によるものなのか、空間や時空そのものの幾何学的な性質なのかは分からない。

この問題を調べるには、少し離れた場所どうしを比べる必要がある。

ところが、異なる場所にあるベクトルは、そのままでは比較できない。

この文書では、

- なぜ異なる場所のベクトルを単純に引き算できないのか
- 普通の微分は何を見落とすのか
- ベクトルを成分に分ける基底とは何か
- 座標方向の変化をどのように微分へ組み込むのか
- 共変微分と平行移動は何を表すのか
- 測地線はどのように定義されるのか

を順番に考える。

> 共変微分は、ベクトルの成分だけでなく、その成分を表すために使う座標方向の変化も含めて測る微分である

という感覚をつかむことが目標である。

## ベクトルを成分に分ける

平面上に、一つのベクトル $\boldsymbol{V}$ があるとしよう。

ベクトルは、大きさと向きを持つ矢印として考えられる。

この矢印を座標の数字で表すには、まず、どの方向を使って矢印を分解するかを決めなければならない。

直交座標 $(x,y)$ では、$x$ が増える方向の矢印と、$y$ が増える方向の矢印を用意する。

それぞれを、

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y
$$

と書く。

ベクトル $\boldsymbol{V}$ は、

$$
\boldsymbol{V}
=
V^x\boldsymbol{e}_x
+
V^y\boldsymbol{e}_y
$$

と表せる。

$V^x$ は $\boldsymbol{e}_x$ の方向へどれだけ進むか、$V^y$ は $\boldsymbol{e}_y$ の方向へどれだけ進むかを表す数字である。この二つの数字が、ベクトルの成分である。

一方、

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y
$$

は、成分を実際のベクトルへ組み立てるために使う方向の矢印である。

このような矢印の組を、基底と呼ぶ。

> ベクトルは矢印そのものであり、成分は、その矢印を選んだ基底で表した数字である。

基底を取り替えれば、同じベクトルを表す成分の数字は変わる。しかし、矢印そのものが変わったわけではない。

これは第1章で見た、「座標軸を変えると同じ矢印の成分が変わる」という話を、基底という言葉を使って書き直したものである。

## 座標ごとに基底を作る

一般の座標を $x^\mu$ と書く。

それぞれの座標 $x^\mu$ が増える方向に基底ベクトルを用意し、

$$
\boldsymbol{e}_\mu
$$

と書く。

ベクトルは、

$$
\boxed{
\boldsymbol{V}
=
V^\mu\boldsymbol{e}_\mu
}
$$

と表せる。

同じ添字 $\mu$ が上と下に一回ずつ現れているので、すべての座標方向について足し合わせる。

二次元なら、この式は、

$$
\boldsymbol{V}
=
V^1\boldsymbol{e}_1
+
V^2\boldsymbol{e}_2
$$

という意味である。

座標から作ったこのような基底を、座標基底と呼ぶ。

座標基底 $\boldsymbol{e}_\mu$ は、ほかの座標を固定したまま $x^\mu$ だけを少し増やしたとき、実際にどの向きへどれだけ移動するかを表す。

微小変位のベクトルも、

$$
d\boldsymbol{x}
=
dx^\mu\boldsymbol{e}_\mu
$$

と書ける。

ここで注意したいのは、基底ベクトルが必ず長さ $1$ になるわけではないことである。

直交座標では、通常、

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y
$$

を長さ $1$ の互いに直角な矢印として選ぶ。

しかし、一般の座標から作る基底は、場所によって向きが変わることもあれば、長さが変わることもある。

極座標 $(r,\theta)$ では、

$$
\boldsymbol{e}_r
$$

は $r$ を増やす方向を表し、

$$
\boldsymbol{e}_\theta
$$

は $\theta$ を増やす方向を表す。

$\boldsymbol{e}_r$ の長さは $1$ だが、$\boldsymbol{e}_\theta$ の長さは $r$ である。

$\boldsymbol{e}_\theta$ は、角度方向を向く長さ $1$ の単位ベクトルではない。座標 $\theta$ の変化を実際の変位へ変換する座標基底である。

そのため、

$$
d\boldsymbol{x}
=
dr\,\boldsymbol{e}_r
+
d\theta\,\boldsymbol{e}_\theta
$$

の角度方向の長さは、

$$
\left|d\theta\,\boldsymbol{e}_\theta\right|
=
r\,d\theta
$$

となる。

これは前の文書で、

$$
ds^2
=
dr^2+r^2d\theta^2
$$

に $r^2$ が現れたことと同じ内容である。

---

Alice「成分だけでは、矢印そのものにはならないんだね。」

Bob「うん。どの方向の矢印を何倍するのか、その方向を与える基底も必要なんだ。」

Alice「しかも極座標では、その基底の向きや長さが場所によって変わるんだね。」

---

## 同じ成分でも同じ向きとは限らない

平面上の二つの場所 P、Q を考えよう。

それぞれの場所で、極座標の基底、

$$
\boldsymbol{e}_r,
\qquad
\boldsymbol{e}_\theta
$$

を置く。

P と Q で、

$$
V^r=1,
\qquad
V^\theta=0
$$

という成分を持つベクトルを考える。

どちらも、それぞれの場所の $\boldsymbol{e}_r$ と同じ向きを向いている。

しかし、P と Q の角度 $\theta$ が異なれば、二つの $\boldsymbol{e}_r$ は平面上で違う向きを向いている。

したがって、二つのベクトルは成分が同じでも、実際には同じ向きではない。

---

Alice「どちらも $(1,0)$ なのに、矢印の向きが違うの？」

Bob「$(1,0)$ はベクトルそのものではなく、基底に掛ける成分の組だからね。P点のベクトルは、」

$$
\boldsymbol{V}(P)
=
1\,\boldsymbol{e}_r(P)
+
0\,\boldsymbol{e}_\theta(P)
=
\boldsymbol{e}_r(P)
$$

Bob「と書ける。一方、Q点では、」

$$
\boldsymbol{V}(Q)
=
1\,\boldsymbol{e}_r(Q)
+
0\,\boldsymbol{e}_\theta(Q)
=
\boldsymbol{e}_r(Q)
$$

Bob「となる。成分の組は同じでも、$\boldsymbol{e}_r(P)$ と $\boldsymbol{e}_r(Q)$ が違う向きを向いているから、二つのベクトルも違う向きになるんだ。」

Alice「数字だけでなく、どの場所の基底と組み合わせた数字なのかを見る必要があるんだね。」

---

異なる場所のベクトルを比べるときは、成分の変化だけでなく、基底の変化も考えなければならない。

## ベクトル全体を微分する

ベクトル場を、

$$
\boldsymbol{V}
=
V^\nu\boldsymbol{e}_\nu
$$

と書く。

$V^\nu$ はベクトルの成分であり、$\boldsymbol{e}_\nu$ はその場所の基底である。

座標 $x^\mu$ の方向へ移動したときに、ベクトル全体がどのように変化するかを調べたい。

積の微分を使うと、

$$
\partial_\mu\boldsymbol{V}
=
\partial_\mu
\left(
V^\nu\boldsymbol{e}_\nu
\right)
$$

$$
=
\left(
\partial_\mu V^\nu
\right)
\boldsymbol{e}_\nu
+
V^\nu
\partial_\mu\boldsymbol{e}_\nu
$$

となる。

右辺には二種類の変化がある。

一つ目は、

$$
\partial_\mu V^\nu
$$

という成分の変化である。

二つ目は、

$$
\partial_\mu\boldsymbol{e}_\nu
$$

という基底の変化である。

成分だけを普通に微分すると、二つ目の変化を見落としてしまう。

直交座標の基底はどこでも同じ向きを向くため、この問題は目立たない。しかし、極座標の基底は場所によって向きや大きさが変わる。

一般の座標で使える微分を作るには、基底の変化も式へ組み込む必要がある。

## 基底の変化を成分で表す

基底の変化も、その場所の基底を使って表せる。

そこで、

$$
\partial_\mu\boldsymbol{e}_\nu
=
\Gamma^\rho_{\mu\nu}
\boldsymbol{e}_\rho
$$

と書く。

$\Gamma^\rho_{\mu\nu}$ は、$x^\mu$ の方向へ移動したときに、基底 $\boldsymbol{e}_\nu$ がどのように変化するかを表す係数である。

この係数をクリストッフェル記号、または接続係数と呼ぶ。

先ほどのベクトルの微分へ代入すると、

$$
\partial_\mu\boldsymbol{V}
=
\left(
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\right)
\boldsymbol{e}_\rho
$$

となる。

括弧の中には、成分の変化と基底の変化の両方が入っている。

この組み合わせを、ベクトルの共変微分と呼ぶ。

$$
\boxed{
\nabla_\mu V^\rho
=
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
}
$$

この定義とベクトル全体の微分との関係を、もう一度まとめておこう。

ベクトル全体を、

$$
\boldsymbol{V}
=
V^\nu\boldsymbol{e}_\nu
$$

と書いて微分すると、

$$
\begin{aligned}
\partial_\mu\boldsymbol{V}
&=
\partial_\mu
\left(
V^\nu\boldsymbol{e}_\nu
\right)\\
&=
\left(
\partial_\mu V^\nu
\right)
\boldsymbol{e}_\nu
+
V^\nu
\partial_\mu\boldsymbol{e}_\nu
\end{aligned}
$$

となる。

クリストッフェル記号の定義、

$$
\partial_\mu\boldsymbol{e}_\nu
=
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho
$$

を代入し、第一項の添字を $\nu$ から $\rho$ へ付け替えると、

$$
\begin{aligned}
\partial_\mu\boldsymbol{V}
&=
\left(
\partial_\mu V^\rho
\right)
\boldsymbol{e}_\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\boldsymbol{e}_\rho\\
&=
\left(
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\right)
\boldsymbol{e}_\rho\\
&=
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho
\end{aligned}
$$

となる。

したがって、

$$
\boxed{
\partial_\mu\boldsymbol{V}
=
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho
}
$$

である。

つまり、共変微分 $\nabla_\mu V^\rho$ は、ベクトル全体の変化 $\partial_\mu\boldsymbol{V}$ を、その場所の基底で表した成分である。

平面上で向きと長さが固定されたベクトルなら、

$$
\partial_\mu\boldsymbol{V}=0
$$

である。

基底ベクトル $\boldsymbol{e}_\rho$ は互いに独立なので、

$$
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho
=0
$$

となるためには、それぞれの基底に掛かる係数がゼロでなければならない。

したがって、

$$
\boxed{
\nabla_\mu V^\rho=0
}
$$

となる。

共変微分がゼロになるのは、成分の微分とクリストッフェル記号の項が偶然打ち消し合ったからではない。共変微分がベクトル全体の変化を表すように作られているため、ベクトル全体が固定されていれば必然的にゼロになる。

ただし、一般の曲がった空間では、離れた場所のベクトルを経路によらず「同じ向き」とすることはできない。後で、指定した経路に沿う共変微分がゼロになるようにベクトルを運ぶことを、平行移動として定義する。

ここで大切なのは、記号の名前よりも、

$$
\text{ベクトル全体の変化}
=
\text{成分の変化}
+
\text{基底の変化}
$$

という考え方である。

## 極座標の基底はどう変わるか

平面上の位置ベクトルを、

$$
\boldsymbol{x}(r,\theta)
=
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}
$$

と書く。

位置ベクトル $\boldsymbol{x}$ は、$r$ と $\theta$ の両方によって変化する。その全微分は、

$$
d\boldsymbol{x}
=
\frac{\partial\boldsymbol{x}}{\partial r}dr
+
\frac{\partial\boldsymbol{x}}{\partial\theta}d\theta
$$

である。

実際に微分すると、

$$
\begin{aligned}
d\boldsymbol{x}
&=
d
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}\\
&=
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
dr
+
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}
d\theta
\end{aligned}
$$

となる。

一方、極座標の微小変位は、$r$ 方向と $\theta$ 方向の座標基底を使って、

$$
d\boldsymbol{x}
=
\boldsymbol{e}_r\,dr
+
\boldsymbol{e}_\theta\,d\theta
$$

と表す。

二つの式で $dr$ と $d\theta$ に掛かっているベクトルをそれぞれ比べれば、

極座標の座標基底は、

$$
\boldsymbol{e}_r
=
\frac{\partial\boldsymbol{x}}{\partial r}
=
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
$$

$$
\boldsymbol{e}_\theta
=
\frac{\partial\boldsymbol{x}}{\partial\theta}
=
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}
$$

である。

つまり、座標基底は、

$$
\boxed{
\boldsymbol{e}_r
=
\frac{\partial\boldsymbol{x}}{\partial r},
\qquad
\boldsymbol{e}_\theta
=
\frac{\partial\boldsymbol{x}}{\partial\theta}
}
$$

として、位置ベクトルの全微分から自然に現れる。

$\boldsymbol{e}_r$ の長さは $1$ だが、$\boldsymbol{e}_\theta$ の長さは $r$ である。

このことは、

$$
g_{rr}=1,
\qquad
g_{\theta\theta}=r^2
$$

という計量成分にも現れている。

基底を微分してみよう。

まず、

$$
\partial_r\boldsymbol{e}_r=0
$$

である。

一方、

$$
\partial_\theta\boldsymbol{e}_r
=
\begin{pmatrix}
-\sin\theta\\
\cos\theta
\end{pmatrix}
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

となる。

また、

$$
\partial_r\boldsymbol{e}_\theta
=
\begin{pmatrix}
-\sin\theta\\
\cos\theta
\end{pmatrix}
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

であり、

$$
\partial_\theta\boldsymbol{e}_\theta
=
\begin{pmatrix}
-r\cos\theta\\
-r\sin\theta
\end{pmatrix}
=
-r\boldsymbol{e}_r
$$

である。

ここで、クリストッフェル記号の定義をもう一度書くと、

$$
\partial_\mu\boldsymbol{e}_\nu
=
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho
$$

である。

二次元の極座標では、右辺の添字 $\rho$ について和を取るので、

$$
\partial_\mu\boldsymbol{e}_\nu
=
\Gamma^r_{\mu\nu}\boldsymbol{e}_r
+
\Gamma^\theta_{\mu\nu}\boldsymbol{e}_\theta
$$

と展開できる。

三つの添字は、

- $\mu$：どの座標方向へ微分するか
- $\nu$：どの基底を微分するか
- $\rho$：微分した結果がどの基底方向を向くか

を表している。

まず、

$$
\partial_r\boldsymbol{e}_r=0
$$

を定義と比較する。

$$
\partial_r\boldsymbol{e}_r
=
\Gamma^r_{rr}\boldsymbol{e}_r
+
\Gamma^\theta_{rr}\boldsymbol{e}_\theta
=0
$$

したがって、

$$
\Gamma^r_{rr}=0,
\qquad
\Gamma^\theta_{rr}=0
$$

である。

次に、

$$
\partial_\theta\boldsymbol{e}_r
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

を比較すると、

$$
\partial_\theta\boldsymbol{e}_r
=
\Gamma^r_{\theta r}\boldsymbol{e}_r
+
\Gamma^\theta_{\theta r}\boldsymbol{e}_\theta
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

なので、

$$
\Gamma^r_{\theta r}=0,
\qquad
\Gamma^\theta_{\theta r}
=
\frac{1}{r}
$$

となる。

同様に、

$$
\partial_r\boldsymbol{e}_\theta
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

を比較すると、

$$
\partial_r\boldsymbol{e}_\theta
=
\Gamma^r_{r\theta}\boldsymbol{e}_r
+
\Gamma^\theta_{r\theta}\boldsymbol{e}_\theta
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

なので、

$$
\Gamma^r_{r\theta}=0,
\qquad
\Gamma^\theta_{r\theta}
=
\frac{1}{r}
$$

となる。

最後に、

$$
\partial_\theta\boldsymbol{e}_\theta
=
-r\boldsymbol{e}_r
$$

を比較すると、

$$
\partial_\theta\boldsymbol{e}_\theta
=
\Gamma^r_{\theta\theta}\boldsymbol{e}_r
+
\Gamma^\theta_{\theta\theta}\boldsymbol{e}_\theta
=
-r\boldsymbol{e}_r
$$

なので、

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{\theta\theta}=0
$$

となる。

以上をまとめると、ゼロでないクリストッフェル記号は、

$$
\boxed{
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta}
=
\Gamma^\theta_{\theta r}
=
\frac{1}{r}
}
$$

であり、それ以外の成分はゼロである。

平面そのものが変化したのではない。極座標の基底が場所によって変わるため、その変化を表すクリストッフェル記号が現れたのである。

## クリストッフェル記号はテンソルではない

同じ平面を直交座標で表すと、基底は場所によらず一定である。

したがって、直交座標では、

$$
\Gamma^\rho_{\mu\nu}=0
$$

となる。

ところが、同じ平面を極座標で表すと、

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta}
=
\Gamma^\theta_{\theta r}
=
\frac{1}{r}
$$

となる。

ある座標ではすべてゼロなのに、別の座標ではゼロでなくなる。この変わり方はテンソルの変換規則とは異なる。

したがって、クリストッフェル記号そのものはテンソルではない。

これは欠点ではない。クリストッフェル記号は、座標によって生じる基底の変化を補うための係数だからである。

普通の微分 $\partial_\mu V^\nu$ も、それだけではテンソルにならない。両者を組み合わせた、

$$
\nabla_\mu V^\nu
=
\partial_\mu V^\nu
+
\Gamma^\nu_{\mu\rho}V^\rho
$$

がテンソルとして変換する。

---

Alice「テンソルではないものを使って、テンソルを作るの？」

Bob「そう。普通の微分に現れる余分な変化を、クリストッフェル記号がちょうど打ち消すんだ。」

---

## 同じベクトルなのに成分は変わる

具体的な例を見てみよう。

直交座標で $x$ 軸の正の向きを向く、長さ $1$ のベクトルを考える。

このベクトルはどこでも同じ向きを向いており、平面上で変化していない。

直交座標の成分で書けば、

$$
\boldsymbol{V}
=
\begin{pmatrix}
1\\
0
\end{pmatrix}
$$

である。

一方、極座標の基底は、

$$
\boldsymbol{e}_r
=
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
$$

$$
\boldsymbol{e}_\theta
=
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}
$$

だった。

$\boldsymbol{V}$ を二つの極座標基底の線形結合として、

$$
\boldsymbol{V}
=
V^r\boldsymbol{e}_r
+
V^\theta\boldsymbol{e}_\theta
$$

と表したい。

ここで、

$$
V^r=\cos\theta,
\qquad
V^\theta=-\frac{\sin\theta}{r}
$$

とすると、

$$
\begin{aligned}
V^r\boldsymbol{e}_r
+
V^\theta\boldsymbol{e}_\theta
&=
\cos\theta
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
-
\frac{\sin\theta}{r}
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}\\
&=
\begin{pmatrix}
\cos^2\theta\\
\sin\theta\cos\theta
\end{pmatrix}
+
\begin{pmatrix}
\sin^2\theta\\
-\sin\theta\cos\theta
\end{pmatrix}\\
&=
\begin{pmatrix}
1\\
0
\end{pmatrix}
\end{aligned}
$$

となり、もとのベクトル $\boldsymbol{V}$ と一致する。

したがって、

極座標の基底で表すと、

$$
\boldsymbol{V}
=
\cos\theta\,\boldsymbol{e}_r
-
\frac{\sin\theta}{r}\boldsymbol{e}_\theta
$$

となる。

したがって成分は、

$$
V^r=\cos\theta
$$

$$
V^\theta=-\frac{\sin\theta}{r}
$$

である。

このベクトルを平面上の別の場所へ平行移動しても、矢印そのものは $x$ 軸の正方向を向く長さ $1$ のベクトルのままである。

しかし、移動先では極座標基底 $\boldsymbol{e}_r$ と $\boldsymbol{e}_\theta$ の向きや長さが変わる。そのため、同じ矢印を移動先の極座標基底で表すと、成分 $V^r$ と $V^\theta$ の数字は変化する。

つまり、平行移動によってベクトルそのものを変化させなくても、そのベクトルの極座標成分は場所によって変化する。

ここで、なぜ成分の微分とクリストッフェル記号の項が打ち消し合うのかを、計算する前に確認しておこう。

このベクトルは平面上で変化していないので、ベクトル全体を $\theta$ で微分すれば、

$$
\partial_\theta\boldsymbol{V}=0
$$

となる。

一方、

$$
\boldsymbol{V}
=
V^r\boldsymbol{e}_r
+
V^\theta\boldsymbol{e}_\theta
$$

を積の規則で微分すると、

$$
\begin{aligned}
\partial_\theta\boldsymbol{V}
&=
\left(\partial_\theta V^r\right)\boldsymbol{e}_r
+
V^r\partial_\theta\boldsymbol{e}_r\\
&\quad
+
\left(\partial_\theta V^\theta\right)\boldsymbol{e}_\theta
+
V^\theta\partial_\theta\boldsymbol{e}_\theta
\end{aligned}
$$

となる。

極座標の基底の微分、

$$
\partial_\theta\boldsymbol{e}_r
=
\frac{1}{r}\boldsymbol{e}_\theta
$$

$$
\partial_\theta\boldsymbol{e}_\theta
=
-r\boldsymbol{e}_r
$$

を代入すると、

$$
\begin{aligned}
\partial_\theta\boldsymbol{V}
&=
\left(
\partial_\theta V^r-rV^\theta
\right)\boldsymbol{e}_r\\
&\quad+
\left(
\partial_\theta V^\theta+\frac{1}{r}V^r
\right)\boldsymbol{e}_\theta
\end{aligned}
$$

となる。

ベクトル全体が変化しないためには、独立な二つの基底に掛かる係数が、それぞれゼロでなければならない。

したがって、

$$
\partial_\theta V^r-rV^\theta=0
$$

$$
\partial_\theta V^\theta+\frac{1}{r}V^r=0
$$

となる。

ここで、

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{\theta r}=\frac{1}{r}
$$

だったので、二つの式は、

$$
\nabla_\theta V^r
=
\partial_\theta V^r
+
\Gamma^r_{\theta\theta}V^\theta
=0
$$

$$
\nabla_\theta V^\theta
=
\partial_\theta V^\theta
+
\Gamma^\theta_{\theta r}V^r
=0
$$

にほかならない。

つまり、クリストッフェル記号は、計算結果を偶然ゼロにするために後から選んだ量ではない。基底を微分したときに現れる係数として定義されているため、成分の変化と基底の変化が最初から一つの式の中で対応している。

実際に、

$$
V^r=\cos\theta,
\qquad
V^\theta=-\frac{\sin\theta}{r}
$$

を代入すれば、

$$
\begin{aligned}
\nabla_\theta V^r
&=
-\sin\theta
+
(-r)
\left(
-\frac{\sin\theta}{r}
\right)
=0,\\
\nabla_\theta V^\theta
&=
-\frac{\cos\theta}{r}
+
\frac{1}{r}\cos\theta
=0
\end{aligned}
$$

となり、一般的な議論と一致する。

## 下付き添字の共変微分

ここまでは上付き添字を持つベクトルを考えた。

下付き添字を持つ共変ベクトル $A_\nu$ では、接続の項の符号が反対になる。

$$
\boxed{
\nabla_\mu A_\nu
=
\partial_\mu A_\nu
-
\Gamma^\rho_{\mu\nu}A_\rho
}
$$

上付き添字には接続の項を足し、下付き添字には接続の項を引く。

例えば、上付きと下付きの添字を一つずつ持つテンソルでは、

$$
\nabla_\mu T^\rho{}_\nu
=
\partial_\mu T^\rho{}_\nu
+
\Gamma^\rho_{\mu\sigma}T^\sigma{}_\nu
-
\Gamma^\sigma_{\mu\nu}T^\rho{}_\sigma
$$

となる。

スカラー $f$ には補うべき添字がないため、

$$
\nabla_\mu f
=
\partial_\mu f
$$

である。

個々の式を別々に暗記するより、

- 上付き添字一つにつき、接続の項を一つ足す
- 下付き添字一つにつき、接続の項を一つ引く

という規則として読むとよい。

## まとめ

- ベクトルそのものと、その成分は区別しなければならない。
- 基底は、成分を実際のベクトルへ組み立てる方向の矢印である。
- 座標基底は、場所によって向きや長さが変わることがある。
- 極座標では、

  $$
  \boldsymbol{e}_r
  =
  \frac{\partial\boldsymbol{x}}{\partial r},
  \qquad
  \boldsymbol{e}_\theta
  =
  \frac{\partial\boldsymbol{x}}{\partial\theta}
  $$

  となる。
- 異なる場所では基底が異なるため、ベクトルの成分をそのまま比較することはできない。
- ベクトル全体の変化には、成分の変化と基底の変化が含まれる。
- クリストッフェル記号は、

  $$
  \partial_\mu\boldsymbol{e}_\nu
  =
  \Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho
  $$

  によって、基底の変化を成分で表す。
- 反変ベクトルの共変微分は、

  $$
  \nabla_\mu V^\rho
  =
  \partial_\mu V^\rho
  +
  \Gamma^\rho_{\mu\nu}V^\nu
  $$

  である。
- 共変微分は、ベクトル全体の変化をその場所の基底で表した成分である。
- 固定されたベクトルの共変微分がゼロになるのは、成分変化と基底変化が偶然打ち消し合うからではない。
- クリストッフェル記号そのものはテンソルではない。
- 上付き添字には接続の項を足し、下付き添字には接続の項を引く。

## 次の疑問

平面の極座標では、位置ベクトル、

$$
\boldsymbol{x}(r,\theta)
=
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}
$$

から座標基底を作り、その基底を直接微分してクリストッフェル記号を求められた。

しかし一般相対論では、時空を外側から眺めた位置ベクトルを用意し、その基底を直接微分するわけではない。

通常、時空の長さと角度の測り方を与える計量 $g_{\mu\nu}$ から出発する。

それでは、計量だけを使って、

$$
\Gamma^\rho_{\mu\nu}
$$

を求めることはできるのだろうか。

次の文書では、計量を基底どうしの内積として偏微分し、計量からクリストッフェル記号を求める公式を一つずつ導く。
