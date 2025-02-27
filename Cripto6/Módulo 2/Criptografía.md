
En pocas palabras, la criptografía se define como la ciencia de codificar y decodificar códigos secretos, incluyendo la creación y estudio de métodos que permitan descifrar códigos que ya habían sido encriptados.

Esta ciencia se apoya en distintas áreas del conocimiento como las matemáticas, computación y la ingeniería. Particularmente, en las matemáticas recurre a campos como el álgebra, teoría de números, teoría de grafos, probabilidad y estadística.

Modernamente, la criptografía se divide en dos áreas:
- Criptografía de clave simétrica
	- Es la cual en la que tanto el emisor como el receptor son los únicos que conocen los algoritmos de codificación y decodificación
- Criptografía de clave pública
	- En la cual el método de encriptación es público, pero solamente quien recibe el mensaje sabe cómo decodificarlos


> Generalmente, a los usuarios en criptografía se les llama Bob y Alice. En español y en este curso los llamaremos <span style="color:#0070c0">Alicia y Beto</span>.

Algunos de los conceptos básicos para usar la criptografía son
- En un mensaje que se envía, el mensaje como tal se le llama **texto plano**, el cual una vez se encriptó se convierte al **texto cifrado**. 
- Normalmente, los **alfabetos** que se utilizan para ambos tipos de texto son los mismos. Los alfabetos son el conjunto de símbolos que están dentro del mensaje.
- El proceso con el cual se codifica el texto plano es la **encriptación**; mientras que lo opuesto se le conoce como **decodificación**.

![[Criptografía 2024-04-22 09.49.42.excalidraw]]

Los algoritmos de encriptación descomponen el texto plano y/o cifrado en **unidades**; las cuales, en general, son vectores de letras de $k$ componentes. Dicho esto, el algoritmo de encriptación se define como una función inyectiva
$$f:\mathcal{P}\to\mathcal{C}$$
donde $\mathcal{P}$ es el conjunto de todas las unidades de texto plano, $\mathcal{C}$ es el conjunto de todas las unidades de texto cifrado y $f$ es una función llamada **mapa de encriptación**.

La **inversa izquierda** de la función $f$, es 
$$G:\mathcal{C}\to\mathcal{P}$$
y representa el **proceso de decodificación**.

Todos juntos, la colección $\{ \mathcal{P},\mathcal{C},f,g \}$ se le conoce como el <span style="color:#ff0000">sistema básico de encriptación</span>.

