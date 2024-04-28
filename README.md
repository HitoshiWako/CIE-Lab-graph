# CIE Lab色空間の表示

## $`L^*a^*b^*`$からXYZへの変換
```math
\begin{aligned}
f_y &= \frac{L^*+16}{116} \\
f_x &= f_{y}+\frac{a^*}{500} \\
f_z &= f_{y}-\frac{b^*}{200}
\end{aligned}
```
とすると
```math
\begin{aligned}
 Y &= \left\{ \begin{array}{ll}
  f_{y}^{3}Y_{n} & (f_{y} > 6/29) \\
  (3/29)^{3} (116f_{y} − 16) Y_{n} & (f_{y} \leq 6/29) 
 \end{array} \right. \\
 X &= \left\{ \begin{array}{ll}
  f_{x}^{3}X_{n} & (f_{x} > 6/29) \\
  (3/29)^{3} (116f_{x} − 16) X_{n} & (f_{x} \leq 6/29)
 \end{array} \right. \\
  Z &= \left\{ \begin{array}{ll}
  f_{z}^{3}Z_{n} & (f_{z} > 6/29) \\
  (3/29)^{3} (116f_{z} − 16) Z_{n} & (f_{z} \leq 6/29)
 \end{array} \right. \\
\end{aligned}
```
## XYZ値からSRGBへ計算する
### XYZ値からリニアRGBを計算する
```math
\begin{aligned}
R &= 3.5064X - 1.7400Y - 0.5441Z  \\
G &= -1.0690X + 1.9777Y + 0.0352Z \\ 
B &= 0.0563X - 0.1970Y + 1.0511Z \\
\end{aligned}
```
### リニアRGBからsRGBへ
モニター画面の輝度の増加がRGB値の増加と直線関係でないためガンマ補正を行う
```math
\begin{aligned}
R'= R^{\frac{1}{2.2}} \\
G'= G^{\frac{1}{2.2}} \\
B'= B^{\frac{1}{2.2}} \\
\end{aligned}
```
