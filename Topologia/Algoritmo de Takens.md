
Este es un algoritmo que sirve para verificar periodicidad en un set de datos
Imaginemos que ... #TODO 


## Ejemplo

Se especifican las condiciones iniciales del algoritmo
$\tau$ (tamaño de paso, como un $∆$)=$1/2$
$d$ (dimensión) = $2$

![[Algoritmo de Takens 2024-04-18 15.21.09.excalidraw]]
Tomamos la señal del coseno 

Lo que hace el alrogitmo es que toma los valores de la tabla de mediciones y manda esos valores a una dimensión diferente. 

$F_{1}=(1,0.88)$
$F_{2}=(0.88,0.54)$
...




# Por qué usamos el encaje de Takens?

### Teorema de Florin Takens

Si se escogen bien los parámetros $(\tau,d)$, la geometría va a ser la misma que teníamos antes; y como estamos usando otras dimensiones, sirve para poder seguir triangulándolo.

La función $Tf_{\tau,d}(t)=(f(t),f(t+\tau),\dots,f(t+(d-1)\tau))$ es un **difeomorfismo**, por lo que los números de Betti no cambian. Entonces, los diagramasde persistencia son similares

Si los datos son periódicos, los números de Betti #TODO 

# Parámetro $\tau$


$\tau$ es el delay entre coordenadas

(1) Restringir $\tau=[0,k]$ y obtener el mínimo absoluto
(2) No restringir a $\tau$ y obtener el primer mínimo local


Sea $\tau>0$

| t     | $x_t$     |
| ----- | --------- |
| $t_i$ | $x_{t_i}$ |
| ...   | ...       |
$(x_{t_i},x_{t_i+\tau})$
