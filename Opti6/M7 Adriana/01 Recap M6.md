
En este modulo habíamos hecho bosquejos de los diagramas de Bode y los habiamos corroborado con Matlab

Qué eran los diagramas de Bode? Son otra interpretación de la estabilidad de un sistema.
%%
 Según Manolo, vamos a usar COMSOL?!?!?!?!?! 💀
%%

**Margen de ganancia:**  es el incremento o decremento máximo de ganancia (medido en decibeles). Esto se lee directamente desde el diagrama de Bode calculando la distancia vertical entre la magnitud y el eje x en la frecuencia e la que el ángulo es -180º.
$$GM=0-G_{dB}$$

**Margen de fase:** entre más grande sea este margen, mayor será la estabilidad del sistema. Generalmente se expresa en grados y se determina midiendo la distancia vertical del diagrama de Bode desde la curva de fase hacia el eje x con frecuencia de ganancia de cruce, es decir, donde son $0\text{ dB}$.
$$PM=\phi-(-180º)$$
Donde $\phi$ es la fase interpretada desde el eje vertical en la frecuencia de ganancia de cruce.


El <span style="color:#ff0000">criterio de estabilidad de Bode</span> es un método usado en la ingeniería de sistemas de control para determinar la estabilidad de un sistema. Este criterio se basa en el análisis de frecuencia de respuesta de un sistema.
- Sistema estable: ambos margenes deben ser positivos o mayores al margen de ganancia
- Sistema marginalmente estable: los márgenes deben ser 0 o iguales al margen de ganancia
- Sistema inestable: si alguno es negativo o el margen de fase es menor al de ganancia

### Ejemplo
Para el ejercicio 1 de la tarea, tuvimos la funcion de transferencia $G(s)=\frac{1}{s(s+1)}$

```matlab title=Ejemplo1
num = [1];
den = [1 1 0];
g = tf(num, den);
bode(g) % diagrama de bode
margin(g) % muestra los márgenes del diagrama de bode
```

En el ejercicio 2, utilizamos la función de transferencia $\frac{U(s)}{E(s)}=\frac{0.1(s+1)^2}{s(s+100)}$
```matlab title=Ejemplo2
num = [1 10 100];
den = [10 1000 0];
g = tf(num, den);
bode(g)
margin(g)
```

![[Captura de Pantalla 2024-05-20 a la(s) 10.56.52 p.m..png|308]]![[Captura de Pantalla 2024-05-20 a la(s) 10.57.07 p.m..png|300]]


# Tarea 1
Demostrar que $$M(s)=\frac{Y(s)}{R(s)}=\frac{G(s)}{1+G(s)H(s)}$$

# Tarea 2
Demostrar que
$$M(s)=\frac{Y(s)}{R(s)}=G(s)$$


