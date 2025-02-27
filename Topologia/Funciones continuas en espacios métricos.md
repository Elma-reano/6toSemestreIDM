#continuidad 

#duda Si bien tengo entendido, una función es continua en un punto si existe una bola con radio mayor que 0 que también toca a la función.
## Definición

Existen varias definiciones :P dependiendo del contexto
- **Espacios métricos:**
Una función $f:A\to B$ es continua si $\forall x\in A\to \lim_{ x \to a }f(x)=f(a)$
$\forall\varepsilon>0\text{ }\exists\delta:d(x,a)<\delta\implies d(f(x),f(a))<\varepsilon$

![[Funciones continuas en espacios métricos 2024-04-10 18.53.42.excalidraw]]

Esto se aborda bien en [[Límites en cálculo real a real]]

- **Espacios topológicos:**
$f:A\to B$
$a\in A\text{ }\lim_{ x \to A }f(x)=f(a)?$ #duda 
$\forall U$ abierto con $f(a)\in U\exists V$ abierto con $a\in V:V\subset f^{-1}U$

**Definición amigable en espacios topológicos**
Tenemos dos conjuntos $X$ y $Y$, cada uno con su respectiva topología $\tau_x$ y $\tau_y$. Ahora a $Y$ vamos a agarrarle un subconjunto $w$ que, fun fact, va a ser abierto.
![[Funciones continuas en espacios métricos 2024-04-10 18.59.44.excalidraw]]

Si a $X$ le aplicamos una función $f:X\to Y$, a $Y$ vamos a aplicarle la función inversa $f^{-1}$ para llegar a donde estábamos antes.
![[Funciones continuas en espacios métricos 2024-04-10 19.00.55.excalidraw]]
Si $f^{-1}(w)$ también es abierto, entonces nuestra función es continua.



## Continuidad en todo el dominio
$f:A\to B$ es continua en $A$ si es continua en $x=a\text{  }\forall a\in A$
$\forall a\in A,\forall U$ abierto con $f(a)=U\text{ }\exists V$ abierto tal que $V\subset f^{-1}(U),a\in V$
![[Funciones continuas en espacios métricos 2024-04-10 23.18.29.excalidraw]]

$f$ es continua en $A$ si $\forall U$ abierto de $B$ se tiene que $f^{-1}(U)$ es abierto en $X$.