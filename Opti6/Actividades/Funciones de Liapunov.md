
1. Considere el sistema de segundo orden y determine la estabilidad de este estado proponiendo una función de Liapunov conveniente
$$\frac{dx}{dt}=x$$
$$\frac{dy}{dt}=-x-y$$




2. Considere el sistema en el espacio descrito por 
$$x'=2y(z-1)$$
$$y'=-x(z-1)$$
$$z'=-z^3$$
- Encuentre los eigenvalores y eigenvectores del sistema lineal asociado
- Encuentre una función de Liapunov
- Clasifique la estabilidad del punto $(0,0,0)$

Sea $\frac{dV}{dt}=\frac{∂V}{∂x}\frac{∂x}{∂t}+\frac{∂V}{∂y}\frac{∂y}{∂t}+\frac{∂V}{∂z}\frac{∂z}{∂t}$

----
<span style="color:#0070c0">Primera propuesta:</span> $\mathbf{V(x,y,z)=2x^2+4y^2+2\ln(z)}$

$$\frac{dV}{dt}=(4x)(2y(z-1))+(8y)(-x(z-1))-\left( \frac{2}{z} \right)(-z^3)$$
$$=(4x)(2yz-2y)+(8y)(-xz+1)+2z^2$$
$$=8xyz-8xy-8xyz+8yz+2z^2$$
$$=-8xy+8yz+2z^2$$
-------
$$f(x,y,z)=\begin{pmatrix}
x & y & z
\end{pmatrix}\begin{pmatrix}
0 & 0 & 0 \\
-8 & 0 & 8 \\
0 & 0 & 2
\end{pmatrix}\begin{pmatrix}
x \\ y \\ z
\end{pmatrix}$$
$$=\begin{pmatrix}
-8y & 0 & 8y+2z
\end{pmatrix}\begin{pmatrix}
x \\ y \\ z
\end{pmatrix}$$
$$=-8xy+8yz+2z^2$$
Dado que los determinantes de la matriz $$\begin{pmatrix}
0 & 0 & 0 \\
-8 & 0 & 8 \\
0 & 0 & 2
\end{pmatrix}$$ son ceros, la solución es indefinida.

--------

<span style="color:#7030a0">Segunda propuesta:</span>  $V()$