Para el siguiente sistema ante una entrada del tipo escalón unitario

$$G(s)=\frac{18}{s^2+2.4s+9}$$
Como es escalón unitario, se multiplica por $1/s$
$$C(s)=\frac{18}{s(s^2+2.4s+9)}$$

##### Halle la expresión de y(t)
Para hallar $y(t)$, hacemos una inversa de laplace. Pero antes le hacemos fracciones parciales. Después de una talacha obtenemos que 
$$C(s)=\frac{2}{s}-\frac{2(s+1.2)+2.4}{(s+1.2)^2+(2.75)^2}$$
$$=\frac{2}{s}-2\left[\frac{s+1.2}{(s+1.2)^2+(2.75)^2}\right]-\frac{2.4}{(s+1.2)^2+(2.75)^2}$$
$$\mathscr{L}^{-1}\{C(s)\}=2-2e^{ -1.2t }\cos(2.75t)-\frac{2.4}{2.75}e^{ -1.2t }\sin(2.75t)=c(t)$$

##### Obtenga el tiempo de máximo pico y el máximo pico
$$t_p=\frac{\pi}{\omega_ns\sqrt{ 1-\xi^2 }}$$

Se sabe que la formula y nuestra ecuación son $$G(s)=\frac{K\omega_n^2}{s^2+2\xi\omega_ns+\omega_n^2}=\frac{18}{s^2+2.4s+9}$$
Se sabe entonces que ome
#TODO 

$t_p=1.14s$


##### Obtenga el valor de la salida en estado estable.
