
Una razón para el uso de funciones es la comparación de conjuntos

¿Cuándo pasa que dos conjuntos tienen la misma cantidad de elementos?

A veces basta con contarlos...
![[Funciones 2024-04-11 01.05.08.excalidraw]]

Pero no siempre es así :(

Tenemos un problema cuando no los podemos contar.

Ej. ¿Quién tiene más elementos? 
- $A=\mathbb{N}$ (naturales)
- $B=2\mathbb{N}$ (pares)

Estos conjuntos tienen infinidades, entonces cómo se comparan?

La clave está en asociar un cada elemento de A con un único elemento de B. (Recomendado que veas el video del [Hotel Infinito](https://www.youtube.com/watch?v=Uj3_KqkI9Zo))
![[Funciones 2024-04-11 01.07.12.excalidraw]]

En este caso, los infinitos son iguales. Sin embargo, hay infinitos que son más grandes que otros.

##### Ejemplo
Sea $f:A\to B$
Donde $A=\mathbb{N}$ y $B=(0,1)$

Esta función no es biyectiva. Esto debido a que no podemos asignarle cada elemento de A a un elemento unico de B.

#duda como demuestro esto? no tome nota de eso



Una función $f$ es una "regla" que asigna a cada elemento de A a un único elemento de B
- A se llama **dominio** de $f$
- B se llama **contradominio** de $f$
- Se denota $f:A\to B$

## Tipos de funciones

- Inyectiva:
	Se cumple que $x_{1}≠x_{2}\implies f(x_{1})≠f(x_{2})$
	Aka no se repite ningún valor de $f$ en el dominio
- Sobreyectiva:
	Se cumple que $\forall y\in B\text{ }\exists x\in A:f(x)=y$
	aka se cubre todo el contradominio/rango

- <span style="color:#ff0000">Biyectiva</span>:
	Es tanto inyectiva como sobreyectiva

Si $f:A\to B$ es biyectiva, entonces existe una función inversa $g:V\to A$ tal que 
- $g(f(x))=x,\forall x\in A$
- $f(g(x))=y,\forall y \in B$

# Preimagen de un conjunto bajo una función

^59be79

#conjuntos 

Sea $f:A\to B$ y $D\subset B$. La preimagen de $D$ bajo $f$ es el conjunto
$f^{-1}(D)=\{ x\in A:f(x)\in D \}$
![[Funciones 2024-04-11 01.28.31.excalidraw]]
Si $x\in f^{-1}(D)$, entonces $f(x)\in D$

# Funciones continuas
#continuidad 
Suponga que $(X,\tau_x),(Y,\tau_y)$ son espacios topológicos. Una función $f:X\to Y$ es continua si:$$\forall U\in \tau_y,f^{-1}(U)\in \tau_x$$
aka la imagen inversa de un abierto en Y es abierta en X




Esto viene más a detalle en [[Funciones continuas en espacios métricos]]
Por qué viene ahí? porque no sabía que ese texto iba aqui

#unfinished checa onenote we que hueva poner el resto ya es la 1:30 am bye


Fun fact: para demostrar suponemos a $f$ como biyectiva

