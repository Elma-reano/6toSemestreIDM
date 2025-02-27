#topologia 
Usualmente, tenemos subconjuntos de un espacio topológico donde queremos trabajar
- La parte no negativa de los números reales (por ejemplo: un caso de la vida real puede ser el tiempo tiempo)
- Una región del plano solamente (dominios de funciones)

### ¿Cómo le podemos heredar a una topología a partir de la que ya tiene el espacio total?

Para $\mathbb{R}$, a partir de la topología donde los abiertos se ven como una unión de intervalos:$$(x-r,x+r)$$
Por otro lado, para $\mathbb{R}^2$, a partir de la topología donde los abiertos se ven como uniones de bolas

![[Captura de Pantalla 2024-04-05 a la(s) 5.55.35 p.m..png]]

# La topología de subespacio

Supongamos que X es un espacio topológico con topología $\tau$ 
![[Topología de Subespacio 2024-04-08 15.33.58.excalidraw]]
Tomemos $A\subset X$, como un subconjunto
Definimos $\tau_A$ como la topología de subespacio en A:
$$\tau_A=\{ U\cap A:U\in\tau \}$$
Donde $U\cap A$ es los abiertos de A que son subespacio de X

---------------

Supongamos $A=[0,\infty)$ con métrica normal $d(x,y)=|x-y|$

Dibujando los abiertos de A en $\mathbb{R}$
![[Topología de Subespacio 2024-04-08 20.36.12.excalidraw]]

La topología de X es
$$\tau_x=\{ \emptyset,\mathbb{R}, \text{uniones de intervalos}, (x-r,x+r) \}$$
La topología del subespacio A sería
$$\tau_A=\{ U\cap A:U\in\tau \}$$
Podemos decir que los intervalos de $(x-r,x+r)$ se podrían hacer 
$$\tau_A=\{ \emptyset,A \}\cup\{[0,1),(2,3),\dots\}$$
Donde los intervalos son

Dentro de A$$\{ \emptyset,A \}\cup \{ \cup_{\alpha \in J}\text{ } U_\alpha:U_\alpha=(a_\alpha,b_\alpha)\land a_\alpha>0\}$$
o parciales en A
$$\{ \emptyset,A \}\cup \{U_\alpha=[0,b_\alpha):a_\alpha,b_\alpha \in\mathbb{R}\}$$
Donde, en $\cup_{\alpha\in J}U_\alpha$, $\alpha \in J$ puede ser
- $\{ 1,2,3,\dots,n \}$
- $\mathbb{N}$
- $\mathbb{R}$

Ya tenemos 2 de los tres posibles intervalos:
- Los que están dentro de A
- Los que están dentro de A
- Los que no tocan A (el que falta)


Por otro lado, dibujando los abiertos de A en $\mathbb{R}^2$
![[Topología de Subespacio 2024-04-09 10.24.26.excalidraw]]

#duda No le veo estructura a las notas de OneNote de esto