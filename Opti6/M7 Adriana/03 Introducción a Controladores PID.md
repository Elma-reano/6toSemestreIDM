
Como ya hemos visto anteriormente, un controlador es un amplificador de una señal con un valor de ganancia $K$. A este tipo de acción se le llama <span style="color:#00b050">control proporcional.</span>

Uno de los controladores más conocidos y utilizados para esto es el <span style="color:#ff0000"><b>Controlador PID</b></span>, para el cual sus siglas significan *proporcional*, *integral* y *derivada*.

![[Captura de Pantalla 2024-05-26 a la(s) 11.42.28 a.m..png|300]]
![[Captura de Pantalla 2024-05-26 a la(s) 11.43.45 a.m..png]]

La función de transferencia **ideal** para un controlador PID es: 
$$C(s)=k_p+\frac{k_i}{s}+k_ds$$
$$\frac{R_{2}}{R_{1}}+\frac{1}{R_iC_is}+R_dC_ds$$
### Ejemplo

Una aplicación de los controladores PID es el sistema de masa-resorte con amortiguador.
![[Captura de Pantalla 2024-05-26 a la(s) 11.46.14 a.m..png|300]]
![[Captura de Pantalla 2024-05-26 a la(s) 11.46.00 a.m..png|300]]

1. Determina la función de transferencia entre la fuerza de entrada $F(s)$ y el desplazamiento $X(s)$
2. Asumir $m=1 \text{ kg}$, $c=10\text{ Ns/m}$, $F=1\text{ N}$. Determina la respuesta a una función escalón con open-loop #traducir , el error estado estable $e_{ss}$, el tiempo de subida y el tiempo de asentamiento (setting time)
3. Diseña un controlador que tenga un tiempo de subida rápido, así como un overshoot #traducir mínimo y un error de estado estacionario de aproximadamente 0. $e(t)=\text{reference signal}-y(t)$
	Pista: Establece un valor $K_p$ para un controlador proporcional
$$G(s)=\frac{X(s)}{F(s)}=\frac{\frac{1}{m}}{s^2+\frac{cs}{m}+\frac{k}{m}}$$
Recordando que $m=1, c=10, k=20, F=1$, tenemos que
$$\ddot{x}+10\dot{x}+20x=1$$
Entonces, aplicando la transformada de Laplace,
$$s^2X(s)-x'(0)+10sX(s)+20X(s)=\frac{1}{s}$$
$$X(s)(s^2+10s+20)=\frac{1}{s}$$
$$\therefore X(s)=\frac{1}{s}·\frac{1}{s^2+10s+20}$$
En simulink, sería una función de transferencia $\frac{1}{s^2+10s+20}$con un bloque escalón.

Con formulazos, podemos obtener los valores del error de estado estacionario, el tiempo de subida y el tiempo de establecimiento.
$$e_{ss}=0.95,t_s=1.279,t_r=900ms$$

> En simulink hay una pestañita que se llama tools. Dentro de esta hay una que se llama measurements; con la que podemos ver qp con los valores de las variables sin necesidad de estar viendo qp manualmente


![[Captura de Pantalla 2024-05-26 a la(s) 12.20.04 p.m..png]]


Si agregamos un controlador proporcional, éste reduce el tiempo de subida y el error de estado estacionario. Peeeero, también incrementa mucho el #traducir overshoot y disminuye un poco el tiempo de asentamiento.

![[Captura de Pantalla 2024-05-26 a la(s) 5.35.03 p.m..png]]

El controlador PD reduce el overshoot y el tiempo de asentamiento. En cuanto al tiempo de subida y el error de estado estacionario, no hay un efecto significativo.
![[Captura de Pantalla 2024-05-26 a la(s) 8.47.43 p.m..png]]

El controlador PI, de forma similar al controlador proporcional, tiene a disminuir el tiempo de subida y el error de estado estacionario; mientras que incrementa el overshoot y el tiempo de asentamiento.
Para solucionar esto, se puede disminuir el valor de $K_p$ a (aprox) $1/2K_i$
![[Captura de Pantalla 2024-05-26 a la(s) 5.39.02 p.m..png]]


Por último, el controlador PID tiende a eliminar el error de estado estacionario.
![[Captura de Pantalla 2024-05-26 a la(s) 5.39.37 p.m..png]]

> Con 3 horas de sueño (debido a que tuvimos un examen el día de hoy lunes 20 de mayo), no pude replicar las gráficas de esta presentación. Sólamente la primera.

![[Captura de Pantalla 2024-05-26 a la(s) 9.30.09 p.m..png]]


