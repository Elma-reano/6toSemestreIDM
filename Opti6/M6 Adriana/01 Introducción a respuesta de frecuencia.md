
Hasta ahorita, hemos analizado inputs a la función escalón, función rampa y función impulso. No obstante, existe otra función de entrada muy importante que no hemos abordado: la función senoidal.
![[Captura de Pantalla 2024-04-26 a la(s) 2.17.29 p.m..png]]
La ventaja de esta función es que cualquier función que tenga una forma senoidal, tan irregular que se vea, se puede expresa como una combinación de ondas senoidales.
![[Introducción a respuesta de frecuencia 2024-04-26 14.18.54.excalidraw]]

Si nos ponemos a pensar, es como la serie de Fourier; la cual es una expansión de una función periódica $f(x)$ en términos de una suma infinita de senos y cosenos.

![[Captura de Pantalla 2024-04-26 a la(s) 2.21.04 p.m..png]]

Ahora bien, abordando la función de los voltajes alternos, podemos observar que tienen tres características muy importantes:
- Amplitud $V_{max}$
- Frecuencia $\frac{\omega}{2\pi}$
- Fase $\theta$
$$v(t)=V_{max}\cos(\omega t+\theta)$$
Donde: $\omega$ es la velocidad angular $$\omega=2\pi f=\frac{2\pi}{T}\text{radianes/s}$$
#funfact
<span style="color:#7030a0">Reminder: un número complejo tambien puede tener su complejo coordinado </span>$$\color{purple} z=x+iy$$
$$\color{purple}\bar{z}=x-iy$$

Un punto en una coordenada rectangular también puede ser expresado con un vector $R$ y un angulo $\theta$.
$$x=R\cos(\theta)$$
$$y=R\sin(\theta)$$
$$R:\text{magnitud de z}$$
$$\theta: \text{fase de z, se mide desde el eje }x\text{ positivo}$$
$$R=\sqrt{ x^2+y^2 }$$
![[Captura de Pantalla 2024-04-26 a la(s) 2.35.09 p.m..png]]
Por lo tanto, $$z=R\cos(\theta)+jR\sin(\theta)$$
Dado que sabemos por la fórmula de Euler que $e^{ i\theta }=\cos(\theta)+j\sin(\theta)$, entonces tendremos que $$z=Re^{ j\theta }=R\angle \theta$$


La respuesta total de un sistema tiene que ser consciente de las respuestas transitoria y la de estado estable
- Transitoria: antes de alcanzar la estabilidad
- Estable: la que se obtiene después de la estabilidad

Hasta ahorita, los pasos para resolver un sistema han sido:
1. Establecer las ED
2. Transformada de Laplace
3. Definir la función de transferencia
4. Transformada inversa de Laplace para tener todo en términos de $t$

Ahora, vamos a usar diagramas de Bode, que se usan con coordenadas polares y analizar las gráficas.

Para trabajar con estas cosas, hay que definir algunas de las terminologías

- Para la función de respuesta en frecuencia, ahora en vez de usar $s$ usaremos $j\omega$. Quedaría como $G(j\omega)=|G(j\omega)|\angle G(j\omega)$ en vez de $G(s)=|G(s)|\angle G(s)$
- El estado estacionario de un sistema lineal es generalmente de la misma forma que de la entrada.
- La representación de una cantidad compleja como vector en espacio complejo se llamará <span style="color:#0070c0"><b>fasor</b></span>, donde la longitud en el espacio complejo se llamará **magnitud**; mientras que el ángulo se llama <span style="color:#ff0000"><b>fase</b></span>.


![[Introducción a respuesta de frecuencia 2024-04-16 11.50.49.excalidraw]]
$$R(\omega)=|W(s)|_{s=j\omega}=|W(j\omega)|$$
$$\phi(\omega)=\angle W(s)|_{s=j\omega}=arg(W(j\omega))$$
Donde:
- $W(j\omega)$ es la función respuesta en frecuencia
- $R(\omega)$ es la proporción de magnitud del componente senoidal de la salida con respecto a la magnitud de la entrada
- $\phi(\omega)$ es la fase entre la entrada y la salida
- Las ecuaciones de la izquierda establecen que la magnitud de la salida $y(t)$ para la entrada senoidal se pueden calcular determinando la magnitud y fase de $W(j\omega)$


Donde $R(\omega)$ es el radio de la magnitud del componente senoidal de la entrada hacia la salida

#TODO poner las tablas de Laplace aquí en las notas

En la imagen anterior, si le aplicamos la transformada de Laplace, nos queda $$\mathscr{L}\{ r(t) \}=R(s)=A\left(\frac{\omega}{s^2+\omega^2}\right)$$
Sabemos que $$Y(s)=R(s)W(s)=\frac{A\omega W(s)}{s^2+\omega^2}$$
Si factorizamos el denominador, tenemos que $$Y(s)=\frac{A\omega W(s)}{(s+j\omega)(s-j\omega)}$$
Por PFE, #duda que es PFE?, obtenemos que $$\frac{A\omega W(s)}{(s+j\omega)(s-j\omega)}=\frac{R_{1}}{s-j\omega}+\frac{R_{2}}{s+j\omega}+\text{otros términos}$$
Donde las fracciones parciales representan a la solución particula para el estado estable (por la función senoidal); mientras que los otros términos, la solución complementaria (estado transitivo)

![[Introducción a respuesta de frecuencia 2024-04-16 12.04.58.excalidraw]]
#funfact 
También hay que tomar en cuenta que $j=e^{ i\pi/2 }$, porque, primero que nada, $j$ es un <span style="color:#0070c0">imaginario</span> (como la $i$) y porque podemos multiplicarla por 1 $\left(\sin\left( \frac{\pi}{2} \right)\right)$ y sumarle 0 $\left( \cos\left( \left( \frac{\pi}{2} \right) \right) \right)$. Y la fórmula de Euler que ya vimos $e^{ i \pi/2 }=\cos(\pi/2)+i\sin(\pi/2)$.

Si consideramos $W(j\omega)$ en forma polar, basados en las ecuaciones anteriores (1) y (2) obtenemos $$W(j\omega)=|W(j\omega)\angle W(j\omega)|=|W(j\omega)|e^{j\omega}=R(\omega)\angle\phi(\omega)=R(\omega)e^{ j\phi(\omega) }$$
Sustituimos esto en $R_{1}$ $$R_{1}=\frac{A}{2}R(\omega)e^{ j\phi(\omega) }e^{ -jπ/2 }=\frac{AR(\omega)}{2}e^{ j(\phi(\omega)-90º) }$$<div style="page-break-after: always;"></div>
 
# Tarea 1
Desarrollar para $R_{2}$ y demostrar que $R_{2}=\frac{AR(\omega)}{2}e^{ -j(\phi(\omega)-90º) }$
--

![[Introducción a respuesta de frecuencia 2024-04-26 15.35.46.excalidraw]]
Sustituimos la formula de $W(s)=R(\omega)e^{ j\phi(\omega) }$ en $R_{2}$ con el cambio de que, en vez de $j\omega$, estamos manejando un valor de $s=-j\omega$. Por lo que $W(-j\omega)=R(\omega)e^{(-j\phi(\omega))}$ 
$$R_2=\frac{AR(\omega)}{-2j}e^{ -j\phi(\omega) }$$
Luego, con la formula $-j=e^{ -j\pi/2 }$ tenemos que 
$$R_2=\frac{AR(\omega)}{2e^{ -j\pi/2 }}e^{ j\phi(\omega) }=\frac{AR(\omega)}{2}e^{ -j\phi(\omega)+j\pi/2 }$$
Dado que podemos interpretar $\frac{\pi}{2}$ radianes como $90º$, resulta en
$$\therefore R_{2}=\frac{AR(\omega)}{-2}e^{ -j(\phi(\omega)-90º) }$$
Finalmente, obtenemos la salida $Y(s)$, que es 
$$Y(s)=\frac{R_{1}}{s-j\omega}+\frac{R_{2}}{j+j\omega}$$
Y aplicando la inversa de Laplace (y talacha) obtenemos esto:$$y(t)=AR(\omega)\left[ \frac{e^{ j(\phi(\omega)-90º+\omega t) }+e^{ -j(\phi(\omega)-90º+\omega t) }}{2} \right]$$que, por propiedad, sabemos que 
$$\frac{e^{ j\theta }+e^{ -j\theta }}{2}=\cos(\theta)$$
Entonces obtenemos 
$$y(t)=AR(\omega)\cos(\phi(\omega)-90º+\omega t)$$
$$\therefore y(t)=AR(\omega)\sin(\phi(\omega)+\omega t)$$
Porque $\cos(\theta-90º)=\sin(\theta)$
# Tarea 2
Resuelve analíticamente el ejercicio con transformada de Laplace. Luego, verifica tu resultado en Matlab y grafica la curva de salida para $y(t)$
--
Dada la función de transferencia $G(s)=\frac{6}{s+2}$ del sistema, encuentra:
	a) La respuesta estable a $u(t)=4\sin(4t)$
	b) La respuesta completa a $u(t)=4\sin(4t)$ cuando las condiciones iniciales son cero.

a)
Para obtener la respuesta $Y(s)$ necesitamos aplicarle la transformada de Laplace a $u(t)$ 

![[Introducción a respuesta de frecuencia 2024-04-28 11.05.50.excalidraw]]

Haciendo ecuaciones parciales 

![[Introducción a respuesta de frecuencia 2024-04-28 11.08.35.excalidraw]]

Dados estos resultados, la ecuación $U(t)$ queda
$$U(t)=\frac{24}{5(s+2)}-\frac{24(s-2)}{5(s^2+16)}$$

Ahora, aplicando la transformada inversa de Laplace, 

![[Introducción a respuesta de frecuencia 2024-04-28 11.29.51.excalidraw]]

<div style="page-break-after: always;"></div>

# Tarea 3
Graficar la respuesta del sistema $y(t)$ a la entrada senoidal
--
Haciendo el siguiente código en matlab para hacer la graficación
```matlab
t = 0:0.1:10;
y = -4.8*cos(4*t) + 2.4*sin(4*t) + 4.8*exp(-2*t);
plot(t,y)
```
![[Captura de Pantalla 2024-04-28 a la(s) 12.43.11 p.m..png]]


Los grafos de frecuencia-dominio $(G(j\omega) \text{ vs }\omega)$ son comúnmente utilizados en el análisis y diseño de sistemas de control lineal. Dichos grafos son:
1. **Grafica de Magnitud-Fase**: se grafica la magnitud en decibeles en relación a la fase de $G(j\omega)$ en coordenadas rectangulares, utilizando $\omega$ como la variable de parámetro en la curva
2. **Grafica polar**: esta es una representación de magnitud-fase en coordenadas polares $(|G(j\omega)|,\phi(\omega))$, pero se representa a $w$ como $(0,\infty)$. Los graficos polares tienen la ventaja de que la magnitud Y fase se pueden ver en una sola gráfica (en vez de dos separadas)
3. <span style="color:#ff0000"><b>Gráficas de Bode:</b></span> Son una gráfica de la magnitud versus $\omega$ en una escala logarítmica de frecuencia. En estos gráficos, la magnitud se suele convertir a GANANCIA en decibeles de la siguiente manera $$\text{Gain}=|G(j\omega)|_{dB}=20\log_{10}|G(j\omega)|$$ [[02 Diagramas de Bode]]

