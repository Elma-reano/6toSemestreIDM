# Introducción

El lugar geométrico de las raíces, que es una represetacion grafica de los polos en lazo cerrado cuando varía un parámetro de un sistema, es un poderoso método de análisis y diseño para estabilidad y respuesta transitoria. Para la comprensión del método se recurre a las matemáticas.

El lugar geométrico de las raíces es una técnica gráfica que nos da la descripción **cualitativa** de la operación de un sistema de control.

<span style="color:#ff0000">Es la línea que siguen los polos cuando hacemos variar la ganancia.</span>

### Temas previos a recordar

- El problema del sistema de control

AAAAA

## Representación vectorial de números complejos

We pues reales en $x$ e imaginarios en $y$

$$\color{blue} F(s)=\frac{∏_{i=1}^m(S+z_i)}{∏_{i=1}^n(S+p_j)}=\frac{∏\text{factores complejos del numerador}}{∏\text{factores complejos del denominador}}$$
En cuanto a los ángulos $\theta$ de $F(S)$ en cualquier punto $S$,
$$\theta=\sum\text{ángulos de los ceros}-\sum\text{ángulos de los polos}$$
$$\color{blue} \theta=\sum_{i=1}^m\angle (S+z_i)-\sum_{i=1}^n\angle (S+p_j)$$
Y la magnitud
$$\color{blue} M=\frac{\Pi \text{ longitudes de ceros}}{\Pi \text{ longitudes de polos}}=\frac{\Pi^m_{i=1}|(S+z_i)|}{\Pi^n_{i=1}|(S+p_j)|}$$

## Ejemplo

Para la función $F(S)=\frac{(S+1)}{S(S+2)}$, calcula $F(S)$ en el punto $S=-3+4j$
$$|-2+4j|=\sqrt{ (-2)^2+4^2 }=\sqrt{ 20 }$$

![[Lugar geométrico 2024-05-24 11.50.59.excalidraw]]
La magnitud de $F(S)\implies M=\frac{\sqrt{ 20 }}{5\sqrt{ 17 }}=0.217$

Angulo de inclinación:
- Polo $-2$: $\sqrt{ 17 }\angle 104º$
- Cero $-1$: $\sqrt{ 20 }\angle 116.6º$
- Polo dle origen: $5\angle 126.9º$

Para el calculo de la magnitud $M$ y del ángulo $\theta$ de $F(s)$:
$M\angle \theta=\frac{\sqrt{ 20 }}{5\sqrt{ 17 }}\angle 116.6º-126.9º-104º$
$$M\angle \theta=0.217\angle-114.3º$$

## Actividad 1

Dada $$F(s)=\frac{(S+2)(S+4)}{S(S+3)(S+6)}$$calcula $F(S)$ en el punto $S=-7+9j$, en las siguientes formas:
1. Al calcular el resultado usando vectores
2. Directamente al sustituir el punto dado en $F(S)$

**Magnitudes**

$$(S+2)\implies |-7+9j+2|=|-5+9j|=\sqrt{ (-5)^2+9^2 }=\sqrt{ 106 }$$
$$(S+4)\implies |-7+9j+4|=\sqrt{ 3^2+9^2 }= 3\sqrt{ 10 }$$
$$(S)\implies |-7+9j|=\sqrt{ 49+81 }=\sqrt{ 130 }$$
$$(S+3)=|-7+9j+3|=|-4+9j|=\sqrt{ 16+81 }=\sqrt{ 97 }$$
$$(S+6)\implies |-7+9j+6|=|-1+9j|=\sqrt{ 82 }$$
Erika le tomo foto a la act (24 de mayo 2024)



## Problema:

Yo

## Otro problema:

Dado el sistema con retroalimentación unitaria que tiene una función de transferencia directa
$$G(S)=\frac{K(S+2)}{S^2+4S+13}$$
1. Calcula el ángulo de $G(s)$ en el punto $(-3+0j)$
2. Determina si el punto especificado en 1. está sobre el lugar geométrico de las raíces

![[01 Lugar geométrico 2024-05-28 11.45.07.excalidraw]]

#TODO 

Una funcion de algo
$$\sum\frac{1}{\sigma+2i}=\sum\frac{1}{\sigma+P_i}$$
$$\frac{1}{\sigma-3}=\frac{1}{\sigma+\sigma}+\frac{1}{\sigma-1}+\frac{1}{\sigma-2}+\frac{1}{\sigma-4}$$
<div style="page-break-after: always;"></div>

# EXAMEN LOLITA

## Pregunta 1

$$F(S)=\frac{(S+1.5)}{S(S+1)(S+10)}$$
$$\text{Cuando }S=-6+8j$$
**Ceros:** -1.5
**Polos:** 0, -1, -10

![[01 Lugar geométrico 2024-06-05 12.57.23.excalidraw]]

- Polo $0$: $-6+8j\implies 10\angle 126.87$
- Polo $-1$: $-6+8j+1=-5+8j\implies 9.43\angle 122.005$
- Cero $-1.5$: $-6+8j+1.5=-4.5+8j\implies 9.17\angle 119.358$
- Polo $-10$: $-6+10+8j=4+8j\implies 8.944\angle 63.4349$

Angulo:
$$119.358º-126.87º-122.005º-63.4349º=-192.952º=167.048º$$
Magnitud:
$$\frac{9.17}{10\times 9.43\times 8.944}=0.010878≈0.011$$
## Pregunta 2

$$G(S)=\frac{K}{S(S+6)(S+9)}$$
Calcula las asintotas

Escribe $\sigma_\alpha$

Polos finitos: $\{ 0, -6, -9 \}$
Ceros finitos: 💀

$$\sigma_\alpha=\frac{\sum\text{polos finitos}-\sum\text{ceros finitos}}{\#\text{polos finitos}-\#\text{ceros finitos}}$$

$$\therefore\sigma_\alpha=\frac{\sum\{ 0, -6, -9 \}}{3}=-\frac{15}{3}=-5$$

