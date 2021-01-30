# CompartoLoQueSe

## Las capas de una pagina/app web

Una app web esta compuesta por 2 grandes capas segun los desarrolladores:
- El front-end: Lo que el usuario ve en sus pantallas del celular, computadora, tablets, etc.
- El back-end: Lo que el usuario no ve pero que trabaja en conjunto al front-end.

Hay varios memes a cerca de este esquema de las app web en donde muestran que el front-end es tooodo lindo y atractivo, mientras que el back-end es un "quilombo" (jaja). En cierta forma es cierto, dentro del back-end hay procesos logicos, algoritmos, validaciones y otras cosas con las que todavia no me he topado y que deben ser complejas.

Lo importante que quiero compartir, despues de varios meses de pruebas y proyectos es que me gustaria agregar un par de componentes mas a ese esquema asi que aca va de vuelta:
- La base de datos: Es obvio que siempre hay una en cualquier tipo de app "dinamica" (explicare eso en otro momento), digamos que este componente es obvio pero no por eso quiero obviarlo como hacen esos memes jaja.
- El ORM: El ORM es un mapeador de lo que hay en la base de datos a "clases" que usa el back-end. Este componente es encargado de reducir el tiempo de produccion de una app web porque reduce el tiempo que perdemos en crear manualmente esas clases. Hay un articulo interesante que habla de la historia de estos ORMs y la "disputa" que habia entre el programador de bases de datos y el programador del back-end, cuando lo encuentre se los paso.
- El back-end: Ya mencionado arriba.
- El puente entre el back-end y el front-end, el protocolo HTTP: Este protocolo es el encargado de comunicar el back-end con el front-end a traves de peticiones por parte del usuario y respuestas por parte del servidor, y si, el front-end es conocida tambien como la capa del cliente y el back-end es conocida como el servidor. Lo importante que quiero destacar es que parece haber 2 metodos para hacer la transferencia de datos entre el cliente y el servidor: "refrescos de pagina" o "transferencias asincronas".
1. La primera se esta poniendo en desuso debido a que en ciertos escenarios representa una mala experiencia para el usuario, hablare mas de esto en otro momento.
2. La segunda se trata de una transferencia de datos en donde el usuario muchas veces no se percata de dicha transderencia, necesario para que la pagina/aplicacion web resulte rapida, atractiva y por ende, amigable al usuario.
- El front-end: Ya mencionado arriba.

Eso es todo por hoy, si quieren aprender más: Google jaja, o pueden escribirme, 0 drama!

Ya cuando pueda me hare un blog y subire todo lo que se ahi, pero bueno, por el momento me manejo asi, ando a full con otras cosas. Saludos!
