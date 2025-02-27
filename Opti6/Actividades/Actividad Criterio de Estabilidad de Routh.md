Cada uno de los polinomios mostrados abajo representa el polinomio característico de algún sistema de lazo cerrado.  
1. Determina un arreglo de Routh necesario para determinar la estabilidad o inestabilidad del sistema para cada inciso.  
2. Obtén las raíces y agrega foto del código de Matlab necesario para obtenerlas.  
3. Grafica el comportamiento de la respuesta de la función de transferencia si suponemos N(s)=1, usando Simulink, comprobando así la estabilidad o inestabilidad.

a) $s^8+7s^7+4s^6-s^5+7s^4+2s^2+s+3$


| $s^8$ | 1      | 4      | 7     | 2     | 3     |
| ----- | ------ | ------ | ----- | ----- | ----- |
| $s^7$ | **7**  | **-1** | **0** | **1** | **0** |
| $s^6$ | 4.14   | 7      | 1.86  | 3     | 0     |
| $s^5$ | -12.83 | -3.14  | -4.07 | 0     | 0     |
| $s^4$ | 5.99   | 0.55   | 3     | 0     | 0     |
| $s^3$ | -1.96  | 2.35   | 0     | 0     | 0     |
| $s^2$ | 7.73   | 3      | 0     | 0     | 0     |
| $s^1$ | 3.11   | 0      | 0     | 0     | 0     |
| $s^0$ | 3      | 0      | 0     | 0     | 0     |
Dado que hubo 4 cambios de signo, es <span style="color:#ff0000">inestable</span>

![[Captura de Pantalla 2024-04-05 a la(s) 10.28.06 p.m..png]]

![[Pasted image 20240405221555.png]]

--------
b) $s^5+2s^4+2s^3+12s^2+21s+10$

| $s^5$ | **1** | **2**  | **21** |
| ----- | ----- | ------ | ------ |
| $s^4$ | **2** | **12** | **10** |
| $s^3$ | -4    | 16     | 0      |
| $s^2$ | 20    | 10     | 0      |
| $s^1$ | 18    | 0      | 0      |
| $s^0$ | 10    | 0      | 0      |
Al haber dos cambios de signo es inestable y, de igual forma, al observar la gráfica se aprecia que no se encuentran en el plano negativo; corroborando que es inestable

![[Pasted image 20240405221525.png]]
![[Pasted image 20240405221941.png]]

-------------
c) $s^4+2s^3+2s^2+6s+10$

| $s^4$ | **1**                                  | **3** | **10** |
| ----- | -------------------------------------- | ----- | ------ |
| $s^3$ | **2**                                  | **6** | **0**  |
| $s^2$ | $\epsilon$                             | 10    | 0      |
| $s^1$ | $-6-20\frac{1}{\epsilon}$              | 0     | 0      |
| $s^0$ | $-\frac{100-30\epsilon}{10+3\epsilon}$ | 0     | 0      |
![[Captura de Pantalla 2024-04-05 a la(s) 10.26.07 p.m..png]]
![[Captura de Pantalla 2024-04-05 a la(s) 10.25.12 p.m..png]]

-----------
d) $s^5+2s^4+6s^3+48s^2+8s+160$

| $s^5$ | 1                                    | 6                                    | 8                                    |
| :---: | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| $s^4$ | **2**                                | **48**                               | **160**                              |
| $s^3$ | -18                                  | -72                                  | 0                                    |
| $s^2$ | 40                                   | 160                                  | 0                                    |
| $s^1$ | <span style="color:#ff0000">0</span> | <span style="color:#ff0000">0</span> | <span style="color:#ff0000">0</span> |
| $s^0$ |                                      |                                      |                                      |
Dada la fila de ceros
$$P_{aux}(s)=40s^2+160$$
$$P_{aux}'(s)=80s$$

| $s^5$ | **1** | **6**  |  **8**  |
| ----- | ----- | ------ | :-----: |
| $s^4$ | **2** | **48** | **160** |
| $s^3$ | -18   | -72    |    0    |
| $s^2$ | 40    | 160    |    0    |
| $s^1$ | 80    | 0      |    0    |
| $s^0$ | 160   | 0      |    0    |
Debido a que hubo cambios de signos y una fila de ceros, es marginalmente inestable

![[Captura de Pantalla 2024-04-05 a la(s) 10.34.27 p.m..png]]
![[Captura de Pantalla 2024-04-05 a la(s) 10.34.44 p.m..png]]
