# ベクトルを運び、真っ直ぐ進む

## はじめに

前の文書「計量からクリストッフェル記号を導く」では、

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
$$

を導いた。計量が分かれば、基底の変化を表すクリストッフェル記号を求められる。

共変微分は、

$$
\nabla_\mu V^\rho
=\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}V^\nu
$$

だった。

この文書では、まず共変微分がテンソルとして変換することを確かめる。その後、経路に沿う共変微分、ベクトルの平行移動、測地線方程式、極座標で見た直線、自由落下と測地線を順番に考える。

> 測地線は、接ベクトルを自分自身に沿って平行移動する経路である

という感覚をつかむことが目標である。

## 共変微分はなぜテンソルなのか

前々回の文書では、クリストッフェル記号そのものはテンソルではないが、

$$
\nabla_\mu V^\rho
=
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
$$

という組み合わせはテンソルとして変換すると述べた。

テンソルではない量を組み合わせて、なぜテンソルを作れるのだろうか。ここでは、座標変換によってそれぞれに現れる余分な項が、互いに打ち消し合うことを確かめる。

### ベクトルを新しい座標で表す

古い座標を $x^\mu$、新しい座標を $x'^\mu$ とする。

上付き添字を持つベクトルの成分は、

$$
V'^\rho
=
\frac{\partial x'^\rho}{\partial x^\sigma}
V^\sigma
$$

と変換する。

一方、新しい座標による偏微分は、連鎖律から、

$$
\partial'_\mu
=
\frac{\partial x^\alpha}{\partial x'^\mu}
\partial_\alpha
$$

と書ける。

もし $\partial_\mu V^\rho$ が一つの下付き添字と一つの上付き添字を持つテンソルなら、

$$
\partial'_\mu V'^\rho
=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma
$$

と変換するはずである。

実際にそうなるかを計算してみよう。

### ベクトルの偏微分を変換する

$V'^\rho$ の変換則を新しい座標で微分すると、

$$
\begin{aligned}
\partial'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\partial_\alpha
\left(
\frac{\partial x'^\rho}{\partial x^\sigma}
V^\sigma
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma\\
&\quad+
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma
\end{aligned}
$$

となる。

第一項は、下付き添字 $\mu$ と上付き添字 $\rho$ を持つテンソルに期待される変換である。しかし第二項には、座標変換の二階微分が含まれている。

座標変換が一定の倍率でしか変化しない線形変換なら、この二階微分はゼロになる。しかし、直交座標から極座標への変換のような一般の座標変換ではゼロにならない。

したがって、$\partial_\mu V^\rho$ だけではテンソルにならない。

### 余分な項を逆変換で書く

この余分な第二項が、クリストッフェル記号から現れる項と打ち消し合うことを見たい。そのため、座標変換と逆変換の関係、

$$
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu}
=
{\delta^\rho}_\nu
$$

を使う。

右辺は一定なので、これを $x'^\mu$ で微分するとゼロになる。左辺を積の微分で展開すると、

$$
\begin{aligned}
0
&=
\frac{\partial}{\partial x'^\mu}
\left(
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu}
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu}
+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
\end{aligned}
$$

となる。ここで両辺に $V'^\nu$ を掛ける。ベクトルの逆変換、

$$
\frac{\partial x^\lambda}{\partial x'^\nu}V'^\nu
=
V^\lambda
$$

を使う。また、$\lambda$ は各項の中で和を取るための添字なので、二つの項を区別しやすいように第一項の $\lambda$ だけを $\sigma$ と書き換える。すると、

$$
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma
+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
=0
$$

となる。第二項を右辺へ移すと、偏微分に現れた余分な項は、

$$
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma
=
-
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
$$

と書き換えられる。

したがって、ベクトルの偏微分の変換は、

$$
\begin{aligned}
\partial'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma\\
&\quad-
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
\end{aligned}
$$

となる。最後の項が、テンソルの変換を妨げている項である。

### クリストッフェル記号はどう変換するか

新しい座標の基底は、古い座標の基底を使って、

$$
\boldsymbol{e}'_\nu
=
\frac{\partial x^\beta}{\partial x'^\nu}
\boldsymbol{e}_\beta
$$

と書ける。この式を $x'^\mu$ で微分すると、座標変換の係数を微分する項と、古い基底 $\boldsymbol{e}_\beta$ を微分する項の二つが現れる。それぞれを新しい座標の基底で表し、

$$
\partial'_\mu\boldsymbol{e}'_\nu
=
\Gamma'^\rho_{\mu\nu}
\boldsymbol{e}'_\rho
$$

と比較すると、クリストッフェル記号の変換則、

$$
\begin{aligned}
\Gamma'^\rho_{\mu\nu}
&=
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x^\beta}{\partial x'^\nu}
\Gamma^\lambda_{\alpha\beta}\\
&\quad+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
\end{aligned}
$$

と変換する。

第一項だけなら、クリストッフェル記号は一つの上付き添字と二つの下付き添字を持つテンソルと同じ変換をする。しかし、実際には座標変換の二階微分を含む第二項が加わる。そのため、クリストッフェル記号そのものはテンソルではない。

この第二項は余計なものに見えるが、共変微分を作るうえでは必要な項である。

$V'^\nu$ を掛け、

$$
\frac{\partial x^\beta}{\partial x'^\nu}V'^\nu
=
V^\beta
$$

を使うと、

$$
\begin{aligned}
\Gamma'^\rho_{\mu\nu}V'^\nu
&=
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\alpha}{\partial x'^\mu}
\Gamma^\lambda_{\alpha\beta}V^\beta\\
&\quad+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
\end{aligned}
$$

となる。

最後の項は、先ほど $\partial'_\mu V'^\rho$ に現れた余分な項と同じ形で、符号だけが反対になっている。

### 二つの余分な項が打ち消し合う

共変微分は、

$$
\nabla'_\mu V'^\rho
=
\partial'_\mu V'^\rho
+
\Gamma'^\rho_{\mu\nu}V'^\nu
$$

である。ここへ二つの変換結果を代入すると、座標変換の二階微分を含む項が打ち消し合い、

$$
\begin{aligned}
\nabla'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\left(
\partial_\alpha V^\sigma
+
\Gamma^\sigma_{\alpha\beta}V^\beta
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\nabla_\alpha V^\sigma
\end{aligned}
$$

となる。

これは、下付き添字 $\mu$ には逆向きの座標変換を、上付き添字 $\rho$ には順向きの座標変換を掛けるという、$(1,1)$ 型テンソルの変換規則そのものである。

したがって、

$$
\boxed{
\nabla_\mu V^\rho
\text{ は }(1,1)\text{ 型テンソルである}
}
$$

と分かる。

ここで正確に区別しておこう。接続 $\nabla$ そのものや、その成分であるクリストッフェル記号がテンソルなのではない。ベクトル場 $V$ に共変微分を作用させて得られる $\nabla_\mu V^\rho$ がテンソルなのである。

クリストッフェル記号がテンソルではないことは欠点ではない。そのテンソルとは異なる変換に含まれる項が、普通の偏微分の余分な項を打ち消す。二つを組み合わせることで、座標の選び方によらないベクトルの変化を表せる。

このことは、これから定義する平行移動にとって重要である。共変微分がテンソルとして変換するからこそ、「共変微分がゼロである」という条件も、座標の選び方によらない幾何学的な意味を持つ。

## 経路を一つ選ぶ

異なる場所にあるベクトルを比較するには、一方をもう一方の場所まで運ぶ必要がある。

しかし、出発点と到着点だけでは、どこを通って運ぶのかが決まらない。そこで、まず経路を、

$$
x^\mu=x^\mu(\lambda)
$$

と指定する。$\lambda$ は、経路上の場所を表す変数である。

経路の接ベクトルは、

$$
U^\mu=\frac{dx^\mu}{d\lambda}
$$

である。$U^\mu$ は、$\lambda$ を少し増やしたとき、各座標がどちらへどれだけ変化するかを表す。

## 経路に沿って微分する

ベクトル場 $V^\rho(x)$ があるとする。経路上では、

$$
V^\rho=V^\rho(x(\lambda))
$$

となる。連鎖律を使えば、

$$
\frac{dV^\rho}{d\lambda}
=\frac{dx^\mu}{d\lambda}\partial_\mu V^\rho
$$

である。

これは成分だけを経路に沿って微分した式であり、基底の変化は含まれていない。

そこで、普通の偏微分を共変微分へ置き換え、

$$
\boxed{
\frac{D V^\rho}{D\lambda}
=\frac{dx^\mu}{d\lambda}\nabla_\mu V^\rho
}
$$

と定義する。$D/D\lambda$ は、経路に沿う共変微分を表す。

$dx^\mu/d\lambda$ は上付き添字を持つベクトルであり、$\nabla_\mu V^\rho$ は $(1,1)$ 型テンソルだった。下付き添字 $\mu$ と上付き添字 $\mu$ を縮約した $DV^\rho/D\lambda$ は、上付き添字 $\rho$ を一つ持つベクトルとして変換する。

展開すると、

$$
\begin{aligned}
\frac{D V^\rho}{D\lambda}
&=\frac{dx^\mu}{d\lambda}
\left(
\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}V^\nu
\right)\\
&=\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
\end{aligned}
$$

となる。

## 平行移動

経路に沿ってベクトル全体を変化させずに運ぶことを、平行移動と呼ぶ。その条件は、

$$
\boxed{
\frac{D V^\rho}{D\lambda}=0
}
$$

である。成分で書けば、

$$
\boxed{
\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
=0
}
$$

となる。この式は、

$$
\frac{dV^\rho}{d\lambda}
=-\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
$$

とも書ける。

右辺は、経路に沿って基底が変わる分を打ち消すため、成分をどのように変えればよいかを示している。

---

Alice「平行に運ぶなら、成分を一定にすればいいんじゃないの？」

Bob「基底が変わらない座標ならそれでいい。でも基底が変わる座標では、同じ矢印を保つために成分の方を変える必要があるんだ。」

---

平行移動で一定に保たれるのは、座標成分の数字ではなく、接続を使って比較したベクトル全体である。

## 直交座標ではどうなるか

普通の平面を直交座標で表すと、クリストッフェル記号はすべてゼロである。

したがって、平行移動の式は、

$$
\frac{dV^\rho}{d\lambda}=0
$$

となる。この場合は、ベクトルの成分を一定に保つことが、そのまま平行移動になる。

極座標ではクリストッフェル記号がゼロではないため、同じ平面であっても、平行移動中の成分は変化する。

平行移動の幾何学的な意味は座標によらないが、その条件を表す成分の式は座標によって見た目が変わる。

## 経路自身の向きを運ぶ

経路の接ベクトルを、

$$
U^\rho=\frac{dx^\rho}{d\lambda}
$$

とする。今度は、別に用意したベクトルではなく、この接ベクトル自身を経路に沿って平行移動する。

その条件は、

$$
\boxed{
\frac{D U^\rho}{D\lambda}=0
}
$$

である。

$U^\rho=dx^\rho/d\lambda$ を代入すると、

$$
\frac{dU^\rho}{d\lambda}
=\frac{d^2x^\rho}{d\lambda^2}
$$

なので、

$$
\boxed{
\frac{d^2x^\rho}{d\lambda^2}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}
\frac{dx^\nu}{d\lambda}
=0
}
$$

となる。これを測地線方程式と呼ぶ。

## なぜ「真っ直ぐ」なのか

平面の直交座標では $\Gamma^\rho_{\mu\nu}=0$ なので、

$$
\frac{d^2x^\rho}{d\lambda^2}=0
$$

となる。一度積分すると、

$$
\frac{dx^\rho}{d\lambda}=\text{一定}
$$

であり、もう一度積分すると、

$$
x^\rho(\lambda)=a^\rho\lambda+b^\rho
$$

となる。これは平面上の直線である。

一般の座標や曲がった時空では、座標成分が一定になることを「真っ直ぐ」とは呼べない。

そこで、

> 接ベクトルを自分自身に沿って平行移動する

ことを、座標によらない「可能な限り真っ直ぐ」の定義として使う。

## パラメータについて

測地線方程式を $D U^\rho/D\lambda=0$ と書くには、経路を進む速さを不自然に伸び縮みさせないパラメータを使う。

このような $\lambda$ をアフィンパラメータと呼ぶ。

時間的な測地線では、固有時 $\tau$ をアフィンパラメータとして選べる。

この文書では、測地線方程式に現れる $\lambda$ はアフィンパラメータであるとする。

## 極座標の測地線方程式

平面の極座標では、

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta}
=\Gamma^\theta_{\theta r}
=\frac1r
$$

だった。

$r$ 成分では、ゼロでない $\Gamma^r_{\mu\nu}$ は $\Gamma^r_{\theta\theta}$ だけなので、

$$
\boxed{
\frac{d^2r}{d\lambda^2}
-r\left(\frac{d\theta}{d\lambda}\right)^2
=0
}
$$

となる。

$\theta$ 成分は、

$$
\frac{d^2\theta}{d\lambda^2}
+\Gamma^\theta_{r\theta}
\frac{dr}{d\lambda}\frac{d\theta}{d\lambda}
+\Gamma^\theta_{\theta r}
\frac{d\theta}{d\lambda}\frac{dr}{d\lambda}
=0
$$

なので、

$$
\boxed{
\frac{d^2\theta}{d\lambda^2}
+\frac{2}{r}
\frac{dr}{d\lambda}
\frac{d\theta}{d\lambda}
=0
}
$$

となる。

同じ平面上の直線でも、極座標では $r$ と $\theta$ が一定の速さで変化するとは限らない。クリストッフェル記号を含む項が、座標基底の変化を補っている。

## 半径方向の直線

角度を一定にして $\theta=\text{一定}$ とする。このとき、

$$
\frac{d\theta}{d\lambda}=0,
\qquad
\frac{d^2\theta}{d\lambda^2}=0
$$

である。二本の測地線方程式は、

$$
\frac{d^2r}{d\lambda^2}=0,
\qquad
0=0
$$

となる。したがって、$r$ が $\lambda$ に比例して変化する半径方向の直線は測地線である。

## 円は測地線ではない

次に、$r=\text{一定}$ として円周上を進む経路を考える。このとき、

$$
\frac{dr}{d\lambda}=0,
\qquad
\frac{d^2r}{d\lambda^2}=0
$$

である。$r$ 成分の測地線方程式は、

$$
-r\left(\frac{d\theta}{d\lambda}\right)^2=0
$$

となる。

$r>0$ で円周上を実際に進むなら $d\theta/d\lambda\neq0$ なので、左辺はゼロにならない。

したがって、円は平面上の測地線ではない。円周上を進み続けるには、進行方向を中心側へ曲げ続ける必要がある。

## 座標上の見た目では決まらない

測地線であるかどうかは、座標上で線が真っ直ぐに見えるかどうかでは決まらない。測地線方程式を満たすかどうかで決まる。

同じ経路を別の座標で表せば、座標上の形は変わる。それでも、測地線であるという幾何学的な性質は変わらない。

## 自由落下と測地線

一般相対論では、重力以外の力を受けていない物体は時空の測地線を進む。

物体の固有時を $\tau$ とすると、四元速度は、

$$
U^\mu=\frac{dx^\mu}{d\tau}
$$

である。四元速度を経路に沿って平行移動する条件は、

$$
U^\nu\nabla_\nu U^\mu=0
$$

である。成分で書けば、

$$
\boxed{
\frac{d^2x^\mu}{d\tau^2}
+\Gamma^\mu_{\rho\sigma}
\frac{dx^\rho}{d\tau}
\frac{dx^\sigma}{d\tau}
=0
}
$$

となる。

地上の座標から見ると、自由落下する物体の空間座標は加速して見える。

しかし一般相対論では、物体に重力という力が加わって経路を曲げるというより、物体は時空の中を可能な限り真っ直ぐ進んでいると考える。

座標上の加速には、時空の計量から作られたクリストッフェル記号が現れる。

## クリストッフェル記号は曲率ではない

平面を極座標で表すと、クリストッフェル記号はゼロではない。同じ平面を直交座標で表せば、すべてゼロになる。

したがって、

> クリストッフェル記号がゼロでないことだけでは、空間や時空に曲率があるとは言えない。

クリストッフェル記号は接続の成分であり、座標によって変化する。

それでは、座標を変えても消えない幾何学的な曲がりを、どのように見つければよいのだろうか。

## まとめ

- ベクトル成分の普通の偏微分は、座標変換の二階微分を含む余分な項が現れるため、それだけではテンソルにならない。
- クリストッフェル記号もテンソルではなく、その変換則には座標変換の二階微分を含む項が現れる。
- 二つの余分な項は共変微分の中で打ち消し合うため、$\nabla_\mu V^\rho$ は $(1,1)$ 型テンソルとして変換する。
- 接続 $\nabla$ 自体ではなく、ベクトル場に作用させて得られる $\nabla_\mu V^\rho$ がテンソルである。
- 経路は $x^\mu=x^\mu(\lambda)$ と表せる。
- 経路の接ベクトルは $U^\mu=dx^\mu/d\lambda$ である。
- 経路に沿う共変微分 $DV^\rho/D\lambda$ は、$U^\mu$ と $\nabla_\mu V^\rho$ を縮約して得られるベクトルである。
- 経路に沿う共変微分は、

  $$
  \frac{D V^\rho}{D\lambda}
  =
  \frac{dx^\mu}{d\lambda}\nabla_\mu V^\rho
  $$

  である。
- 経路に沿う共変微分がゼロになるようにベクトルを運ぶことを平行移動という。
- 平行移動では、ベクトルの座標成分が一定になるとは限らない。
- 接ベクトルを自分自身に沿って平行移動する経路が測地線である。
- 測地線方程式は、

  $$
  \frac{d^2x^\rho}{d\lambda^2}
  +
  \Gamma^\rho_{\mu\nu}
  \frac{dx^\mu}{d\lambda}
  \frac{dx^\nu}{d\lambda}
  =0
  $$

  である。
- 極座標でも平面上の直線は測地線であり、円は測地線ではない。
- 重力以外の力を受けない物体は、時空の測地線を進む。
- クリストッフェル記号がゼロでないだけでは、曲率があるとは言えない。

## 次の疑問

ベクトルを指定した経路に沿って平行移動する方法が分かった。

それでは、同じ出発点から同じ到着点まで、異なる二つの経路に沿ってベクトルを運んだら、結果は同じになるのだろうか。

あるいは、小さな閉曲線に沿ってベクトルを一周させ、出発点へ戻したら、最初と同じベクトルに戻るのだろうか。

平面では元に戻る。しかし、一般の空間や時空では、経路によって結果が異なることがある。

次の文書では、閉曲線に沿う平行移動と、共変微分を行う順序の違いから、座標では消せない曲率へ進む。
