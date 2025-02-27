#conjuntos 

<span style="color:#00b050">Esto ya te lo sabes</span>....  <span style="color:#ff0000">NOT</span>

# Unión
- Si $x\in A$ o $x\in B$, entonces
	 $\exists r_1>0:B_{r_1}(x)\subset A$
	 $\exists r_2>0:B_{r_2}(x)\subset A$ 

Si unes abiertos, te da abiertos.

Cuando tenemos ya muchos muchos conjuntos abiertos, estos se expresan de la forma $\{A_\alpha\}_{\alpha\in J}$, que significa **Colección arbitraria**
**Cómo podríamos llamar a J?** J es como la I, es un conjunto de cosas que no sabemos que es. Puede ser $\mathbb{R}$, $\mathbb{Z}$, $\{ 0,1 \}$, etc etc etc.......

Si escalamos esto, y tienes una cantidad infinita de conjuntos abiertos, $\{A_1,A_2,...,A_n,...\}$ entonces se puede expresar como $\{A_i\}_{i\in \mathbb{N}}$
$$\{A_1,A_2,A_3,...,A_n,...\}=\{A_i\}_{i\in \mathbb{N}}$$
$$\{X\}=\{A_{i}\}_{i\in\mathbb{R}}$$
$$\{A_1,\dots,A_{1000000000}\}=\{A_i\}_{1,\dots,1000000000}$$
Seguirán siendo abiertos :D

# Intersección

- Si $x\in A\cap B$ entonces $x\in A\land x\in B$
$\exists r_1>0:B_{r_1}(x)\subset A$
$\exists r_2>0:B_{r_2}(x)\subset B$

Necesitamos un radio que queda dentro de la intersección aka el más pequeño de A y B

Para esto, tomo $r_3=min\{r_1,r_2\}>0$
$B_{r_3}(x)\subset B_{r_1}(x)\cap B_{r_2}(x)\subset A\cap B$

Hay conjuntos que al conjuntarlos te dan 0

#duda 