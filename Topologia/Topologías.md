#topologia 
Las topologías son colecciones que se pueden comparar aka. conjuntos de conjuntos abiertos 

> Es topología si todos los elementos combinados con union/intersección están presentes en el conjunto

# Definición

**Una topología es una familia de conjuntos abiertos tales que su unión arbitraria es otro elemento de la familia y su intersección finita también da un conjunto abierto**
$$\cup_{i\in I}A_i \in \tau $$
```I``` es un conjunto arbitrario de cualquier cosa (no sabemos)


$$\cap_{i=1}^nA_i\in\tau$$

Lo importante de esto es que podemos describir cualquier funcion continua en función de conjuntos abiertos
#continuidad ?

<span style="color:#ff0000">NO PUEDE HABER PUNTOS FRONTERA EN CONJUNTOS ABIERTOS</span> 

# Comparación de Topologías

Se pueden comparar como conjuntos!

Sea $X=\{ a,b,c,2 \}$
$$\tau_1=\{ \emptyset,\{ a,b,c,2 \},\{ a \},\{ 2 \},\{ b \},\{ a,b \},\{ a,2 \},\{ b,2 \},\{ a,b,2 \} \}$$
$$\tau_3=\{ \emptyset,\{ a,b,c,2 \} \}$$
$$\therefore \tau_1\subset \tau_3$$

SI TENEMOS... perdon. Ahem... Si tenemos un espacio con tres (tres?) puntos $X=\{ 1,2,a,b,c \}$, entonces
$\tau_1=\{ \emptyset,X \}$
$\tau_2=\{ \emptyset,\{ 1,2,a,b,c \},\{ 1 \},\{ a \},\{ 2,c \}\{ 2,a,c \}\{ 1,2,a,c \} \}$
$\tau_3=\{ \emptyset,\{ 1,2,a,b,c \},\{ b \}\{ 2 \}\{ 2,b \} \}$
$\tau_4=\{ \emptyset, \{ 1,2,a,b,c \},\{ 1 \},\{ 2 \},\{ a \},\{ 1,2 \},\{ 1,a \},\{ 2,a \}\{  1,2,a  \} \}$

En base a estos $\tau$,

$\tau_1\subset \tau_2$               $\tau_2\not\subset \tau_3$
$\tau_1\subset \tau_3$               $\tau_3\not\subset \tau_2$
$\tau_1\subset \tau_4$               $\tau_3$ y $\tau_2$ no son compatibles


Qué sucede si es un espacio infinito? $X=\mathbb{R}$

1. $\tau_1=\{ \emptyset, \mathbb{R} \}$
2. $\tau_2=\{ \emptyset,\mathbb{R}\cup \{ A\subset \mathbb{R}:\mathbb{R} \text{ Es un conjunto finito} \} \}$
$$\tau_2=\{ \emptyset,\mathbb{R} \}\cup \{ (-\infty,a)\cup(a,\infty):a\in\mathbb{R} \}\cup \{ \mathbb{R}-\{ a_1,a_2 \}\backslash x_\alpha \in\mathbb{R},r_\alpha>0 \}$$
3. $\tau_3$ la topología inducida por la distancia $d(x,y)=|x-y|$
$$\tau_3=\{ \emptyset,\mathbb{R} \}\cup \{ (x-r,x+r):r>0,x\in\mathbb{R} \}\cup \{ \mathbb{R}-\{ a_1,a_2 \}\backslash x_\alpha \in\mathbb{R},r_\alpha>0 \}$$
4. $\tau_4$ la topología inducida por la distancia discreta
$$\tau_4=\{ \emptyset,\mathbb{R} \}\cup \{ \{ x \}:{\mathbf{x}}\in\mathbb{R} \}\cup\dots=2^\mathbb{R}$$
$$\mathbb{N}=\{ 1,2,3,4,5,6 \}≠\{ \{ 1 \},\{ 2 \},\{ 3 \},\dots \}$$


# Topología Inducida por una métrica

También conocidas como topologías métricas.

Sea $(X,d)$ un espacio métrico

$\tau_d=\{ U\subset X:\forall x\in U\exists B_r(x)\subset U \}$
Un radio mayor a 0
Conjunto U dentro del espacio X que es abierto

$\tau_d$ es una topología para X


# Video
[¿Qué es la TOPOLOGÍA? Donas, tazas y espacios topológicos.](https://www.youtube.com/watch?v=9YdpvOYvqS4)

# 4 axiomas de una topología

1. El conjunto vacío y el conjunto $X$ están en $\tau$
2. La intersección finita de conjuntos en $\tau$ está en $\tau$, es decir, si $\{ A_i \}_{i\in I}$ son conjuntos en $\tau$, entonces $\bigcap_{i\in I}A_i\in \tau$
3. La unión abitraria de conjuntos en $\tau$ está en $\tau$, es decir, si $\{ A_i \}_{i\in I}$ son conjuntos en $\tau$, entonces $\bigcup_{i\in I A_i\in\tau}$
4. El conjunto $X$ es el conjunto de todos los elementos que pueden ser alcanzados por los conjuntos en $\tau$

## Cómo le hacemos para comparar entre topologías inducidas por una métrica?

Supongamos que tenemos dos métricas $d_1$ y $d_2$ en un mismo espacio.

¿Cómo vamos a saber que todos los abiertos de $\tau_1$ están dentro de $\tau_2$?

Pues,![[Captura de Pantalla 2024-04-05 a la(s) 12.02.34 p.m..png]]
![[Captura de Pantalla 2024-04-05 a la(s) 12.02.43 p.m..png]]

Siempre habrá un radio con el que se pueda dibujar una métrica dentro de la otra sin salirse del límite

Todos los conjuntos que sean abiertos con Pitágoras son abiertos en Chebyshev y en Manhattan (y viceversa)

### Actividad Grupal
#actividad 
![[Captura de Pantalla 2024-04-05 a la(s) 12.06.08 p.m..png]]

[[Topología de Subespacio]]

