# シュヴァルツシルト解を計算する

## はじめに

前の文書[「球対称な時空を予想する」](./09-SphericallySymmetricSpacetime.md)では、静的で球対称な計量を、

$$
ds^2=-A(r)\,dw^2+B(r)\,dr^2
+r^2(d\theta^2+\sin^2\theta\,d\phi^2)
$$

という形に絞った。 $w=ct$ であり、 $r$ は球面の面積が $4\pi r^2$ になるように選んだ面積半径である。

未知なのは、二つの関数 $A(r),B(r)$ である。この章では、物質や電磁場がなく、宇宙定数もゼロの領域で、

$$
R_{\mu\nu}=0
$$

を満たすように、この二つを求める。前章に続き、 $A,B>0$ の静的な領域を扱う。

---

Alice「未知の関数は二つになったけれど、方程式にはまだリッチテンソルがあるね。」

Bob「計量を微分して接続を作り、接続からリッチテンソルを計算しよう。そうすれば、 $A,B$ が満たす微分方程式になるよ。」

---

## 計量のどの成分が変化するか

![庭の机に球面模型とノートを広げ、計量からの計算に取り組むAliceとBob](../../../images/general-relativity/10/alice-bob-start-calculation.png)

座標の順序を $(w,r,\theta,\phi)$ とすると、計量と逆計量は、

$$
g_{\mu\nu}=
\begin{pmatrix}
-A&0&0&0\\
0&B&0&0\\
0&0&r^2&0\\
0&0&0&r^2\sin^2\theta
\end{pmatrix},
\qquad
g^{\mu\nu}=
\begin{pmatrix}
-1/A&0&0&0\\
0&1/B&0&0\\
0&0&1/r^2&0\\
0&0&0&1/(r^2\sin^2\theta)
\end{pmatrix}
$$

である。式を短くするため、 $A(r),B(r)$ の引数を省略した。以下、プライムは $r$ による微分を表す。

ゼロでない計量成分の微分を、先に並べておこう。

$$
\begin{aligned}
\partial_r g_{ww}&=-A',&
\partial_r g_{rr}&=B',\\
\partial_r g_{\theta\theta}&=2r,&
\partial_r g_{\phi\phi}&=2r\sin^2\theta,\\
\partial_\theta g_{\phi\phi}&=2r^2\sin\theta\cos\theta.
\end{aligned}
$$

これ以外はゼロである。特に、どの成分も $w,\phi$ には依存しない。ただし、 $g_{\phi\phi}$ は角度座標の性質により $\theta$ に依存する。

## クリストッフェル記号を求める

第5章の[式 (5.2)](./05-ChristoffelFromMetric.md#eq-christoffel-from-metric)は、

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
$$

だった。今回は逆計量が対角行列なので、上の添字 $\rho$ を固定すると、和の中で残るのは $\sigma=\rho$ だけである。

### 時間と動径に関する成分

まず $\Gamma^w_{wr}$ では、

$$
\begin{aligned}
\Gamma^w_{wr}
&=\frac12g^{ww}
\left(
\partial_w g_{wr}
+\partial_r g_{ww}
-\partial_w g_{wr}
\right)\\
&=\frac12\left(-\frac1A\right)(-A')
=\frac{A'}{2A}.
\end{aligned}
$$

次に $\Gamma^r_{ww}$ では、時間微分がゼロなので、

$$
\begin{aligned}
\Gamma^r_{ww}
&=\frac12g^{rr}
\left(
\partial_w g_{rw}
+\partial_w g_{rw}
-\partial_r g_{ww}
\right)\\
&=\frac1{2B}A'
=\frac{A'}{2B}.
\end{aligned}
$$

二つのマイナスが打ち消し合うことに注意しよう。最後に、

$$
\Gamma^r_{rr}
=\frac1{2B}(B'+B'-B')
=\frac{B'}{2B}
$$

となる。

### 動径と角度に関する成分

$g_{\theta\theta}=r^2$ を使えば、

$$
\Gamma^r_{\theta\theta}
=-\frac1{2B}\partial_r(r^2)
=-\frac rB,
\qquad
\Gamma^\theta_{r\theta}
=\frac1{2r^2}\partial_r(r^2)
=\frac1r.
$$

$\phi$ 方向も同じ手順で、

$$
\Gamma^r_{\phi\phi}
=-\frac1{2B}\partial_r(r^2\sin^2\theta)
=-\frac{r\sin^2\theta}{B},
$$

$$
\Gamma^\phi_{r\phi}
=\frac1{2r^2\sin^2\theta}
\partial_r(r^2\sin^2\theta)
=\frac1r
$$

となる。

角度による微分からは、

$$
\Gamma^\theta_{\phi\phi}
=-\frac1{2r^2}\partial_\theta(r^2\sin^2\theta)
=-\sin\theta\cos\theta,
$$

$$
\Gamma^\phi_{\theta\phi}
=\frac1{2r^2\sin^2\theta}
\partial_\theta(r^2\sin^2\theta)
=\frac{\cos\theta}{\sin\theta}
=\cot\theta
$$

を得る。

下の二添字を交換したものも同じ値を持つ。以上がゼロでない成分のすべてである。

### 計算に使う略記

繰り返し現れる三つの量を、

$$
\alpha=\frac{A'}{2A},\qquad
\beta=\frac{B'}{2B},\qquad
q=\frac{A'}{2B}
$$

と略記する。これらは新しい未知関数を増やすものではなく、 $A,B$ とその微分の別名である。

接続成分を整理すると、次の表になる。

| 成分 | 値 |
|---|---|
| $\Gamma^w_{wr}=\Gamma^w_{rw}$ | $\alpha$ |
| $\Gamma^r_{ww}$ | $q$ |
| $\Gamma^r_{rr}$ | $\beta$ |
| $\Gamma^r_{\theta\theta}$ | $-r/B$ |
| $\Gamma^r_{\phi\phi}$ | $-r\sin^2\theta/B$ |
| $\Gamma^\theta_{r\theta}=\Gamma^\theta_{\theta r}$ | $1/r$ |
| $\Gamma^\phi_{r\phi}=\Gamma^\phi_{\phi r}$ | $1/r$ |
| $\Gamma^\theta_{\phi\phi}$ | $-\sin\theta\cos\theta$ |
| $\Gamma^\phi_{\theta\phi}=\Gamma^\phi_{\phi\theta}$ | $\cot\theta$ |

## 接続からリッチテンソルへ

第7章の[式 (7.2)](./07-CurvatureFromParallelTransport.md#eq-riemann-curvature)で、最初の上付き添字と三番目の添字を縮約すると、リッチテンソルになる。

曲率の定義に ${R^\lambda}_{\mu\lambda\nu}$ を代入して、

$$
\begin{aligned}
R_{\mu\nu}
={}&\partial_\lambda\Gamma^\lambda_{\nu\mu}
-\partial_\nu\Gamma^\lambda_{\lambda\mu}\\
&+\Gamma^\lambda_{\lambda\sigma}\Gamma^\sigma_{\nu\mu}
-\Gamma^\lambda_{\nu\sigma}\Gamma^\sigma_{\lambda\mu}
\end{aligned}
\qquad (10.1)
$$

を得る。 $\lambda,\sigma$ は $w,r,\theta,\phi$ の四つについて和を取る。

これから各成分を求めるときは、この式の右辺を第一項から第四項まで順番に計算する。

第三項などに現れる接続の和を、先に求めておこう。

$$
\begin{aligned}
\Gamma^\lambda_{\lambda r}
&=\Gamma^w_{wr}+\Gamma^r_{rr}
+\Gamma^\theta_{\theta r}+\Gamma^\phi_{\phi r}\\
&=\alpha+\beta+\frac2r.
\end{aligned}
$$

これを $S=\alpha+\beta+2/r$ と略記する。また、

$$
\Gamma^\lambda_{\lambda\theta}=\cot\theta,\qquad
\Gamma^\lambda_{\lambda w}
=\Gamma^\lambda_{\lambda\phi}=0
$$

である。

## 時間成分 Rww を計算する

式 (10.1) で $\mu=\nu=w$ とする。

第一項では、 $\Gamma^\lambda_{ww}$ がゼロでないのは $\lambda=r$ だけなので、

$$
\partial_\lambda\Gamma^\lambda_{ww}
=\partial_r\Gamma^r_{ww}
=q'
$$

となる。第二項は時間微分なのでゼロである。

第三項では $\sigma=r$ だけが残り、

$$
\Gamma^\lambda_{\lambda\sigma}\Gamma^\sigma_{ww}
=Sq
$$

となる。

第四項で残るのは、 $(\lambda,\sigma)=(w,r),(r,w)$ の二組である。

$$
\begin{aligned}
-\Gamma^\lambda_{w\sigma}\Gamma^\sigma_{\lambda w}
&=-\Gamma^w_{wr}\Gamma^r_{ww}
-\Gamma^r_{ww}\Gamma^w_{rw}\\
&=-2\alpha q.
\end{aligned}
$$

四項を足せば、

$$
R_{ww}=q'+qS-2\alpha q
=q'+q\left(-\alpha+\beta+\frac2r\right).
$$

ここで $q=(A/B)\alpha$ を使う。積と商の微分から、

$$
\left(\frac AB\right)'
=\frac AB\left(\frac{A'}A-\frac{B'}B\right)
=\frac AB(2\alpha-2\beta)
$$

なので、

$$
q'=\frac AB\left[\alpha'+(2\alpha-2\beta)\alpha\right].
$$

これを代入してまとめると、

$$
\boxed{
R_{ww}
=\frac AB
\left(\alpha'+\alpha^2-\alpha\beta+\frac{2\alpha}{r}\right)
}
\qquad (10.2)
$$

を得る。

## 動径成分 Rrr を計算する

今度は $\mu=\nu=r$ とする。

第一項は $\beta'$、第二項は $-S'$、第三項は $\beta S$ になる。

第四項では、 $\Gamma^\lambda_{r\sigma}$ がゼロでないのは $\lambda=\sigma$ の四組である。そのため、

$$
-\Gamma^\lambda_{r\sigma}\Gamma^\sigma_{\lambda r}
=-\left(\alpha^2+\beta^2+\frac1{r^2}+\frac1{r^2}\right).
$$

したがって、

$$
R_{rr}
=\beta'-S'+\beta S-\alpha^2-\beta^2-\frac2{r^2}.
$$

$S=\alpha+\beta+2/r$ を微分すると、

$$
S'=\alpha'+\beta'-\frac2{r^2}
$$

なので、

$$
\begin{aligned}
R_{rr}
={}&\beta'-\alpha'-\beta'+\frac2{r^2}\\
&+\alpha\beta+\beta^2+\frac{2\beta}{r}
-\alpha^2-\beta^2-\frac2{r^2}.
\end{aligned}
$$

$\beta'$、 $\beta^2$、 $2/r^2$ がそれぞれ打ち消し合い、

$$
\boxed{
R_{rr}
=-\alpha'-\alpha^2+\alpha\beta+\frac{2\beta}{r}
}
\qquad (10.3)
$$

となる。

## 二つの式から AB を求める

![二冊のノートを見比べ、二つの式を組み合わせる手掛かりに気づくAliceとBob](../../../images/general-relativity/10/alice-bob-combine-equations.png)

---

Alice「どちらにも $\alpha'$ や $\alpha^2$ があるね。ここからどう解くの？」

Bob「時間成分の式に $B/A$ を掛けてから足すと、その項が消えるよ。まず二つの未知関数の関係を取り出そう。」

---

いま扱っている星の外側は、重力があっても物質や電磁場のない真空領域である。宇宙定数をゼロとしているので、真空の方程式から $R_{ww}=R_{rr}=0$ となる。したがって、式 (10.2)、(10.3) より、

$$
\begin{aligned}
0
&=\frac BA R_{ww}+R_{rr}\\
&=\frac{2(\alpha+\beta)}r.
\end{aligned}
$$

$r>0$ の領域で考えているため、

$$
\boxed{\alpha+\beta=0\qquad\Longleftrightarrow\qquad\beta=-\alpha}
$$

定義に戻せば、

$$
\frac{A'}A+\frac{B'}B=0.
$$

左辺は $\ln(AB)$ の微分である。したがって、

$$
\frac{d}{dr}\ln(AB)=0
\quad\Longrightarrow\quad
AB=K
$$

となる。 $K$ は $r$ によらない定数である。

前章で選んだ、遠方で $A\to1$、 $B\to1$ という条件を使うと $K=1$ なので、

$$
\boxed{B=\frac1A}
$$

を得る。ここで初めて、二つの未知関数が一つに減った。

## 角度成分 Rθθ を計算する

残った関数を求めるため、式 (10.1) で $\mu=\nu=\theta$ とする。

第一項では $\lambda=r$ だけが残るので、

$$
\partial_\lambda\Gamma^\lambda_{\theta\theta}
=\frac{d}{dr}\left(-\frac rB\right)
=-\frac1B+\frac{rB'}{B^2}.
$$

第二項では $\lambda=\phi$ だけが残るので、

$$
-\partial_\theta\Gamma^\lambda_{\lambda\theta}
=-\frac{d}{d\theta}\cot\theta
=\frac1{\sin^2\theta}
$$

であり、第三項は $-rS/B$ である。

第四項では、 $(\lambda,\sigma)=(r,\theta),(\theta,r),(\phi,\phi)$ が残る。

$$
\begin{aligned}
-\Gamma^\lambda_{\theta\sigma}\Gamma^\sigma_{\lambda\theta}
&=-\left[
\left(-\frac rB\right)\frac1r
+\frac1r\left(-\frac rB\right)
+\cot^2\theta
\right]\\
&=\frac2B-\cot^2\theta.
\end{aligned}
$$

四項を足し、 $1/\sin^2\theta-\cot^2\theta=1$ を使うと、

$$
R_{\theta\theta}
=1+\frac1B+\frac{rB'}{B^2}-\frac{rS}{B}.
$$

ここに $B'/B=2\beta$ と $S=\alpha+\beta+2/r$ を代入して、

$$
\begin{aligned}
R_{\theta\theta}
&=1+\frac1B+\frac{2r\beta}{B}
-\frac rB\left(\alpha+\beta+\frac2r\right)\\
&=1-\frac1B+\frac rB(\beta-\alpha).
\end{aligned}
$$

したがって、

$$
\boxed{
R_{\theta\theta}
=1-\frac1B+\frac rB(\beta-\alpha)
}
\qquad (10.4)
$$

である。

## 残った微分方程式を解く

すでに $B=1/A$、 $\beta=-\alpha$ と分かったので、式 (10.4) は、

$$
R_{\theta\theta}
=1-A-2rA\alpha
$$

になる。 $\alpha=A'/(2A)$ より $2A\alpha=A'$ なので、真空の条件は、

$$
1-A-rA'=0
$$

である。つまり、

$$
A+rA'=1.
$$

左辺は積 $rA$ の微分そのものである。

$$
\frac{d}{dr}(rA)=1.
$$

両辺を $r$ で積分すると、

$$
rA=r+C
$$

となる。 $C$ は積分定数である。この定数を $C=-\ell$ と書けば、

$$
A=1-\frac{\ell}{r},\qquad
B=\left(1-\frac{\ell}{r}\right)^{-1}.
\qquad (10.5)
$$

この段階では、 $\ell$ の値も符号もまだ決めていない。 $A$ は無次元なので、 $\ell$ は長さの単位を持つ。

## 使っていない方程式も確かめる

![計算用紙を順に並べ、求めた解を一緒に確かめるAliceとBob](../../../images/general-relativity/10/alice-bob-check-solution.png)

二つの式を足して得た条件だけでは、それぞれがゼロになるとは限らない。求めた関数を、もとの方程式へ戻して確認しよう。

$\beta=-\alpha$、 $B=1/A$ を式 (10.2) に入れると、

$$
R_{ww}=A^2\left(\alpha'+2\alpha^2+\frac{2\alpha}{r}\right).
$$

ここで、

$$
\alpha'
=\frac{A''}{2A}-\frac{(A')^2}{2A^2},
\qquad
2\alpha^2=\frac{(A')^2}{2A^2}
$$

なので、

$$
R_{ww}
=\frac A2\left(A''+\frac{2A'}r\right).
$$

$A=1-\ell/r$ なら、

$$
A'=\frac{\ell}{r^2},\qquad
A''=-\frac{2\ell}{r^3}
$$

だから、確かに $R_{ww}=0$ になる。さらに $\frac BA R_{ww}+R_{rr}=0$ より $R_{rr}=0$ も成り立つ。

### もう一つの角度成分

$R_{\phi\phi}$ も、式 (10.1) の四項を順に計算して確かめられる。

第一項では $r$ 微分と $\theta$ 微分が残り、

$$
\begin{aligned}
\partial_\lambda\Gamma^\lambda_{\phi\phi}
&=\partial_r\left(-\frac{r\sin^2\theta}{B}\right)
+\partial_\theta(-\sin\theta\cos\theta)\\
&=\sin^2\theta\left(-\frac1B+\frac{rB'}{B^2}\right)
+\sin^2\theta-\cos^2\theta.
\end{aligned}
$$

第二項は $\phi$ 微分なのでゼロである。第三項は、

$$
-\frac{r\sin^2\theta}{B}S-\cos^2\theta.
$$

第四項では $(r,\phi),(\phi,r),(\theta,\phi),(\phi,\theta)$ の四組が残り、

$$
-\left[
2\left(-\frac{r\sin^2\theta}{B}\right)\frac1r
+2(-\sin\theta\cos\theta)\cot\theta
\right]
=\frac{2\sin^2\theta}{B}+2\cos^2\theta.
$$

足し合わせると $\cos^2\theta$ の項が消え、

$$
\begin{aligned}
R_{\phi\phi}
&=\sin^2\theta
\left(1+\frac1B+\frac{rB'}{B^2}-\frac{rS}{B}\right)\\
&=\sin^2\theta\,R_{\theta\theta}
=0
\end{aligned}
$$

となる。

### 非対角成分について

リッチテンソルも、この計量の球対称性を受け継ぐ。第9章で計量に使った回転の議論と同じように、時間・動径と角度の交差成分、および角度どうしの非対角成分はゼロになる。

残る $R_{wr}$ は、時間座標だけを $w'=-w$ と反転し、空間座標は変えない変換で確かめられる。いまの計量は時間に依存せず、 $dw\,dr$ の項もないので、この反転で変わらない。

一方、 $R_{wr}$ の二つの添字は、 $w$ が時間方向、 $r$ が動径方向を表す。下付き添字を二つ持つテンソルの変換則を使うと、 $r'=r$ なので、

$$
\begin{aligned}
R_{w'r'}
&=\frac{\partial w}{\partial w'}
\frac{\partial r}{\partial r'}R_{wr}\\
&=(-1)(1)R_{wr}\\
&=-R_{wr}
\end{aligned}
$$

となる。時間方向の添字に対応してマイナスが一つ掛かるため、この成分の符号が反転する。

同じ幾何学から作る成分が、時間によらず同じ値を持つことと合わせれば、

$$
R_{wr}=-R_{wr}
\quad\Longrightarrow\quad
R_{wr}=0
$$

である。これで、真空の方程式の全成分を満たすことが確かめられた。

## 積分定数を星の質量と結びつける

---

Alice「方程式は解けたけれど、 $\ell$ が残っているね。」

Bob「真空の方程式だけでは、中心の星の質量までは指定していないからね。遠方でニュートンの重力と比べて、この定数の意味を決めよう。」

---

第8章の[式 (8.1)](./08-EinsteinEquation.md#eq-newtonian-time-metric)では、弱い重力場での時間方向の計量を求めた。そこでは $x^0=w=ct$ としていたので、 $g_{00}$ は、ここで使う $g_{ww}$ と同じ成分である。したがって、

$$
g_{ww}=g_{00}\simeq-\left(1+\frac{2\Phi}{c^2}\right)
$$

となる。 $\Phi$ は単位質量あたりの重力ポテンシャルである。

球対称な天体の外側では、遠方で $\Phi\to0$ と選ぶと、

$$
\Phi=-\frac{GM}{r}
$$

なので、

$$
g_{ww}\simeq-\left(1-\frac{2GM}{c^2r}\right).
$$

一方、いま求めた解では、

$$
g_{ww}=-A=-\left(1-\frac{\ell}{r}\right).
$$

遠方の $1/r$ の係数を比較すると、

$$
\ell=\frac{2GM}{c^2}
$$

と決まる。ここで $M$ は、遠方の重力場から読み取る天体の質量である。

ニュートン近似を使ったのは、積分定数の意味を決めるためである。式 (10.5) 自体は、近似せずに真空の方程式を解いて得ている。

## シュヴァルツシルト解

![天文台で星の模型を囲み、その外側の時空を表す解が求まったことを喜ぶAliceとBob](../../../images/general-relativity/10/alice-bob-schwarzschild-discovery.png)

長さ、

$$
r_{\mathrm s}=\frac{2GM}{c^2}
$$

をシュヴァルツシルト半径と呼ぶ。これは質量 $M$ から決まる長さであり、星の表面までの半径とは異なる。

例えば、太陽の表面の半径は[約70万 km](https://science.nasa.gov/sun/facts/)だが、太陽の質量から計算したシュヴァルツシルト半径は[約3 km](https://www.einstein-online.info/en/explandict/schwarzschild-radius/)である。太陽のような普通の星では、 $r_{\mathrm s}$ は星の表面の半径よりはるかに小さい。

ただし、太陽の内部の $r=3\,\mathrm{km}$ に事象の地平面がある、という意味ではない。今回求めたのは星の外側の真空解であり、物質のある内部へそのまま延長して使うことはできない。

式 (10.5) に $\ell=r_{\mathrm s}$ を代入すると、

$$
A(r)=1-\frac{r_{\mathrm s}}r,\qquad
B(r)=\left(1-\frac{r_{\mathrm s}}r\right)^{-1}
$$

である。これらを、もとの線素に代入すれば、

$$
\boxed{
\begin{aligned}
ds^2
&=-A(r)\,dw^2+B(r)\,dr^2
+r^2(d\theta^2+\sin^2\theta\,d\phi^2)\\
&=-\left(1-\frac{r_{\mathrm s}}r\right)dw^2
+\frac{dr^2}{1-r_{\mathrm s}/r}\\
&\quad+r^2(d\theta^2+\sin^2\theta\,d\phi^2)
\end{aligned}
}
$$

となる。これがシュヴァルツシルト解である。

この章で求めた解は、星の表面より外の真空領域で使う。普通の星では表面の半径が $r_{\mathrm s}$ より大きいため、その外側では $r>r_{\mathrm s}$ も満たされる。星の内部には物質があるので、同じ真空の方程式は使えない。

$M=0$ なら $r_{\mathrm s}=0$ となり、

$$
ds^2=-dw^2+dr^2+r^2d\Omega^2
$$

という平坦な時空の線素に戻る。また、 $M\ne0$ でも、十分遠方ではこの形に近づく。

## 解を時計と物差しへつなぐ

![座標の図と時計・物差しを見比べ、求めた計量を測定につなげて考えるAliceとBob](../../../images/general-relativity/10/alice-bob-read-measurements.png)

第9章で求めた、静止する時計と動径方向の物差しの式に、 $A,B$ を代入してみよう。

$$
\begin{aligned}
d\tau
&=\sqrt{A(r)}\,dw
=\sqrt{1-\frac{r_{\mathrm s}}r}\,dw,\\
d\ell
&=\sqrt{B(r)}\,|dr|
=\frac{|dr|}{\sqrt{1-r_{\mathrm s}/r}}.
\end{aligned}
$$

計量を解いたことで、座標の差と測定値を結ぶ係数が具体的に分かった。ただし、最初の式は、その場所に静止する時計についての式である。運動する時計では空間方向の変位も線素に寄与する。

---

Alice「最初は名前だけだった $A,B$ が、時計や物差しの読み方になったね。」

Bob「次は、この座標の数字と、実際に測る時間や長さを区別しながら、式が何を教えているか読んでいこう。」

---

$r=r_{\mathrm s}$ では、この座標表示の係数にゼロや発散が現れる。しかし、それだけで時空そのものが壊れているとは判断できない。静止する観測者とこの座標が使える範囲については、後の章で改めて調べる。

次の文書[「座標というキャンバスと局所的な測定」](./11-CoordinatesAndLocalMeasurements.md)では、座標を時空の出来事に付ける目印として捉え直し、局所的な時計や物差しによる測定との対応を整理しよう。
