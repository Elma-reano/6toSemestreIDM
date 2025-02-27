
# <span class="center-text" style="color:#000">Examen Práctico</span>
## <span class="center-text" style="color:#666666">Mariano Luna Delgado&emsp;A01570406</span>

### Planteamiento del Problema

Pokémon es una franquicia de videojuegos que comenzó en el Game Boy, en la cual el o la protagonista de cada juego busca "capturar" a todos los pokémon para convertirse en un *Maestro Pokémon*. Además de capturarlas, el jugador puede jugar a combates; en los cuales se pelea un equipo de 6 pokémon contra otro. En dicho combate se toman en cuenta las estadísticas de vida, ataque, defensa, tipo, etc. de cada pokémon para calcular el daño de los ataques hacia el otro combatiente, así como el daño recibido y la vida restante de cada integrante del equipo, entre otras cosas. 
Cada tipo único de pokémon tiene un impacto relevante en el combate. Es por eso que se desea encontrar un equipo de Pokémon que esté balanceado tanto en las estadísticas (vida, ataque, defensa, etc.) como en los tipos de Pokémon; para que, en una batalla competitiva, el equipo pueda combatir cualquier tipo de Pokémon.
%%
A partir de esto nacen las siguientes preguntas de investigación:
- ¿Existen Pokémon con estadísticas y/o características similares en términos de tipo?
- ¿Cómo se puede tomar en cuenta la evolución y mega evolución de los Pokémon en la selección del equipo?
- ¿Cómo se incorpora la resistencia y debilidad de cada Pokémon en la selección de equipo?
%%
### Metodología

Lo primero, se extrajo la base de datos de Pokémon desde kaggle para comenzar la preparación de los datos y, una vez importada al código, se exploró y observó que la base de datos abarca hasta la generación 6; así como que incluye a las mega evoluciones de los pokémon que la tenían disponible en esa generación y que no hay entradas repetidas dentro del dataset.
Luego, se tomó en cuenta el nivel de interacción entre cada uno de los tipos de pokémon. Dicha interacción se obtuvo a partir del grafo siguiente:
![imagen|250](https://img.pokemondb.net/images/typechart.png) 
Dado esto, se hizo una matriz con cada uno de los valores multiplicadores de las interacciones de tipo con cada uno de los pokémon; para luego establecer una columna con un coeficiente de versatilidad (hecho con una fórmula arbitraria).

Después, se observó si las columnas numéricas tenían correlación entre sí y se le aplicó one-hot encoding a las columnas de *Tipo* de cada pokémon.![[Examen Práctico 2024-05-03 20.54.59.excalidraw]]
Además, se estandarizaron los datos para luego convertirlos a una matriz de datos de numpy y hacer la proyección de los datos con la que se haría el clustering.

Se utilizaron las funciones fit_transform, map y visualize de la librería de Kepler Mapper para hacer la clusterización, de la cual se seleccionaron 6 pokémon de nodos diferentes para formar el equipo.
### Resultados

![[Captura de Pantalla 2024-05-03 a la(s) 8.59.10 p.m..png|350]]

Analizando los resultados, se observó que en el sigleton se clusterizaron pokémon con baja versatilidad y de monotipo, pero con altas estadísticas. En el cluster de arriba a la izquierda, se observa que se clusterizaron pokémon de ambos monotipos y doble tipos, pero con estadísticas más bajas en comparación al singleton. Por último, en el cluster más grande se observó que eran sólamente pokémon de alta versatilidad (doble tipos) con estadísticas altas.
Por lo tanto, para tener un equipo balanceado se optó por elegir un pokémon del singleton, dos del cluster pequeño y tres del cluster grande, con la restricción de que sólo se puede elegir un pokémon por nodo.

Los nodos fueron elegidos aleatoriamente, siendo los nodos elegidos `cube27_cluster0`, `cube29_cluster0`, `cube17_cluster0`, `cube25_cluster0`, `cube26_cluster0` y `cube6_cluster0`.

Se observaron las tablas y gráficas de cada uno de los nodos y se eligieron pokémon tomando en cuenta su tipo, su versatilidad y su estadística total.

Los pokémon elegidos fueron:
- Xerneas
- Garchomp (Mega)
- Charizard
- Empoleon
- Reuniclus
- Pikachu
Aunque Charizard también cuenta con mega evolución, se puede optar por no utilizarla.
Se eligió la mega evolución de Garchomp debido a que la mega evolución X de Charizard le cambia el tipo y termina desbalanceando el equipo (y la mega evolución Y no se ve tan cool)

Para evaluar el balance del equipo, se utilizó una [herramienta web](https://mypokemonteam.com/) para comprobar si el equipo efectivamente podía hacer frente a cualquier tipo de pokémon. Dicha herramienta fue específicamente elegida debido a que hace la evaluación del equipo tomando en cuenta la generación 9, la cual es muy cercana a la generación 6
Se obtuvo el siguiente resultado:
![[Captura de Pantalla 2024-05-03 a la(s) 11.37.34 p.m..png|500]]
Aunque se muestra que es débil contra los tipos tierra y fantasma, en fantasma es debido a que sólamente un pokémon es débil contra ese tipo; mientras que los demás son indiferentes. En cuanto a tierra, le hace daño a dos pero uno de los pokémon es inmune (Charizard).

![[Examen Práctico 2024-05-03 23.41.52.excalidraw|900]]