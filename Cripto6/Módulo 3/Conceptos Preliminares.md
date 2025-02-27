## Anillo

Es un conjunto $R$ al que se le asocian dos operaciones binarias conocidas como **suma** y **multiplicación**, las cuales se denotan como $+$ y $·$ respectivamente. Estas operaciones binarias satisfacen las propiedades:
- La **suma** es <span style="color:#0070c0">conmutativa</span>: $\forall a,b\in R,a+b=b+a$
- La **suma** es <span style="color:#0070c0">asociativa</span> $\forall a,b,c\in R,(a+b)+c=a+(b+c)$
- Existe una <span style="color:#0070c0">identidad aditiva</span> $0\in R:\forall a\in R,a+0=a$
- Para cada $a\in R$ existe un <span style="color:#0070c0">inverso aditivo</span>, que se denota como $-a$, tal que $a+(-a)=0$
- La **multiplicación** es asociativa: $\forall a,b,c\in R,a·(b·c)=(a·b)·c$
- La **multiplicación** es distributiva respecto a la adición: $\forall a,b,c\in R,$
$$a·(b+c)=a·b+a·c$$
$$(b+c)·a=b·a+c·a$$
Un anillo se puede definir con matrices, se pueden sumar. Pero no todas las matrices tienen un inverso. Por eso no hemos dicho de una identidad multiplicativa ni inversa multiplicativa

Si para todo $a,b\in R$ tenemos que $a·b=b·a$, entonces decimos que $R$ es un **anillo conmutativo**

Si existe una identidad multiplicativa, la cual denotamos como $1:1·a=a·1=a$para todo $a\in R$
#TODO

Consideremos los conjuntos $\mathbb{Z}_4$ y $\mathbb{Z}_5$ con sus respectivas sumas y multiplicaciones binarias. ¿Cuáles serían las tablas de Cayley de $\mathbb{Z}_4$ para ambas operaciones? ¿Cuáles serían las de $\mathbb{Z}_5$?¿Se nota alguna diferencia fundamental?

$$\mathbb{Z}_4=\{ 0,1,2,3 \}$$
$$\mathbb{Z}_5=\{ 0,1,2,3,4 \}$$

| $\mathbb{Z}_4$,x | 0   | 1   | 2   | 3   |
| ---------------- | --- | --- | --- | --- |
| **0**            | 0   | 0   | 0   | 0   |
| **1**            | 0   | 1   | 2   | 3   |
| **2**            | 0   | 2   | 0   | 2   |
| **3**            | 0   | 3   | 2   | 1   |

| $\mathbb{Z}_5$,x | 0   | 1   | 2   | 3   | 4   |
| ---------------- | --- | --- | --- | --- | --- |
| **0**            | 0   | 0   | 0   | 0   | 0   |
| **1**            | 0   | 1   | 2   | 3   | 4   |
| **2**            | 0   | 2   | 4   | 1   | 3   |
| **3**            | 0   | 3   | 1   | 4   | 2   |
| **4**            | 0   | 4   | 3   | 2   | 1   |
Se observa que para los elementos diferentes de 0 en $\mathbb{Z}_5$, todos los elementos tienen un elemento inverso multiplicativo; mientras que en $\mathbb{Z}_4$ no. Esto es una propiedad de los grupos $\mathbb{Z}_p$ donde $p$ es un número primo.

## Campo

La **característica** de un campo $F$, la cual denotamos como $char(F)$, nos permite distinguir entre campos <span style="color:#0070c0">finitos</span> e <span style="color:#ec05f0">infinitos</span>. Para un campo infinito, como los números reales, se tiene que $char(\mathbb{R})=0$; en el caso de un campo finito, como $\mathbb{Z}_p$, la característica es $char(\mathbb{Z}_p)=p$

**Teorema I:** La característica de un campo $F$ es cero o un número primo.

La característica de un campo se define como el número natural $n\in \mathbb{N}$ más pequeño tal que $n·1=0$. Si no existe dicho número natural, entonces se dice que la característica del campo $F$ es cero.
$$p·1\equiv 0\text{ mod }p$$

### Extensión de un Campo

Es una adición que le metemos a un campo para tener otras cosas (duh). Así como tenemos campos finitos e infinitos, también tenemos extensiones finitas e infinitas.

Si $F$ y $\hat{F}$ son campos, pero $F$ es un subcampo de $\hat{F}$, entonces $\hat{F}$ se le conoce como la extensión de $F$.
En estas circunstancias, $\hat{F}$ se comporta como un espacio vectorial cuyo campo escalas es $F$. Por ejemplo, los complejos son una extensión de los números reales, ya que
$$\mathbb{C}=\alpha(1)+\beta(i)$$
donde $\alpha,\beta \in \mathbb{R}$ y $\{ 1,i \}$ son una base de los complejos.

![[Conceptos Preliminares 2024-05-23 10.14.23.excalidraw]]

El grado de la extensión es igual a la dimensión de $\hat{F}$ como un espacio vectorial con campo escalar $F$. En el ejemplo anterior, el grado de extensión de $\mathbb{C}$ respecto a $\mathbb{R}$ es 2, lo cual es una extensión finita.

Un ejemplo de extensión infinita sería $\mathbb{R}$ respecto a $\mathbb{Q}$: no existe una combinación finita de números reales multiplicados por números racionales tal que su **span** sea igual a $\mathbb{R}$. Esto porque el infinito de $\mathbb{R}$ es más grande que el infinito de $\mathbb{Q}$.
$$|\mathbb{Z}|=|\mathbb{Q}|<|\mathbb{R}|$$
$$\mathbb{R}[i]=\hat{F}=\{ \alpha+\beta i:\alpha,\beta \in \mathbb{R} \}=\mathbb{C}$$
$$F=\mathbb{R}$$
#btw $\mathbb{Q}$ se refiere a los números racionales
## Polinomios

Sea $F[x]$ el conjunto de polinomios cuyos coeficientes pertenecen al campo $F$. Un polinomio $f(x)\in F[x]$ cuyo grado es mayor o igual a uno es **irreducible** si no se puede expresar como el producto de dos polinomios de orden menor.

> Esto va a ser relevante en el caso de curvas elípticas, porque ahí vamos a hablar de algo llamado **clausura algebraica**.

Una raíz de un polinomio $f(x)\in F[x]$ es un elemento $c\in F$ tal que $f(c)=0$. Esto implica que 
$$f(x)=(x-c)h(x)$$
donde $h(x)\in F[x]$

Supongamos que $\hat{F}$ es una extensión de $F$ y $\alpha \in \hat{F}$. Entonces $\alpha$ es algebraico respecto a $F$ si existe un polinomio $0\neq p(x)\in F[x]$ tal que $p(\alpha)=0$

Consideremos el polinomio $p(x)=x^2-x-1\in \mathbb{Q}[x]$. Una de sus raíces es la <span style="color:#d4af37"><b>proporción áurea</b></span>.
$$\phi=\frac{1+\sqrt{ 5 }}{2}\neq \frac{p}{q},p,q\in \mathbb{Z}$$
Claramente, $\phi \in \mathbb{R}$, así que $p(\phi)=0$ y $\phi$ es un elemento de $\mathbb{R}$, que es una extensión infinita de $\mathbb{Q}$.
$$\mathbb{Q}[\sqrt{ 5 }]=\{ \alpha+\beta \sqrt{ 5 }: \alpha,\beta \in \mathbb{Q} \}$$

Si cada elemento de $\hat{F}$ es algebraico respecto a $F$, entonces $\hat{F}$ es una **extensión algebraica** de $F$. Es más, si $\alpha \in \hat{F}$ no es algebraico respecto a $F$, entonces $\alpha$ es **trascendental** respecto a $F$. Una extensión que no sea algebraica se le llama una **extensión trascendente**

#btw La proporción áurea es un <span style="color:#0070c0">número algebraico</span>, pues es la raíz de un polinomio con coeficientes racionales. En cambio, $\pi$ no es un número algebraico, sino un <span style="color:#0070c0">número trascendente</span>; pues no es la raíz de ningún polinomio con coeficientes que pertenezcan a $\mathbb{Q}$.

**Teorema II:** Si $\hat{F}$ es una extensión finita de $F$, entonces $\hat{F}$ es una extensión algebraica de $F$.

**Teorema III:** Sea $f(x)\in F[x]$ un polinomio irreducible. Entonces, existe una extensión finita $\hat{F}$ de $F$ en la cual dicho polinomio $f(x)$ tiene una raíz.

#TODO 


Dado esto, podemos definir la **clausura algebraica** de $F$, la cual denotamos como $\bar{F}$. Y es el campo más pequeño donde cualquier $f(x)\in F[x]$ tiene sus raíces.
Entonces, se dice que $\bar{F}$ está **algebraicamente cerrado**.

> Nótese que el famoso **teorema fundamental del álgebra** dice que el campo de los números complejos $\mathbb{C}$ está algebraicamente cerrado.

![[Conceptos Preliminares 2024-05-28 09.34.27.excalidraw]]
- Finitas: $(F=\mathbb{R},\hat{F}=\mathbb{C}=\mathbb{R}[i]=\{ \alpha(1)+i\beta:\alpha,\beta \in \mathbb{R} \})$
- Infinitas: $(F=\mathbb{Q}, \hat{F}=\mathbb{R})$
- Algebraicas: $(F=\mathbb{Q},\hat{F}=\mathbb{Q}[\sqrt{ 5 }]=\{ \alpha+\beta \sqrt{ 5 }:\alpha,\beta \in \mathbb{Q} \})$
- Trascendentes: $(\mathbb{Q}[x]\exists p(x),p(\pi)\neq 0)$

> No podemos expresar π como con la proporción áurea. Tenemos que expresarlo sí o sí con el símbolo π

