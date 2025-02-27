
Estas son distancias utilizadas para medir la distancia entre **conjuntos**. 
#conjuntos 

# Distancia de Hausdorff

Tomemos un espacio métrico $(X,d)$ y dos conjuntos no vacíos $A$ y $B$.

$d_H(A,B)=max\{ sup\{ inf \{ d(a,b) \}_{b\in B}\}_{a\in A}\text{ , }sup\{ inf\{ d(a,b) \}_{a\in A} \}_{b\in B} \}$

Pero, qué es <span style="color:#ff0000">inf</span> y <span style="color:#0070c0">sup</span>??? Son el **ínf**imo y **sup**remo

- <span style="color:#ff0000">inf</span>imo: es el mínimo de cantidades a partir de los mínimos de varios conjuntos de un universo. <span style="color:#00b050">Es el mínimo de mínimos.</span>
- <span style="color:#0070c0">sup</span>remo: es como el mínimo pero en máximo. <span style="color:#00b050">El máximo de máximos</span>

### Ejemplo
Tomemos el plano con la métrica euclidiana y sean 
$A=\{ (0,0),(1,0),(0,1) \}$
$B=\{ (0,0)(1,0),(0,1),(1,1) \}$
![[Distancias Hausdorff y Gromov-Hausdorff 2024-04-11 00.05.52.excalidraw]]
## Vecindades de radio *r* alrededor de A

Una r-vecindad es el siguiente conjunto: $$A_r=\{ x\in X:d(x,A)<r \}$$
$$\text{donde }d(x,A)=inf\{ d(x,y) \}_{y\in A}$$
En palabras más simples, una r-vecindad es como una "bola" pero en la métrica de Hausdorff
$$x\in A\implies d(x,A)=0$$
![[Distancias Hausdorff y Gromov-Hausdorff 2024-04-11 00.29.02.excalidraw]]
Es como un espacio personal? #solved Smn 

# Distancia de Gromov-Hausdorff

Se utiliza cuando se desea comparar conjuntos en distintos espacios métricos.

Sea $A\subset X$ un espacio métrico
y $B\subset Y$ otro espacio métrico

Inventamos un espacio $Z$ más grande donde vivan $X$ y $Y$.
$$Z=X\bigsqcup Y=\{ (x,1):x\in X \}\cup \{ (y,2):y\in Y \}$$
(El 1 y 2 funcionan como etiquetas en este ejemplo)

<span style="color:#ff0000">Que chingados es</span> $\bigsqcup$ <span style="color:#ff0000">?</span> 

![[Distancias Hausdorff y Gromov-Hausdorff 2024-04-11 00.38.41.excalidraw]]

$X=\{ x \}$                       $X\bigsqcup Y=\{ x,a,b \}$
$Y=\{ y \}$

![[Distancias Hausdorff y Gromov-Hausdorff 2024-04-11 01.01.45.excalidraw]]