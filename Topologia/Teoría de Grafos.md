Una gráfica es una herramienta muy poderosa en las matemáticas. Las usamos para proporcionar información combinatoria de algún conjunto de puntos. Dichos grafos pueden aceptar métricas

Este *concepto* se usa en muchos campos como la informática, biología, redes sociales, etc. para representar las relaciones entre diferentes entidades.

## Tipos de Grafos

Un grafo dirigido $G$ es una colección de 
- Vértices : $V=\{ v_j: j\in J\}$
- Aristas : $E\subset V\times V$
(j es el conjunto de vértices?) #duda 

> El conjunto de aristas E es una colección de pares ordenados de vértices, y decimos que la arista $(v_i,v_j)$ está dirigida de $v_i$ a $v_j$

Ejemplo: $$G=\{ 2,3,\dots,11,(7,11),(5,11),(7,8),\dots \}$$
En este caso, las aristas y vértices quedan
$$V=\{ 2,3,4,5,6,7,8,9,10,11 \}$$
$$E=\{ (7,11),\dots,(11,10) \}$$
- G es finito si V y E son finitos
- G es simple si no tiene bucles ni aristas mútiples (del mismo vértice de inicio y mismo de destino)
- G no está dirigido si introducimos una identificación en E:
	- $(v_i,v_j)~(v_j,v_i)$
	- Ej. (3,8) es lo mismo que (8,3)

En ocasiones vamos a estudiar los subgrafos; que, como su nombre lo indica, son grafos más pequeños que vienen a partir de uno ya existente

# Subgrafos

Si $G$ y $H$ son grafos, decimos que $H$ es un subgrafo de $G$ si:
- $V(H)\subset V(G)$
- $E(H)\subset E(G)$

<span style="color:#0070c0">Ejemplo:</span> 
$$H=\begin{cases}
V=\{2,9,10,8,11\} \\
E=\{(11,2),(11,9),(11,10),(8,9)\}
\end{cases}$$
$$H_2=\begin{cases}
V=\{ 2 \} \\
E=\{ (11,9) \}
\end{cases}$$
En los subgrafos, no es a fuerza que para todas las aristas existan sus respectivos vértices.

### Caminos en un grafo

Un gamino $\gamma$ en $G$ de longitud $n=|\gamma|$ es una secuencia de vértices $(v_1,v_2,v_3,\dots,v_n)$ tal que $v_i,v_{i+1}\in E(G)$

- $v_1$ se llama vértice inicial de $\gamma$
- $v_n$ se llama vértice terminal de $\gamma$
- $\gamma$ se llama ciclo si $v_1=v_n$

#conexidad
$G$ se llama <span style="color:#ff0000">conexo</span> si $\forall v,w\in V(G)$ existe un camino entre $v$ y $w$

Si $G$ es conexo, podemos medir distancias en $V(G)$

$d(v_i,v_j)=min\{ |\gamma| : \gamma \text{ tiene vertice inicial }v_i\text{ y vertice terminal }v_j \}$

<span style="color:#00b050">Oye y... existen grafos vacíos?</span>
### Topología en un grafo G
#topologia 

Un grafo vacío o nulo $K_{0}$ es el grafo cuyos vértices y aristas son el $\emptyset$

$\tau=\{ H_a,a\in J,H_a\subset G \}$ se le llama topología en $G$ si $\tau$ es un conjunto y sus elementos son subconjuntos de $G$

1. $K_{0},G\in\tau$
2. Si $\{ A_a \}$ es una colección de elementos en $\tau$ entonces $\cup_aA_a\in\tau$ es el equivalente a que la unión de abiertos de como resultado a otro abierto
3. Si $\{A_i\}$ es una colección finita de elementos en $\tau$, entonces $\cap_iA_i\in\tau$

Ejemplo:$$V=\{ a,b,c,d \}$$$$E=\{ (a,d),(b,d),(c,d) \}$$$$\tau_1=\{ \{ (a,d) \},\{ (b,d) \},\{ (c,d) \},\{ (a,d),(b,d) \},\{ (b,d),(c,d) \},\{ (a,d),(c,d) \},\{ (a,d),(b,d),(c,d) \} \}\cup \{ \emptyset,G \}$$
Es topología? simon?

# Simplejos
#simplejos ^4e32be

## Definición

Un *n-simplejo* en $\mathbb{R}^{n+1}$ se define matemáticamente como
$$K^n=\left\{  (x_1,x_2,x_3,\dots,x_n,x_{n+1})\in R^{n+1}:\sum_{i=1}^{n+1} x_i=1,x_i≥0p \right\}$$

En palabras, un simplejo es un "*triángulo*" que a la vez no es un triángulo (pero sí es); y se usa para cosas como la triangulación

Las **caras** de un *n-simplejo* son los subconjuntos de $K^n$
$$\Delta_j^{n-1}=\left\{  (x_1,x_2,\dots x_n,x_{n+1})\in\mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_i=1,x_j=0  \right\}$$
![[Teoría de Grafos 2024-04-09 15.46.59.excalidraw]]

#solved Ver si coloco bien las caras
La cara es una dimension menor al simplejo
# Complejos Simpliciales Geométricos

También conocidos como <span style="color:#ff0000"><b>triangulaciones</b></span>, son colecciones cuyos elementos son de varias dimensiones
## Definición 

T es una triangulación si es una colección finita de simplejos de varias dimensiones tal que

1. Si $K^n\in T$ entonces cada cara $\Delta_j^{n-1}\in T$, es decir, pertenecen a T.
2. Para todo $\sigma,\tau \in T$ se cumple que $\sigma \cap \tau=\emptyset$ o que $\sigma \cap \tau \in T$
$$\sigma \cap \tau=\begin{cases}
\emptyset \\
\text{una cara en comun}
\end{cases}$$
Sus propiedades son
- La dimensión de $T$ es la dimensión más grande de sus simplejos
- El m-esqueleto de $T$ es la subcolección de simplejos de dimensión $m$ de $T$
- Fun fact: generalmente se les da una orientación en contra de las manecillas del reloj

### Ejemplos

Algunas de las cosas que se pueden triangular son:
- La esfera en $\mathbb{R}^3$
- El cilindro en $\mathbb{R}^3$
- La banda de Möbius
![[Teoría de Grafos 2024-04-09 16.17.06.excalidraw]]
En estos ejemplos se calcula la <span style="color:#0070c0"><b>característica de Euler</b></span>, la cual es un número que, no importa cuántos puntos (y los vértices y triángulos que vienen con ellos) el número nunca va a cambiar.

Dos conjuntos con características de Euler distintas no son homeomorfos. #homeomorfismo 

La fórmula es: $$X(x)=\# \Delta^0s-\#\Delta^1s+\#\Delta^2s+\dots$$
