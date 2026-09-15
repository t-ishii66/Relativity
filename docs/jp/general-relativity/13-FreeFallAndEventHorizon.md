# 自由落下と事象の地平面

## はじめに

前の文書[「重力赤方偏移と光の進み方」](./12-GravitationalRedshiftAndLight.md)では、静止する Alice が送る光を、外側に静止する Charlie が受け取った。二人の位置が変わらないため、続けて送った信号は、同じ座標時をかけて届いた。

今度は、Bob が Alice のいる場所から自由落下する。Bob も時計と発光装置を持ち、落下しながら外側の Charlie へ光を送る。

Bob の時計はどれだけ進むのか。その光は Charlie にどのように届くのか。そして、$r=r_{\mathrm s}$ で計量の係数に現れるゼロや発散は、何を意味するのだろうか。

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

普通の星で、表面が $r_{\mathrm s}$ より外側にある場合には、Bob は地平面に近づく前に星の表面に着く。星の物質がある場所へ真空の計量をそのまま使うことはできない。今回の舞台は、その場合とは区別する。

| 登場人物 | 役割 |
|---|---|
| Alice | $r=r_0>r_{\mathrm s}$ に支えられて静止する |
| Bob | Alice の隣で相対速度ゼロから自由落下を始め、動径方向に進む |
| Charlie | $r=r_{\mathrm{Charlie}}>r_0$ に静止し、Bob から外向きに届く光を受け取る |

Alice と Charlie はその場所にとどまるための支えを持つ。Bob は出発後、ロケットを噴射せず、重力以外の力を受けないものとする。

---

Alice「Bob の時計も、私の時計と同じように $d\tau=\sqrt f\,dw$ で計算できるの？」

Bob「僕は場所を変えるから、空間方向の項も残るよ。まず、どう落ちるのかを求めよう。」

---

## 自由落下の運動を決める量

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

もう一つ、自由落下の条件を使おう。第6章で学んだ測地線方程式の $w$ 成分は、

$$
\ddot w+2\Gamma^w_{wr}\dot w\dot r=0
$$

である。今回の計量では、$f'=df/dr$ として、

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
\tag{13.3}
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
\tag{13.4}
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
\tag{13.5}
$$

で表せる。落下して $r$ が小さくなるほど、この変化の絶対値は大きくなる。

## 座標での動きと、その場で測る速度

式 (13.3)、(13.4) の比を取ると、キャンバス上の Bob の動きは、

$$
\boxed{
\frac{dr}{dw}
=-\frac{f(r)}{\varepsilon}\sqrt{\varepsilon^2-f(r)}
}
\tag{13.6}
$$

となる。$r\to r_{\mathrm s}$ では $f\to0$ なので、$dr/dw\to0$ である。

これだけを見ると、Bob は地平面の手前で動きを止めるように思える。しかし、$dr/dw$ は、共通の座標に付けた数字の変化の比だった。

Bob が通過する場所に静止する観測者を考えよう。これは各場所での測定を考えるための観測者であり、$r_0$ に残る Alice が Bob と一緒に落ちるという意味ではない。

第11章の換算式より、その観測者が手元の時計と物差しで測る Bob の動径方向の速度は、

$$
v_{\mathrm{Bob}}
=\frac{c}{f(r)}\frac{dr}{dw}
=-c\sqrt{1-\frac{f(r)}{\varepsilon^2}}.
\tag{13.7}
$$

外側のどの場所でも $|v_{\mathrm{Bob}}|<c$ だが、地平面に近い場所に静止する観測者ほど、Bob の速さが $c$ に近いと測る。

ここでの極限は、異なる場所に静止する観測者による測定を並べたものである。地平面上に静止して待つ観測者を置いたわけではない。そのような静止ができない理由は、後で確かめよう。

## Bob の時計では、有限の固有時で地平面に着く

Bob が $r_0$ から $r<r_0$ まで落ちる間に、自分の時計が刻む固有時は、式 (13.5) を積分して、

$$
\Delta\tau_{\mathrm{Bob}}
=\int_r^{r_0}
\frac{d\rho}{\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}}.
\tag{13.8}
$$

$\rho$ は積分の中で使う半径の変数である。

地平面 $\rho=r_{\mathrm s}$ では、分母は $\sqrt{1-r_{\mathrm s}/r_0}=\varepsilon>0$ であり、発散しない。出発点では分母がゼロになるが、その近くの積分は $\int d\rho/\sqrt{r_0-\rho}$ の形なので有限である。

実際に積分してみよう。

$$
\rho=r_0\cos^2\eta
$$

と置く。出発点は $\eta=0$ で、落下するにつれて $\eta$ が増える。すると、

$$
d\rho=-2r_0\sin\eta\cos\eta\,d\eta,
\qquad
\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}
=\sqrt{\frac{r_{\mathrm s}}{r_0}}\tan\eta.
$$

式 (13.8) は、$r=r_0\cos^2\eta$ として、

$$
\begin{aligned}
\Delta\tau_{\mathrm{Bob}}
&=2\sqrt{\frac{r_0^3}{r_{\mathrm s}}}
\int_0^\eta\cos^2 u\,du\\
&=\sqrt{\frac{r_0^3}{r_{\mathrm s}}}
(\eta+\sin\eta\cos\eta).
\end{aligned}
\tag{13.9}
$$

地平面では $\eta=\arccos\sqrt{r_{\mathrm s}/r_0}$ であり、この値も、固有時の増分も有限である。秒での所要時間が必要なら、$\Delta\tau_{\mathrm{Bob}}$ を $c$ で割ればよい。

## 同じ落下を w で描くと、地平面は無限に先になる

一方、式 (13.3)、(13.4) から、

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

Bob が外側の $r$ にいるとき、座標時 $w_{\mathrm{emit}}$ に外向きの光を送る。固定された $r_{\mathrm{Charlie}}$ に届く座標時は、第12章の光の道筋から、

$$
w_{\mathrm{receive}}
=w_{\mathrm{emit}}
+\int_r^{r_{\mathrm{Charlie}}}\frac{d\rho}{f(\rho)}.
\tag{13.10}
$$

次の光を送るとき、Bob はより内側へ移動している。したがって、伝播に必要な座標時も長くなる。

近接した二つの送信と、それぞれに対応する受信を比べよう。式 (13.10) を Bob の固有時で微分すると、積分の下端 $r$ も変わるため、

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{dw_{\mathrm{emit}}}{d\tau_{\mathrm{Bob}}}
-\frac1{f(r)}\frac{dr}{d\tau_{\mathrm{Bob}}}.
$$

式 (13.3)、(13.4) を代入すれば、

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}.
$$

Charlie の時計では $d\tau_{\mathrm{Charlie}}=\sqrt{f_{\mathrm{Charlie}}}\,dw_{\mathrm{receive}}$ だから、$f_{\mathrm{Charlie}}=f(r_{\mathrm{Charlie}})$ として、

$$
\boxed{
\frac{d\tau_{\mathrm{Charlie}}}{d\tau_{\mathrm{Bob}}}
=\sqrt{f_{\mathrm{Charlie}}}
\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}
}
\tag{13.11}
$$

を得る。左辺の分子は受信する Charlie の時計の増分、分母は送信する Bob の時計の増分である。

第12章の静止する送信者の場合と違い、平方根を含む項が加わっている。Bob 自身の時計の進み方に加えて、次の光をより内側から送ることによる伝播の遅れも入ったためである。

### 光の振動数には、運動の効果も入る

波長が十分短く、光を光線として扱える場合、近接した波の山にも同じ計算を使える。それぞれが自分の時計で測る振動数を $\nu_{\mathrm{Bob}},\nu_{\mathrm{Charlie}}$ とすれば、その比は式 (13.11) の逆数である。

$$
\boxed{
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Bob}}}
=\frac{f(r)}{\sqrt{f_{\mathrm{Charlie}}}
\left(\varepsilon+\sqrt{\varepsilon^2-f(r)}\right)}
=\frac{\varepsilon-\sqrt{\varepsilon^2-f(r)}}{\sqrt{f_{\mathrm{Charlie}}}}
}
\tag{13.12}
$$

最後の変形では、分母と分子に $\varepsilon-\sqrt{\varepsilon^2-f}$ を掛けた。

出発の瞬間には $f(r_0)=\varepsilon^2$ なので、比は $\sqrt{f(r_0)/f_{\mathrm{Charlie}}}$ となり、第12章の静止した送信者の式に戻る。

落下中の速さを、その場に静止する観測者の測定で、

$$
\beta=\frac{|v_{\mathrm{Bob}}|}{c}
=\sqrt{1-\frac{f(r)}{\varepsilon^2}}
$$

と書くと、式 (13.12) は、

$$
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Bob}}}
=\sqrt{\frac{f(r)}{f_{\mathrm{Charlie}}}}
\sqrt{\frac{1-\beta}{1+\beta}}
$$

とも書ける。最初の因子は静止した観測者どうしの重力赤方偏移、次の因子は、内向きに動く Bob が外向きに光を送るときの特殊相対論的なドップラー効果である。

### Charlie は地平面への到着を見届けられるか

地平面へ近づくと $f\to0$ なので、式 (13.11) の比は発散し、式 (13.12) の振動数の比はゼロへ近づく。Bob が一定の振動数で送る光は、Charlie の時計では振動の間隔が広がり、ますます低い振動数として届く。

これは近接した送受信の関係である。1秒など有限の間隔で点滅させる場合には、その区間で Bob の位置が変わるため、式 (13.10) から各信号の到着時刻を別々に求める。

Bob が地平面の直前から送る光ほど、Charlie に届く座標時は際限なく遅くなる。Charlie は固定された場所にいて $d\tau_{\mathrm{Charlie}}=\sqrt{f_{\mathrm{Charlie}}}\,dw$ だから、自分の時計でも有限の時間内に「地平面を通過した」という光を受け取ることはない。

このことは、Bob の鮮明な像が地平面上に永久に残ることを意味しない。届く光は強く赤方偏移し、実際の検出には受光装置の感度も関わる。Bob の側で地平面までに刻む固有時が有限であることとも矛盾しない。

## 地平面をまたげる座標を作る

Bob は有限の固有時で着くのに、$w$ では無限に先になる。この座標の行き詰まりを避けるため、内向きの光に合わせた座標を作ろう。

まず、外側で、

$$
r_*=r+r_{\mathrm s}\ln\left|\frac r{r_{\mathrm s}}-1\right|
$$

と置くと、

$$
\frac{dr_*}{dr}=\frac1{f(r)}.
$$

内向きの光は $dw=-dr/f=-dr_*$ なので、$w+r_*$ が一定の線になる。そこで新しい座標を、

$$
q=w+r_*,\qquad dw=dq-\frac{dr}{f(r)}
$$

と定義する。$q$ も距離の単位を持つ。

式 (13.1) に代入して、動径方向の項を展開すると、

$$
\begin{aligned}
ds^2
&=-f\left(dq-\frac{dr}{f}\right)^2
+\frac{dr^2}{f}+r^2d\Omega^2\\
&=-f\,dq^2+2\,dq\,dr-\frac{dr^2}{f}
+\frac{dr^2}{f}+r^2d\Omega^2.
\end{aligned}
$$

発散していた二つの項が打ち消し合い、

$$
\boxed{ds^2=-f(r)dq^2+2\,dq\,dr+r^2d\Omega^2}
\tag{13.13}
$$

となる。$(q,r)$ 部分の計量の行列式も、

$$
\det\begin{pmatrix}-f&1\\1&0\end{pmatrix}=-1
$$

なので、$f=0$ で逆計量が作れなくなるわけでもない。この形の計量は $r=r_{\mathrm s}$ で滑らかであり、内側へも延長できる。

これは内向きのエディントン＝フィンケルシュタイン座標と呼ばれる。地平面での発散を取り除くこの座標の考え方は、[David Tong の一般相対論講義「Black Holes」](https://www.damtp.cam.ac.uk/user/tong/gr/grhtml/S6.html)でも説明されている。

Bob の運動についても、外側からの極限で、

$$
\frac{dq}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon-\sqrt{\varepsilon^2-f}}{f}
=\frac1{\varepsilon+\sqrt{\varepsilon^2-f}}
\longrightarrow\frac1{2\varepsilon}
$$

となる。$dr/d\tau_{\mathrm{Bob}}\to-\varepsilon$ も有限である。Bob の軌道を、地平面をまたいで連続して描けるようになった。

座標の発散が消えることは、広い範囲の曲率や潮汐力まで消えることではない。離れた体の部分が異なる落下をする効果は残るが、地平面そのものが局所的な物理量の発散する場所というわけではない。

## 外へ向けた光でも、内側では半径が減る

新しい座標で、動径方向の光に $ds^2=0$ を使うと、

$$
0=dq(-f\,dq+2\,dr).
$$

二つの光の向きは、

$$
dq=0
\quad\text{または}\quad
\frac{dr}{dq}=\frac{f(r)}2
\tag{13.14}
$$

である。最初は内向きの光で、未来へ進むと $r$ が減る。二つ目は外側で外向きだった光であり、未来へ進む向きに $dq>0$ を取る。

| 場所 | $f(r)$ | 外側で外向きだった光の $dr/dq$ |
|---|---|---|
| $r>r_{\mathrm s}$ | 正 | 正：外へ進める |
| $r=r_{\mathrm s}$ | ゼロ | ゼロ：地平面に沿って進む |
| $0<r<r_{\mathrm s}$ | 負 | 負：半径が減る |

内側では、外へ向けた光も小さい $r$ へ進む。角度方向へ進む場合も逃げ道にはならない。未来向きの光や物体では $ds^2\leq0$ だから、$dq>0$ に対して、

$$
\frac{dr}{dq}
\leq\frac f2-\frac{r^2}{2}
\left[\left(\frac{d\theta}{dq}\right)^2
+\sin^2\theta\left(\frac{d\phi}{dq}\right)^2\right]
\leq\frac f2.
$$

$f<0$ なら、どの場合も $dr/dq<0$ となる。$dq=0$ の場合に許されるのは、先ほどの内向きの動径光である。

このブラックホールのモデルで、遠方へ光を届けられる領域と、届けられない領域の境界が $r=r_{\mathrm s}$ である。これが**事象の地平面**である。地平面は時空全体での光の到達可能性によって決まる境界であり、一般の時空でも単に計量の一成分がゼロの場所を探せばよいわけではない。

### 地平面に静止する Alice は置けない

$r,\theta,\phi$ を一定に保つ軌道では、式 (13.13) は、

$$
ds^2=-f(r)dq^2
$$

となる。外側では負なので、時計を持つ観測者の軌道になれる。地平面ではゼロになり、光のような軌道になる。内側では正になるので、時計を持つ観測者の軌道にはできない。

したがって、地平面上や内側に静止した Alice を置き、その時計と Bob の時計を比較することはできない。第11章の静止した観測者による換算式も、適用する領域を守る必要がある。

Bob は自分の近くでは、いつも局所慣性系を使って光速 $c$ を測る。内側から逃げられない理由は、光の速さが局所的に遅くなったからではなく、未来へ進める方向が、遠方へ抜ける方向につながっていないからである。

---

Alice「Bob の時計は止まらずに進む。でも、内側から私たちに知らせる光は送れないんだね。」

Bob「うん。僕自身が経験する経過時間と、Charlie に届けられる情報を分けて考える必要があるんだ。」

---

## 三つの問いを分けて読む

| 問い | 今回分かったこと |
|---|---|
| Bob の時計では、地平面までどれだけかかるか | 有限の固有時で到達し、通過する |
| シュヴァルツシルト座標の $w$ ではどう描くか | 地平面への到達は $w\to\infty$ になる |
| Charlie は何を受け取るか | 地平面直前の光ほど遅く、低い振動数で届き、通過を知らせる光は届かない |
| 地平面で時空は壊れるか | 適切な座標で滑らかに記述できる |
| なぜ内側から逃げられないか | 未来向きの光や物体の進路が、外側へ出る方向につながらない |

計量を使うときには、どの座標で描いているか、誰の時計を読んでいるか、どの光を受け取るかを区別する。同じ Bob の落下について、これらは違う問いへの答えなのである。

次章では、時計と光を使う測定へ戻ろう。光を往復させ、二つの経路を比べることで、計量の変化をどのように読み取れるのかを考える。
