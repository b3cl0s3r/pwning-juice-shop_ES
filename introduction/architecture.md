# Visión general de la arquitectura

OWASP Juice Shop es una aplicación web puramente implementada
en JavaScript y TypeScript (que es compilado en JavaScript). En el
frontend se utiliza el framework popular [Angular](https://angular.io/)
para crear lo llamado _Single Page Application_ o una aplicación de una 
sola página. El diseño de la interfaz de usuario está implementado con 
[Material Design](https://material.io/) de Google utilizando componentes 
de [Angular Material](https://material.angular.io/). Se emplea 
[Angular Flex-Layout](https://github.com/angular/flex-layout)
para lograr un diseño responsivo. Todos los iconos encontrados en la 
interfaz de usuario provienen de la librería [Font Awesome](https://fontawesome.com).

Se utiliza también JavaScript en el backend como lenguaje de programación
exclusivo: Una aplicación [Express](http://expressjs.com) aloja en un 
servidor [Node.js](https://nodejs.org) que entrega el código del lado 
del cliente a través de una API RESTful. Como base de datos subyacente,
[SQLite](https://www.sqlite.org) fue elegida, por su naturaleza basada
en ficheros. Esto hace que la base de datos sea sencilla de crear desde
cero de forma programática sin la necesidad de tener un servidor dedicado.
[Sequelize](http://docs.sequelizejs.com) y
[epilogue](https://github.com/dchester/epilogue) fueron utilizados como
una capa de abstracción de la base de datos. Esto permite usar dinámicamente
los endpoints creados de la API para simple interacciones (p.e. operaciones 
CRUD) con recursos de la base de datos mientras que todavía permite ejecutar
SQL propio para consultas más complejas.

Como un almacenador de datos adicional, [MarsDB](https://github.com/c58/marsdb)
es parte de OWASP Juice Shop. Es un derivado de JavaScript de la base de
datos NoSQL ampliamente utilizada [MongoDB](https://www.mongodb.com), que
es compatible con la mayoría de sus operaciones de consulta/modificación.

Las notificaciones que son mostradas cuando un reto ha sido resuelto 
exitosamente, están implementadas via 
[WebSocket Protocol](https://tools.ietf.org/html/rfc6455).
La aplicación también ofrece registración de usuario a través de 
[OAuth 2.0](https://oauth.net/2/), así los usuarios pueden conectarse
utilizando su cuenta de Google.

El siguiente diagrama muestra la traza de la comunicación de alto 
nivel entre las capas de cliente, servidor y datos:

![Architecture overview diagram](https://raw.githubusercontent.com/bkimminich/pwning-juice-shop/master/introduction/img/architecture-diagram.png)
