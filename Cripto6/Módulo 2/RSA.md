El algoritmo RSA se apoya en el siguiente teorema de teoría de números

**Teorema III:** Supongamos que $p$ y $q$ son primos impares distintos. Sean $e$ y $d$ enteros tales que $1<e,d<\phi(pq)-1,\text{mcd}(e,\phi(pq))\text{ y }ed\equiv 1\text{ mod }\phi(pq)$. Entonces, para todo $n\in \mathbb{Z}_{pq}$ tenemos que
$$n^{ed}\equiv n\text{ mod }pq$$
**Reminder**
$e\in U(\phi(pq)),d=e^{-1}$. Entonces, en este caso,

| $A\to 0$ | $B\to 1$ | ... | $Z\to 26$ |
| -------- | -------- | --- | --------- |

## Preparación de la encriptación

- Cada usuario $u$ debe escoger aleatoriamente dos primos impares grandes $p_u,q_u$ y calcular $n_u=p_uq_u$. Este entero se conoce como el <span style="color:#ff0000"><b>módulo RSA</b></span> 
- Todos los usuarios deben poseer un método para encriptar unidades de texto plano usando aritmética módulo $n_u$.
- Cada usuario calcula $\phi(n_u)$ y debe elegir aleatoriamente un entero $\color{red}e_u:1<e_u<\phi(n_u)-1\land \text{mcd}((e_u,\phi(n_u))=1)$. A este entero se le llama el **exponente de encriptación**.
- Utilizando el algoritmo Euclidiano extendido, se calcula $d_u$ tal que $d_ue_u=\equiv 1\text{ mod }\phi(n_u)$. A $d_u$ se le conoce como el **exponente de decodificación**

$\phi(n_u)=(p_u-1)(q_u-1)$
## Encriptación y decodificación

- La **clave pública** de cada usuario es el par $(n_u,e_u)$, mientras que la **clave privada** es la tupla $(p_u,q_u,d_u)$.
- Para encriptar un mensaje $m\in \mathbb{Z}_{n_u}$, el mapa de encriptación está dado por $$f_u(m)\equiv m^{e_u}\text{ mod }n_u$$
- La decodificación, dado el mensaje cifrado $c\in \mathbb{Z}_{n_u}$, se lleva a cabo aplicando la función $$g_u(c)\equiv c^{d_u}\text{ mod }n_u$$

#### Ejemplo
$$10^4\text{ mod }23\equiv(10^2)^2\text{ mod }23$$
$$\equiv 8^2\text{ mod }23\equiv 64\text{ mod }23$$
$$\equiv(46+18)\text{ mod }23\equiv 18\text{ mod }23$$

### Otro ejemplo

Supongamos que $n=27,k=2$ y $l=3$. Digamos que Alicia escoge los primos $p_a=29$ y $q_a=41$, así que $n_a=p_aq_a=1189$. Además, Alicia escoge un entero $e_a$ tal que $$\text{mcd}(e_a,\phi(n_a))=1$$
Ya que $\phi(n_a)=(p_a-1)(q_a-1)=1120$, una opción es $e_a=3$. Dicho esto, la clave pública de Alicia es $(1189,3)$.

Para determinar su clave privada solo falta calcular $d_a$, tal que $e_ad_a\equiv 1\text{ mod }1120$. Según el algoritmo Euclidiano extendido, $d_a=747$. Entonces, la clave privada de Alicia es $(29,41,747)$.

##### <span style="color:#0070c0">Beto</span>

Supongamos que Beto le quiere enviar a Alicia el mensaje $\text{BALI}$. Lo primero que debe hacer Beto es dividir el texto plano en bloques de $k=2$ letras. Entonces, Beto tiene que $BA\to(1,0)$ y $LI\to(11,8)$; cada componente de estos vectores se ve como una cifra de un número en base $n=27$. Dicho esto, Beto llega a que
$$BA\to(1)(27)+(0)(1)=27$$
$$LI\to(11)(27)+(8)(1)=305$$
Para encriptar la unidad $\text{BA}$, Beto recurre al mapa de encriptación:
$$f(1,0)=27^3\text{ mod }1189\equiv 659$$
Esta cantidad se convierte a un número de $l=3$ cifras en base 27:
$$659=(0)(27^2)+(24)(27)+(11)(1)$$
Así que el mensaje codificado es la tupla $(0,24,11):\text{BA}\to \text{AXL}$.

##### <span style="color:#ec05f0">Alicia</span>

Alicia decodifica la primera unidad enviada por Beto con su exponente de decodificación $d_a=747$:
$$g(0,24,11)=659^{747}\text{ mod }1189\equiv 27$$

$$\text{AXL}\to(0,24,11)\to 0(27)+24(27')+11(27')=659$$

Dado esto, Alicia concluye que $\text{AXL}\to \text{BA}$.

Siguiente este procedimiento, Alicia decodifica la seugnda unidad que le envía Beto, concluyendo que el mensaje secreto es $\text{BALI}$. ¿Será que Beto quiere que vayan a Bali?

$(20,0,2,15)$

$e=121$
$$n_u=527$$
$$f_u(m)\equiv m^{e_u}\text{ mod }n_u$$

$$T:20^{121}\text{ mod }527\equiv 174$$
$$A:0\equiv 0$$
$$C:2^{121}\text{ mod }527\equiv 377$$
$$O:52$$
$$(174,0,377,52)$$


