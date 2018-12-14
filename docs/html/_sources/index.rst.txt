.. created by　sphinx-quickstart on Tue Dec 11 16:42:11 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

凝縮系物理学特論　講義資料その３
================

.. toctree::
   :maxdepth: 2
   :caption: Contents:


多粒子系のハミルトニアンの実際と応用例
-----------------------------------
前回までの講義で、場の演算子で表記することで、多体量子系でのハミルトニアンが１粒子系と
似たような形で手に入ることや、場の演算子を生成消滅演算子と基底関数によって展開することで
生成消滅演算子で表記されたハミルトニアンが得られることを紹介した。
その具体的な応用例を紹介し、多体系での量子効果を扱う方法の感覚を紹介したい。

電子電子相互作用
^^^^^^^^^^^^^^^

アンダーソンモデル
"""""""""""""""""
電子電子相互作用を含むシンプルなモデルとしては、互いに相互作用をしない自由電子的な
伝導電子と、局在した軌道に存在するため強い電子-電子相互作用を感じる局在電子とが
相互作用をする場合を考えた、アンダーソンモデルがあげられる。

.. math::
   H=\sum_{k\sigma} \epsilon_k c_{k\sigma}^\dagger c_{k\sigma}+\sum_{\sigma}E_d d_{\sigma}^\dagger
   d_{\sigma} +Un_{d\uparrow}n_{d\downarrow} +\sum_{k\sigma}(V_{0}
   c_{k\sigma}^\dagger d_{\sigma} + h.c.)

:math:`\sum_{k\sigma} \epsilon_k c_{k\sigma}^\dagger c_{k\sigma}`　
は自由な伝導電子の部分を表している。
この項だけならば、それぞれの波数の電子が
:math:`\epsilon_k`
のエネルギーを持つという対角的なハミルトニアンになっている。
しかし、その自由な伝導電子はトンネル効果によって局在軌道に入り込むことがある。
それを記述しているのが
:math:`\sum_{k\sigma}(V_{0} c_{k\sigma}^\dagger d_{\sigma} + h.c.)`
の部分である。
:math:`Un_{d\uparrow}n_{d\downarrow}`
は局在電子が感じる電子間相互作用である。
:math:`n_{d\uparrow}=d^\dagger_\uparrow d_\uparrow`
のように電子数の演算子を書き直してやれば、前回の講義資料の最後に紹介した
２体のハミルトニアンに相当していることがわかるだろう。

このアンダーソンモデルは当初、非磁性金属中の磁性原子不純物が磁性を持つか否かを議論するためのモデルとして提案された。
提案者のアンダーソン自身は、
:math:`Un_{d\uparrow}n_{d\downarrow}`
の２つの電子数演算子のうち、片方を平均値にしてしまうという平均場近似で、あるUの値を境に磁性を持つ場合と持たない場合に
区別されるということを提唱した。
しかし、このような不連続性は近似が単純であったために生じており、実際はより複雑な状況が生じている。
複雑さの原因は、
伝導電子と局在電子がトンネル効果によってすり替わる過程にある。
十分に低温で熱ゆらぎが少ない場合には、この過程を介して、
全体のエネルギーを下げる方向に働く。
その結果、この過程が可能になる伝導電子と局在電子がスピン1重項をとった状態が
基底状態として現れてくる。伝導電子が１つ２つならこの１重項形成は大して複雑な問題ではないが、
実際に出てくるのは無数の伝導電子がゆるく局在電子と１重項を組んだ状態である。
このような多体状態を扱うことは非常に難しい。

そういった状態が実際にあらわれていることは、電気抵抗の異常として確認される。
通常の金属では電気抵抗は
温度を下げて行くと単調に減少し、
不純物散乱に由来する残留抵抗が最後に残る。
しかし、磁性不純物を含んだ金属では上記のような状態があらわれ、
伝導電子がゆるく局在電子に束縛されることになる結果、電気抵抗が上昇する。
そのため、冷やしていくと、一旦さがったのちに電気抵抗が上がるという、電気抵抗に極小点が現れる
という現象が起きる。これを近藤効果という。

近藤効果自体は、1920年ごろから発見されており、上に述べたメカニズムは
日本人の近藤淳先生や芳田奎先生らによって60年代にあらかた解明されていた。
しかし、前述した量子多体状態を扱う困難により、厳密解や数値的に高精度な解が得られるようになったのは
80年代以降である。

最近でも、量子ドットの電子と、量子ドットにつながる電極の電子の間で
近藤効果が起きることや、分子系でも起きることなど、もともとの磁性不純物が入った金属以外に
様々な系で起きることが報告されており、今だに研究が続けられている問題の一つである。


ハバードモデル
"""""""""""""
アンダーソンモデルと似ているが、ありとあらゆるところで電子-電子相互作用が強力な場合に
相当するのがハバードモデルである。
ハバードモデルの場合は、局在電子と局在電子の間をホッピングする項と
局在電子が感じる電子-電子相互作用の2つの項からなる。

.. math::
   H=\sum_{i j\neq i\sigma}( t_{ij\sigma} d_{i\sigma}^\dagger d_{j\sigma}+h.c.) +\sum_{i\sigma}Un_{d_i\uparrow}n_{d_i\downarrow}

これはちょうど強束縛模型に電子間相互作用が加わったような形をしている。
この模型がとくに対応するのが遷移金属酸化物である。
遷移金属中のdやf電子は比較的原子に局在しており、酸素のp軌道を介して他の原子に飛び移ることができる。
この飛び移りに対応するのが
:math:`\sum_{i j\neq i\sigma}( t_{ij\sigma} d_{i\sigma}^\dagger d_{j\sigma}+h.c.)`
の部分である。
飛び移って運動エネルギーを稼ぐ効果と、電子間の相互作用が拮抗することで、
ハバードモデルでは様々な状態が現れる。電子間相互作用のほうが飛び移りよりも大きければ、
電子間相互作用がない場合には金属的になる占有数が1/2の状態でも電子は各原子にとどまり絶縁体の状態が現れる。
このような電子間相互作用によって現れる絶縁体状態をモット絶縁体という。
モット絶縁体状態は、反強磁性状態を取ることが多く、磁性を持った絶縁体は大抵がモット絶縁体である。
興味深いことに酸化物中の元素の一部を置換して、占有数を1/2から少しずらしてやると、
この磁性が大きく変わったり、超伝導状態が現れることがある。このような現象のメカニズムについては
長らく研究がされているものの、高温超伝導を始めとして今だ決着がついていない物もある。


電子格子相互作用
^^^^^^^^^^^^^^^^
電子格子相互作用もまた、典型的な多体効果である。格子振動、すなわちフォノンが生じると、原子の座標の変化とともに
電子が感じるポテンシャルの変化が生じる。それによって電子の波動関数が変調されるのが
電子格子相互作用が生じる原理である。電子格子相互作用は、電気抵抗、ポーラロン形成、電荷密度波、熱電効果から超伝導に至るまで固体物理のなかの
様々な現象の元になっている。

まず、非常に簡単な電子フォノン相互作用の導出から始めよう。以下の導出は主にMahanの教科書をベースにしている。
電子とイオン、それらの振動から成るハミルトニアンは
以下のように定義される。

.. math::

   \begin{aligned}
   H=H_p+H_e+H_{ei} \\
   H_p=\sum_{q\lambda} \omega_{q\lambda} \alpha_{q\lambda}^\dagger
   \alpha_{q\lambda} \\
   H_e =\sum_{i} \left [ \frac{p_i^2}{2m} + \frac{e^2}{2} \sum_{j\neq i}
   \frac{1}{r_{ij}} \right] \\
   H_{ei} = \sum_{ij} V(\bf{r_i} -  \bf{R_j})\end{aligned}

:math:`H_p`\ はフォノンのハミルトニアンであり、\ :math:`H_e`\ は電子系のハミルトニアン、そして\ :math:`H_{ei}`\ は電子とイオンの間の相互作用を表すハミルトニアンである。
フォノンが生じるというのは\ :math:`H_{ei}`\ の中の\ :math:`\bf{R_j}`\ が変化することであると捉えることができる。
平衡状態での原子の座標を\ :math:`\bf{R_j^{0}}`\ として、一般的な座標を変位\ :math:`\bf{Q_j}`\ を用いて\ :math:`\bf{R_j}=\bf{R_j^{0}}+\bf{Q_j}`
で表す。変位は小さいものとして、変位についてのテイラー展開を実行すると

.. math::

   \begin{aligned}
   V({\bf r_i} - {\bf R_j^{0}}-{\bf Q_j})=V({\bf r_i} - {\bf
   R_j^{0}})-{\bf Q_j}\cdot \nabla V_{ei}({\bf r_i} - {\bf R_j^{0}}) +O(Q^2)\end{aligned}

が得られる。この第2項が電子フォノン相互作用を与える。
第一項は、原子の変位がない状態での電子－イオン相互作用である。この第一項と\ :math:`H_e`\ が
電子系の無摂動ハミルトニアンであるとみなし、そのBloch状態を元に、摂動である第2項の評価を行うのが
ボルン・オッペンハイマー近似に則った通常の評価方法である。動的ヤーンテラー効果等の場合にはこの方法はうまくいかない。

第二項が電子フォノン相互作用であることは、変位\ :math:`\bf{Q_j}`\ をフォノンの生成消滅演算子を使って書き直せば分かる。
フォノンは通常「格子振動」であり、結晶についての議論をされることが多いので、逆格子空間をつかったフーリエ変換した形で考えてみる。
電子イオン相互作用のフーリエ変換は

.. math::

   \begin{aligned}
   V_{ei} ({\bf r}) = \frac{1}{N} \sum_{q} V_{ei}({\bf q})\exp^{i{\bf q\cdot r}}\end{aligned}

である。これを微分することで

.. math::

   \begin{aligned}
   \nabla V_{ei} ({\bf r}) = \frac{i}{N} \sum_{q} {\bf q} V_{ei}({\bf
   q})\exp^{i{\bf q\cdot r}}\end{aligned}

が得られる。 電子フォノン相互作用に相当する項全体を考えると

.. math::

   \begin{aligned}
   V_{ep}&=\sum_j  {\bf Q_j}\cdot \nabla V_{ei}(i{\bf r_i} - {\bf
   R_j^{0}})=\sum_j \sum_q {\bf Q_j}\cdot \nabla V_{ei}(q) \exp^{i{\bf r_i} - {\bf
   R_j^{0}}} \nonumber \\
   &=\frac{i}{N} \sum_j \sum_q
   {\bf Q_j}\cdot  {\bf q}V_{ei}(q) \exp^{i{\bf q} \cdot ({\bf r_i} - {\bf R_j^{0}})}
   \nonumber
   \\
   &= \frac{i}{N} \sum_j \sum_q {\bf Q_j} \exp^{-i{\bf q} \cdot {\bf
   R_j^{0}}}\cdot  {\bf q}V_{ei}(q) \exp^{i {\bf q} \cdot{\bf r_i}}\end{aligned}

変位ベクトルのフーリエ変換した形は

.. math::

   \begin{aligned}
   {\bf Q_j}(t)=i\sum_q \left(\frac{\hbar}{2MN\omega_q} \right)^\frac{1}{2} \xi_q
   (\alpha_q \exp^{(-i\omega_q t)}+\alpha_q^\dagger \exp^{(i\omega_q t)})
   \exp^{(i{\bf q\cdot R_i^{(0)}})}\end{aligned}

で与えられる。\ :math:`\xi_q`\ は偏極ベクトルと呼ばれる、振動モードによって原子がどの方向に変位するかを表す3N（3次元の場合）の要素数を持つベクトルである。
Mはイオンの質量である。変位ベクトルの時間依存性を無視して

.. math::

   \begin{aligned}
   {\bf Q_j}(t)=i\sum_q \left(\frac{\hbar}{2MN\omega_q} \right)^\frac{1}{2} \xi_q
   (\alpha_q +\alpha_q^\dagger )
   \exp^{(i{\bf q\cdot R_i^{(0)}})}\end{aligned}

とし、これを電子フォノン相互作用の項に代入してやれば

.. math::

   \begin{aligned}
   V_{ep}&=\frac{i}{N} \sum_j \sum_{qq'}
   \left(\frac{\hbar}{2MN\omega_q'}\right)^\frac{1}{2} \xi_q' (\alpha_q' +\alpha_q'^\dagger ) e^{i{\bf q'\cdot R_i^{(0)}}} \cdot e^{-i{\bf q} \cdot {\bf
   R_j^{0}}} \cdot  {\bf q}V_{ei}(q)
   e^{i {\bf q} \cdot{\bf r_i}}  \\
   &=-\sum_{q}e^{i {\bf q} \cdot{\bf r_i}} {\bf q}V_{ei}(q) \cdot
   \left(\frac{\hbar}{2MN\omega_q} \right)^\frac{1}{2} \xi_q (\alpha_q +\alpha_q^\dagger )\end{aligned}

とすれば良いように思う。しかし、ここでqの和に関する問題を解消しなくてはいけない。
ここでのqはフーリエ変換から定義されるものなので、逆格子空間全域をカバーする。
しかし、結晶における固有状態はブロッホの定理に従い、位相と周期関数の積で書かれ、
それを規定する波数は第一ブリルアンゾーン内のものに限られる。なので、フォノンの生成消滅演算子の波数
qを逆格子空間全域にしておくのは良くない。
そこで、電子の場合と同様に、波数空間内での和を、第一ブリルアンゾーン内の波数qと逆格子ベクトルGに関する和で表現することを行う。
この表記を用いると

.. math::

   \begin{aligned}
   V_{ep}=-\sum_{qG}e^{i {\bf (q+G)} \cdot{\bf r_i}} {\bf (q+G)}V_{ei}(q+G) \cdot
   \left(\frac{\hbar}{2MN\omega_q} \right)^\frac{1}{2} \xi_q (\alpha_q +\alpha_q^\dagger )
   \end{aligned}

が最終的に得られる。 このポテンシャル :math:`V_{ep}` を元に第二量子化形式のハミルトニアンを求めておく。

ブロッホ波動関数を用いた電子の場の演算子を以下のように定義する。

.. math::

   \begin{aligned}
   \psi(r) = \sum_{\mathbf{k},\eta}c_{\mathbf{k}\eta}\phi_{\mathbf{k}\eta}(r), \\
   \psi^{\dagger}\left( r \right) =
   \sum_{\mathbf{k},\eta}{c_{\mathbf{k}\eta}^{\dagger}\phi_{\mathbf{k}\eta}^{*}(r)}\end{aligned}

ここで\ :math:`\phi_{\mathbf{k}\eta}(r)`\ は第一ブリルアンゾーン内の波数\ :math:`\mathbf{k}`\ を持つバンド\ :math:`\eta`\ の電子状態のブロッホ波動関数であり、
:math:`c_{\mathbf{k}\eta}`\ はその電子状態に対する消滅演算子を指す。ブロッホ波動関数は

.. math::

   \begin{aligned}
   \phi_{\mathbf{k}\eta}\left( r \right) = u_{\mathbf{k}\eta}\exp{\left(
   i\mathbf{k} \cdot \mathbf{r} \right)}\end{aligned}

で表されるものとする。

電子フォノン相互作用に相当する第二量子化形式のハミルトニアンは

.. math::
   H_{ep} &= - \sum_{\lambda}\int_{}^{}dr \psi^{\dagger}(r)V_{ep}(r)\psi(r) \\
   &= -i\sum_{\mathbf{k,k'},\eta,\eta^{'}} \sum_{\mathbf{qG}}
   \int dr\phi^*_{\mathbf{k'}\eta'}(r)e^{i(\mathbf{q+G}) \cdot
   \mathbf{r}} \mathbf{\xi}_{\mathbf{q}}\cdot
   (\mathbf{q+G})V_{ei}( \mathbf{q+G}) \nonumber \\
   &\left(\frac{\hbar}{2MN\omega_{\mathbf{q}\lambda}} \right)^{\frac{1}{2}}
   \phi_{\mathbf{k}\eta}(r)c_{\mathbf{k'}\eta^{'}}^{\dagger}
   c_{\mathbf{k}\eta}\left(\alpha_{q}{+ \alpha_{-q}^{\dagger}}
   \right) \nonumber \\
   &= -i\sum_{\mathbf{k,k'},\eta,\eta'}\sum_{\mathbf{qG}}\int dr
   u_{\mathbf{k'}\eta'}^{*}\ e^{i (\mathbf{k -k'+ q +G}) \cdot \mathbf{r}}
   \mathbf{\xi}_{\mathbf{q}}\mathbf{\cdot}(\mathbf {q + G})V_{ei}\left( \mathbf{q}
   + \mathbf{G} \right)\nonumber \\
   & \left( \frac{\hbar}{2MN\omega_{q}}
   \right)^{\frac{1}{2}}\ u_{\mathbf{k}\eta}\ c_{\mathbf{k'}\eta'}^{\dagger}c_{\mathbf{k}\eta}
   \left( \alpha_{q}+ \alpha_{-q}^{\dagger} \right)
   :label: Hep

で表される。この積分は\ :math:`\mathbf{k}^{\mathbf{'}}\mathbf{-}\mathbf{k}^{}\mathbf{= q}`
または\ :math:`\mathbf{k}^{\mathbf{'}}\mathbf{-}\mathbf{k}^{} = \mathbf{q} + \mathbf{G}`\ の場合のみ、有限の値を持つ。前者の場合をNormal
process、後者をUmklapp processと呼ぶ。

このような議論から、一般に、電子フォノン相互作用は

.. math::

   \begin{aligned}
   H_{ep} =
   \sum_{\mathbf{k}\eta\eta'}{\sum_{\mathbf{q}}^{}M_{\mathbf{kq}}^{\eta\eta'}}c_{\mathbf{k
   + q}\eta'}^{\dagger}c_{\mathbf{k}\eta}\left(\alpha_q+ \alpha_{-q}^{\dagger} \right)\end{aligned}

の形にかけることが分かる。これは、ちょうど波数\ :math:`\mathbf{k}`\ バンド\ :math:`\eta`\ の電子が波数\ :math:`\mathbf{q}`
(:math:`- \mathbf{q}`)のフォノンを吸収（放出）することで波数\ :math:`\mathbf{k + q}`\ バンド\ :math:`\eta'`\ の電子が生じるプロセスに対応している。
:math:`M_{kq}^{\eta\eta'}`\ は式(:eq:`Hep`)に含まれる、ポテンシャルの微分とブロッホ波動関数から得られる電子フォノン相互作用行列要素である。




References
==================

* :ref:`genindex`
* :ref:`search`
