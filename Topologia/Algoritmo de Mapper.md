#algoritmos

Cómo funciona?

El primer paso es hacer la función proyección, que se usa como una función $f:\mathbb{R}^n\to \mathbb{R}^m$, donde $n>m$.
![[Algoritmo de Mapper 2024-04-15 15.18.25.excalidraw]]

Después, 
![[Algoritmo de Mapper 2024-04-15 15.21.00.excalidraw]]

Como tercer paso, se obtienen imágenes inversas a partir de la cubierta para una preimagen coloreada
![[Algoritmo de Mapper 2024-04-15 15.20.20.excalidraw]]
Luego, se clusterizan las imágenes inversas. Puede ser con criterio Kmeans, basado en densidad, jerárquica, etc.

![[Algoritmo de Mapper 2024-04-15 15.21.41.excalidraw]]


Finalmente, para nuestro output hacemos un nervio de los clusters hasta dimensión 1.
![[Algoritmo de Mapper 2024-04-15 15.22.35.excalidraw]]


## Aplicaciones de Mapper

Más que nada en clusterizar bases de datos. Yo lo usé en el examen jijiji