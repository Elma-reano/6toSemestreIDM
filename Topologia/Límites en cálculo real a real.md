
En cálculo el límite es: $f:\mathbb{R}\to \mathbb{R}$

En cambio, la noción de límite en cálculo diferencial es $\lim_{ x \to a }f(x)=L$
Si $x$ está cerca de $a$, entonces $f(x)$ está cerca de $L$

Si quiero que $f(x)$ esté cerca de $L$ (tan cerca como desee) entonces $x$ debe estar cerca de $a$ tal que $$\forall\varepsilon>0,\exists\delta>0:|x-a|<\delta\implies|f(x)-L|<\varepsilon$$
![[Límites en cálculo real a real 2024-04-11 16.01.29.excalidraw]]

Dicho de otra manera, en $f:\mathbb{R}\to \mathbb{R}$, con la métrica usual$$\lim_{ x \to a }f(x)=L $$
Siempre y cuando se cumpla lo expresado anteriormente, pero lo repito por si acaso $$\forall\varepsilon>0,\exists\delta>0:|x-a|<\delta\implies|f(x)-L|<\varepsilon$$
Si quisiéramos probar lo contrario, es decir, $\lim_{ x \to a }f(x)≠L$, entonces tendríamos que decir que $\exists\varepsilon>0:\forall\delta>0,\exists x\in R:|x-a|<\delta \text{ pero } |f(x)-L|≥\varepsilon$

El límite no existe si $\forall L\in \mathbb{R}, \lim_{ x \to a }f(x)≠L$

<span style="color:#00b050">Cómo funcionan los límites con diferentes espacios métricos?</span> 

## Límites en Espacios Métricos

Suponiendo que $f:A\to B$ donde $(A,d_A)$ y $(B,d_B)$ son espacios métricos, definimos el límite $\lim_{ x \to a }f(x)=L$ si se cumple que: $$\forall\varepsilon>0,\exists\delta>0:x\in B_\delta(a)\implies f(x)\in B_\varepsilon(L)$$
![[Límites en cálculo real a real 2024-04-11 16.16.23.excalidraw]]
Otras formas de expresarlo:
- $\forall\varepsilon>0,\exists\delta>0:|x-a|<\delta\implies|f(x)-L|<\varepsilon$
- $\forall\varepsilon>0,\exists \delta>0:d(x,a)<\delta\implies d(f(x),L)<\varepsilon$
- $\forall\varepsilon>0,\exists\delta>0:x\in B_\delta^{d_A}(a)\implies f(x)\in B_\varepsilon^{d_B}(L)$
- $\forall\varepsilon>0,\exists\delta>0:B_\delta(a)\subset f^{-1}(B_\varepsilon(L))$
- $\forall\varepsilon>0,\exists\delta>0:B_\delta(a)\subset f^{-1}(B_\varepsilon(L))$
- $\forall\varepsilon>0,a\text{ es un punto interior de }f^{-1}(B_\varepsilon(L))$

Esto tiene que ver con la [Preimagen de un conjuto bajo una función](Funciones#^59be79)

$f^{-1}(D)=\{ x\in A:f(x)\in D \}$

