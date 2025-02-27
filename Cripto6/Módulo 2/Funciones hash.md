Una función **hash** es una función determinística que le asigna a cada mensaje un valor cuyo tamaño siempre tiene le mismo número de bits. La convención es que la longitud en bits del mensaje es mayor al valor que retorna la función, el cual también se le conoce como **valor hash**, o simplemente, *hash*.
Hoy en día, el estándar de las funcinoes hash es $\text{SHA-512}$.

Una función hash ideal debe tener las siguientes propiedades:
- Su valor hash debe ser fácil de calcular para cualquier mensaje
- No es posible determinar un mensaje dado su valor hash, es decir, su objetivo es que no se pueda invertir la función. A esto se le llama **resistencia a la preimagen**.
	- $'abc'\to \#_1$
	- $'abd'\to \#_2$
- No es posible modificar un mensaje sin cambiar su hash
- No es viable que dos mensajes tengan el mismo hash. Esto se le conoce como **resistencia a la colisión**. En otras palabras, que sea inyectiva.

![[Funciones hash 2024-05-02 09.38.42.excalidraw|400]]

Estas funciones se pueden usar junto con otras funciones de encriptación para construir protocolos de encriptación. Supongamos que Beto y Alicia se quieren comunicar públicamente y que han intercambiado una clave secreta $k$. Sea $f_k$ la función se encriptación asociada a la llave.
Alicia le quiere enviar el mensaje $m$ a Beto, entonces ella le comunica lo siguiente:
$$ f_k(m)\oplus h(k)$$
donde $h$ es la función hash
#btw $\oplus$ es la operación XOR.

Dado que Beto tiene la llave $k$ y su valor hash $h(k)$, para recuperar $f_k(m)$ calcula
$$f_k(m)\oplus h(k) \oplus h(k)=f_k(m)$$
Esto es posible porque la operación XOR es equivalente a una adición módulo 2.

![[Funciones hash 2024-05-02 09.53.11.excalidraw]]

Finalmente, para obtener $m$, Beto utiliza el mapa de decodificación $g_k$ 

Sean A y B dos conjuntos no vacíos. Entonces, una función hash es un mapa $h:A\to B$ con las siguientes propiedades:
- *h* es libre de colisiones, es decir, no existe un método eficiente para encontrar dos elementos $a_{1},a_{2}\in A$ tales que $f(a_{1})=f(a_{2})$
- *h* no se puede invertir eficientemente: si $b\in Im(h)$, no existe un método viable que permita encontrar $a\in A$ tal que $h(a)=b$
#btw $Im$ es la preimagen (o imagen?), aka la inversa del hash

En términos prácticos, sí es importante tener una forma de invertir la función hash. Por lo tanto, llegamos al concepto de la **escotilla**: la cual es una función hash con un mapa $h:A\to B$ que satisface que:

#### Factorización

Sea $\mathcal{P}$ el conjunto de los números primos impares. Sea $h:\mathcal{P}\times\mathcal{P}\to \mathbb{N}$ igual a 
$$h(x,y)=xy=n$$
No se conoce un método viable que permita factorizar $n$ si $p-1$ y $q-1$ tienen factores primos grandes. Entonces, $h$ es un ejemplo de una función de una sola vía
<div style="page-break-after: always;"></div>

#### Cuadrados Perfectos Modulares

Sean $p$ y $q$ dos primos impares tales que $p,q\geq 3$, y sea $n=pq$. Sea también $h:U(n)\to U(n)$ igual a 
$$h(x)=x^2\text{ mod }n$$
Entonces, tenemos que:
- Si conocemos $p$ y $q$, entonces, dado $y\in Im(h)$, es posible encontrar de manera eficiente un $x$ tal que $y=x^2=h(x)$
- Si solo conocemos $n$, no se conoce un algoritmo eficiente que pueda encontrar $x$ tal que $h(x)=x^2=y$
- Es posible restringir el dominio de $h$ para que sea libre de colisiones. En este caso, los primos $p$ y $q$ serían la escotilla de $h$.


#### Logaritmos Discretos

Ver [[Criptografía de clave pública#^79d73f]]

Si $G=\langle g \rangle$, donde $g\in G$, y $h\in G$ tal que $h=g^k$, entonces $k$ es el logaritmo discreto de $h$. Consideremos $h:U(p)\to U(p)$, donde $p$ es un número primo grande. Nótese que $U(p)$ es cíclico. Entonces, la función
$$h(k)=g^k\text{ mod }p$$
es una función de una sola vía; ya que no se conoce un algoritmo eficiente que resuelva el problema del logaritmo discreto si $p-1$ tiene un factor primo grande.