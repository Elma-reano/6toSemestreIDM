## Teorema de Euler

En el módulo anterior se menciona el la **función de Euler**, la cual se expresa como $\phi:\mathbb{N}\to \mathbb{N}$; y cuenta el número coprimos de $n$.
Si $n=1$, entonces $\phi(1)=1$. En cambio, si $n>1$, entonces $\phi(n)$ cuenta cuantos enteros $m$, tales que $1≤m<n$, satisfacen $mcd(m,n)=1$, es decir, son coprimos.

En general, $|U(n)|=\phi(n)$. Es más, $\phi(p)=p-1$ si $p$ es un número primo. Por otro lado, $\phi(p^k)=p^k-p^{k-1}$
Además, $$\phi(n)=\phi(p_{1}^{k_1}p_{2}^{k_2}p_{3}^k\dots p_{n}^k)$$
$$=(p_{1}^{k_{1}}-p_{1}^{k_{1}-1})(p_{2}^{k_{2}}-p_{2}^{k_{2}-2})\dots(p_{m}^{k_{m}}-p_{m}^{k_{m}-1}$$
$$=n\prod_{p|n}\left( 1-\frac{1}{p} \right)$$
#### Ejemplo

Si $n=12$, entonces $|U(n)|=4$ ya que $1,5,7,11$ son los primos relativos (coprimos) de $12$
$$\phi(12)=\phi(2^23)=\phi(2^2)\phi(3)=(2^2-2)(3-1)=4$$
En este caso, se cumple que $|U(n)=\phi(n)|$.


Además, sean $a,n\in\mathbb{Z}:n>0\land mcd(a,n)=1$. Entonces, $$a^{\phi(n)}\equiv 1\text{ mod }n$$
#### Ejemplo
Sean $a=5$ y $n=3$. Claramente $mcd(5,3)=1$, así que 
$$5^{\phi(3)}\equiv 1\text{ mod }$$
$$25\equiv 1\text{ mod }3$$
## Teorema de Fermat

Sea $p$ un número primo y supongamos que $p$ no divide a $a$. Entonces $$a^{p-1}\equiv 1\text{ mod }p$$
Es más, para cualquier $b\in\mathbb{Z},b^p\equiv b\text{ mod }p$. 

Nótese que el teorema de Fermat es un caso especial del teorema de Euler cuando $n=p$. Para verlo en acción, sea $p=7$ y $a=2$, entonces 
$$2^{7-1}\equiv 1\text{ mod }7$$
$$\therefore64\equiv 1\text{ mod }7$$

#### Ejemplo

$$U(5)= \langle g\rangle= \{ g^1,g^2,g^3,g^4 \}$$
$$|U(5)|=\phi(5)=5-1=4$$
$$\forall a\in U(5),a^{5-1}\equiv 1\text{ mod }5$$
$$|U(5)|=|g|=4$$

## Algoritmo Euclidiano

Este algoritmo nos permite calcular el mcd de dos enteros $a$ y $b$. Este se basa en el hecho de que si $a>b$, entonces $\text{mcd}(a,b)=\text{mcd}(b,a\text{ mod }b)$.

#### Ejemplo

Sean $a=168$ y $b=154$. Entonces, 
$$\text{mcd}(168,154)=\text{mcd}(154,168\text{ mod }154)$$
$$=\text{mcd}(154,14)$$
$$=\text{mcd}(14,154\text{ mod }14)$$
$$=\text{mcd}(14,0)$$
$$\therefore\text{mcd}(168,154)=14$$
<div style="page-break-after: always;"></div>

### Pseudocódigo

Dado lo anterior, podemos proponerlo de esta manera
**inicializar** $a,b\in\mathbb{Z},a>b;$
**repetir** mientras $b≠0$
	$r=a\text{ mod }b$
	$a=b$
	$b=r$
**retornar** a

El algoritmo euclidiano tiene una versión más cabrona...
## Algoritmo Euclidiano Extendido

Este algorimo no sólo nos da el máximo común divisor $\text{mcd}(a,b)$; sino que también nos encuentra enteros $x$ y $y$ tales que $ax+by=d$.
#btw $d$ es el máximo común divisor
### Pseudocódigo

**inicializar** $a,b\in\mathbb{Z}:a>b$
**si** $b=0$:
	$d=a$, $x=1$, $y=0$
	**retornar** $d,x,y$
$x_{1}=0,x_{2}=1,y_{1}=1,y_{2}=0$
**repetir** mientras $b\neq0$
	$q=\left\lfloor  \frac{a}{b}  \right\rfloor,r=a-qb,x=x_{2}-qx_{1},y=y_{2}-qy_{1}$
	$a=b,b=r,x_{2}=x_{1},x_{1}=x,y_{2}=y_{1},y_{1}=y$
$d=a,x=x_{2},y=y_{2}$
**retornar** $d,x,y$

#btw Lo de $\left( \left\lfloor  \frac{a}{b}  \right\rfloor \right)$ es un *floor*.
<div style="page-break-after: always;"></div>

Entonces, sean $a=168$ y $b=154$. Entonces,

| i   | $q$ | $r$ | $x$ | $y$ | $a$ | $b$ | $x_{1}$ | $x_2$ | $y_1$ | $y_2$ |
| --- | --- | --- | --- | --- | --- | --- | ------- | ----- | ----- | ----- |
| 1   | -   | -   | -   | -   | 168 | 154 | 0       | 1     | 1     | 0     |
| 2   | 1   | 14  | 1   | -1  | 154 | 14  | 1       | 0     | -1    | 1     |
| 3   | 11  | 0   | -11 | 12  | 14  | 0   | -11     | 1     | 12    | -1    |
Así que $d=14,x=1,y=-1$


Este algoritmo también sirve para encontrar inversos multiplicativos. Sean $b=27\in U(50)$ y $a=50$. Entonces 


| i   | $q$ | $r$ | $x$ | $y$ | $a$ | $b$ | $x_{1}$ | $x_2$ | $y_1$ | $y_2$ |
| --- | --- | --- | --- | --- | --- | --- | ------- | ----- | ----- | ----- |
| 1   | -   | -   | -   | -   | 50  | 27  | 0       | 1     | 1     | 0     |
| 2   | 1   | 23  | 1   | -1  | 27  | 23  | 1       | 0     | -1    | 1     |
| 3   | 1   | 4   | -1  | 2   | 23  | 4   | -1      | 1     | 2     | .1    |
| 4   | 5   | 3   | 6   | -11 | 4   | 3   | 6       | -1    | -11   | 2     |
| 5   | 1   | 1   | -7  | 13  | 3   | 1   | -7      | 6     | 13    | -11   |
| 6   | 3   | 0   | 27  | -50 | 1   | 0   | 27      | -7    | 50    | 13    |
Por lo tanto, $d=1, x=-7 \text{ y }y=13$. Esto implica que $27^{-1}\equiv 13\text{ mod }50$
