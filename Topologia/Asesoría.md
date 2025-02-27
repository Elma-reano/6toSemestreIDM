### Asesoría

Preguntas de la Act sesion 13
Cómo sabemos que $S:\mathbb{R}^2\times \mathbb{R}^2\to \mathbb{R}^2$ es continua en todo punto?

2. $f(x,y)=2x-3y$
3. $f(x)=x^2$


Ahi va

Este es el tema

$f:A\to B$ es continua en $a_{0}\in A$ si $\forall \epsilon>0$ podemos proponer un valor $\delta>0$ tal que $d(x,a_{0})<\delta \implies d(f(x),f(a_{0}))<\epsilon$

$x=((z_{1},z_{2}),(w_{1},w_{2}))$
$a_{0}=((x_{1},x_{2}),(y_{1},y_{2}))$
A la hora de elegir métricas, no nos conviene usar métricas que usen raíces porque pues qué hueva. Entonces podemos elegir la del máximo y Manhattan

Métricas: dominio $\mathbb{R}^4\leftarrow max$
        rango $\mathbb{R}^2\leftarrow Manh$

Sea $\epsilon>0$, $\delta=\frac{}{?}$

$d(x,a_{0})<\delta\implies d(f(x),f(a))<\epsilon$
			   $d((z_{1}+w_{1},z_{2}+w_{2})(x_{1}+y_{1},x_{2}+y_{2}))$ 
$max\{ |x_{1}-z_{1}|,|x_{1}-z_{2}|,|y_{2}-w_{1}|,|y_{1}-w_{2}| \}<\delta$
$\implies|(z_{1}+w_{1})-(x_{1}+y_{1})|+|(z_{2}+w_{2})-(x_{2}+y_{2})|<\varepsilon$

![[Asesoría 2024-04-09 18.21.16.excalidraw]]
Luego alguien dice: sea $\delta=\frac{\epsilon}{4}$ (esto tendrá que ver en el $\therefore$)

$\implies|z_{1}+w_{1}-x_{1}-y_{1}|+|z_{2}+w_{2}-x_{2}-y_{2}|=$
$|z_{1}-x_{1}+w_{1}-y_{1}|+|z_{2}+x_{2}+w_{2}-y_{2}|$

Se sabe que $|a+b|=|a|+|b|$

Tons $|z_{1}-x_{1}+w_{1}-y_{1}|+|z_{2}+x_{2}+w_{2}-y_{2}|≤$
$|z_{1}-x_{1}|+|w_{1}-y_{1}|+|z_{2}-x_{2}|+|w_{2}-y_{2}|=$
$|x_{1}-z_{1}|+|y_{1}-w_{1}|+|x_{2}-z_{2}|+|y_{2}-w_{2}|$

Qué tiene que ver este con el máximo de los 4. Aquí se nos tiene que ocurrir.
Estos son, individualmente, menores o iguales que dicho máximo
$$\therefore |x_{1}-z_{1}|+|y_{1}-w_{1}|+|x_{2}-z_{2}|+|y_{2}-w_{2}|≤4max\{ \dots \}<4\delta=\frac{4\epsilon}{4}=\varepsilon$$
Entonces, $d(f(x),f(a_{0}))≤\epsilon$
#### estrategias para continuidad

Hacer una bolita $U$ abierta en B
checar que $f^{-1}(U)=?$ en A y "<span style="color:#00b050">dibujarlo</span>" 


##### estrategias de Retracto por deformación

X, A conjuntos
X "grande"
A "pequeño"

i) $r:X\to A$ continua
ii) $H(x,t)$ continua
$H(x,1)=r(x)$
$H(x,0)=x$
No importa cuánto tiempo nos tome, se queda en A
$H(x,t)=x,x\in A$
![[Funciones continuas en espacios métricos 2024-04-09 17.18.48.excalidraw]]


Hacer un retracto
4. $X=B_1((0,0))$
		$A=\{ (0,0) \}$
En este caso, se puede ver como un circulo que se reduce a un punto

Cuando no hay retracto,
$A\not\subset$
$b_i(A)≠b_i(X)$
Comparten conexidad

Qué eran los números de Betti? #TODO

Manolo hizo una pregunta sobre una pregunta de la act 13

Sea $\tau_x=\{ \{ a \},\{ c \},\{ a,c \},\{ b,c \},X,\emptyset \}$
Si $A=\{ a,b \}$
Cuales son los puntos cerradura de A ($\bar{A}$)?

Son a y b. 

## Métricas equivalentes

$$d(x,y)=max\{ |x_{1}-x_{2}|,|y_{1}-y_{2}| \}$$
$$h(x,y)=|x_{1}-x_{2}|+|y_{1}-y_{2}|$$
$$?*d(x,y)≤h(x,y)≤?*d(x,y)$$
Donde ? son constantes que vamos a colocar

$$?max\{ |x_{1}-x_{2}|,|y_{1}-y_{2}| \}≤|x_{1}-x_{2}|+|x_{1}-x_{2}|$$
Aqui se presentan dos casos

Caso 1: $max=|x_{1}-x_{2}|$
$$1max=|x_{1}-x_{2}|≤|x_{1}-x_{2}|+|y_{1}-y_{2}|$$
Caso 2: $max=|y_{1}-y_{2}|$
$$1max=|y_{1}-y_{2}|≤|y_{1}-y_{2}|$$

Sea el que sea el que se elija, es mayor que el otro. Por lo tanto, 2\*max es mayor que los dos elementos sumados
$$\therefore 1d(x,y)≤h(x,y)≤2d(x,y)$$
