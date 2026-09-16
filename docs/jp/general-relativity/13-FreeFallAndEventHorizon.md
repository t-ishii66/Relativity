# 自由落下と事象の地平面

## はじめに

前の文書[「重力赤方偏移と光の進み方」](./12-GravitationalRedshiftAndLight.md)では、静止する Alice が送る光を、外側に静止する Charlie が受け取った。二人の位置が変わらないため、続けて送った信号は、同じ座標時をかけて届いた。

今度は、Bob が Alice のいる場所から自由落下する。Bob も時計と発光装置を持ち、落下しながら外側の Charlie へ光を送る。

Bob の時計はどれだけ進むのか。その光は Charlie にどのように届くのか。地平面へ近づく落下を例に、Bob 自身が経験する時間、座標で描いた運動、Charlie が受け取る光を区別して考えよう。

この章でも、$w$ と固有時 $\tau$ は、通常の時間に $c$ を掛けた距離単位の量である。

## 今回の舞台と三人の役割

まず、外側の $r>r_{\mathrm s}$ では、これまでと同じ計量を使う。

$$
f(r)=1-\frac{r_{\mathrm s}}r,\qquad
r_{\mathrm s}=\frac{2GM}{c^2},
$$

$$
ds^2=-f(r)dw^2+\frac{dr^2}{f(r)}+r^2d\Omega^2,
\qquad
d\Omega^2=d\theta^2+\sin^2\theta\,d\phi^2.
\tag{13.1}
$$

ただし、地平面までの落下を考えるため、ここからは**回転も電荷も持たないブラックホールの、時間に依存しない理想的なモデル**を扱う。落下する Bob の質量や、送る光による時空への影響は無視する。

事象の地平面とは、その内側から遠方へ光を届けられなくなる境界である。今回扱うブラックホールでは、$r=r_{\mathrm s}$ がその境界に当たる。この章では、まずその外側 $r>r_{\mathrm s}$ から地平面へ近づく Bob の運動と、Bob が外向きに送る光を調べる。

普通の星で、表面が $r_{\mathrm s}$ より外側にある場合には、Bob は地平面に近づく前に星の表面に着く。星の物質がある場所へ真空の計量をそのまま使うことはできない。今回の舞台は、その場合とは区別する。

| 登場人物 | 役割 |
|---|---|
| Alice | $r=r_0>r_{\mathrm s}$ に支えられて静止する |
| Bob | Alice の隣で相対速度ゼロから自由落下を始め、動径方向に進む |
| Charlie | 重力の影響を無視できるほど遠い $r=r_{\mathrm{Charlie}}>r_0$ に静止し、Bob から外向きに届く光を受け取る |

Alice と Charlie はその場所にとどまるための支えを持つ。Bob は出発後、ロケットを噴射せず、重力以外の力を受けないものとする。

Charlie の位置は十分遠く、$r_{\mathrm s}/r_{\mathrm{Charlie}}$ を無視できるとする。この章では、その近似のもとで $f(r_{\mathrm{Charlie}})=1$ として計算する。したがって、

$$
d\tau_{\mathrm{Charlie}}=dw
$$

となり、Charlie の時計の進みは座標時の進みと一致する。Charlie は遠いが有限の位置に置き、光が届くまでの時間は、これまでどおり経路に沿って計算する。

---

Alice「Bob の時計も、私の時計と同じように $d\tau=\sqrt f\,dw$ で計算できるの？」

Bob「僕は場所を変えるから、空間方向の項も残るよ。まず、どう落ちるのかを求めよう。」

---

## 自由落下の運動を決める量

![落下実験カプセルのBobを足場から見送るAlice](../../../images/general-relativity/13/alice-bob-fall-capsule.png)

*時計を持って落下実験に臨む Bob と、見送る Alice。自由落下を考えるためのイメージ。*

Bob の固有時を $\tau_{\mathrm{Bob}}$ とし、以下の点はそれによる微分を表すことにする。

$$
\dot w=\frac{dw}{d\tau_{\mathrm{Bob}}},\qquad
\dot r=\frac{dr}{d\tau_{\mathrm{Bob}}}.
$$

動径方向だけの運動なので $d\theta=d\phi=0$ である。Bob の軌道では $ds^2=-d\tau_{\mathrm{Bob}}^2$ だから、式 (13.1) を $d\tau_{\mathrm{Bob}}^2$ で割ると、

$$
-1=-f(r)\dot w^2+\frac{\dot r^2}{f(r)}.
\tag{13.2}
$$

もう一つ、自由落下の条件を使おう。第6章で導いた[測地線方程式 (6.3)](./06-ParallelTransportAndGeodesics.md#eq-geodesic-equation)を、もう一度書くと、

$$
\frac{d^2x^\rho}{d\lambda^2}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}
\frac{dx^\nu}{d\lambda}
=0
$$

である。$\rho$ は、どの座標成分の運動を調べるかを指定する添字であり、繰り返される $\mu,\nu$ については、すべての座標方向の和を取る。

今回はパラメータ $\lambda$ に Bob の固有時 $\tau_{\mathrm{Bob}}$ を選び、$\rho=w$ とする。すると、時間座標 $w$ の変化を決める式として、

$$
\ddot w+\sum_{\mu,\nu}
\Gamma^w_{\mu\nu}\dot x^\mu\dot x^\nu=0
$$

を得る。ここで $\mu,\nu$ は、それぞれ $w,r,\theta,\phi$ を取る。

Bob は動径方向だけに落下するので、$\dot\theta=\dot\phi=0$ である。したがって、角度方向の速度を含む項はゼロになり、残る組み合わせは $(w,w),(w,r),(r,w),(r,r)$ の四つである。和を展開すると、

$$
\ddot w
+\Gamma^w_{ww}\dot w^2
+\Gamma^w_{wr}\dot w\dot r
+\Gamma^w_{rw}\dot r\dot w
+\Gamma^w_{rr}\dot r^2
=0.
$$

さらに、今回の計量では $\Gamma^w_{ww}$ と $\Gamma^w_{rr}$ もゼロになる。接続の式を使って、その理由を確かめよう。

クリストッフェル記号の一般式は、

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
$$

である。ここで $\rho=w$ とすると、

$$
\Gamma^w_{\mu\nu}
=\frac12g^{w\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right).
$$

右辺では、$\sigma=w,r,\theta,\phi$ について和を取る。しかし、今回の計量も逆計量も対角なので、$g^{w\sigma}$ がゼロでないのは $\sigma=w$ の場合だけである。したがって、和の中に残る $\sigma=w$ の項を書くと、

$$
\Gamma^w_{\mu\nu}
=\frac12g^{ww}
\left(
\partial_\mu g_{w\nu}
+\partial_\nu g_{w\mu}
-\partial_w g_{\mu\nu}
\right).
\tag{13.3}
$$

今回の計量は $w$ に依存せず、$g_{wr}=0$ でもある。よって、

$$
\begin{aligned}
\Gamma^w_{ww}
&=\frac12g^{ww}\partial_w g_{ww}=0,\\
\Gamma^w_{rr}
&=\frac12g^{ww}
\left(2\partial_r g_{wr}-\partial_w g_{rr}\right)=0.
\end{aligned}
$$

残る二つの接続は、下の添字を交換しても等しく、$\Gamma^w_{wr}=\Gamma^w_{rw}$ である。また、$\dot w\dot r=\dot r\dot w$ なので、二つの項を足すと、

$$
\Gamma^w_{wr}\dot w\dot r
+\Gamma^w_{rw}\dot r\dot w
=2\Gamma^w_{wr}\dot w\dot r.
$$

こうして、測地線方程式の $w$ 成分は、

$$
\ddot w+2\Gamma^w_{wr}\dot w\dot r=0
$$

となる。係数2は、添字の組み合わせ $(w,r)$ と $(r,w)$ の二つから生じたものである。

最後に、残った接続 $\Gamma^w_{wr}$ を計算する。接続の式 (13.3) で $\mu=w,\nu=r$ とし、$g_{wr}=0$ を使うと、$f'=df/dr$ として、

$$
\Gamma^w_{wr}
=\frac12 g^{ww}\partial_r g_{ww}
=\frac12\left(-\frac1f\right)(-f')
=\frac{f'}{2f}.
$$

これを代入して $f$ を掛けると、

$$
f\ddot w+f'\dot r\dot w=0.
$$

左辺は積の微分なので、

$$
\frac{d}{d\tau_{\mathrm{Bob}}}(f\dot w)=0.
$$

したがって、落下中に変わらない量として、

$$
\boxed{\varepsilon=f(r)\frac{dw}{d\tau_{\mathrm{Bob}}}}
\tag{13.4}
$$

を得る。$\varepsilon$ は無次元の正の定数であり、出発時の条件で決まる。

式 (13.2) に $\dot w=\varepsilon/f$ を代入し、両辺に $f$ を掛ければ、

$$
-f=-\varepsilon^2+\dot r^2.
$$

よって、内向きに落下する側を選ぶと、

$$
\boxed{\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\sqrt{\varepsilon^2-f(r)}}.
\tag{13.5}
$$

出発点 $r=r_0$ では $\dot r=0$ だから、

$$
\varepsilon=\sqrt{f(r_0)}
=\sqrt{1-\frac{r_{\mathrm s}}{r_0}}.
$$

したがって、Bob の落下は、

$$
\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\sqrt{r_{\mathrm s}\left(\frac1r-\frac1{r_0}\right)}
\tag{13.6}
$$

で表せる。落下して $r$ が小さくなるほど、この変化の絶対値は大きくなる。

## 座標での動きと、その場で測る速度

式 (13.4)、(13.5) の比を取ると、キャンバス上の Bob の動きは、

$$
\boxed{
\frac{dr}{dw}
=-\frac{f(r)}{\varepsilon}\sqrt{\varepsilon^2-f(r)}
}
$$

となる。$r\to r_{\mathrm s}$ では $f\to0$ なので、$dr/dw\to0$ である。

これだけを見ると、Bob は地平面の手前で動きを止めるように思える。しかし、$dr/dw$ は、共通の座標に付けた数字の変化の比だった。

Bob が通過する場所に静止する観測者を考えよう。これは各場所での測定を考えるための観測者であり、$r_0$ に残る Alice が Bob と一緒に落ちるという意味ではない。

第11章の速度の換算式 (11.6) より、その観測者が手元の時計と物差しで測る Bob の動径方向の速度は、

$$
v_{\mathrm{Bob}}
=\frac{c}{f(r)}\frac{dr}{dw}
=-c\sqrt{1-\frac{f(r)}{\varepsilon^2}}.
$$

外側のどの場所でも $|v_{\mathrm{Bob}}|<c$ だが、地平面に近い場所に静止する観測者ほど、Bob の速さが $c$ に近いと測る。

ここでの極限は、異なる場所に静止する観測者による測定を並べたものである。静止した観測者との比較は、地平面の外側で行う。地平面上に静止して待つ観測者を置いたわけではない。

## Bob の時計では、有限の固有時で地平面に着く

Bob が $r_0$ から $r<r_0$ まで落ちる間に、自分の時計が刻む固有時は、式 (13.6) を積分して、

$$
\Delta\tau_{\mathrm{Bob}}
=\int_r^{r_0}
\frac{d\rho}{\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}}.
\tag{13.7}
$$

$\rho$ は積分の中で使う半径の変数である。

地平面 $\rho=r_{\mathrm s}$ では、分母は $\sqrt{1-r_{\mathrm s}/r_0}=\varepsilon>0$ であり、積分される関数は発散しない。

一方、出発点 $\rho=r_0$ では分母がゼロになる。この部分の積分が有限になるかを、式 (13.7) から確かめよう。

まず、平方根の中の差を通分すると、

$$
\frac1\rho-\frac1{r_0}
=\frac{r_0-\rho}{\rho r_0}.
$$

したがって、式 (13.7) の積分される部分は、

$$
\begin{aligned}
\frac{d\rho}{\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}}
&=\frac{d\rho}
{\sqrt{r_{\mathrm s}(r_0-\rho)/(\rho r_0)}}\\
&=\sqrt{\frac{\rho r_0}{r_{\mathrm s}}}
\frac{d\rho}{\sqrt{r_0-\rho}}
\end{aligned}
$$

と書き直せる。

出発点の近くでは $\rho\simeq r_0$ なので、前の係数は、

$$
\sqrt{\frac{\rho r_0}{r_{\mathrm s}}}
\simeq\frac{r_0}{\sqrt{r_{\mathrm s}}}
$$

という有限の値になる。したがって、この付近の積分は、定数倍を除けば、

$$
\int\frac{d\rho}{\sqrt{r_0-\rho}}
$$

の形になる。

この積分も確かめよう。出発点から少し内側までの半径の差を $\delta>0$ とし、$s=r_0-\rho$ と置くと、$d\rho=-ds$ だから、

$$
\begin{aligned}
\int_{r_0-\delta}^{r_0}
\frac{d\rho}{\sqrt{r_0-\rho}}
&=\int_0^\delta\frac{ds}{\sqrt{s}}\\
&=\lim_{a\to0+}\left[2\sqrt{s}\right]_a^\delta\\
&=2\sqrt{\delta}.
\end{aligned}
$$

積分される関数は出発点で発散しても、その付近の積分値は有限なのである。元の積分に付いていた係数も、この区間では $r_0/\sqrt{r_{\mathrm s}}$ 以下なので、式 (13.7) の出発点付近の寄与も有限になる。

したがって、出発点から地平面までの積分は有限であり、Bob は自分の時計で有限の時間のうちに地平面へ到達する。

## 同じ落下を w で描くと、地平面は無限に先になる

![長く延びる座標の巻紙を見上げるAliceと手元の時計を見るBob](../../../images/general-relativity/13/alice-bob-coordinate-scroll.png)

*どこまでも延びるキャンバスと、手元で進む時計。座標時と固有時の違いを表すイメージ。*

一方、式 (13.4)、(13.5) から、

$$
\frac{dw}{dr}
=-\frac{\varepsilon}{f(r)\sqrt{\varepsilon^2-f(r)}}.
$$

地平面の近くでは $\sqrt{\varepsilon^2-f}\to\varepsilon$ なので、

$$
\frac{dw}{dr}\simeq-\frac1f
\simeq-\frac{r_{\mathrm s}}{r-r_{\mathrm s}}.
$$

積分すると、発散する部分は、

$$
w\simeq-r_{\mathrm s}\ln\left(\frac{r-r_{\mathrm s}}{r_{\mathrm s}}\right)
+\text{有限の項}
$$

となる。$r\to r_{\mathrm s}+0$ では $w\to+\infty$ である。

Bob の有限の固有時に対応する軌道を、この $w$ の目盛りでは無限に引き延ばして描いている。ここまでで分かったのは座標での記述であり、Charlie に届く映像については、光の伝播も含めて調べる必要がある。

---

Alice「座標の上で止まりそうに見えることと、Bob 自身の時計が止まることは、同じではないんだね。」

Bob「そう。僕の時計が刻む固有時は、地平面まで有限なんだ。」

---

## 落下する Bob からの光は、どの間隔で届くか

![出発前に発光装置の点滅を確かめるAliceとBob](../../../images/general-relativity/13/alice-bob-pulse-check.png)

*出発前に点滅を確かめる二人。落下中に送った光は、遠方の Charlie にどの間隔で届くだろうか。*

Bob が外側の $r$ にいるとき、座標時 $w_{\mathrm{emit}}$ に外向きの光を送る。第12章で求めた、光の伝播にかかる座標時の式 (12.4) で、送信位置 $r_{\mathrm{Alice}}$ を送信時の Bob の位置 $r$ に置き換える。この伝播にかかる座標時を送信時刻に足すと、固定された $r_{\mathrm{Charlie}}$ に届く座標時は、

$$
w_{\mathrm{receive}}
=w_{\mathrm{emit}}
+\int_r^{r_{\mathrm{Charlie}}}\frac{d\rho}{f(\rho)}.
\tag{13.8}
$$

次の光を送るとき、Bob はより内側へ移動している。したがって、伝播に必要な座標時も長くなる。

近接した二つの送信と、それぞれに対応する受信を比べよう。式 (13.8) を Bob の固有時で微分すると、積分の下端 $r$ も変わるため、

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{dw_{\mathrm{emit}}}{d\tau_{\mathrm{Bob}}}
-\frac1{f(r)}\frac{dr}{d\tau_{\mathrm{Bob}}}.
$$

右辺第二項のマイナス符号は、積分の下端が動くことから生じる。式 (13.8) の積分部分を、

$$
F(r)=\int_r^{r_{\mathrm{Charlie}}}\frac{d\rho}{f(\rho)}
$$

と書こう。上端 $r_{\mathrm{Charlie}}$ を固定したまま下端 $r$ を少し大きくすると、そのぶん積分する区間が短くなる。したがって、

$$
\frac{dF}{dr}=-\frac1{f(r)}
$$

となる。積分の上端を動かす場合とは逆の符号である。

さらに、下端 $r$ は Bob の固有時によって変わるので、連鎖律から、

$$
\frac{dF}{d\tau_{\mathrm{Bob}}}
=\frac{dF}{dr}\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\frac1{f(r)}\frac{dr}{d\tau_{\mathrm{Bob}}}
$$

を得る。これが右辺第二項である。

落下中は $dr/d\tau_{\mathrm{Bob}}<0$ で、地平面の外側では $f(r)>0$ なので、この項全体は正になる。Bob が内側へ落ちるほど、外側の Charlie まで光が進む区間が長くなり、伝播に必要な座標時が増えることを表している。

式 (13.4)、(13.5) を代入すれば、

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}.
$$

Charlie は十分遠方にいるので、受信する座標時の間隔を、そのまま自分の時計の間隔として読める。$d\tau_{\mathrm{Charlie}}=dw_{\mathrm{receive}}$ より、

$$
\boxed{
\frac{d\tau_{\mathrm{Charlie}}}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}
}
\tag{13.9}
$$

を得る。左辺の分子は受信する Charlie の時計の増分、分母は送信する Bob の時計の増分である。

第12章の静止する送信者の場合と違い、平方根を含む項が加わっている。Bob 自身の時計の進み方に加えて、次の光をより内側から送ることによる伝播の遅れも入ったためである。

### 光の振動数には、運動の効果も入る

波長が十分短く、光を光線として扱える場合、近接した波の山にも同じ計算を使える。それぞれが自分の時計で測る振動数を $\nu_{\mathrm{Bob}},\nu_{\mathrm{Charlie}}$ とすれば、その比は式 (13.9) の逆数である。

$$
\boxed{
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Bob}}}
=\frac{f(r)}{\varepsilon+\sqrt{\varepsilon^2-f(r)}}
=\varepsilon-\sqrt{\varepsilon^2-f(r)}
}
\tag{13.10}
$$

最後の変形では、分母と分子に $\varepsilon-\sqrt{\varepsilon^2-f}$ を掛けた。

出発の瞬間には $f(r_0)=\varepsilon^2$ なので、比は $\varepsilon=\sqrt{f(r_0)}$ となる。これは、第12章の静止した送信者の式で、受信者を十分遠方に置いた場合に一致する。

落下中の Bob は、外側の Charlie から遠ざかりながら光を送る。そのため、重力による赤方偏移に加えて、運動によって受信する振動数が下がるドップラー効果も生じる。式 (13.10) は、この両方を含んだ結果である。

### Charlie は地平面への到着を見届けられるか

地平面へ近づくと $f\to0$ なので、式 (13.9) の比は発散し、式 (13.10) の振動数の比はゼロへ近づく。Bob が一定の振動数で送る光は、Charlie の時計では振動の間隔が広がり、ますます低い振動数として届く。

これは近接した送受信の関係である。1秒など有限の間隔で点滅させる場合には、その区間で Bob の位置が変わるため、式 (13.8) から各信号の到着時刻を別々に求める。

Bob が地平面の直前から送る光ほど、Charlie に届く座標時は際限なく遅くなる。Charlie の時計の進みは座標時の進みと一致するので、自分の時計でも有限の時間内に「地平面を通過した」という光を受け取ることはない。

このことは、Bob の鮮明な像が地平面上に永久に残ることを意味しない。届く光は強く赤方偏移し、実際の検出には受光装置の感度も関わる。Bob の側で地平面までに刻む固有時が有限であることとも矛盾しない。

Bob 自身の時計が地平面で止まるわけではない。式 (13.1) では、$r=r_{\mathrm s}$ に近づくと $f(r)\to0$ となり、$dw^2$ の係数はゼロへ、$dr^2$ の係数は無限大へ向かう。しかし、これはシュヴァルツシルト座標による表示が地平面で使えなくなることを表しており、時空そのものがそこで壊れることを意味しない。

地平面では、曲率や潮汐力に座標によらない発散は起こらない。ただし、潮汐力の大きさはブラックホールの質量によって異なり、小さなブラックホールでは地平面でも強くなり得る。Bob の地平面通過とその内側まで座標で描くには、地平面でも破綻しない別の座標を使う必要がある。この章ではそこへ進まず、外側から分かる範囲に限って考えている。

ここで大切なのは、Bob が経験する時間、シュヴァルツシルト座標による表示、Charlie が光を通して知ることを区別することである。

---

Alice「Bob の時計は止まらずに進む。でも、内側から私たちに知らせる光は送れないんだね。」

Bob「うん。僕自身が経験する経過時間と、Charlie に届けられる情報を分けて考える必要があるんだ。」

---

## 三つの問いを分けて読む

| 問い | 今回分かったこと |
|---|---|
| Bob の時計では、地平面までどれだけかかるか | 有限の固有時で到達する |
| シュヴァルツシルト座標の $w$ ではどう描くか | 地平面への到達は $w\to\infty$ になる |
| Charlie は何を受け取るか | 地平面直前の光ほど遅く、低い振動数で届き、通過を知らせる光は届かない |

計量を使うときには、どの座標で描いているか、誰の時計を読んでいるか、どの光を受け取るかを区別する。同じ Bob の落下について、これらは違う問いへの答えなのである。

次の文書[「計量の変化を光で測る」](./14-MeasuringMetricChangesWithLight.md)では、時計と光を使う測定へ戻ろう。光を往復させ、二つの経路を比べることで、計量の変化をどのように読み取れるのかを考える。
