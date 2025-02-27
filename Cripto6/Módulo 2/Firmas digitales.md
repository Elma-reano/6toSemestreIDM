Una forma robusta de autenticación es la que proporciona un protocolo de firma digital. Se puede entender como la contraparte digital de la firma escrita, pero para mensajes electrónicos o digitales. Una firma digital se puede considerar como un procedimiento matemático para manejar las siguientes necesidades de autenticación:
- Verificar la autenticidad del remitente
- Verificar que el mensaje no ha sido manipulado
- Proporcionado un medio para evitar la negación
Estos son los requisitos esenciales de cualquier firma escrita o electrónica.

Matemáticamente, un protocolo de firma digital consta de estos algoritmos criptográficos
- <span style="color:#0070c0"><b>Algoritmo de Generación de Claves:</b></span> es un algoritmo que selecciona una clave privada al azar de un conjunto de claves privadas y luego emite la clave privada y su pública correspondiente
- <span style="color:#0070c0"><b>Algoritmo de Firma Digital:</b></span> es un algoritmo que, dado un mensaje $m$, produce una firma que estará vinculada al mensaje
- <span style="color:#0070c0"><b>Algoritmo de Verificación de Firma Digital:</b></span> tiene como entradas el mensaje $m$, una clave pública $k$ y una firma $\mathcal{S}$ y luego, basándose en estas entradas, acepta o rechaza la autenticidad del mensaje.


Uno de los protocolos de firma digital más usados es el "*Digital Signature Algorithm*", mejor conocido como <span style="color:#00b050"><b>DSA</b></span>. 

Supongamos que Alicia le quiere mandar un mensaje a Beto. Si deciden utilizar DSA deben seguir una serie de pasos. 
El primero de estos es escoger algunos parámetros.
##### Parámetros
- Alicia elige aleatoriamente un numero primo $q$
- Alicia elige otro número primo $p$ tal que $p\equiv 1\text{ mod }q$
- $|U(p)|=p-1\text{ y }q|(p-1)$. Entonces existe un entero $g\in U(p):|g|=q$ 
	- #btw Se refiere a que queremos que $q$ sea un divisor de $p-1$ y que $U(p)$ es cíclico.
	- Entonces, el orden de $g$ es $q$. $g^q=e,|g|=q$

##### Firma privada y claves públicas
- Alicia elige aleatoriamente una llave privada $x \in U(p)$
- Alicia calcula $y\equiv g^x\text{ mod }p$
- La <span style="color:#ec05f0">llave pública</span> es $(p,q,g,y)$, mientras que la llave privada es $x$

Reminder de que x es, naturalmente, <span style="color:#ff0000">privado</span>
##### Algoritmo de firma
- Sea $m$ el mensaje transmitido y $h(m)$ su valor *hash*.
- Alicia genera aleatoriamente, por cada mensaje, un número entero $k\in U(q)$ y calcula $r\equiv(g^k\text{ mod }p)\text{ mod }q$
- Si $r=0$, elige otro $k$
- Calcula $s\equiv k^{-1}(h(m)+xr)\text{ mod }q$
- Si $s=0$, elige otro $k$
- La firma digital es $(r,s)$

##### Algoritmo de verificación
- Beto calcula un entero $t$ tal que $st\equiv 1\text{ mod }(p-1)$. Además, calcula los dos enteros $u_{1}$ y $u_{2}$ que son iguales a:
$$u_{1}\equiv th(m)\text{ mod }q$$
$$u_{2}\equiv tr\text{ mod }q$$
- Beto obtiene el entero $g^{u_{1}}y^{u_{2}}\text{ mod }p$ y aplica el algoritmo de la división utilizando a $q$ como el divisor. Si el residuo es $r$, entonces Beto acepta la firma 
<div style="page-break-after: always;"></div>

<span style="color:#0070c0">Resumido matemáticamente:</span>
$$p,q,|U(p)|=p-1,q|p-1,|g|=q$$
$$x \in U(p), y=g^x\text{ mod }p, (p,q,g,y)$$
$$m, h(m), k\in U(q), s\equiv k^{-1}(h(m)+xr)\text{ mod }q,r\equiv(g^k\text{ mod }p)\text{ mod }q$$
$$(g^{u_1} y^{u_2}\text{ mod }p)\text{ mod }q\equiv r$$

## Ejemplo

Alicia quiere transmitirle a Beto el mensaje $m=16$ (alch ya bésense). Además, ella utiliza la siguiente función hash:
$$h(m)=2^m\text{ mod }19$$
Si elige la clave privada $x=3$ y los primos $p=11$ y $q=5$, ¿a qué sería igual $y$ y $g$?

Por otro lado, en el algoritmo de firma, Alicia elige de manera aleatoria el entero $k=4$. Nótese que $k\in U(q)$. ¿Cuál sería la firma digital de Alicia? ¿Aceptaría Beto esa firma?

> Cuantos elementos en $U(5)$ tienen orden 4? Este es todo el pedo

###### <span style="color:#ec05f0">Clave pública</span>

Dado que $x \in U(p)$, entonces $x \in U(11)$.  Entonces, $x \in\{ 1,2,3,4,5,6,7,8,9,10 \}$.
Cosa que hace sentido, pues $x=3$

En cuanto a $y$ y $g$, $y\equiv g^{x}\text{ mod }p$. O sea, $y\equiv g^3\text{ mod }11$

Tenemos que utilizar la **función de Euler**.
$$g^q\equiv e\text{ mod }p$$
$$|g|=q$$
<div style="page-break-after: always;"></div>

El orden de $g$ debe de ser $q=5$. Por lo tanto
$$\begin{matrix}
|1|=1 & |2|=10 & \color{#3970d3}|3|=5 & \color{#3971d3}|4|=5 \\
\color{#3972d3}|5|=5 & |6|=10 & |7|=10 & |8|=10 \\
\color{#3973d3}|9|=5 & |10|=2
\end{matrix}$$
Podemos elegir cualquiera de los que tienen orden $5$ (3, 4, 5, 9), yo elijo el número $4$.
$$4^5\equiv 1\text{ mod }11$$

Como $g=4$, entonces $y\equiv 4^3\text{ mod }11$, entonces $y=9$. Por lo tanto, la clave pública es $(11,5,4,9)$

###### <span style="color:#ec05f0">Algoritmo de firma</span>

En el algoritmo de firma la k vale 4. Entonces
$$r\equiv(g^k\text{ mod }p)\text{ mod }q$$
O sea
$$r\equiv (4^{4}\text{ mod }11)\text{ mod }5$$
$$r\equiv 3$$
Ahora sigue la $s$
$$s\equiv k^{-1}(h(m)+xr)\text{ mod }q$$
calculando los parametros,
$$h(16)\equiv 2^{16}\text{ mod }19\equiv 5$$
$$k=4\in U(5)$$
$$k=k^{-1}$$
$$\therefore s\equiv 4(5+(3)(3))\text{ mod }5\equiv 4(14)\text{ mod }5\equiv 56\text{ mod }5\equiv 1$$
Entonces la firma digital es $(r,s)=(3,1)$
<div style="page-break-after: always;"></div>

###### <span style="color:#ec05f0">Verificación</span> 

$$st\equiv 1\text{ mod }(p-1)$$
$$(1)t\equiv 1\text{ mod }10$$
$$\therefore t=1$$
$$u_{1}\equiv(1)(5)\text{ mod }5\equiv 0$$
$$u_{2}\equiv(1)(3)\text{ mod }5\equiv 3$$
$$\color{red}\therefore(4^{0}9^{3}\text{ mod }11)\text{ mod }3\equiv \color{blue}(729\text{ mod }11)\text{ mod }5\equiv \color{green}3\text{ mod }5\equiv \color{purple}3=r$$
![hola](https://img.favpng.com/2/21/2/emoji-emoticon-smiley-like-button-thumb-signal-png-favpng-BUN2QZQcb6hejAuixi64CquKn.jpg)


