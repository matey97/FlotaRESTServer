# FlotaRESTServer
Project from EI1021-Sistemas Distribuidos. Battleship server side REST WebService with JAX-RS

Se diferencian el modelo y los servicios:

- Modelo (/src/modelo): el juego en sí.
  - Barco.java
  - Partida.java
- Servicios (/src/servicios): tratarán las peticiones de los clientes.
  - AplicaciónJuego.java: instancia los objetos que ofrecen los servicios, en este caso solo instanciamos uno, manteniéndolo como Singleton.
  - RecursoPartida.java: mantiene las partidas de los clientes y trata sus peticiones. Consta de los siguientes métodos:
    - nuevaPartida: responde a peticiones HTTP POST, devuelve al cliente como respuesta la URI de la nueva partida.
    - borraPartida: responde a peticiones HTTP DELETE, devuelve el resultado de borrar la partida, OK o NOT_FOUND.
    - pruebaCasilla: responde a peticiones HTTP PUT, devuelve el resultado de probar una casilla o NOT_FOUND.
    - getBarco: responde a peticiones HTTP GET y produce text/plain, devuelve un String que representa el barco o NOT_FOUND.
    - getSolucion: responde a peticiones HTTP GET y produce application/xml, devuelve las posiciones de los barcos en formato XML.
    
