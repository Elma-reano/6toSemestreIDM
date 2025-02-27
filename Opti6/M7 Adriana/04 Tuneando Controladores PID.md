> Así es. Como los tsurus.

En simulink podemos alterar los parámetros de los controladores para cambiar la respuesta que deseamos que el controlador maneje.

Si consideramos una función de transferencia $G(s)=\frac{0.3}{s^2+0.1s}$, creamos un disturbio con una función escalor. Con una magnitud de 0.02, ocurriendo en el tiempo $t=200s$

Si modelamos esto solamente queda
![[Captura de Pantalla 2024-05-26 a la(s) 9.43.49 p.m..png]]

Sin embargo, en los parámetros del controlador PID podemos darle a una opción que dice "Tune".

Por alguna razón que desconozco, ninguna de las gráficas me da como la presentación.
![[Captura de Pantalla 2024-05-26 a la(s) 9.51.24 p.m..png]]

En teoría, antes de tunear el controlador debería de tener esto.
![[Captura de Pantalla 2024-05-26 a la(s) 9.52.31 p.m..png|300]]

En cambio, yo tengo esto.
![[Captura de Pantalla 2024-05-26 a la(s) 9.53.09 p.m..png|350]]

Por qué? #duda 

Después de tunear el controlador, queda un resultado bastante diferente.


![[Captura de Pantalla 2024-05-26 a la(s) 9.55.11 p.m..png|200]]
![[Captura de Pantalla 2024-05-26 a la(s) 9.55.37 p.m..png]]
#solved Ya quedo. Solo tenia que moverle a los parametros a lo wey hasta que quedara poco overshoot y poco tiempo de subida.

![[Captura de Pantalla 2024-05-27 a la(s) 10.10.09 a.m..png]]

