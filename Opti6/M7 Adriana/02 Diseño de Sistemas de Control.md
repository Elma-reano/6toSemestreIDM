
Los sistemas de control se suelen hacer dentro del dominio del tiempo o de frecuencia.
En cuanto el dominio de tiempo, se usa mucho el plano *s* y la raíz loci; en cambio, el dominio de frecuencia se basa en manipular la ganancia y fase de la función de transferencia.

Para diseñar un sistema de control hay que seguir 3 pasos:
1. determinar qué debe hacer el sistema y cómo para poder establecer especificaciones del diseño como estabilidad relativa, robustez, sensibilidad, etc.
2. Determinar el controlador y su configuración
3. Determinar los valores de los parámetros del controlador
![[Captura de Pantalla 2024-05-20 a la(s) 11.11.47 p.m..png]]

- La función de transferencia del controlador es el parámetro principal a la hora de diseñar un sistema de control.
- La estabilidad del sistema se define como la capacidad de encontrar un punto de equilibrio una vez alterado. Por lo tanto, un sistema inestable tendrá una respuesta transitiva que diverge a magnitudes infinitas, sin importar la entrada.
- Si la salida es una constante, entonces el controlador se llama un *regulador*. Por otro lado, si cambia con el tiempo, el sistema de control se denomina **tracking system**

Resumido: la tarea prinicpal del controlador es lograr $yd-y=0$ ASAP

Para que el sistema se clasifique como sistema de control por retroalimentación, debe tener una variable controlada que va a comparar y modificar la entrada de referencia.

Un sistema puede contener:
- Retroalimentación Unitaria: es cuando el sistema tiene una salida $C(s)=G(s)E(s)$ 
![[Captura de Pantalla 2024-05-26 a la(s) 10.44.01 a.m..png|300]]
- Elemento de retroalimentación: es un elemento que convierte la señal de salida según la comparación que se haga. Compara la señal de entrada con $B(s)=H(s)C(s)$
![[Captura de Pantalla 2024-05-26 a la(s) 10.47.17 a.m..png|300]]
### Ejercicio en Clase

Asumiendo que la función de transferencia de una planta es $$G(s)=\frac{1}{RCs+1}$$
1. Asumiendo $R=1, C=0.1$, determina la respuesta de un sistema a una función impulso, tanto en matlab como en simulink

```matlab title="En Matlab"
num = 1;
den = [0.1 1];
sys = tf(num, den);
impulse(sys)
```

![[Captura de Pantalla 2024-05-13 a la(s) 12.23.52 p.m..png|400]]
Ahora, en simulink
![[Captura de Pantalla 2024-05-13 a la(s) 12.31.25 p.m..png|300]]

![[Captura de Pantalla 2024-05-13 a la(s) 12.28.00 p.m..png|500]]

Esta gráfica tiene un error, es decir, no está exacta al impulso que obtuvimos con código. Por lo tanto, hay que ajustarlo con retroalimentación.
![[Captura de Pantalla 2024-05-13 a la(s) 12.49.07 p.m..png]]
![[Captura de Pantalla 2024-05-13 a la(s) 12.47.58 p.m..png]]

Aunque no parece mucha diferencia, en mayores escalas esto puede llegar a hacer muuuuucha diferencia.

