Hay distintos métodos de encriptación en los que se usan curvas elípticas. Sin embargo, nosotros vamos a centrarnos en el método **ECES** (<span style="color:#00b050">Elliptic Curve ElGamal Cryptosystem</span> en inglés).

Sean $P \in E(\mathbb{Z}_p)$ y $nP \in \bar{E}(\mathbb{Z}_p)$. Nótese que encontrar $n$ a partir de estos dos elementos es equivalente a resolver el problema del <span style="color:#ff0000">logaritmo discreto</span>, cosa que no es viable en términos computacionales. Este método se basa en este hecho para encriptar los mensajes de forma segura 😃👍.

## Preparación

- Escoger un primo grande $p: p≥5$ y escoger $a,b\in \mathbb{Z}_p$ tales que $E(\mathbb{Z}_p):y^2=x^3+ax+b$ es una curva elíptica.
- Escoger un mapa inyectivo $\rho:\mathcal{P}\to E(\mathbb{Z}_p)$ que se pueda invertir eficientemente, donde $\mathcal{P}$ es el conjunto de unidades de texto plano
- Escoger $P \in E(\mathbb{Z}_p)$
- Escoger un entero secreto $d\in \mathbb{Z}$ y calcular $dP \in \bar{E}(\mathbb{Z}_p)$
- La llave pública es $(P,dP)\in E(\mathbb{Z}_p)\times \bar{E}(\mathbb{Z}_p)$; mientras que la llave secreta es $d$.

## Encriptación

- Sea $m\in P$ una unidad de texto plano. Calcular $Q=p(m)$
- Escoger aleatoriamente $k\in \mathbb{N}$ y definir 
$$c=(kP,Q+k(dP))\in E(\mathbb{Z}_p)\times E(\mathbb{Z}_p)=\mathcal{C}$$
Dicha $c$ es la unidad de texto cifrado

## Decodificación

- Sea $c=(c_{1},c_{2})\in\mathcal{C}$ una unidad de texto cifrado. Calcular $Q=c_{2}-dc_{1}$
- Calcular $m=\rho ^{-1}(Q)$
#btw No olvides que $(c_{1},c_{2})$ es $(kP,Q+k(dP))$

## Resumido

#### Preparación
- Escoger $p$ primo grande $(F=\mathbb{Z}_p)$
- $P \in E(\mathbb{Z}_p)=\bar{E}(\mathbb{Z}_p)\text{\\} \mathcal{O}$
- $d\in \mathbb{Z}$, calcular $dP \in \bar{E}(\mathbb{Z}_p)$
- Publico: $(P,dP)$; Privado: $d$

#### Encriptación
- $\rho(m)=Q\in E(\mathbb{Z}_p)$
- Escoger $k\in \mathbb{N}$
- $c=(kP,Q+k(dP))$

#### Decodificación
- $c_{1}\to dc_{1}=dkP=c_{1}+c_{1}+c_{1}+\dots \text{(k veces)}$
- $c_{2}\to c_{2}-dc_{1}=Q+kdP+(-kdP)=Q$

## PREGUNTA

Sea $C(F): y^2=x^3+7x+13$, donde $F=\mathbb{Z}_{17}$. Es $C(F)$ suave? (mente?) ¿Cuáles son los elementos de $\bar{E}(F)$? Pista: $|\bar{E}(F)|=13$
#### Suave

Tenemos 3 formas de determinar si una curva es suave:
1. Encontrar 3 raíces diferentes en el polinomio
2. Derivadas parciales para encontrar puntos singulares
	1. $\frac{∂g}{∂x}=-3x^2-7\to x=\pm \sqrt{ \frac{-7}{3} }$
	2. $\frac{∂g}{∂y}=2y\to y=0$
3. Con el discriminante.

Utilicemos el <span style="color:#ff0000"><b>discriminante</b></span>.
$$y^2=x^3+7x+13, F=\mathbb{Z}_{17}$$
$$∆=-4a^3-27b^2$$
$$= -4(7)^3-27(13)^2=-4(3)-27(16)$$
$$=-12-7=-19\equiv 15\text{ mod }17\not\equiv 0\text{ mod }17$$
Como el discriminante no es equivalente con $0\text{ mod }17$, entonces <span style="color:#ff0000">no es suave</span>
$$\mathbb{Z}_{17}\times \mathbb{Z}_{17}=\mathbb{Z}_{17}^2$$

Sean $P=(1,2)$, $Q=(15,5)=\rho(m)$, $d=5$ y $k=2$. ¿A qué es igual la llave pública $(P,dP)$? Encripta el mensaje calculando $c=(kP, Q+k(dP))$

##### Preparación

#reminder de que $F=\mathbb{Z}_{17}$.

$dP=5P=2P+2P+P$
$2P=P+P$

$$m=(3x_{1}^2+a)(2y_{1})^{-1}$$
$$=(3(1)^2+7)(2(2))^{-1}=(10)(4^{-1})$$
$$=[(10)(13)]_{17}=[130]_{17}=[11]_{17}$$
$$x_{3} = m^2-2x_{1}$$
$$= 11^2-2(1)$$
$$= [119]_{17}=[0]$$
$$y_{3}=m(x_{1}-x_{3})-y_{1}$$
$$y_{3}=11(1-0)-2=11-2$$
$$=[7]_{17}$$
$$\therefore 2P=(0,7)$$
Ahora, obtenemos $4P$

$$m=(3x_{1}^2+a)(2y_{1})^{-1}$$
$$=(3(0)^2+7)(2(9))^{-1}$$
$$=(7)(18^{-1})=(7)(1^{-1})=[7]_{17}$$
$$x_{3}=m^2-2x_{1}=7^2-2(0)=[15]_{17}$$
$$y_{3}=m(x_{1}-x_{3})-y_{1}=[7(0-15)-9]_{17}=[15]_{17}$$
Ahora, terminamos calculando $5P=4P+P=(15,5)+(1,2)$
$$m=(y_{2}-y_{1})(x_{2}-x_{1})^{-1}=(2-5)(1-15)^{-1}$$
$$=(-3)(-14)^{-1}=(14)(3)^{-1}=(14)(6)=[84]_{17}=[16]_{17}$$
$$x_{3}=m^2-x_{1}-x_{2}=16^2-15-1=1-15-1=-15=[2]_{17}$$
#btw/reminder $|16|_{17}=2$
$$y_{3}=m(x_{1}-x_{3})-y_{1}=16(15-2)-5=16(13)-5$$
#btw usamos el truco de que $16\equiv-1\text{ mod }17$
$$=-13-5=-18=[16]_{17}$$
$$\therefore 5P=(2,16)$$
Por lo tanto, la clave pública es $(P,5P)=((1,2),(2,16))$

##### Encriptación

$$K=2, Q=(15,5)=4P$$
$$C=(2P,Q+10P)=(2P,4P)$$
#btw $13P+P=\mathcal{O}+O=P$
#btw $\mathcal{O}$ es la identidad

$$=((0,9),(15,5)+10(1,2))=((0,9),(1,2))$$

##### Decodificación

$$Q=C_{2}-dC_{1}$$
$$Q+10P-10P=(1,2)-10P$$
$$m=(3x_{1}+a)(2y_{1})^{-1}=(3(2)^2+7)(2(16)^{-1})$$
$$=(19)(32)^{-1}=[2]_{17}[15^{-1}]_{17}=[2]_{17}[8]_{17}=\color{red}[16]_{17}$$
$$x_{3}=m^2-2x_{1}=16^2-2(2)=[1]_{17}-[4]_{17}=\color{red}[14]_{17}$$
$$y_{3}=m(x_{1}-x_{3})-y_{1}=16(2-14)-16=16(-12)-16=16(5)-16$$
$$=[64]_{17}=\color{red}[13]_{17}$$
$$\therefore 10P=(14,13)$$

#TODO alguien debio haberle tomado foto al procedimiento de otero para terminar este ejercicio