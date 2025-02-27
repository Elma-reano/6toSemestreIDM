Un grupo es **cíclico** si existe un elemento $a\in G$ tal que $G=\langle a \rangle$. Dicho elemento $a$ se le llama un **generador** de $G$
Por ejemplo, $\mathbb{Z}_{8}$ es cíclico ya que $\mathbb{Z}_8=\langle 1 \rangle=\langle 3 \rangle=\langle 5 \rangle=\langle 7 \rangle$. Sin embargo, $U(8)$ no lo es. ¿Por qué?
$$3^1=3\text{ mod }8$$
$$3^2=3·3=3+3=6\text{ mod }8$$
$$3^3=3·3·3=3+3+3=1\text{ mod }8$$
$$3^4=3+3+3+3=4\text{ mod }8$$
$$3^5=(5)(3)=7\text{ mod }8$$
$$3^6=2\text{ mod }8$$
$$3^7=5\text{ mod }8$$
$$3^8=0\text{ mod }8$$
$$\therefore \langle 3 \rangle =\{ 3,6,1,4,7,2,5,0 \}=\mathbb{Z}_8$$
$$|3|=|\mathbb{Z}_8|=|5|=|7|$$
Los generadores de $\mathbb{Z}_n$ son coprimos de $n$.

$$U(8)=\{ 1,3,5,7 \}$$
$$|1|=1$$
$$|3|=|5|=|7|=2\neq |U(8)|=4$$
$$n\in\mathbb{Z}^+=\mathbb{N}$$
