# 計量からクリストッフェル記号を導く

## はじめに

前の文書「場所の違うベクトルをどう比べるか」では、基底の変化を、

$$
\partial_\mu\boldsymbol{e}_\nu =
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho
$$

と書いた。

$\Gamma^\rho_{\mu\nu}$ がクリストッフェル記号だった。

平面の極座標では、

$$
\boldsymbol{x}(r,\theta) =
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
- 計量の共変微分がゼロになることを確かめる
- クリストッフェル記号の下二つの添字が対称になる条件を使う
- 三本の式を足し引きする
- 逆計量で添字を上げる
- 極座標で公式を確かめる

という順に進む。

> クリストッフェル記号の公式は、計量の偏微分を適切に組み合わせて得られる

ということを理解するのが目標である。

## 計量は基底どうしの内積

座標基底を $\boldsymbol e_\mu$ とする。

前の文書では、二つのベクトルの内積を、

$$
\boldsymbol{A}\cdot\boldsymbol{B} =
g_{\rho\sigma}A^\rho B^\sigma
$$

と書いた。

まず、基底自身の成分表示について確認しておこう。

任意のベクトル $\boldsymbol{V}$ は、座標基底を使って、

$$
\boldsymbol{V} =
V^\rho\boldsymbol{e}_\rho
$$

と表せる。ここで $\boldsymbol{V}=\boldsymbol e_\mu$ とすると、

$$
\boldsymbol{e}_\mu =
(\boldsymbol{e}_\mu)^\rho\boldsymbol{e}_\rho
$$

となる。

例えば二次元なら、

$$
\boldsymbol{e}_1 =
1\boldsymbol{e}_1+0\boldsymbol{e}_2,
\qquad
\boldsymbol{e}_2 =
0\boldsymbol{e}_1+1\boldsymbol{e}_2
$$

である。基底ベクトルを同じ基底で成分表示すると、自分自身に対応する成分だけが $1$ で、ほかは $0$ になる。したがって、

$$
(\boldsymbol{e}_\mu)^\rho =
{\delta^\rho}_\mu
$$

と書ける。

この式が成り立つのは、 $\mu$ と $\rho$ が同じ座標基底のラベルである場合である。

例えば、極座標基底 $\{\boldsymbol e_r,\boldsymbol e_\theta\}$ を使って基底自身を表すと、

$$
\boldsymbol{e}_r =
1\boldsymbol{e}_r+0\boldsymbol{e}_\theta,
\qquad
\boldsymbol{e}_\theta =
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

一方、同じ二つのベクトルを、平面の直交座標基底 $\{\boldsymbol e_x,\boldsymbol e_y\}$ で表すと、

$$
\boldsymbol{e}_r =
\cos\theta\,\boldsymbol{e}_x
+\sin\theta\,\boldsymbol{e}_y
$$

$$
\boldsymbol{e}_\theta =
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
(\boldsymbol{e}_r)^x =
\frac{\partial x}{\partial r} =
\cos\theta,
\qquad
(\boldsymbol{e}_r)^y =
\frac{\partial y}{\partial r} =
\sin\theta
$$

である。

> **Tips：なぜ $(\boldsymbol e_r)^x=\partial x/\partial r$ なのか**
>
> この関係の詳しい導出は、前の文書の「[極座標の基底はどう変わるか](./04-CovariantDerivative.md#極座標の基底はどう変わるか)」で行った。
>
> そこでは、位置ベクトルの全微分
>
> $$
> d\boldsymbol{x} =
> \frac{\partial\boldsymbol{x}}{\partial r}dr
> +
> \frac{\partial\boldsymbol{x}}{\partial\theta}d\theta
> $$
>
> と、座標基底による表示
>
> $$
> d\boldsymbol{x} =
> \boldsymbol e_r\,dr
> +
> \boldsymbol e_\theta\,d\theta
> $$
>
> の係数を比べて、
>
> $$
> \boldsymbol e_r =
> \frac{\partial\boldsymbol{x}}{\partial r}
> $$
>
> を得た。さらに、位置ベクトルを
>
> $$
> \boldsymbol{x} =
> x\boldsymbol e_x+y\boldsymbol e_y
> $$
>
> と書いて右辺を微分すれば、
>
> $$
> \boldsymbol e_r =
> \frac{\partial x}{\partial r}\boldsymbol e_x
> +
> \frac{\partial y}{\partial r}\boldsymbol e_y
> $$
>
> となる。したがって、 $\boldsymbol e_r$ の直交座標基底に対する成分は、
> $(\boldsymbol e_r)^x=\partial x/\partial r$、
> $(\boldsymbol e_r)^y=\partial y/\partial r$ である。

つまり、

$$
(\boldsymbol{e}_\mu)^\rho =
{\delta^\rho}_\mu
$$

は、基底ベクトルを同じ基底で成分表示した場合の式である。どの基底から見ても成分が常に $0$ と $1$ になるという意味ではない。

また、極座標基底に対する $\boldsymbol e_\theta$ の成分が $(0,1)$ であっても、その長さが $1$ になるとは限らない。この点は、以下で内積を計算した後に詳しく確認する。

この区別に注意して、二つの座標基底の内積を計算しよう。前の文書で導入した内積の式へ、 $(\boldsymbol e_\mu)^\rho={\delta^\rho}_\mu$ を代入すると、

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

![温室で基底の長さと角度を調べるAliceとBob](../../../images/general-relativity/05/metric-in-greenhouse.png)

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

> **Tips：成分が $(0,1)$ でも、なぜ長さは $1$ ではないのか**
>
> $\boldsymbol e_\theta$ を極座標基底で成分表示すると、
>
> $$
> (\boldsymbol e_\theta)^\rho =
> \begin{cases}
> 0 & \rho=r\\
> 1 & \rho=\theta
> \end{cases}
> $$
>
> となる。つまり、
>
> $$
> \bigl(
> (\boldsymbol e_\theta)^r,
> (\boldsymbol e_\theta)^\theta
> \bigr) =
> (0,1)
> $$
>
> である。これは、
>
> $$
> \boldsymbol e_\theta =
> 0\boldsymbol e_r
> +
> 1\boldsymbol e_\theta
> $$
>
> という、基底ベクトルを何倍ずつ使うかを表しているだけであり、ベクトルの長さを表しているわけではない。
>
> 長さの二乗は、成分の単純な二乗和ではなく、計量を使って、
>
> $$
> \begin{aligned}
> \lVert\boldsymbol e_\theta\rVert^2
> &=
> g_{\rho\sigma}
> (\boldsymbol e_\theta)^\rho
> (\boldsymbol e_\theta)^\sigma\\
> &=
> g_{\theta\theta}\\
> &=
> r^2
> \end{aligned}
> $$
>
> と求める。したがって、
>
> $$
> \lVert\boldsymbol e_\theta\rVert=r
> $$
>
> である。これは、半径 $r$ の場所で角度を $d\theta$ だけ変えると、実際には $r\,d\theta$ だけ進むことに対応している。
>
> 極座標の座標基底 $\boldsymbol e_\theta$ と、角度方向の単位ベクトルは同じではない。単位ベクトルを $\hat{\boldsymbol{e}}_\theta$ と書けば、
>
> $$
> \hat{\boldsymbol{e}}_\theta =
> \frac{1}{r}\boldsymbol e_\theta
> $$
>
> であり、こちらの長さが $1$ になる。

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

によって、新しい量 $\Gamma_{\sigma\mu\nu}$ を定義する。これは、クリストッフェル記号の上付き添字を計量で下げた量である。

先ほどの式は、

$$
\boxed{
\partial_\lambda g_{\mu\nu}
=\Gamma_{\nu\lambda\mu}
+\Gamma_{\mu\lambda\nu}
}
$$

となる。この式が導出の出発点である。

## 計量の共変微分を確かめる

先ほど得た式を、共変微分を使って読み直してみよう。

04で導いたように、下付き添字を二つ持つテンソル $T_{\mu\nu}$ の共変微分は、

$$
\nabla_\lambda T_{\mu\nu}
\coloneqq \partial_\lambda T_{\mu\nu}
-\Gamma^\rho_{\lambda\mu}T_{\rho\nu}
-\Gamma^\rho_{\lambda\nu}T_{\mu\rho}
$$

である。通常の偏微分に、下付き添字一つにつき一つの補正項が加わる。この補正項が、基底の変化を考慮する役割を担う。

計量 $g_{\mu\nu}$ も下付き添字を二つ持つテンソルなので、この定義を適用すると、

$$
\nabla_\lambda g_{\mu\nu}
=\partial_\lambda g_{\mu\nu}
-\Gamma^\rho_{\lambda\mu}g_{\rho\nu}
-\Gamma^\rho_{\lambda\nu}g_{\mu\rho}
$$

となる。ここに、先ほど基底の内積を偏微分して得た式、

<a id="eq-metric-compatibility"></a>

$$
\partial_\lambda g_{\mu\nu}
=\Gamma^\rho_{\lambda\mu}g_{\rho\nu}
+\Gamma^\rho_{\lambda\nu}g_{\mu\rho}
\qquad (5.1)
$$

を代入すると、右辺の項が打ち消し合い、

$$
\boxed{
\nabla_\lambda g_{\mu\nu}=0
}
$$

を得る。この条件を計量適合性と呼ぶ。

ここでは、平面上に基底 $\boldsymbol e_\mu$ を実際に描き、その内積から計量を定め、基底の変化からクリストッフェル記号を定めた。そのため、計量適合性は、それらの定義から確かめられる性質として現れた。

一方、一般の曲がった時空では、異なる場所にある基底をそのまま比べることはできない。そこで、計量を長さや内積の測り方、接続をベクトルの運び方として、まず別々の規則と考える。この立場では、どの接続を選んでも計量適合性が自動的に成り立つわけではない。以下では、いま確かめた性質を、接続に課す条件として改めて採用する。

この条件は、次章で説明する平行移動において、二つのベクトルの内積が保たれることに対応する。平行移動の定義と、内積が保たれる理由は、[06の「平行移動で内積が保たれる」](./06-ParallelTransportAndGeodesics.md#平行移動で内積が保たれる)で説明する。

## 下二つの添字が対称になるという条件

ここで、接続という言葉の意味を確認しておこう。

04では、場所によって基底が変わるため、ベクトルの成分の数字だけを比べても、ベクトル全体の変化は分からないことを見た。

そこで、ある場所の矢印をすぐ隣の場所へ運び、そこでの矢印と比べることを考えよう。平面なら「向きと長さを変えずに運ぶ」と考えられる。しかし、曲がった空間では、どのように運べば「変えずに運んだ」ことになるのか、その規則が必要になる。

この、隣の場所へベクトルを運んで比べるための規則を、接続と呼ぶ。その規則に従って運ぶことが平行移動である。

例えば、各場所に風速を表す矢印があると考えよう。このように、場所ごとにベクトルが与えられているものを、ベクトル場という。

ある地点 $P$ の風速の矢印を、接続の規則に従ってすぐ隣の地点 $Q$ へ運ぶ。そして、「 $P$ から運んできた矢印」と「 $Q$ での風速を表す矢印」を、同じ場所で比べる。この二つの矢印の差を移動量で割り、移動量をゼロに近づけて変化を測るのが、移動方向の共変微分である。

これまで使ってきた式、

$$
\nabla_\mu V^\rho
=\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}V^\nu
$$

では、 $\partial_\mu V^\rho$ が成分の数字の変化を表し、 $\Gamma^\rho_{\mu\nu}V^\nu$ が、その規則に従ってベクトルを比べるための補正を表す。04の平面の例では、この補正は基底の変化から生じた。

この $\Gamma^\rho_{\mu\nu}$ が、接続を選んだ座標で表す係数である。今の段階では、「接続を決めるとは、共変微分の式に入る $\Gamma^\rho_{\mu\nu}$ を決めること」と捉えれば、この先の計算を追える。

計量は、ベクトルの長さや内積の「測り方」を定める。一方、接続は、ベクトルの「運び方・比べ方」を定める。計量適合性（ $\nabla_\lambda g_{\mu\nu}=0$）は、この二つを結びつけ、平行に運んでも内積が保たれることを要求する条件である。

しかし、計量適合性の式だけでは、 $\Gamma^\rho_{\mu\nu}$ は一つに決まらない。そこで、もう一つ条件を加える。

04の極座標の例では、クリストッフェル記号の下二つの添字は対称だった。この章でも、座標基底で表したクリストッフェル記号について、この対称性を仮定する。つまり、

$$
\boxed{
\Gamma^\rho_{\mu\nu}=\Gamma^\rho_{\nu\mu}
}
$$

と仮定する。例えば、 $\Gamma^r_{r\theta}=\Gamma^r_{\theta r}$ とする。

これは、計量適合性から導かれた結論ではなく、ここで追加する条件である。04の例はこの条件に親しむための手掛かりであり、一般の場合の証明ではない。

以下では、計量適合性とこの対称性を使って、クリストッフェル記号の具体的な式を求めよう。

---

Alice「計量を偏微分するだけでは、まだ式が一つに決まらないの？」

Bob「うん。ここでは計量適合性に加えて、下二つの添字を交換しても値が変わらないと仮定する。その二条件から、具体的な式を求めるんだ。」

---

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

仮定した下二つの添字の対称性により、

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

![図書室で二本の式を足して一本を引く仕組みを確かめるAliceとBob](../../../images/general-relativity/05/combining-equations-in-library.png)

## 逆計量で添字を上げる

逆計量 $g^{\rho\sigma}$ を使って、

$$
\Gamma^\rho_{\mu\nu}
=g^{\rho\sigma}\Gamma_{\sigma\mu\nu}
$$

と添字を上げる。先ほどの式を代入すると、

<a id="eq-christoffel-from-metric"></a>

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
\qquad (5.2)
$$

となる。これが、計量からクリストッフェル記号を求める公式である。

得られた式が、最初に仮定した対称性を満たすことを確認しよう。 $\mu$ と $\nu$ を交換すると、

$$
\Gamma^\rho_{\nu\mu}
=\frac{1}{2}g^{\rho\sigma}
\left(
\partial_\nu g_{\sigma\mu}
+\partial_\mu g_{\sigma\nu}
-\partial_\sigma g_{\nu\mu}
\right)
$$

となる。最初の二項は順序が入れ替わっただけであり、最後の項も、計量の対称性 $g_{\nu\mu}=g_{\mu\nu}$ によって元と同じになる。したがって、

$$
\Gamma^\rho_{\nu\mu}=\Gamma^\rho_{\mu\nu}
$$

が確かめられる。これは、得られた式が採用した仮定と整合していることの確認であり、対称性そのものを導いたわけではないことに注意しよう。この対称性は一般の接続で必ず成り立つ性質ではなく、本書では追加の条件として採用する。その幾何学的な背景の詳しい説明は、本書の範囲外とする。

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

次に、 $\rho=\theta,\mu=r,\nu=\theta$ を代入する。

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

となる。仮定した下二つの添字の対称性により、

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

![噴水広場で基底と計量から求めたクリストッフェル記号の一致を確かめるAliceとBob](../../../images/general-relativity/05/polar-coordinates-at-fountain.png)

## 何を仮定していたのか

前半で具体的な基底から確かめた計量適合性を、ここでは一般の接続に課す条件として採用した。今回の公式は、計量だけから無条件に得られたわけではなく、次の二条件を使っている。

1. 計量適合性

$$
\nabla_\lambda g_{\mu\nu}=0
$$

2. クリストッフェル記号の下二つの添字が対称であること

$$
\Gamma^\rho_{\mu\nu}=\Gamma^\rho_{\nu\mu}
$$

この二条件を採用すると、与えられた計量からクリストッフェル記号が一つに決まる。

一般相対論では、通常、この二条件を満たすものを使う。

> 計量適合性と下二つの添字の対称性を条件にすると、計量からクリストッフェル記号を求められる

と考えられる。

補足として名称を挙げると、座標基底での下二つの添字の対称性は「捩率（れいりつ）ゼロ」と呼ばれる。また、計量適合性とこの対称性を満たす接続を「レヴィ・チヴィタ接続」と呼ぶ。この章では、名称よりも、どの二条件を使って式を求めたかを押さえておけばよい。

## まとめ

- 計量成分は基底どうしの内積として読める。
- 計量を偏微分すると、基底の変化が二項現れる。
- クリストッフェル記号の下二つの添字が対称であると仮定する。
- 添字を入れ替えた三本の式を、二本足して一本引く。
- 逆計量で添字を上げると、

$$
\Gamma^\rho_{\mu\nu} = \frac{1}{2} g^{\rho\sigma} \left( \partial_\mu g_{\sigma\nu} + \partial_\nu g_{\sigma\mu} - \partial_\sigma g_{\mu\nu} \right)
$$

  を得る。
- 得られた公式は、仮定した下二つの添字の対称性を確かに満たしている。
- 極座標では、基底を直接微分した場合と同じクリストッフェル記号が得られる。

## 次の疑問

計量からクリストッフェル記号を求められるようになった。

共変微分を使えば、ベクトルがその場所でどのように変化しているかを表せる。

それでは、一つのベクトルをある場所から別の場所へ運ぶには、どのような条件を課せばよいのだろうか。

また、空間や時空の中で「可能な限り真っ直ぐ進む」とは、どのような意味なのだろうか。

次の文書では、経路に沿う共変微分から平行移動を定義し、測地線と自由落下へ進む。
