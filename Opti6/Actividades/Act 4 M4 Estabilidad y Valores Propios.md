************

1. Para cada inciso realiza lo siguiente:
	1. Determina los valores y vectores propios
	2. Clasifica el punto crítico $(0,0)$ del sistema lineal dado
	3. Grafica los planos claves correspondientes verificando que se cumple tu conclusión (clasifica como: nodo estable, inestable, espiral estable, inestable, etc.) 
	Muestra todo tu proceso sólo en el inciso a)
 
(a) $$\begin{cases}
\frac{dx}{dt}=-5x+3y \\
\frac{dy}{dt}=2x+7y
\end{cases}$$
(b) $$\begin{cases}
\frac{dx}{dt}=-\frac{3}{2}x+\frac{1}{4}y \\
\frac{dy}{dt}=-x-\frac{1}{2}y
\end{cases}$$
(c) $$\begin{cases}
\frac{dx}{dt}=0.02x-0.11y \\
\frac{dy}{dt}=0.10x-0.05y
\end{cases}$$
[Herramienta de graficación](https://www.geogebra.org/m/vabxytnc)
 
 2. Determina la estabilidad mostrando claramente su multiplicidad algebraica y geométrica para las siguientes matrices del sistema $X'=AX$ (usa software y agrega fotos)
$$A=\begin{bmatrix}22 & -18 & 20 \\
-15 & 13 & -14 \\
-33 & 27 & -30\end{bmatrix}$$
$$B=\begin{bmatrix}-7 & 0 & 0 \\
32 & -1 & 0 \\
15 & 27 & 0\end{bmatrix}$$
$$C=\begin{bmatrix}-63 & 28 & 20 \\
228 & 109 & 36 \\
-255 & -126 & -44\end{bmatrix}$$

3. Escribe la ecuación diferencial no lineal como un sistema de EDs y luego determina los puntos de equilibrio en cada inciso. (Realiza todo tu proceso)
> a)  $x''+x'(1-x^3)-x^2=0$

Sea $y=x'=\frac{dx}{dt}$ y $y'=x''=\frac{d^2x}{dt^2}$
Sustituyendo en la ecuación original resulta $$y'+(1-x^3)y-x^2=0$$$$\therefore \begin{cases} y'=x^2+(x^3-1)y \\
x'=y \end{cases}$$

Para encontrar los puntos de equilibrio se requiere igualar $x'$ y $y'$ a 0. Por lo tanto,
$$\begin{cases}
x^2+(x^3-1)y=0 \\
y=0
\end{cases}$$
$$\therefore x^2=0$$
$$\therefore \text{El punto de equilibrio es (0,0)}$$
> b) $y''+(y')^2+2y=0$

Sea $x=y'=\frac{dy}{dt}$ y $x'=y''=\frac{d^2y}{dt^2}$
Sustituyendo esto en la ecuación original queda como resultado
$$x'+x^2+2y=0$$
$$\therefore \begin{cases}
x'=-x^2-2y \\
y'=x
\end{cases}$$
Para encontrar los puntos de equilibrio se requiere igualar $x'$ y $y'$ a 0. Por lo tanto,
$$\begin{cases}
-x^2-2y=0 \\
x=0
\end{cases}$$
$$\therefore \text{El punto de equilibrio es (0,0)}$$


<div style="page-break-after: always;">---</div>

4. Encuentra todos los puntos críticos (o de equilibrio) del sistema autónomo
> a) $$\begin{cases}
x'=x(1-x^2-3y^2) \\
y'=y(3-x^2-3y^2)
\end{cases}$$


![[Captura de Pantalla 2024-04-25 a la(s) 11.23.00 p.m..png]]

<div style="page-break-after: always;">---</div>

> b) $$\begin{cases}
x'=-2x+y+10 \\
y'=2x-y-15\frac{y}{y+5}
\end{cases}$$

Para encontrar los puntos críticos se necesita igualar $x'$ y $y'$ a 0. Por lo tanto,
$$\begin{cases}
-2x+y+10= 0 \\
2x-y-15\frac{y}{y+5}=0
\end{cases}$$
$$\begin{cases}
2x=y+10 \\
2x=\frac{y^2-10y}{y+5}
\end{cases}$$
$$y+10=\frac{y^2-10y}{y+5}\implies y^2+15y+50=y^2-10y\implies 25y+50=0$$
$$\therefore y=-2$$
$$\therefore 2x=-2+10=8\implies x=4$$
