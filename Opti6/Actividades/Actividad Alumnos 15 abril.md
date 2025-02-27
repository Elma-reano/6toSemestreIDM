Para la función de transferencia $G(s)=\frac{50}{S+50}$ con entrada $R(S)=\frac{1}{S}$

Calcula:
a. La posición de los polos y grafíquelos en el plano S
$$S+50=0$$
$$S=-50$$![[Actividad Alumnos 15 abril 2024-04-15 11.41.25.excalidraw]]
Por lo tanto, es estable


b. La constante de tiempo de la respuesta

$$\frac{C}{\tau S+1}$$
$$\frac{50}{S+50}=\frac{\frac{1}{50}}{\frac{1}{50}}*{\frac{50}{S+50}}=\frac{1}{\frac{1}{50}S+1}$$
La constante $\tau$ es $\frac{1}{50}$

c. El tiempo en que llega a la respuesta estable (98% de la respuesta)

$$1-e^{-at}=0.98$$
$$1-e^{-50t}=0.98$$
$$-e^{-50t}=-0.02$$
$$\ln(e^{-50t})=\ln(0.02)$$
$$-50t=\ln(0.02)$$
$$t=0.0782≈4\tau=\frac{4}{50}=0.08$$

d. Escribe una expresión para la forma general de la respuesta, sin obtener la transformada inversa de Laplace 

$$c(t)=1-e^{-at}$$
Dado que $a=\frac{1}{\tau}=50$
$$c(t)=1-e^{-50t}$$
