
$$G(s)=\frac{2s+1}{s^2+7s+9}$$
$2\dot{z}+z$
$\ddot{z}+7\dot{z}+9z=u(t)\implies \ddot{z}=u(t)-7\dot{z}-9z$
$x_{1}=z$
$x_{2}=\dot{z}$
$x_{3}=\ddot{z}$

$\dot{x}_1=\dot{z}=x_{2}$
$\dot{x}_{2}=\ddot{z}=x_{3}=u(t)-7\dot{z}-9z$

$$\begin{bmatrix}\dot{x}_{1} \\
\dot{x}_{2}\end{bmatrix}=\begin{bmatrix}0 & 1 \\
-9 & -7
\end{bmatrix}\begin{bmatrix}x_{1} \\
x_{2}\end{bmatrix}+\begin{bmatrix}0 \\
1\end{bmatrix}u(t)$$
$$y=\begin{bmatrix}1 & 2\end{bmatrix}\begin{bmatrix}x_{1} \\
x_{2}\end{bmatrix}+0$$
