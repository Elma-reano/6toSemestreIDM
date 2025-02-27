#topologia
Geometría, Euclides y sus elementos.

Cómo estudiar la forma de algo sin necesidad de medidas?

## Espacios Métricos

- ¿Cómo medimos distancias?
- De qué otra forma es posible medir distancias en un plano?
- En qué otros espacios pueden medir distancias?
- Qué es una distancia o métrica?

La <span style="color:#ff0000">distancia</span> tiene las siguientes propiedades
- Es un número no negativo
- Depende de la unidad
- Es simétrica

Formalmente, una distancia se define como:...

### Distancia: definición

Un par $(X,d)$ se llama espacio métrico si $X$ es un conjunto y $d$ es una función 
$$ d:X\times X\rightarrow \mathbb{R} $$
1. La función $d$ nunca es negativa
		Si $x\in X,y\in X$, entonces $d(x,y)≥0$
2. La función $d$ es cero si y sólo si es el mismo punto
		$d(x,y)=0\Leftrightarrow x=y$
3. La función es simétrica
		$d(x,y)=d(y,x)$
4. La función cumple la desigualdad triangular
		Si quiero pasar de un punto A a un punto B, la distancia más corta es una línea recta
		$d(x,z)≤d(x,y)+d(y,z)$

Imagínate a X como el "universo"

Si no se cumple alguna de estas condiciones, <span style="color:#ff0000">NO</span> es una métrica.

Algunos ejemplos de espacios métricos

- [[Distancia de Pitágoras]]
- [[Distancia de Hamming]]
- [[Distancia de Chebyshev]]
- [[Distancia Discreta]]
- [[Distancia Lp]]

#reminder $|x+y|≤|x|+|y|$


Entonces, podemos pensar en conjuntos más interesantes como los polinesios de grado a lo más 2:
$$R[x]_2=\{ax^2+bx+c:a,b,c\in\mathbb{R}\}$$

Pero entonces, cómo podemos medir distancias entre polinomios??

En este caso, podemos usar dos cosas:
1. Podemos medir las distancias en cada valor del dominio
2. Podemos obtener la diferencia de los valores del dominio de las funciones y agarrar la más grande
![[Captura de Pantalla 2024-04-01 a la(s) 4.47.27 p.m..png|250]]

![[Topología 2024-04-02 11.52.19.excalidraw|250]]


#### Otro ejemplo

**Distancia en un grafo G**

Dado un conjunto de vértices $v(G)$ y aristas $e(G)$, ¿Cómo podríamos definir una métrica en el conjunto de vértices?

Si A,B son vértices, entonces

$$ d(A,B)={\matrix{0, A=B\\ min\{k:\exists se me paso xd}}$$
![[Drawing 2024-04-02 11.48.45.excalidraw]]

## Esferas y bolas de radio **r**

Dada una distancia en un espacio métrico X $(X,d)$ y un punto $x\in X$, definimos la esfera de radio $r$ con centro en $x$ como $$S_r^d(x)=\{y\in X: d(x,y)=r\}$$
¿Qué es una bola? No es **literal** una bola/pelota. Sino que es agarrar un punto y aumentar el radio hasta cierta distancia diferente de 0 **SIN** incluir el limite.

Ej si tuvieramos una bola de radio 1 con centro en el origen, podríamos visualizarla como algo similar a $$x^2+y^2<1$$
Porque sí incluye todo adentro jeje