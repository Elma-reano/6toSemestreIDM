enLa contraparte del algoritmo de firma digital (DSA) que usa curvas elípticas es <span style="color:#ec05f0">ECDSA</span> (por sus siglas en inglés: *Elliptic Curve Digital Signature Algorithm*)
Los pasos para esto son:
- Generación de Clave
- Firma Digital
- Verificación de la Firma
## Generación de Clave
- Alicia escoge un primo grande $p: p≥5$ y una curva elíptica $E(\mathbb{Z}_p)$
- Alicia elige $P \in E(\mathbb{Z}_p)$
- Ahora, Alicia elige aleatoriamente un entero $x:1≤x≤q-1$ y calcula $Q=xP$. La llave pública es $Q$ y la privada es $x$
- Alicia selecciona una función hash $\mathcal{P}\to \{ 1,2,3,\dots,n \}$, donde $n$ es suficientemente grande.
## Firma Digital
- Alicia elige aleatoriamente un entero $k:1≤k≤q-1$ y calcula $kP=(x_{1},y_{1})\in E(\mathbb{Z}_p)$
- Alicia calcula $r\equiv x_{1}\text{ mod }q$. Si $r\equiv 0\text{ mod }q$, entonces Alicia repite el paso anterior hasta que $r$ no sea un múltiplo de $q$
- Usando el algoritmo Euclidiano extendido, Alicia encuentra un entero $l$ tal que $lk\equiv 1\text{ mod }q$
- Alicia calcula el número $s\equiv l(h(m)+xr)\text{ mod }q:0≤s≤q-1$. Si $s\equiv 0\text{ mod }q$, entonces Alicia vuelve a comenzar desde el **primer** paso.
- Alicia firma el mensaje con la pareja $(r,s)$ y le envía mensaje y firma a Beto
## Verificación de la Firma
- Beto comprueba si $1≤r,s≤q-1$
- Beto calcula $w\equiv s^{-1}\text{ mod }q$ y $h(m)$
- Beto calcula los enteros
	- $u_{1}\equiv h(m)w\text{ mod }q$
	- $u_{2}\equiv rw\text{ mod }q$
- Beto calcula $u_{1}P+u_{2}Q=(x_{0},y_{0})\in E(\mathbb{Z}_p)$ y $v\equiv x_{0}\text{ mod }q$
- Si $v\equiv r\text{ mod }q$, Beto acepta la firma.

## Resumido
#### Generación de Clave
$F=\mathbb{Z}_p, P \in E(F)$
$|P|=q\neq p: \text{q es primo}$
$\text{Elegir }x:1≤x≤q-1$
$Q=xP$
#### Firma digital
$\text{Elegir }k:1≤k≤q-1$
$kP=(x_{1},y_{1})\in E(F)$
$r\equiv x_{1}\text{ mod }q$
$\text{Calcular }l: lk\equiv 1\text{ mod }q$
$s\equiv l(h(m)+xr)\text{ mod }q$
$\color{green}\text{Firma: }\color{black}(r,s)$
#### Verificación de Firma
$w\equiv s^{-1}\text{ mod }q$
$u_{1}\equiv wh(m)\text{ mod }q$
$u_{2}\equiv rw\text{ mod }q$
$u_{1}P+u_{2}Q=(x_{0},y_{0})$
$v\equiv x_{0}\text{ mod }q$
$\text{Si }v\equiv r\text{ mod }q\text{, se acepta la firma}$

#btw Hay una página en la que podemos hacer los calculos de la curva elíptica muy fácilmente [aquí](https://andrea.corbellini.name/ecc/interactive/modk-add.html)

## Ejemplo

Sea $C(F): y^2=x^3+2x+2$, donde $F=\mathbb{Z}_{17}$. ¿Es $C(F)$ suave? ¿Cuáles son los elementos de $\bar{E}(F)$? Pista: $|\bar{E}(F)|=19$

Para ver si es suave, calcula el discriminante.
##### Generación de Clave
$P=(5,1)\in \bar{E}(F)$
$|P|=19=q\neq p=17$
$x=10$
$Q=10P=(7,11)$
##### Firma Digital
Si $h(m)=4$ y $k=13$, ¿a qué es igual la firma digital $(r,s)$?

$13P=(16,4)$
$r\equiv x_{1}\text{ mod }q$
$r\equiv 16\text{ mod }19$
$lk\equiv 1\text{ mod }19$
$\therefore l \equiv3\text{ mod }19$
$s=l(h(m)+xr)\text{ mod }19\equiv 3(4+(10)(16))\text{ mod }19$
$\equiv 17\text{ mod }19$
$\therefore(16,17)$
##### Verificacion
$sw\equiv 1\text{ mod }19$
$w\equiv 9\text{ mod }19$
$u_{1}\equiv(9)(4)\text{ mod }19\equiv 17\text{ mod }19$
$u_{2}\equiv(16)(9)\text{ mod }19\equiv 11\text{ mod }19$
$17P+11Q=(16,4)$
$v\equiv 16\text{ mod }19$
$r\equiv 4\text{ mod }19$

# FIN

Finalmente, después de un ardúo semestre, Alicia y Beto pasaron un merecido descanso en Bali.
