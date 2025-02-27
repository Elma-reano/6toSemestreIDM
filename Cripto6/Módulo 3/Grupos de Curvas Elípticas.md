Sea $E(F): y^2=x^3+ax+b$ una curva elíptica definida sobre $F$. Sea $\mathcal{O}$ un punto en el infinito. Entonces, para cualquier par de puntos $P_{1},P_{2}\in E(F)$, su "suma" define a un grupo Abeliano cuyo elemento identidad es $\mathcal{O}$. En la siguiente figura se muestra esta situación
![[Grupos de Curvas Elípticas 2024-05-28 10.11.14.excalidraw|250]]
Para cada tupla de puntos va a existir un tercer punto de intersección con la curva elíptica #duda Si, no?
Y para ese punto existe un punto en el inverso $(x,-y)$

#btw Más abajo viene qué eran las propiedades de un grupo Abeliano

Los puntos que satisfacen la curva elíptica son elementos de un grupo + la identidad.
#TODO/duda corroborar esto

Sea $E(F)$ #TODO 

Entonces, prácticamente podemos encontrar el inverso de un punto agarrando su coordenada en $y$ y multiplicándola por $-1$.

Qué pasaría si $P_{1}=P_{2}$?

#TODO 
Wey #TODO fest

$P_{1}=P,P+P=2P=P^2=0$, en este caso podemos decir que el orden de P $|P|=2$

**Teorema VIII:** La adición de puntos que pertenecen a una curva elíptica $E(F)$ satisface las propiedades de un grupo Abeliano, las cuales son:
- **Conmutativa:** $\forall P_{1},P_{2}\in E(F),P_{1}+P_{2}=P_{2}+P_{1}$
- **Identidad:** $\forall P \in E(F),P+\mathcal{O}=P$
- **Inversa:** $\forall P\in E(F)$ #TODO 

Alv me perdí

## Ejemplo

Sea $F=\mathbb{Z}_{11}$ y $y^2=x^3+x+6$. 
$$E(\mathbb{Z}_{11}):=y^2=x^3+x+6,F=\mathbb{Z}$$
$$a=1, b=6$$
Esta ecuación define una curva elíptica sobre $\mathbb{Z}_{11}$ ya que
$$∆=-4a^3-27b^2=-4(1)^3-27(6)^2$$
$$=[-4]_{11}-[27]_{11}[36]_{11}=[-4]_{11}-[5]_{11}[3]_{11}=[-4]_{11}-[15]_{11}$$
$$=[-4-4]_{11}=[-8]_{11}=[3]_{11}\neq[0]_{11}$$
Es más,
$$\bar{E}(\mathbb{Z}_{11})=\{ \mathcal{O},(2,4),(2,7),(3,5),(3,6),(5,2),(5,9), (7,2), (7,9), (8,3), (8,8), (10,2),(10,9) \}$$
Por lo tanto, $|\bar{E}(\mathbb{Z}_{11})|=13$, lo que implica que es un grupo cíclico generado por cualquier elemento que no sea la identidad.
$$P=(2,4)$$
$$P^{-1}=-P=(2,-4)=(2,7)$$
$$(-4\equiv 7\text{ mod }11)$$
Por cierto, los elementos $(5,9)$ y $(10,2)$ sí pertenecen a $\bar{E}(\mathbb{Z}_{11})$?. A qué sería igual $(5,9)+(10,2)$?

Dado que $y^2=x^3+x+6$
$$\begin{matrix}
P_{1}=(x_{1},y_{1})=(5,9) & P_{2}=(x_{2},y_{2})=(10,2) \\
9^2\equiv(5^3+5+6)\text{ mod }11 & 2^2\equiv(10^3+10+6)\text{ mod }11 \\
4\equiv 4\text{ mod }11 & 4\equiv(10+10+6)\text{ mod }11\equiv 4
\end{matrix}$$
#btw $10^2=100\equiv 1\text{ mod }11\implies10^3=10^2·10\equiv10\text{ mod }11$

Entonces $P_{1}+P_{2}=P_{3}=(x_{3},y_{3})$
$$m=(y_{2}-y_{1})(x_{2}-x_{1})^{-1}=(2-9)(10-5)^{-1}$$
$$=[(-7)(5^{-1})]_{11}=[4]_{11}[9]_{11}=[36]_{11}=[3]_{11}$$
$$x_{3}=m^2-x_{1}-x_{2}=3^2-5-10=-6\equiv 5\text{ mod }11$$
$$y_{3}=m(x_{1}-x_{3})-y_{1}=(3)(5-5)-9=-9\equiv 2\text{ mod }11$$
$$\therefore P_{1}+P_{2}=(5,2)=P_{3}$$
