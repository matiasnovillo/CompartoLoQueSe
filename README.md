# CompartoLoQueSe

## ¿Qué es el tipo MIME de un archivo? (04/02/2021)
Pregunta hecha en Quora y que respondi, la cual comparto por aca tambien.

Hola, cómo te va?
A esto del tipo/formato MIME lo vi en dos lugares: 1. En la transferencia de datos mediante el protocolo HTTP: Cuando entras a un sitio web, al servidor que contiene dicho sitio le estas solicitando el acceso, él, como respuesta te devuelve una serie de archivos, por ejemplo, si entro a Google buscando algo, este me devuelve los archivos que ves debajo, en la pestaña Network (Ctrl + Mayus + I para acceder).

![MIME](https://botanicopadel.com/PublicSharing/MIME1.png)

Como veras, el formato MIME esta especificado en la columna Type.
Otro lugar donde lo he visto es en la configuracion de un servidor. Hay una seccion que dice transferencia de archivos, ahi debes especificar que formatos MIME queres proveer a tus usuarios (salida). Incluso creo que te deberia dejar configurar que formatos MIME pueden ser aceptados en las solicitudes de tus usuarios (entrada).

Espero te sirva, saludos!

## ¿Qué debo saber antes del desarrollo web multiplataforma? (02/02/2021)
Pregunta hecha en Quora y que respondi, la cual comparto por aca tambien.

Hola, cómo te va? 
Te puedo dar tips sobre eso para que tengas en cuenta y lo busques en Google, acá voy:
1.  El desarrollo web multiplataforma se basa en el paradigma "programación por capas" y en el paradigma "programación por componentes". Ambos paradigmas hacen que tu aplicación/sistema web pueda ser fácilmente leído, monitoreado y cambiado ante diferentes escenarios. ¿Para qué? Te ahorrará tiempo y dinero. 
2. El desarrollo web multiplataforma, y en realidad cualquier desarrollo informático necesita de principios de programación como KISS (Keep it simple, stupid) o el SOLID. Estos principios van muy de la mano con los paradigmas mencionados anteriormente.
3. La palabra API, el diseño responsive y el diseño PWA son palabras que explican como una aplicación/sistema web debe adaptarse a diferentes escenarios como: 1. El usuario que visita tu página desde un browser de Windows. 2. El usuario que visita tu página desde una tablet. 3. El usuario que visita tu página desde un celular. 4. El usuario que visita tu negocio desde una app Android o iPhone. 5. El usuario que quiere consumir tus APIs a través de interfaces distintas a las usuales como entrar al Google Chrome (este generalmente es también un desarrollador o comerciante).
4. Si empiezas desde 0% o 25% en la programación te recomiendo que aprendas de las buenas prácticas de desarrollo (BPD) como primer objetivo. Cuando hablo de las BPD me refiero a aprender primero de los estándares que hay en cada fase del desarrollo web, hay un estándar para el modelado de bases de datos, hay un estandar para el desarrollo de APIs, hay un estándar incluso para cómo debes escribir tu código.
5. Segundo paso: Aprende a usar Git y GitHub, no se en que parte del camino estás pero te aconsejo que lo aprendas si no lo sabes. Después de usarlo un tiempo llegue a la conclusión de que es una especie de copy paste más poderoso que el Ctrl + C y Ctrl + V. Hay memes que muestran a Git como el autito que te permitr volver al pasado y cambiar cosas en tu código mal hecho, ya me viene salvando las papas 4 veces con mis códigos. Por otro lado GitHub es un lugar donde vas a ver la rueda ya inventada, cualquier proyecto informático que quieras incursionar ya esta en GitHub de forma gratuita para que lo uses a tu favor (busca los que tengan licencia Apache o MIT, preferiblemente). Además, ahí podrás hacer desarrollo colaborativo con personas de cualquier lado del mundo.
Cualquier cosa hablame para más tips, saludos desde Argentina! 

## Los tipos de datos y reglas de caracter estandar en MS SQL Server (31/01/2021)
DataTypes availables:
1. VARCHAR(N) where N can be any number, it depends the clients requirements
2. VARCHAR(MAX) for textarea tags, Rich Text Editors, files location like .jpg or .exe, URLs, passwords, tags/chips/multi select dropdowns/options separated with ;, or any kind of large string
3. TINYINT to manage boolean types in the backend: 0=false, 1=true
4. INT for integers (obvious!)
5. DATETIME accepting this only syntax yyyy/mm/dd hh:mm:ss. Example: '2021/01/26 08:10:50'. I don't manage PM or AM syntax
6. TIME(3) for time hh:mm:ss. Example: '08:10:50.123'. I don't manage PM or AM syntax
7. VARCHAR(6) for hexadecimal colour avoiding the # symbol, just the 6 values
8. NUMERIC(24,6) for decimal values. NUMERIC is better than DECIMAL by one tiny advantage. The maximum precision number is 38, and it seems that the scale can scale up to that number, 38.

Rules:
1. All the tables must have 1 and just 1 primary key (PK) and has to be [int] IDENTITY(1,1) NOT NULL. Does not matter your personal convention, you must put a PK.
2. All the tables and fields must be named in PascalCase notation, not camelCase either UPPERCASE or lowercase. This is made to make more readable that two objects.
3. All the fields of the tables don't need any kind of prefix to identify them because in any kind of DB operation the table name appears. The only field that need a prefix is the PK of the table because the word "Id" is reserved in MS SQL Server, so if your table is named as Product, your PK has to be named as ProductId.
4. Avoid using conventions like IntAge or VCName (Varchar). There is no need to do this because the back-end identifies easily all datatype.
5. In the case of foreign keys (FK), these must be the same as their referenced PK. Example: TableA/TableAId is PK and TableB/TableAId is FK of TableA/TableAId
6. A PK must be unique in the DB. You can't have TableA/TableAId and TableB/TableAId.
7. Avoid using reserved words from MS SQL Server like user, password or view. This have to be a must although you can use brackets to avoid this problem.
8. In case of fields that contains grouped information use plural nouns like TechnologiesUsed. Also, the grouped information has to be separated by ;. 
9. In the case of boolean fields, avoid simple nouns, instead, use questions like HasHusband or IsMarried. Also, avoid negative expressions like IsNotMarried, you might be confused in some cases.
10. All tables must have 1 TINYINT field to make logical deletions.
11. All tables must have 4 fields for audit: 1 field to know who made the new register, 1 field to know who changed the register, 1 field to know when was made the new register and 1 field to know when was modified the register.
12.  If we have 3 tables represented like this: A -> B <- C, and table A is more important than table C, table B can be named as AC
13. Stored procedures (SPs) must have the following syntax in their names: [Table.Action]. This make more readable the SPs listing.
14. The unique scheme that can be used in the DBs is: dbo

Si, esta en ingles, cuando pueda lo paso al español. Saludos!

## Las capas de una pagina/app web (30/01/2021)

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
