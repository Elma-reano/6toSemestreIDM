#metricas 

Supongamos que $A$ tiene dos métricas $d_A,\bar{d}_A$

Diremos que son equivalentes si existen constantes $k,l\in\mathbb{R}$ fijas tales que:
$$\forall x,y\in A\text{ se cumple que }d_A(x,y)≤\bar{d}_A(x,y)≤l·d_A(x,y)$$

Sea $A=\mathbb{R}^2$

$$\bar{d}_\mathbb{R^2}(x,y)≤?d_\mathbb{R^2}(x,y)$$
$$k*max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}≤\sqrt{ (x_{1}-y_{1})^2+(x_{2}-y_{2})^2} ≤\frac{2}{?}max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}$$
$$≤\sqrt{ (x_{1}-y_{1})^2+(x_{2}-y_{2})^2 }≤\sqrt{ max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}^2+max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}^2 }$$
$$=\sqrt{ 2 }max\{ |x_{1}-y_{1}|,|x_2-y_{2}| \}=\frac{2}{l}max\{ |x_{1}-y_{1}@,|x_{2}-y_{2}| \}$$

$$\therefore k*max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}≤\frac{2}{l}max\{ |x_{1}-y_{1}|,|x_{2}-y_{2}| \}$$
Si elegimos un valor $k=1$ y un $l≥2$ se cumple
Dado que existen estos valores, se cumple que son métricas equivalentes