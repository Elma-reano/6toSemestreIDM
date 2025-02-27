#conexidad #topologia 

Un espacio es conexo por caminos si, intuitivamente, se puede unir todo par de puntos por un camino continuo.

![[Conexidad de un espacio topológico 2024-04-11 16.40.17.excalidraw]]

## Separación de un conjunto

Una separación de $A\subset X$ es un par de abiertos $(U,V)$ tales que:
1. $A\cap U≠\emptyset\land A\cap V≠\emptyset$
2. $A\subset(U\cup V)$
3. $A\cap U\cap V=\emptyset$

Ej. #duda esto dibujo está correcto?

![[Conexidad de un espacio topológico 2024-04-12 09.52.03.excalidraw]]

### Ejemplo
Un conjunto A se dice que es conexo si no existe una separación para él.

Sean $U=(-\infty,4.5)$ y $V=(4,\infty)$ y $A=(2,4)\cup(5,7]\cup \{ -n \}_{n\in\mathbb{N}} \}$

Es A conexo?

Para que sea conexo, no deben de cumplirse estas condiciones
#duda es conexo con que una no se cumpla o no se deben de cumplir todas?
1. $A\cap U≠\emptyset\land A\cap V≠\emptyset$


2. $A\subset(U\cup V)$


3. $A\cap U\cap V=\emptyset$


# Relación de Equivalencia

Sea un conjunto $X$, una relación de equivalencia es una regla:
- Reflexiva: $x\sim x$
- Simétrica: $x\sim y\implies y\sim x$
- Transitiva:$x\sim y\land y\sim z\implies x\sim z$
$$x\sim y=\Leftrightarrow Reglas(x,y)$$

Si tenemos una clase de equivalencia, automáticamente estamos haciendo particiones

![[Conexidad de un espacio topológico 2024-04-12 12.07.29.excalidraw]]

# Componentes Conexos

### Partición de un espacio en componentes

Definimos la siguiente relación de equivalencia en $X$ como $$x\sim y\Leftrightarrow \exists C\text{ conexo}:x,y\in C$$
1. 