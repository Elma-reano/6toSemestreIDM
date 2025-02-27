## Cifrado de Permutación

El algoritmo de encriptación más simple es el **cifrado de permutación**. Un ejemplo de esto fue la encriptación de la frase "LA PRUEBA DE TURING", la cual se dividía en unidades de cuatro letras y luego a cada unidad se le aplicó la permutación $\alpha(1324)$. Con esto se obtuvo el siguiente texto cifrado:
$$\text{RPLAABUEUTDEGNRI}$$

Como es de esperarse, el texto original se puede decodificar con la permutación inversa $\alpha^{-1}=(1423)$.

Un caso especial de este cifrado es el **algoritmo de corrimiento**. Por ejemplo, si consideramos cada letra del alfabeto español como un número, donde $a$ es el número $0$, $b$ se representa con el dígito $1$, y así sucesivamente ( #btw  esto viene en el [tema anterior](Módulo%202/Criptografía.md)), entonces el algoritmo de encriptación, para algún entero $k\in \mathbb{Z}_{27}$, está dado por
$$f(m)=m+k\text{ mod }27$$
Este tipo de encriptación es conocido como <span style="color:#ff0000">cifrado de César</span>, en honor al emperador Julio César, quien se cree que lo inventó.

Por ejemplo, la palabra TURING le corresponde la secuencia de números 20, 21, 18, 8, 13 y 6. Si $k=5$, tenemos que 
$$\begin{matrix}f(20)\equiv 25\text{ mod }27 & f(21)\equiv 26\text{ mod }27 \\
f(18)\equiv 23\text{ mod }27 & f(8)\equiv 13\text{ mod }27 \\
f(13)\equiv 18\text{ mod }27 & f(6)\equiv 11\text{ mod }27\end{matrix}$$
Así que el texto crifrado es "$\text{YZWNRL}$". Este texto se puede decodificar con la función
$$f(c)=f^{-1}(c)\equiv c-k\text{ mod }27$$
<div style="page-break-after: always;"></div>

## Cifrado Afín

El algoritmo de conocimiento es un caso especial del cifrado afín. En este caso, el mapa de encriptación se define como $$f(m)\equiv am+b \text{ mod } n$$
donde $n$ es el número de símbolos del alfabeto, $a,b\in\mathbb{Z}_n$, $\text{mcd}(a,n)=1$ y $b\neq 0$. 
Los elementos $a$ y $b$ se les conoce como las **llaves** del sistema de encriptación.

| A     | B     | C     | D     | E     | F     | G     | H     | I     |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 0     | 1     | 2     | 3     | 4     | 5     | 6     | 7     | 8     |
| **J** | **K** | **L** | **M** | **N** | **Ñ** | **O** | **P** | **Q** |
| 9     | 10    | 11    | 12    | 13    | 14    | 15    | 16    | 17    |
| **R** | **S** | **T** | **U** | **V** | **W** | **X** | **Y** | **Z** |
| 18    | 19    | 20    | 21    | 22    | 23    | 24    | 25    | 26    |
La decodificación se puede llevar a cabo utilizando la siguiente función: $$g=f^{ -1 }(c)\equiv a^{-1}(c-b)\text{ mod }n$$
donde $a^{-1}$ es el inverso multiplicativo de $a$.


#### Ejemplo
Supongamos que tenemos el siguiente mapa de encriptación: $$f(m)\equiv 5m+3\text{ mod }27$$
¿Cuál sería el texto cifrado de TURING? ¿A qué sería igual $g=f^{ -1 }$?

$$\text{TURING}=(20,21,18,8,13,6)$$
$f(\text{TURING})=(22,0,12,16,14,6)=\text{VAMPÑG}$

En este caso, el inverso multiplicativo $a^{-1}$ es 11 debido a que $5·11\equiv 1\text{ mod }27$

$g(c)=11(c+3)\text{ mod }27$

