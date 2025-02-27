La idea básica es tener una función de una sola vía, la cual es fácil de implementar pero muy difícil de invertir.
Por lo tanto, cifrar el mensaje es sencillo pero decodificarlo es muy difícil. Claro, a no ser que se conozca la inversa del mapa de encriptación.

En este caso podemos tener nuestro mapa de encriptación de esta forma
![[Criptografía de clave pública 2024-04-25 09.19.06.excalidraw]]
En el modelo estándar de clave pública, tanto el emisor como el receptor tienen una clave pública y una privada. Ambas son el mapa de encriptación y el mapa de decodificación respectivamente.

Sean $f_a:\mathcal{P}\to \mathcal{C}$ y $f_b:\mathcal{P}\to \mathcal{C}$ las claves públicas, y sean $g_a:\mathcal{C}\to :P$ y $g_b:\mathcal{C}\to \mathcal{P}$ las claves privadas.

Si queremos transmitir un mensaje $m\in P$ que solo pueda decodificar la persona que tenga la clave privada $g_a$, entonces enviamos $f_a(m)$. Así que la decodificación está dada por
$$(g_a\circ f_a)(m)=m$$ 
Supongamos ahora que la persona que tiene la clave privada $g_b$ y quiere cerciorarse de que recibió un mensaje de la persona que posee la clave privada $g_a$. Entonces, la persona que transmite el mensaje debe enviar $$(f_b\circ g_a)(m)$$
Ya que el receptor posee la clave privada $g_b$ y $f_a$ es pública, se tiene que 
$$(g_b\circ (f_b\circ g_a))(m)=((g_b\circ f_b)\circ g_a)(m)$$
$$=g_a(m)$$
Finalmente, aplicando $f_a$, se decodifica el mensaje: 
$$(f_a\circ g_a)(m)=m$$
Como se observa, se pueden autenticar los mensajes recibidos. Esta verificación se llama **firma digital**.

-

Un **criptosistema general** es una colección de criptomonedas básicos indexados por el conjunto de índices $\mathcal{K}$, el cual se conoce como el espacio de claves.

Formalmente, un criptosistema es la colección $\{\mathcal{P}, \mathcal{C}, \mathcal{K}, \mathcal{E}, \mathcal{D}\}$, donde los elementos de K se les llama **claves**, $\mathcal{E}$ es un espacio de funciones inyectivas $f_k, k\in\mathcal{K}$, y $\mathcal{D}$ es un espacio de mapas de decodificación $g_k, k\in\mathcal{K}$

Es decir,  para cada $k\in\mathcal{K}$ existe un criptosistema básico $\{ \mathcal{P},\mathcal{C},f_k,g_k \}$.
y que $g_k$ es la inversa izquierda de $f_k$.

## Diffie-Hellman

^79d73f

En 1976, Diffie y Hellman<span style="color:#FF00FF">(s)</span> desarrollaron la idea de encriptación de clave pública utilizando el **problema del logaritmo discreto**: sea $G=\langle g \rangle$ y $h\in G$. El reto de este problema es encontrar el entero $x$ mayor o igual que <span style="color:#0070c0">cero</span> más pequeño tal que $h=g^x$. A $x$ se le llama el <span style="color:#ff0000">logaritmo discreto</span> de $h$ respecto al generador $g:\log_g(h)=x$.

Por ejemplo, si $G=U(19)$, $6=\log_{2}(7)$ ya que $2^6=64\equiv 7\text{ mod }19$

#btw<span style="color:#00b050">No se de que me sirva esta info pero el problema del logaritmo discreto es NP
</span>

El logaritmo discreto no siempre es único. Si $G=U(8)$, $2\log_{3}(1)$ pues $3^2\equiv 1\text{ mod }8$. Sin embargo, $4=\log_{3}(1)$ ya que $3^4\equiv 1\text{ mod }8$. Esto ocurre porque $U(8)$ no es cíclico, empero, si $G=\langle g \rangle$, entonces el logaritmo en base $g$ de cualquier $h\in G$ está bien definido y es único.

Aparte de una búsqueda exhaustiva, no se conoce ningún algoritmo que permita resolver el problema del logaritmo discreto: en aritmética modular es fácil elevar un número a alguna potencia, pero dado un número, no es sencillo saber si es igual a la potencia de algún elemento.

### El protocolo de intercambio de Diffie-Hellman

Este protocolo de intercambio se usa en conjunto con sistemas criptográficos **simétricos** para elegir la llave con la que dos personas se van a estar comunicando. El procedimiento es:
- Alicia y Beto escogen un primo grande $p$ y un generador $g$ del grupo cíclico $U(p)$. El generador $g$ es público.
- Alicia escoge un entero $a:1<a<p-1$ y le envía a Beto $g^a\text{ mod }p$
- Beto elige un entero $b:1<b<p-1$ y le envía a Alicia $g^b\text{ mod }p$
- Alicia calcula, con su clave secreta, $(g^b)^a\text{ mod }p$
- Beto calcula, con su clave secreta, $(g^a)^b\text{ mod }p$
Al final del proceso, tanto Alicia como Beto tienen la misma llave secreta $g^{ab}\text{ mod }p$

#### Ejemplo

Alicia y Beto escogen un primo "grande" $p=23$ y un generador $g=5$ del grupo cíclico $U(23)$.
- Alicia escoge un entero $a=4$. Envía a Beto $4\equiv 5^4\text{ mod }23$
- Beto elige un entero $b=3$. Envía a Alicia $10\equiv 5^3\text{ mod }23$
- Alicia calcula con su clave secreta $10^4\text{ mod }23\equiv 18$
- Con su clave secreta, Beto calcula $4^3\text{ mod }23\equiv 18$
Ahora Beto y Alicia comparten un secreto: el número $18$
Este ejemplo fue tomado de [Wikipedia](https://en.wikipedia.org/wiki/Diffie-Hellman_key_exchange)

## ElGamal

En 1984 ElGamal encontró la forma de transformar el protocolo de intercambio de clave de Diffie-Hellman en un protocolo de encriptación de clave pública. Aunque este método fue inicialmente propuesto para los grupos $U(p)$, donde $p$ es un número primo, el protocolo sigue siendo válido para cualquier grupo cíclico en el que el problema del logaritmo discreto sea difícil de resolver.


Supongamos que Beto le quiere enviar ~~flores~~ un mensaje a Alicia. El proceso de encriptación y decodificación es el siguiente:
- Alicia y Beto escogen un primo grande $p$ y un generador $g$ del grupo cíclico $U(p)$. El elemento $g$ es público.
- Alicia escoge un entero $a:1<a<p-1$. La llave pública de Alicia es $(p,g,g^2\text{ mod }p)$.
- Beto encripta el mensaje $m$ con un método eficiente que Alicia también conozca.
- Beto escoge aleatoriamente un entero $b:1<b<p-1$ y le envía a Alicia $(g^b\text{ mod }p,g^{ab}m\text{ mod }p)$. Nótese que $g^{ab}\text{ mod }p$ es la clave compartida del protocolo Diffie-Hellman.
- Alicia obtiene la clave compartida usando $g^b\text{ mod }p$. Esto es posible porque ella tiene $g^a\text{ mod }p$
- Ya que ella conoce la clave compartida y el número primo $p$, puede calcular $g^{-ab}\text{ mod }p$
- El mensaje $m$ se recupera cuando Alicia multiplica $g^{ab}m\text{ mod }p$ por $g^{-ab}\text{ mod }p$

#### Ejemplo
- Alicia y Beto escogen un primo "grande" $p=23$ y un generador $g=7$ del grupo cíclico $U(23)$.
- Alicia escoge un entero $a=6$. La llave pública de alicia es $(23,7,4)$ pues $4\equiv 7^6\text{ mod }23$
- Beto encripta el mensaje con un método eficiente que Alicia también conoce y obtiene que $m=7$.
- Beto escoge aleatoriamente el entero $b=3$. Envía a Alicia $(21,11)$ porque $21\equiv 7^3\text{ mod }23$ y $$7^{18}\equiv \begin{cases}
4^3\text{ mod }23 \\
18\text{ mod }23
\end{cases}$$
	Entonces $(18)(7)\equiv 11\text{ mod }23$
- Alicia obtiene la clave compartida usando $21\text{ mod }23$. Esto es posible porque ella tiene $7^6\text{ mod }23$
- Ahora Alicia calcula $9\equiv 18^{-1}\text{ mod }23$
- El mensaje $m=7$ se recupera cuando Alicia multiplica $11\text{ mod }23$ por $9\text{ mod }p$:
	$7\equiv(9)(11)\text{ mod }23$
