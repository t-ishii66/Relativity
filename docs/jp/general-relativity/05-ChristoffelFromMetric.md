# 計量からクリストッフェル記号を導く

## はじめに

前の文書「場所の違うベクトルをどう比べるか」では、基底の変化を、

$$
\partial_\mu\boldsymbol{e}_\nu
=
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho
$$

と書いた。

$\Gamma^\rho_{\mu\nu}$ がクリストッフェル記号だった。

平面の極座標では、

$$
\boldsymbol{x}(r,\theta)
=
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}
$$

という位置ベクトルから基底を作り、その基底を直接微分できた。

しかし、一般の時空で外側の空間を用意し、そこから時空の基底を直接眺めるわけではない。

一般相対論では、まず計量、

$$
g_{\mu\nu}
$$

が与えられる。

それでは、計量だけからクリストッフェル記号を求められるのだろうか。

この文書では、

- 計量を基底どうしの内積として読む
- 計量を偏微分する
- 長さと角度を保つ条件を式にする
- 接続に捩れがないという条件を使う
- 三本の式を足し引きする
- 逆計量で添字を上げる
- 極座標で公式を確かめる

という順に進む。

> クリストッフェル記号の公式は、計量の偏微分を適切に組み合わせて得られる

ということを理解するのが目標である。

## 計量は基底どうしの内積

座標基底を $\boldsymbol{e}_\mu$ とする。

前の文書では、二つのベクトルの内積を、

$$
\boldsymbol{A}\cdot\boldsymbol{B}
=
g_{\rho\sigma}A^\rho B^\sigma
$$

と書いた。

まず、基底自身の成分表示について確認しておこう。

任意のベクトル $\boldsymbol{V}$ は、座標基底を使って、

$$
\boldsymbol{V}
=
V^\rho\boldsymbol{e}_\rho
$$

と表せる。ここで $\boldsymbol{V}=\boldsymbol{e}_\mu$ とすると、

$$
\boldsymbol{e}_\mu
=
(\boldsymbol{e}_\mu)^\rho\boldsymbol{e}_\rho
$$

となる。

例えば二次元なら、

$$
\boldsymbol{e}_1
=
1\boldsymbol{e}_1+0\boldsymbol{e}_2,
\qquad
\boldsymbol{e}_2
=
0\boldsymbol{e}_1+1\boldsymbol{e}_2
$$

である。基底ベクトルを同じ基底で成分表示すると、自分自身に対応する成分だけが $1$ で、ほかは $0$ になる。したがって、

$$
(\boldsymbol{e}_\mu)^\rho
=
{\delta^\rho}_\mu
$$

と書ける。

この式が成り立つのは、$\mu$ と $\rho$ が同じ座標基底のラベルである場合である。

例えば、極座標基底 $\{\boldsymbol{e}_r,\boldsymbol{e}_\theta\}$ を使って基底自身を表すと、

$$
\boldsymbol{e}_r
=
1\boldsymbol{e}_r+0\boldsymbol{e}_\theta,
\qquad
\boldsymbol{e}_\theta
=
0\boldsymbol{e}_r+1\boldsymbol{e}_\theta
$$

となる。したがって、極座標基底に対する成分は、

$$
(\boldsymbol{e}_r)^r=1,
\qquad
(\boldsymbol{e}_r)^\theta=0
$$

$$
(\boldsymbol{e}_\theta)^r=0,
\qquad
(\boldsymbol{e}_\theta)^\theta=1
$$

である。

一方、同じ二つのベクトルを、平面の直交座標基底 $\{\boldsymbol{e}_x,\boldsymbol{e}_y\}$ で表すと、

$$
\boldsymbol{e}_r
=
\cos\theta\,\boldsymbol{e}_x
+\sin\theta\,\boldsymbol{e}_y
$$

$$
\boldsymbol{e}_\theta
=
-r\sin\theta\,\boldsymbol{e}_x
+r\cos\theta\,\boldsymbol{e}_y
$$

となる。したがって、直交座標基底に対する成分は、

$$
(\boldsymbol{e}_r)^x=\cos\theta,
\qquad
(\boldsymbol{e}_r)^y=\sin\theta
$$

$$
(\boldsymbol{e}_\theta)^x=-r\sin\theta,
\qquad
(\boldsymbol{e}_\theta)^y=r\cos\theta
$$

である。

異なる座標基底をまたいで見た成分には、クロネッカーのデルタではなく、座標変換の微分が現れる。例えば、

$$
(\boldsymbol{e}_r)^x
=
\frac{\partial x}{\partial r}
=
\cos\theta,
\qquad
(\boldsymbol{e}_r)^y
=
\frac{\partial y}{\partial r}
=
\sin\theta
$$

である。

つまり、

$$
(\boldsymbol{e}_\mu)^\rho
=
{\delta^\rho}_\mu
$$

は、基底ベクトルを同じ基底で成分表示した場合の式である。どの基底から見ても成分が常に $0$ と $1$ になるという意味ではない。

また、極座標基底に対する $\boldsymbol{e}_\theta$ の成分が $(0,1)$ であっても、その長さが $1$ とは限らない。成分とベクトルの長さは別のものである。

この区別に注意して、二つの座標基底の内積を計算しよう。前の文書で導入した内積の式へ、$(\boldsymbol{e}_\mu)^\rho={\delta^\rho}_\mu$ を代入すると、

$$
\begin{aligned}
\boldsymbol{e}_\mu\cdot\boldsymbol{e}_\nu
&=
g_{\rho\sigma}
(\boldsymbol{e}_\mu)^\rho
(\boldsymbol{e}_\nu)^\sigma\\
&=
g_{\rho\sigma}
{\delta^\rho}_\mu
{\delta^\sigma}_\nu\\
&=
g_{\mu\nu}
\end{aligned}
$$

となる。つまり、計量成分は、その座標基底どうしの内積として、

$$
\boxed{
g_{\mu\nu}=\boldsymbol{e}_\mu\cdot\boldsymbol{e}_\nu
}
$$

と読める。

上で直交座標基底を使って表した極座標基底の内積を計算すると、

$$
g_{rr}=\boldsymbol{e}_r\cdot\boldsymbol{e}_r=1
$$

$$
g_{r\theta}=\boldsymbol{e}_r\cdot\boldsymbol{e}_\theta=0
$$

$$
g_{\theta\theta}=\boldsymbol{e}_\theta\cdot\boldsymbol{e}_\theta=r^2
$$

となる。計量には、基底の長さと基底どうしの角度が記録されている。

## 計量を偏微分する

計量成分を座標 $x^\lambda$ について偏微分すると、

$$
\begin{aligned}
\partial_\lambda g_{\mu\nu}
&=\partial_\lambda(\boldsymbol{e}_\mu\cdot\boldsymbol{e}_\nu)\\
&=(\partial_\lambda\boldsymbol{e}_\mu)\cdot\boldsymbol{e}_\nu
+\boldsymbol{e}_\mu\cdot(\partial_\lambda\boldsymbol{e}_\nu)
\end{aligned}
$$

となる。ここへ、

$$
\partial_\lambda\boldsymbol{e}_\mu
=\Gamma^\rho_{\lambda\mu}\boldsymbol{e}_\rho,
\qquad
\partial_\lambda\boldsymbol{e}_\nu
=\Gamma^\rho_{\lambda\nu}\boldsymbol{e}_\rho
$$

を代入すると、

$$
\begin{aligned}
\partial_\lambda g_{\mu\nu}
&=\Gamma^\rho_{\lambda\mu}
\boldsymbol{e}_\rho\cdot\boldsymbol{e}_\nu
+\Gamma^\rho_{\lambda\nu}
\boldsymbol{e}_\mu\cdot\boldsymbol{e}_\rho\\
&=\Gamma^\rho_{\lambda\mu}g_{\rho\nu}
+\Gamma^\rho_{\lambda\nu}g_{\mu\rho}
\end{aligned}
$$

となる。計量の偏微分とクリストッフェル記号が、ここで結びついた。

## クリストッフェル記号の添字を下げる

式を見やすくするため、

$$
\boxed{
\Gamma_{\sigma\mu\nu}
=g_{\sigma\rho}\Gamma^\rho_{\mu\nu}
}
$$

と置く。これは、クリストッフェル記号の上付き添字を計量で下げた書き方である。

先ほどの式は、

$$
\boxed{
\partial_\lambda g_{\mu\nu}
=\Gamma_{\nu\lambda\mu}
+\Gamma_{\mu\lambda\nu}
}
$$

となる。この式が導出の出発点である。

## 長さと角度を保つ

ここでは、ベクトルを平行に運ぶとき、その長さと二つのベクトルの間の角度が保たれる接続を考える。

これは、計量と接続が互いに両立するということである。式では、

$$
\boxed{
\nabla_\lambda g_{\mu\nu}=0
}
$$

と書き、計量適合性と呼ぶ。

共変微分を展開すると、

$$
\nabla_\lambda g_{\mu\nu}
=\partial_\lambda g_{\mu\nu}
-\Gamma^\rho_{\lambda\mu}g_{\rho\nu}
-\Gamma^\rho_{\lambda\nu}g_{\mu\rho}
$$

である。これをゼロと置けば、

$$
\partial_\lambda g_{\mu\nu}
=\Gamma^\rho_{\lambda\mu}g_{\rho\nu}
+\Gamma^\rho_{\lambda\nu}g_{\mu\rho}
$$

となり、基底の内積を偏微分して得た式と一致する。

したがって、ここまでの計算は、

> 基底を運ぶときに、計量が定める長さと角度を保つ

という条件を表している。

## 捩率がないという条件

計量適合性だけでは、接続は一つに決まらない。

もう一つ、座標方向に余分な捩れがないことを要求する。座標基底では、この条件を、

$$
\boxed{
\Gamma^\rho_{\mu\nu}=\Gamma^\rho_{\nu\mu}
}
$$

と書ける。クリストッフェル記号の下二つの添字が対称になる。この条件を捩率ゼロと呼ぶ。

---

Alice「計量を偏微分するだけでは、まだ式が一つに決まらないの？」

Bob「うん。長さと角度を保つことに加えて、座標方向に余分な捩れがないことも使うんだ。」

---

計量適合性と捩率ゼロを同時に満たす接続を、レヴィ・チヴィタ接続と呼ぶ。

一般相対論で通常使うクリストッフェル記号は、この接続の成分である。

## 添字を入れ替えた三本の式

先ほど得た、

$$
\partial_\lambda g_{\mu\nu}
=\Gamma_{\nu\lambda\mu}+\Gamma_{\mu\lambda\nu}
$$

を使う。求めたいのは $\Gamma_{\sigma\mu\nu}$ である。

添字を入れ替えて、次の三本の式を作る。

$$
\partial_\mu g_{\nu\sigma}
=\Gamma_{\sigma\mu\nu}+\Gamma_{\nu\mu\sigma}
$$

$$
\partial_\nu g_{\sigma\mu}
=\Gamma_{\mu\nu\sigma}+\Gamma_{\sigma\nu\mu}
$$

$$
\partial_\sigma g_{\mu\nu}
=\Gamma_{\nu\sigma\mu}+\Gamma_{\mu\sigma\nu}
$$

## 二本を足して一本を引く

一本目と二本目を足し、三本目を引く。

左辺は、

$$
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
$$

となる。右辺を省略せずに書けば、

$$
\begin{aligned}
&
\Gamma_{\sigma\mu\nu}
+\Gamma_{\nu\mu\sigma}
+\Gamma_{\mu\nu\sigma}
+\Gamma_{\sigma\nu\mu}\\
&\quad
-\Gamma_{\nu\sigma\mu}
-\Gamma_{\mu\sigma\nu}
\end{aligned}
$$

である。

捩率ゼロにより、

$$
\Gamma_{\nu\mu\sigma}=\Gamma_{\nu\sigma\mu},
\qquad
\Gamma_{\mu\nu\sigma}=\Gamma_{\mu\sigma\nu}
$$

なので、これらの項は足し算と引き算で消える。

また、

$$
\Gamma_{\sigma\nu\mu}=\Gamma_{\sigma\mu\nu}
$$

なので、残る二項は同じである。したがって、

$$
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
=2\Gamma_{\sigma\mu\nu}
$$

となる。よって、

$$
\boxed{
\Gamma_{\sigma\mu\nu}
=\frac{1}{2}
\left(
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
}
$$

を得る。

## 逆計量で添字を上げる

逆計量 $g^{\rho\sigma}$ を使って、

$$
\Gamma^\rho_{\mu\nu}
=g^{\rho\sigma}\Gamma_{\sigma\mu\nu}
$$

と添字を上げる。先ほどの式を代入すると、

$$
\boxed{
\Gamma^\rho_{\mu\nu}
=\frac{1}{2}
g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
}
$$

となる。これが、計量からクリストッフェル記号を求める公式である。

公式の三つの項は、突然選ばれたものではない。計量を偏微分して作った三本の式を、

$$
\text{一本目}+\text{二本目}-\text{三本目}
$$

と組み合わせた結果である。

## 極座標で確かめる

平面の極座標では、

$$
g_{\mu\nu}
=\begin{pmatrix}1&0\\0&r^2\end{pmatrix},
\qquad
g^{\mu\nu}
=\begin{pmatrix}1&0\\0&\dfrac{1}{r^2}\end{pmatrix}
$$

だった。場所によって変化する計量成分は $g_{\theta\theta}=r^2$ だけなので、ゼロでない偏微分は、

$$
\partial_r g_{\theta\theta}=2r
$$

である。

## $\Gamma^r_{\theta\theta}$ を求める

公式へ $\rho=r,\mu=\theta,\nu=\theta$ を代入する。

$$
\begin{aligned}
\Gamma^r_{\theta\theta}
&=\frac{1}{2}g^{r\sigma}
\left(
\partial_\theta g_{\sigma\theta}
+\partial_\theta g_{\sigma\theta}
-\partial_\sigma g_{\theta\theta}
\right)
\end{aligned}
$$

$g^{r\sigma}$ がゼロでないのは $\sigma=r$ の場合だけなので、

$$
\begin{aligned}
\Gamma^r_{\theta\theta}
&=\frac{1}{2}g^{rr}
\left(
\partial_\theta g_{r\theta}
+\partial_\theta g_{r\theta}
-\partial_r g_{\theta\theta}
\right)\\
&=\frac{1}{2}(0+0-2r)\\
&=-r
\end{aligned}
$$

となる。

## $\Gamma^\theta_{r\theta}$ を求める

次に、$\rho=\theta,\mu=r,\nu=\theta$ を代入する。

$$
\begin{aligned}
\Gamma^\theta_{r\theta}
&=\frac{1}{2}g^{\theta\sigma}
\left(
\partial_r g_{\sigma\theta}
+\partial_\theta g_{\sigma r}
-\partial_\sigma g_{r\theta}
\right)
\end{aligned}
$$

$g^{\theta\sigma}$ がゼロでないのは $\sigma=\theta$ の場合だけなので、

$$
\begin{aligned}
\Gamma^\theta_{r\theta}
&=\frac{1}{2}g^{\theta\theta}
\left(
\partial_r g_{\theta\theta}
+\partial_\theta g_{\theta r}
-\partial_\theta g_{r\theta}
\right)\\
&=\frac{1}{2}\frac{1}{r^2}(2r+0-0)\\
&=\frac{1}{r}
\end{aligned}
$$

となる。捩率ゼロにより、

$$
\Gamma^\theta_{\theta r}
=\Gamma^\theta_{r\theta}
=\frac{1}{r}
$$

である。

## 残りの成分

同じ公式へほかの添字を代入すると、

$$
\Gamma^r_{rr}=0
$$

$$
\Gamma^r_{r\theta}=\Gamma^r_{\theta r}=0
$$

$$
\Gamma^\theta_{rr}=0,
\qquad
\Gamma^\theta_{\theta\theta}=0
$$

となる。したがって、ゼロでない成分は、

$$
\boxed{
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta}
=\Gamma^\theta_{\theta r}
=\frac{1}{r}
}
$$

である。これは、前の文書で極座標の基底を直接微分して得た結果と一致する。

---

Alice「基底を直接見ることができなくても、計量の変化から同じ答えを出せるんだね。」

Bob「うん。計量には基底の長さと角度が入っているから、その変化を調べれば基底がどう変わるかも分かるんだ。」

---

## 何を仮定していたのか

今回の公式は、計量だけから無条件に得られたわけではない。次の二条件を使った。

1. 計量適合性

   $$
   \nabla_\lambda g_{\mu\nu}=0
   $$

2. 捩率ゼロ

   $$
   \Gamma^\rho_{\mu\nu}=\Gamma^\rho_{\nu\mu}
   $$

この二条件を満たすレヴィ・チヴィタ接続は、与えられた計量に対して一意に決まる。

一般相対論では、通常、この接続を使う。

> 計量を与えると、長さと角度を保ち、捩率を持たない接続が一つに決まる

と考えられる。

## まとめ

- 計量成分は基底どうしの内積として読める。
- 計量を偏微分すると、基底の変化が二項現れる。
- 計量適合性は、平行移動で長さと角度を保つことを表す。
- 捩率ゼロでは、クリストッフェル記号の下二つの添字が対称になる。
- 添字を入れ替えた三本の式を、二本足して一本引く。
- 逆計量で添字を上げると、

  $$
  \Gamma^\rho_{\mu\nu}
  =
  \frac{1}{2}
  g^{\rho\sigma}
  \left(
  \partial_\mu g_{\sigma\nu}
  +
  \partial_\nu g_{\sigma\mu}
  -
  \partial_\sigma g_{\mu\nu}
  \right)
  $$

  を得る。
- この公式が与えるのは、計量適合的で捩率のないレヴィ・チヴィタ接続である。
- 極座標では、基底を直接微分した場合と同じクリストッフェル記号が得られる。

## 次の疑問

計量からクリストッフェル記号を求められるようになった。

共変微分を使えば、ベクトルがその場所でどのように変化しているかを表せる。

それでは、一つのベクトルをある場所から別の場所へ運ぶには、どのような条件を課せばよいのだろうか。

また、空間や時空の中で「可能な限り真っ直ぐ進む」とは、どのような意味なのだろうか。

次の文書では、経路に沿う共変微分から平行移動を定義し、測地線と自由落下へ進む。
