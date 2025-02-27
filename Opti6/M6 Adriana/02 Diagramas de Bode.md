También conocido como gráfico de esquina/asintótico, está conformado por dos gráficos:
- Un gráfico de $|G(j\omega)_{dB}|$ vs $\log_{10}(\omega)$ o $\omega$
- Un gráfico de $arg(G(j\omega))$ en grafos, así como una función de $\log_{10}(\omega)$ o $\omega$

Este método se usa para expresar la magnitud y fase de la funcion frecuencia de respuesta 
$$W(s)=K\frac{(∏_{n=1}^m(s+z_n))}{∏_{i=1}^j(s+p_i)}$$

Podemos determinar su magnitud y fase de la siguiente forma:
$$|W(j\omega)|=K \frac{|j\omega+z_{1}|\dots |j\omega+z_m|}{|j\omega+p_{1}|\dots |j\omega+p_j|}$$
$$\phi(\omega)=\text{arg }W(j\omega)=(\psi_{1}+\dots+\psi_m)-(\varphi_{1}+\dots+\varphi_j)$$

Podemos también escribir la función de transferencia y escribirla de distintas formas: la forma <span style="color:#ff0000">polo-zero</span>, forma <span style="color:#00b050">tiempo constante</span> y la <span style="color:#0070c0">función respuesta de frecuencia</span>
$$\color{red} W(s)=\frac{K(s+\omega_{1})}{s(s+\omega_{2})}\implies \color{green}W(s)=\frac{K\omega_{1}(1+s/\omega_{1})}{\omega_{2}s(1+s/\omega_{2})} \implies \color{blue} W(j\omega)=\frac{K\omega_{1}}{\omega_{2}}\frac{(1+j\omega/\omega_{1})}{j\omega(1+j\omega/\omega_{2})}$$
- $\omega_{1}$ y $\omega_{2}$ son conocidos como las frecuencias de esquina (en inglés corner frequencies) debido a que son los puntos en los que la línea puede cambiar de ángulo
- $$|W(j\omega)|_{dB}=20\log_{10}|W(j\omega)|=20\log \left|\frac{K\omega_{1}}{\omega_{2}}\right|+20\log \left|1+\frac{j\omega}{\omega_{1}}\right|-20\log \left|j\omega\right|-20\log \left|1+\frac{j\omega}{\omega_{2}}\right|$$
- El término constante es frecuencia independiente. Por lo tanto, describe una linea horizontal pasando por este valor
- $\log |j\omega|=\log \omega$ por eso la pendiente es +1, es decir, la gráfica de este termino vs $\omega$ es una linea recta con pendiente +1
<div style="page-break-after: always;"></div>

Para hacer un gráfico de diagrama de Bode con el método de la línea recta, hay que seguir los siguientes pasos:
1. Identificar los polos y ceros en la función de transferencia y escribir la función desde la forma  <span style="color:#ff0000">polo-zero</span> a <span style="color:#00b050">forma constante de tiempo</span> y, de ahí, a la función de <span style="color:#0070c0">respuesta de frecuencia</span>.
2. Determinar los puntos de inicio de la gráfica calculando la magnitud y fase de $W(j\omega)$
	1. Para  $\omega\ll\text{polo mas pequeño o zero}$, la parte imaginaria de todos los polos y ceros en $W(j\omega)$ será mucho más pequeña que la parte real. Por lo tanto, se pueden ignorar 👍
	2. Calcular $W(j\omega)$ como el punto de inicio
3. Dibujar el gráfico
	1. Marcar el punto de inicio de la magnitud y dibujar una línea recta hasta llegar a la primera frecuencia de esquina
	2. En ese punto, cada término en el numerador hace que la gráfica suba (+20dB/decade slope); mientras que cada término en el denominador hace que la gráfica baje (-20dB/decade slope). Si $\omega$ tiene un exponente (términos repetidos) la pendiente se multiplica por el exponente
	3. El efecto de cada término se suma para dar el resultado de la linea recta resultante aproximada

<span style="color:#0070c0">Decade: una década es un cambio de diez veces la frecuencia. Ejemplo: desde 10Hz hasta 100 Hz o desde 1,000Hz hasta 10,000Hz.</span>
### Resumido
1. Encontrar el centro de frecuencia de cada término (para $s+\omega_{1}$ y $s+\omega_{2}$ son $\omega_{1}$ y $\omega_{2}$ respectivamente)
2. Calcular la fase inicial de $W(j\omega)$
3. Dibujar la gráfica
	1. Empezar por el punto de inicio y dibujar una línea recta horizontal hasta llegar a la primera frecuencia de esquina
	2. Por cada termino en el numerador se incrementa 90º por cada dos décadas (+20dB/decada); mientras que por cada numerador, -90º (-20dB/decada)
	3. Todos los incrementos se suman al final

### Ejemplo
$$G(s)=\frac{10^4(s+1)}{(s+1)(s+100)}$$
Para poder graficar el diagrama de Bode necesitamos que todas las constantes $\omega$ en $s+\omega_n$ valgan 1. Por lo tanto,

$$G(s)=\frac{10^4(s+1)}{10\left( \frac{s}{10}+1 \right)100\left( \frac{s}{100}+1 \right)}$$
Además, sustituimos $s=j\omega$
$$G(j\omega)=\frac{10(j\omega+1)}{\left( \frac{j\omega}{10} +1\right)\left( \frac{j\omega}{100}+1 \right)}$$

Ahora, podemos observar que tenemos $\omega_{1}=1\frac{rad}{s}$, $\omega_{2}=10\frac{rad}{s}$ y $\omega_{3}=100\frac{rad}{s}$. Esto significa que en estas frecuencias el ángulo de la línea cambiará +20, -20 y -20 decibeles respectivamente
Establecemos $\omega_{prueba}=\frac{1}{10}$ para calcular el punto inicial
$$\omega_{prueba}=\frac{1}{10}(1)=\frac{1}{10}$$
$$\to G(j\omega)\mid_{\omega_{prueba}}=\lim_{ j \to 0 } \frac{10\left( \frac{j}{10} +1\right)}{\left( \frac{j}{100}+1 \right)\left( \frac{j}{1000}+1 \right)}=10$$
$$|G(j\omega)|_{dB}=20\log(10)=20\text{dB}$$
Por lo tanto, el punto inicial es 20 decibeles

$$\phi(j\omega)\text{ }\text{ arg}G(j\omega)=\arctan\left( \frac{imag}{Re} \right)=0º$$

![[Diagramas de Bode 2024-04-19 11.44.22.excalidraw|375]]
<div style="page-break-after: always;"></div>

# Tarea
Para los siguientes ejercicios, bosqueja el diagrama de Bode con la aproximación de línea recta y grafica el diagrama correspondiente en Matlab
--
a) $G(s)=\frac{1}{s(s+1)}$

![[Diagramas de Bode 2024-04-28 18.55.16.excalidraw|700]]
El código de matlab es el siguiente:
```matlab
num = 1;
den = [1 1 0];
sys = tf(num, den);
bode(sys)
```
![[Captura de Pantalla 2024-04-28 a la(s) 8.15.46 p.m..png|500]]

b) $\frac{U(s)}{E(s)}=\frac{0.1(s+10)^2}{s(s+100)}$
![[Diagramas de Bode 2024-04-28 19.16.02.excalidraw|700]]
A continuación se muestra el código de matlab utilizado
```matlab
num = [1 20 100];
den = [10 1000 0];
sys = tf(num, den);
bode(sys)
```
![[Captura de Pantalla 2024-04-28 a la(s) 8.38.27 p.m..png|500]]

c) $W(s)=\frac{s+5}{25s(s+50)}$

![[Diagramas de Bode 2024-04-28 21.26.09.excalidraw|700]]
En cuanto al código de matlab,
```matlab
num = [1 5];
den = [25 1250 0];
sys = tf(num, den);
bode(sys)
```
![[Captura de Pantalla 2024-04-28 a la(s) 9.25.50 p.m..png|500]]



d) $W(j\omega)=10\frac{1+j\omega/10}{(1+j\omega/1000)(1+j\omega/10,000)}$

![[Diagramas de Bode 2024-04-28 21.46.53.excalidraw|700]]
El código de matlab utilizado fue:
```matlab
num = [1 10];
den = [1e-7 0.0011 1];
sys = tf(num, den);
bode(sys)
```
![[Captura de Pantalla 2024-04-28 a la(s) 9.46.30 p.m..png|500]]




e) $W(j\omega)=1000\frac{j\omega/1000}{(1+j\omega/100)(1+j\omega/10,000)}$

![[Diagramas de Bode 2024-04-28 22.05.19.excalidraw|700]]
El código utilizado en matlab para graficar los diagramas es el siguiente
```matlab
num = [1 0];
den = [1e-6 0.0101 1];
sys = tf(num, den);
bode(sys)
```
![[Captura de Pantalla 2024-04-28 a la(s) 10.19.26 p.m..png|500]]

