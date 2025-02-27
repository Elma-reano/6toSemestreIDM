
Son los métodos que se utilizan para establecer una comunicación entre dos o más personas o entidades que se pueda considerar segura. Para esto todas las partes deben comunicarse entre sí y cooperar; por lo que deben seguir ciertas reglas y aplicar ciertos algoritmos que hayan acordado utilizar.

Un ejemplo de bastante uso es el *Transport Layer Security* (TLS), el cual fue diseñado para proporcionar seguridad en las comunicaciones a través de una red. Se usa mucho en el correo electrónico, mensajería instantánea y la voz sobre IP y, el más importante, en HTTPS.


Algunas de las tareas criptográficas pueden ser las siguientes:
- **Autenticación:** Se refiere al proceso de determinar que un mensaje, supuestamente de una persona determinada, efectivamente provenga de esa persona y que no haya sido manipulado.
	- [[Funciones hash]]
	- [[Firmas digitales]]
- **Intercambio y transporte de claves:** En un protocolo de intercambio declaves, dos personas intercambian una clave secreta compartida que se usa en un cifrado simétrico (Diffie-Hellman)
- **Compartir secretos:** implica métodos en los que algún secreto debe ser compartido por $k$ personas pero no está disponible para ningún subconjunto de ellas. Para poder reconstruir el secreto todas las partes deben colaborar compartiendo la información que tienen al respecto (Esquema de Shamir)

