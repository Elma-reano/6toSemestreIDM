 #topologia #conjuntos #metricas
 

Por ahora, estaremos viendo espacios métricos y distancias

## Conjuntos Abiertos

Son conjuntos que tienen intervalos abiertos $(-1,3),(-\infty,\sqrt{2}),(-\infty,\infty),(0,0),(a,b)$
Pensemos en el plano con métrica de Pitágoras como vivimos normalmente.

<span style="color:#0070c0">Ejemplo. El conjunto es abierto?</span>
$$(-\infty,8)\cup[10,20)$$
	No. Porque tiene una **orilla** en 10 
------
$$\mathbb{R} \backslash \mathbb{Z}$$
![[Topología Métrica 2024-04-02 12.02.10.excalidraw]]
	Si porque es no incluyente de los puntos enteros? **Son uniones de intervalos**
------

$$[d(a,b)=|b-a|]\in \mathbb{R}$$
![[Topología Métrica 2024-04-02 11.57.34.excalidraw]]
	Ni siquiera es un conjunto XDDDDDDDDDDDDDDDDDDD
-----
$$S_r^d(x)=\{x-r,x+r\}$$
![[Topología Métrica 2024-04-02 11.59.51.excalidraw]]
	Sí es abierto porque es una bola no incluyente

Este pedo es diferente cuando son dos dimensiones

## Conjunto Abierto: Definición

Suponga que $(X,d)$ es un espacio métrico y $A\subset X$ un subconjunto.

(Imagínate a X como el "universo" y a A como un conjunto dentro de él)

A es un conjunto abierto si: $$\forall x\in A,\exists r>0:B_r^d\subset A$$
Es decir, A es un conjunto abierto si para todos los puntos dentro de A existe una bola $B_r^d$ con radio mayor a cero que queda dentro del conjunto sin salirse.

Por cierto, para que sea abierto tiene que ser una desigualdad (aka <>, no ≤≥) porque si hubiera un límite hay puntos en el límite y las bolas se saldrían

Oye y el conjunto no abierto?

### Conjunto no Abierto

El conjunto NO abierto se define como $$\exists x\in A:\forall r>0, B_r^d(x)\not\subset A$$
Es decir, existe al menos un punto dentro de A que, sin importar la magnitud del radio, está fuera del conjunto.
<span style="color:#ff0000">OJO</span>: No confundir con un conjunto **cerrado**.

También, un conjunto puede ser abierto con una métrica y con otra no.

Por ejemplo: un circulo...
- En la métrica de Pitágoras: no es
- En la métrica del Máximo: no es
- En la métrica de Manhattan: no es
- En la métrica discreta: smn

![[Topología Métrica 2024-04-02 13.19.10.excalidraw]]
Para hacer el *proceso* de verificar si es abierto o no hay que hacerlo viendo si NO es abierto, es decir, checar si existe algún punto en el radio de B (las figuras delineadas fuera del circulo original)

En este caso, todas las métricas son incluyentes de los puntos externos menos la discreta; porque la discreta no toma en cuenta nada lol

## Conjunto Cerrado

Supongamos que $(X,d)$ es un espacio métrico y $A\subset X$ es un subconjunto.

### Conjunto Cerrado: Definición

A es un conjunto cerrado si $X\backslash A$ es un conjunto abierto

<span style="color:#ff0000">OJO:</span> que un conjunto sea no abierto no significa que sea cerrado.

# <span style="color:#7030a0">Tipos de puntos en un conjunto</span> $A\subset X$ 
 
![[Topología Métrica 2024-04-02 15.17.57.excalidraw]]

- Punto de A: 
$$ x\in A$$
- Punto interior de A: 
	- <span style="color:#0070c0">Por dentro</span> (duh)
	- Estos y los puntos de A son los que tienen que estar si o si dentro de A
	- $\dot{A}$ 
$$x\in A \land \exists r>0:B_r^d(x)\subset A$$
- Punto de Cerradura: 
	- "pegados" al límite
	- Es como esa persona que no es de tu familia pero ahí está siempre
	- <span style="color:#0070c0">Son puntos que cuando hacen su bolita tocan al conjunto</span>
	- (Ver antes los puntos límite) pueden estar tocándose solo a sí mismos
	- Todos los puntos interiores son cerradura; pero no todos los cerradura son interiores.
	- $A'$ 
$$\forall r>0:B_r^d(x)\cap A≠\emptyset$$
- Punto Límite de A
	- "Muy pegados" al límite (más que los cerradura)
	- <span style="color:#0070c0">Son los que con su bolita tocan al conjunto en un punto diferente de sí mismos</span> 
	- Casi siempre son igual a los cerradura, el pedo es cuando el conjunto incluye puntos únicos y aislados
	- $\bar{A}$ 
	- Creo que la expresion matematica esta incompleta #duda 
$$\forall r>0,\exists y≠x:y\in B_r^d(x)\cap A$$
- Punto Frontera de A
	- Están pegados a A y a X\\A
	- <span style="color:#0070c0">Cuando hacen bola tocan a A y al complemento de A</span> 
	- Están en la mera linea I think
	- ∂A
$$ \forall r>0:B_r^d(x)\cap (X\backslash A)≠\emptyset$$

### Casos especiales
- Conjunto Vacío Ø
	- No tiene puntos, por lo que no hay nadie dentro que no sea punto interior. Entonces todos los puntos son interiores ;)
		Por lo tanto, es abierto
	- Si a X le restamos el conjunto vacío nos da X ($X-\emptyset=X$), y es abierto. Por lo tanto, también es cerrado :v


Se sabe que, por definición, A es cerrado si X-A es abierto.

<span style="color:#7030a0"><b>Propiedad</b></span>
Si $x\in A$ y tomas $r>0$, entonces
$x\in B_r(x)$
$x\in B_r(x)\cap A≠0\Rightarrow x\in \bar{A}$

Si x está dentro de la bola y está dentro de A

Que hueva seguirle a esto
![[Captura de Pantalla 2024-04-04 a la(s) 5.55.09 p.m..png]]

### Actividad grupal
#actividad

![[Captura de Pantalla 2024-04-04 a la(s) 6.04.47 p.m..png]]

