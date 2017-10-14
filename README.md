# CIE Lab色空間の表示

## L\*a\*b\*からXYZへの変換
参考:http://w3.kcua.ac.jp/~fujiwara/infosci/colorspace/colorspace3.html

\begin{equation*}
f_{y} = \frac{L^{*}+16}{116} \\
f_{x} = f_{y}+\frac{a^{*}}{500} \\
f_{z} = f_{y}-\frac{b^{*}}{200} 
\end{equation*}

とすると

 \begin{equation*}
 Y =\left\{ \begin{array}{ll}
  f_{y}^{3}Y_{n} & (f_{y} > 6/29) \\
  (3/29)^{3} (116f_{y} − 16) Y_{n} & (f_{y} \leq 6/29) \\
 \end{array} \right. \\
\\
 X =\left\{ \begin{array}{ll}
  f_{x}^{3}X_{n} & (f_{x} > 6/29) \\
  (3/29)^{3} (116f_{x} − 16) X_{n} & (f_{x} \leq 6/29) \\
 \end{array} \right. \\
  \\
  Z =\left\{ \begin{array}{ll}
  f_{z}^{3}Z_{n} & (f_{z} > 6/29) \\
  (3/29)^{3} (116f_{z} − 16) Z_{n} & (f_{z} \leq 6/29) \\
 \end{array} \right. \\
\end{equation*}

## XYZ値からSRGBへ計算する
参考：http://www005.upp.so-net.ne.jp/fumoto/linkp25.htm

### XYZ値からリニアRGBを計算する

\begin{equation*}
R = 3.5064X - 1.7400Y - 0.5441Z  \\
G = -1.0690X  + 1.9777Y + 0.0352Z \\ 
B= 0.0563X - 0.1970Y + 1.0511Z \\
\end{equation*}

### リニアRGBからsRGBへ

モニター画面の輝度の増加がRGB値の増加と直線関係でないため
ガンマ補正を行う

\begin{equation*}
R'= R^{\frac{1}{2.2}} \\
G'= G^{\frac{1}{2.2}} \\
B'= B^{\frac{1}{2.2}} \\
\end{equation*}