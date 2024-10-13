# curso-devops-docker basico

4.1-Ejercicio. día 8/10/24.
primer ejercicio: necesitamos descargarnos un contenedor de NGINX, leyendo la documentación debo de ser capaz de levantarlo y ponerlo en funcionamiento. Como se que es un servidor HTTP necesito que desde mi navegador, al acceder a la url más puerto del contenedor se me muestre la pagina inicial de NGINX. (tambien puedo encontrar la documentación en docker hub)

Una vez configurado todo. necesito que el puerto inicial de entrada, cambie y sea ese numero más uno, es decir, que si fuera el 1000, en este punto debe ser el 1001

SOLUCION, YO LO HE HECHO CON EL PORT 8000:80,, Y LUEGO DE 8001:80

--
4.2. ejercicio
tenemos una base de un proyecto, necesitamos crear un microservicio de cada uno de estos:
mailService
userService
Database. (mongo, sql, etc, de lo que queramos) (ahora mismo no abra conexion entre ellos, pero más adelante si.)

tengo una arquitectura basada de estos microservicios necesito desplegar con docker-compose. el archivo docker compose, debe ser unico y debe estar en la carpeta raiz donde estarán contenidas las carpetas del mailService y del userService

cada microservicio se compondra de las siguientes partes:
la carpeta src y test, dockerfile, jest.config.js
package.json y el readme.md,

recordar que el mailService y el userService comparten codigo.

tened en cuenta los PUERTOS y lo ideal es que docker-compose.yml haga el build tanto del mailService como del userService.

la base de datos debe ser a elección propia.

## por tanto en el docker compose yml , tendriamos 3 services: mailService, userService y Database(será compartida por todos los microservicios).

3 ejercicio. necesitamos tener un wordpress instalado en mi local mediante docker. necesito modificar el docker-compose.yml para que me levante un servicio de wordpress en mi local y poder acceder a el desde mi ordenador. Y además, cuando el wordpress me funcione, necesito modificar el puerto de entrada desde mi maquina.. creamos una rama nueva eliminamos micro servicios (emailService y userService)
