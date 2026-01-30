# Servicios en Red - Práctica 6: Base de Datos
En esta práctica, desplegaremos una base de datos MariaDB (que es un fork de MySQL) en una máquina virtual. Accederemos a esta base de datos desde otra máquina virtual y desde nuestra máquina host, utilizando tanto una interfaz gráfica, también conocida como GUI (Graphical User Interface), como una interfaz de línea de comandos (CLI, Command Line Interface).

## Bases de Datos
Una base de datos es un sistema organizado para almacenar, gestionar y recuperar datos de manera eficiente. Permite a los usuarios y aplicaciones acceder a la información de forma rápida y estructurada. 

Son importantes en muchos ámbitos, desde aplicaciones web y móviles hasta sistemas empresariales, medicos y científicos, ya que facilitan la gestión y el análisis de grandes cantidades de datos.

### Tablas, Filas y Columnas

### Tipos de Datos

### Modificadores de Datos

### Relaciones entre Tablas

## Tipos de Bases de Datos
Existen varios tipos de bases de datos, cada una con sus propias características y usos. La clasificación mas importante es entre Bases de Datos Relacionales y no Relacionales. Básicamente, las bases de datos relacionales utilizan tablas para organizar los datos y SQL (Structured Query Language) como lenguaje de consulta, mientras que las bases de datos no relacionales lo único que tienen en común es que no utilizan tablas para organizar los datos y no utilizan SQL como lenguaje de consulta.

Habitualmente se les llama a las bases de datos relacionales y no relacionales como SQL y NoSQL respectivamente. Es un error común pensar que el término NoSQL significa "no SQL" o "sin SQL", cuando en realidad significa "no solo SQL" (Not Only SQL). Esto se debe a que algunas bases de datos NoSQL pueden soportar consultas SQL o lenguajes de consulta similares, pero no es su característica principal.

## SGBDs
Los Sistemas de Gestión de Bases de Datos (SGBD) o DBMS (Database Management Systems) son programas que permiten crear, gestionar y manipular bases de datos. Proveen una interfaz entre los usuarios y las bases de datos, facilitando la realización de operaciones como la creación, lectura, actualización y eliminación de datos (conocidas como operaciones CRUD). Algunos ejemplos populares de SGBDs incluyen MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server y MongoDB.

Comunmente se utiliza el término "base de datos" para referirse tanto a la base de datos en sí como al SGBD que la gestiona, aunque técnicamente son conceptos diferentes.

Poddemos definir la base de datos como un **conjunto organizado de datos estructurados** y el SGBD como el **software que permite gestionar y manipular esos datos**.

Los SGBDs determinan cómo se almacenan, organizan y acceden a los datos en la base de datos, por lo que el tipo de BBDD  y las operaciones que se pueden realizar dependen del SGBD utilizado. Esto quiere decir, por ejemplo, que las Bases de Datos Relacionales utilizan unos SGBDs específicos (como MySQL, PostgreSQL, MariaDB, etc.) y las Bases de Datos NoSQL utilizan otros SGBDs diferentes (como MongoDB, Cassandra, Redis, etc.).


## MariaDB y MySQL
MariaDB es un sistema de gestión de bases de datos (SGBD) relacional de código abierto que se deriva de MySQL. MariaDB fue creado por los desarrolladores originales de MySQL (que pertenece a Oracle) como una versión de código abierto de MySQL. Ambas bases de datos son muy similares en términos de funcionalidad y sintaxis SQL, ya que MariaDB se basa en el código fuente de MySQL. Sin embargo, MariaDB ha introducido varias mejoras y características adicionales que no están presentes en MySQL. Ademas, la mayoría de herramientas y aplicaciones que funcionan con MySQL también son compatibles con MariaDB.

_Fun fact_: El nombre "MariaDB" proviene del nombre de la hija del fundador de la empresa, quién se llama Maria.

## PhpMyAdmin
PhpMyAdmin es un cliente web para la administración de bases de datos MySQL/MariaDB. Nos permite gestionar las bases de datos a través de una interfaz gráfica en el navegador web. Tiene la ventaja de que no es necesario instalar ningún software adicional en el cliente, ya que solo necesitamos un navegador web. Es uno de los clientes GUI más populares e intuitivos para MySQL/MariaDB. No es necesario saber SQL para utilizarlo, aunque todo lo que hagamos en la interfaz gráfica se traducirá en consultas SQL que es lo único que entiende la base de datos.

PhpMyAdmin utiliza PHP, un lenguaje de programación backend, de ahi su nombre. Por lo tanto, para utilizar PhpMyAdmin, necesitamos tener un servidor web (como Apache o Nginx) con soporte para PHP instalado en el servidor donde se ejecuta PhpMyAdmin.

## SQL
SQL (Structured Query Language) es un lenguaje de programación utilizado para gestionar y manipular bases de datos relacionales. Permite realizar diversas operaciones en las bases de datos, como la creación, modificación y eliminación de tablas, así como la inserción, actualización, eliminación y consulta de datos. No es un lenguaje de proposito general, sino que está específicamente para una tarea concreta: la gestión de bases de datos relacionales.

En SQL podemos distinguir cuatro tipos de sentencias principales:
- **DDL (Data Definition Language)**: Sentencias que definen la estructura de la base de datos, como la creación, modificación y eliminación de tablas y otros objetos de la base de datos (por ejemplo, CREATE, ALTER, DROP).
- **DML (Data Manipulation Language)**: Sentencias que manipulan los datos dentro de las tablas, como la inserción, actualización, eliminación y consulta de datos (por ejemplo, SELECT, INSERT, UPDATE, DELETE).
- **DCL (Data Control Language)**: Sentencias que controlan el acceso a los datos y la gestión de permisos en la base de datos (por ejemplo, GRANT, REVOKE).
- **TCL (Transaction Control Language)**: Sentencias que gestionan las transacciones en la base de datos. Una transacción es una secuencia de operaciones que se ejecutan "en pack" y que deben cumplirse todas o ninguna.

Nos centraremos principalmente en las sentencias DDL y DML.

- Todas las sentencias SQL terminan con un punto y coma (;). El salto de línea no afecta a las sentencias SQL, por lo que podemos escribirlas en varias líneas para mejorar su legibilidad.
- SQL no distingue entre mayúsculas y minúsculas en las palabras reservadas. Pero es recomendable y habitual escribir las palabras reservadas en mayúsculas y los nombres de tablas y columnas en minúsculas para mejorar la legibilidad.
- Las consultas SQL se pueden escribir y ejecutar desde una interfaz gráfica (GUI) o desde una interfaz de línea de comandos (CLI).

### EXIT
La sentencia `EXIT` en SQL se utiliza para salir de la sesión actual del cliente de base de datos. Al ejecutar `EXIT;`, se cierra la conexión con el servidor de bases de datos y se termina la sesión.

### SHOW
La sentencia `SHOW` en SQL se utiliza para mostrar información sobre las bases de datos, tablas, columnas y otros objetos dentro de SGBD. Por ejemplo, podemos utilizar `SHOW DATABASES;` para listar todas las bases de datos disponibles en el servidor de bases de datos, o `SHOW TABLES;` para listar todas las tablas dentro de una base de datos específica.

### CREATE DATABASE 
La sentencia `CREATE DATABASE` en SQL se utiliza para crear una nueva base de datos en el servidor de bases de datos. La sintaxis básica es `CREATE DATABASE nombre_base_de_datos;`. Esto crea una base de datos vacía con el nombre especificado.

### DROP DATABASE
La sentencia `DROP DATABASE` en SQL se utiliza para eliminar una base de datos existente del servidor de bases de datos. La sintaxis básica es `DROP DATABASE nombre_base_de_datos;`.

### USE
La sentencia `USE` en SQL se utiliza para seleccionar una base de datos específica para trabajar con ella. Al ejecutar `USE nombre_base_de_datos;`, todas las operaciones posteriores se realizarán en la base de datos seleccionada hasta que se cambie a otra base de datos o se cierre la conexión.

### CREATETE TABLE
La sentencia `CREATE TABLE` en SQL se utiliza para crear una nueva tabla dentro de una base de datos. La sintaxis básica es:
```sql
CREATE TABLE nombre_tabla ( 
    columna1 tipo_dato [modificadores],
    columna2 tipo_dato [modificadores],
    ...
);
```

**Nota**: Que "modificadores" este entre corchetes significa que es opcional, no que se deben escribir los corchetes.

### Tipos de Dato
- `INT`: Entero.
- `VARCHAR(n)`: Cadena de caracteres de longitud variable, donde `n` es la longitud máxima.
- `CHAR(n)`: Cadena de caracteres de longitud fija, donde `n` es la longitud.
- `TEXT`: Cadena de caracteres de longitud variable, para textos largos.
- `DATE`: Fecha en formato AAAA-MM-DD.
- `DATETIME`: Fecha y hora en formato AAAA-MM-DD HH:MM:SS
- `FLOAT`: Número de punto flotante (decimal).
- `BOOLEAN`: Valor booleano (TRUE o FALSE).

### Modificadores 
- `NOT NULL`: La columna no puede contener valores nulos.
- `UNIQUE`: Los valores en la columna deben ser únicos.
- `PRIMARY KEY`: Define la columna como clave primaria de la tabla, lo que significa que los valores en esta columna deben ser únicos y no nulos.
- `AUTO_INCREMENT`: La columna se incrementa automáticamente con cada nuevo registro insertado. Solo se puede utilizar en columnas de tipo entero que sean claves primarias.
- `DEFAULT valor`: Establece un valor predeterminado para la columna si no se proporciona ningún valor al insertar un nuevo registro.
- `CHECK (condición)`: Establece una condición que los valores de la columna deben cumplir.
- `FOREIGN KEY (columna) REFERENCES tabla(columna)`: Define una clave foránea que establece una relación entre la columna de la tabla actual y una columna en otra tabla.
- `VIRTUAL`: Define una columna virtual cuyo valor se calcula a partir de otras columnas en la misma tabla.

### DROP TABLE
La sentencia `DROP TABLE` en SQL se utiliza para eliminar una tabla existente de una base de datos. La sintaxis básica es `DROP TABLE nombre_tabla;`. Esto elimina la tabla y todos los datos almacenados en ella de forma permanente.

### INSERT INTO
La sentencia `INSERT INTO` en SQL se utiliza para insertar nuevos registros (filas) en una tabla. La sintaxis básica es:
```sql
INSERT INTO nombre_tabla (columna1, columna2, ...)
VALUES (valor1, valor2, ...);
```

Se pueden insertar múltiples filas en una sola sentencia separando cada conjunto de valores con comas:
```sql
INSERT INTO nombre_tabla (columna1, columna2, ...)
VALUES (valor1a, valor2a, ...),
(valor1b, valor2b, ...),
...;
```

Normalmente los datos los introducen programas o aplicaciones que ejecutan consultas SQL de forma automática, no los introduce un usuario de forma manual.

### DELETE
La sentencia `DELETE` en SQL se utiliza para eliminar registros (filas) de una tabla. La sintaxis básica es:
```sql
DELETE FROM nombre_tabla
WHERE condicion;
```

### WHERE
La cláusula `WHERE` en SQL se utiliza para especificar una condición para filtrar los registros que se van a ser afectados por una sentencia SQL, como `SELECT`, `UPDATE` o `DELETE`. Solo los registros que cumplan la condición especificada serán afectados por la operación.

### UPDATE
La sentencia `UPDATE` en SQL se utiliza para modificar los datos existentes en una tabla. La sintaxis básica es:
```sql
UPDATE nombre_tabla
SET columna1 = valor1, columna2 = valor2, ...
WHERE condicion;
```

### SELECT
La sentencia `SELECT` en SQL se utiliza para consultar y recuperar datos de una o más tablas en una base de datos. La sintaxis básica es:
```sql
SELECT columna1, columna2, ...
FROM nombre_tabla
WHERE condicion;
```
El asterisco (*) es un comodín en SQL, que se utiliza en la sentencia `SELECT` para indicar que se desean seleccionar todas las columnas de una tabla.

### ALTER TABLE
La sentencia `ALTER TABLE` en SQL se utiliza para modificar la estructura de una tabla existente en una base de datos. Permite agregar, eliminar o modificar columnas, así como cambiar otros aspectos de la tabla. La sintaxis básica es:
```sql
ALTER TABLE nombre_tabla
ADD columna tipo_dato [modificadores];
```
o
```sql
ALTER TABLE nombre_tabla
DROP COLUMN columna;
```
o
```sql
ALTER TABLE nombre_tabla
MODIFY COLUMN columna tipo_dato [modificadores];
```
o
```sql
ALTER TABLE nombre_tabla
RENAME TO nuevo_nombre_tabla;
```

### ORDER BY
La cláusula `ORDER BY` en SQL se utiliza para ordenar los resultados de una consulta en un orden específico, ya sea ascendente (ASC) o descendente (DESC). La sintaxis básica es:
```sql
SELECT columna1, columna2, ...
FROM nombre_tabla
ORDER BY columna1 [ASC|DESC], columna2 [ASC|DESC], ...;
```
Nota: El orden ascendente (ASC) es el valor predeterminado si no se especifica ningún orden. En el caso de caracteres, el ordenamiento se realiza según el valor ASCII de los caracteres, que son ascendentes y ademas las mayúsculas se ordenan antes que las minúsculas y los números antes que las letras.

### LIMIT
La cláusula `LIMIT` en SQL se utiliza para restringir el número de registros devueltos por una consulta. La sintaxis básica es:
```sql
SELECT columna1, columna2, ...
FROM nombre_tabla
LIMIT numero_registros;
```

Nota: coge los primeros `numero_registros` registros del conjunto de resultados, por lo que se ve afectado por el ordenamiento si se utiliza `ORDER BY`.

### DISTINCT
La palabra clave `DISTINCT` en SQL se utiliza en la sentencia `SELECT` para eliminar los registros duplicados en el conjunto de resultados. Cuando se utiliza `DISTINCT`, solo se devuelven los registros únicos, es decir, aquellos que no tienen duplicados en las columnas seleccionadas. La sintaxis básica es:
```sql
SELECT DISTINCT columna1, columna2, ...
FROM nombre_tabla;
```

### AND, OR, NOT
La cláusula `AND`, `OR` y `NOT` en SQL se utilizan para combinar múltiples condiciones en una sentencia SQL, como `SELECT`, `UPDATE` o `DELETE`. Permiten crear condiciones más complejas para filtrar los registros que se van a ver afectados por la operación.

```sql
SELECT columna1, columna2, ...
FROM nombre_tabla
WHERE condicion1 AND condicion2 OR NOT condicion3;
```

### AS
La palabra clave `AS` en SQL se utiliza para asignar un alias a una columna o tabla en una consulta. Un alias es un nombre temporal que se utiliza para referirse a una columna o tabla de manera más conveniente o legible en el conjunto de resultados. La sintaxis básica es:
```sql
SELECT columna1 AS alias_columna1, columna2 AS alias_columna2, ...
FROM nombre_tabla AS alias_tabla;
```

### JOIN

### COUNT

### GROUP BY y HAVING


## Otros Componentes de una Base de Datos
A parte de las tablas, una base de datos relacional, dependiendo del SGBD utilizado, puede tener otros componentes algunos de los mas comunes e importantes son:

- **Vistas (Views)**: Son tablas virtuales que se crean a partir de consultas SQL. No almacenan datos físicamente, sino que muestran datos de una o más tablas según una consulta predefinida.
- **Índices (Indexes)**: Son estructuras de datos que mejoran la velocidad de las operaciones de consulta en una tabla. Funcionan como índices en un libro, permitiendo un acceso rápido a los datos.
- **Usuarios y Roles**: Son cuentas que tienen permisos específicos para acceder y manipular la base de datos. Los roles son conjuntos de permisos que se pueden asignar a múltiples usuarios. Además, los SGBDs suelen tener mecanismos de autenticación y autorización para controlar el acceso a la base de datos.
- **Procedimientos Almacenados (Stored Procedures)**: Son bloques de código SQL (como funciones) que se almacenan en la base de datos y se pueden ejecutar como una función.
- **Triggers (Disparadores)**: Son procedimientos que se ejecutan automáticamente en respuesta a ciertos eventos en la base de datos, como la inserción, actualización o eliminación de registros en una tabla.
- **Transacciones**: Son conjuntos de operaciones SQL que se ejecutan como una unidad atómica. Las transacciones garantizan que todas las operaciones dentro de la transacción se completen correctamente o ninguna se aplique, evitando así la corrupción de datos.

## Parte Práctica
Utilizaremos dos máquinas virtuales (VMs) para esta práctica:
- **servidorBBDD**: Servidor de base de datos MariaDB.
- **clienteBBDD**: Cliente que accederá a la base de datos en el servidor.

La máquina **servidorBBDD** tendrá los siguientes adaptadores de red:
- **Adaptador 1**: NAT (para acceso a Internet).
- **Adaptador 2**: Red Interna (para comunicación con la máquina cliente).
- **Adaptador 3**: Adaptador Solo Anfitrión (para comunicación con la máquina host).

La máquina **clienteBBDD** tendrá los siguientes adaptadores de red:
- **Adaptador 1**: NAT (para acceso a Internet).
- **Adaptador 2**: Red Interna (para comunicación con la máquina servidor).

Ambas máquinas las podemos clonar de la máquina base de Debian que hemos estado utilizando en prácticas anteriores.

### Configuración de las Interfaces de Red
Debian puede dar problemas al configurar múltiples interfaces de red con su herramienta de configuración automática de red (Network Manager). Por lo que sera necesario configurar manualmente las interfaces de los adaptadores de red de ambas máquinas. En los adaptadores de NAT y Adaptador Solo Anfitrión, el propio VirtualBox actua como router desplegando un servidor DHCP, por lo que no es necesario configurar esas interfaces manualmente, solo decirles que obtengan la configuración automáticamente por DHCP. La interfaz de Red Interna si que la debemos configurar manualmente en ambas máquinas.

Podemos ver el nombre y estado de las interfaces de red de la máquina utilizando `ip a`.

En la máquina **servidorBBDD**, la configuración de las interfaces de red sera la siguiente:

- **Adaptador 1 (NAT)**: Configurado para obtener IP automáticamente por DHCP
```
auto <nombre_interfaz_nat>
iface <nombre_interfaz_nat> inet dhcp
```

- **Adaptador 2 (Red Interna)**: Configurado con IP estática
```
auto <nombre_interfaz_red_interna>
iface <nombre_interfaz_red_interna> inet static
address 192.168.1.1
netmask 255.255.255.0
```

- **Adaptador 3 (Adaptador Solo Anfitrión)**: Configurado para obtener IP automáticamente por DHCP
```
auto <nombre_interfaz_solo_anfitrion>
iface <nombre_interfaz_solo_anfitrion> inet dhcp
```

En la máquina **clienteBBDD**, la configuración de las interfaces de red sera la siguiente:

- **Adaptador 1 (NAT)**: Configurado para obtener IP automáticamente por DHCP
```
auto <nombre_interfaz_nat>
iface <nombre_interfaz_nat> inet dhcp
```
- **Adaptador 2 (Red Interna)**: Configurado con IP estática**
```
auto <nombre_interfaz_red_interna>
iface <nombre_interfaz_red_interna> inet static
address 192.168.1.2
netmask 255.255.255.0
```

Después de configurar las interfaces de red, reiniciamos el servicio de red o reiniciamos las máquinas para aplicar los cambios.

Comprobad que ambas máquinas pueden comunicarse entre si haciendo ping a las IPs de la Red Interna, que tienen acceso a Internet haciendo ping a una IP externa (por ejemplo 8.8.8.8) y que la máquina **servidorBBDD** puede comunicarse con la máquina host haciendo ping a la IP del Adaptador Solo Anfitrión de la máquina host.

### Configuración común de ambas máquinas
Previamente deberiamos de tener en ambas máquinas un usuario con nuestro nombre y con privilegios de sudo (que este en el grupo sudo). Este sera el usuario con el que trabajaremos en ambas máquinas.

- Actualizar los repositorios e instalar las actualizaciones disponibles:
  ```bash
  sudo apt update && sudo apt upgrade
  ```

- Cambiar el nombre de la máquina:
  ```bash
  sudo nano /etc/hostname
  ```

- Cambiar el archivo de hosts, cambiando la línea que contiene el nombre antiguo de la máquina por el nuevo nombre:
  ```bash
  sudo nano /etc/hosts
  ```

- Reiniciar la máquina para aplicar los cambios:
  ```bash
  sudo reboot
  ```
- Asegurarse de que las máquinas no tienen firewall el firewall activo:
  ```bash
  sudo ufw status
  ```
  Si el firewall esta activo, desactivarlo con:
  ```bash
  sudo ufw disable
  ```
  Si no esta instalado o esta desactivado, no es necesario hacer nada.

### Configuración de la Máquina clienteBBDD
En la máquina **clienteBBDD**, solo sera necesario instalar el cliente CLI de MariaDB para poder conectarnos a la base de datos en la máquina servidorBBDD.

- Instalar el cliente CLI de MariaDB:
  ```bash
  sudo apt install mariadb-client
  ```

### Configuración de la Máquina servidorBBDD
En la máquina **servidorBBDD**, primero nos vamos a asegurar que Apache2 no esta instalado y no hay archivos de configuración de Apache2 que nos puedan dar problemas luego.

- Desinstalar Apache2 y sus archivos de configuración si esta instalado:
  ```bash
  sudo apt purge apache2
  ```

- Eliminar el directorio /var/www y sus contenidos si existe:
  ```bash
  sudo rm -r /var/www
  ```

#### Instalación de MariaDB
- Instalar el servidor de base de datos MariaDB:
  ```bash
  sudo apt install mariadb-server
  ```

- Después de la instalación, el servicio de MariaDB debería iniciarse automáticamente. Podemos verificar su estado con:
  ```bash
  sudo systemctl status mariadb
  ```

- Tambien deberemos configurar MariaDB para que sea accesible desde otras máquinas. Para ello, editamos el archivo de configuración principal de MariaDB:
  ```bash
  sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
  ```

  Buscamos la línea que contiene `bind-address` y la cambiamos de `127.0.0.1` a `0.0.0.0` para que MariaDB escuche en todas las interfaces de red.

- Reiniciamos el servicio de MariaDB para aplicar los cambios:
  ```bash
  sudo systemctl restart mariadb
  ```

#### Instalación de Apache2 y modulos PHP
Ahora instalaremos Apache2, PHP y los módulos necesarios para que PhpMyAdmin funcione correctamente.

- Instalar Apache2:
  ```bash
  sudo apt install apache2
  ```

- Instalar PHP y los módulos necesarios:
  ```bash
  sudo apt install php8.4 php8.4-fpm php8.4-mysql php8.4-mbstring php8.4-zip php8.4-gd php8.4-curl php8.4-xml
  ```

- Habilitar los módulos proxy_fcgi y setenvif en Apache2:
  ```bash
  sudo a2enmod proxy_fcgi setenvif
  ```

- Habilitar el manejador de PHP en Apache2:
  ```bash
  sudo a2enconf php8.4-fpm
  ```

- Reiniciar Apache2 para aplicar los cambios:
  ```bash
  sudo systemctl restart apache2
  ```
Apache2 y PHP ya deberían estar funcionando correctamente. Podemos comprobarlo accediendo a la URL `http://<IP_servidorBBDD>/` desde un navegador web, donde `<IP_servidorBBDD>` es la dirección IP de la máquina servidorBBDD en la red desde la que estemos accediendo (Red Interna o Adaptador Solo Anfitrión). Deberíamos ver la página de bienvenida por defecto de Apache2.
  
#### Instalación de PhpMyAdmin
Ahora instalaremos PhpMyAdmin para gestionar la base de datos MariaDB a través de una interfaz gráfica web. Apache funciona como servidor web para PhpMyAdmin, el cual recibe las peticiones HTTP del navegador y las procesa utilizando PHP. Después, PHP se comunica con MariaDB para realizar las operaciones solicitadas y devuelve los resultados al navegador a través de Apache.

- Instalar PhpMyAdmin:
  ```bash
  sudo apt install phpmyadmin
  ```

- Durante la instalación, se nos pedirá que seleccionemos el servidor web que queremos configurar automáticamente. Seleccionamos Apache2 utilizando la barra espaciadora y luego presionamos Enter.
- También se nos preguntará si queremos configurar la base de datos para PhpMyAdmin con dbconfig-common. Seleccionamos "Sí" y proporcionamos una contraseña para el usuario de configuración de PhpMyAdmin en la base de datos, le podemos poner simplemente "phpmyadmin" para esta práctica.
- Después de la instalación, debemos asegurarnos de que el archivo de configuración de PhpMyAdmin esta enlazado en el directorio de configuración de Apache2.
  ```bash
  sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
  ```
- Despúes reiniciamos Apache2 para aplicar los cambios:
  ```bash
  sudo systemctl restart apache2
  ```
PhpoMyAdmin ya debería estar accesible desde un navegador web en la siguiente URL: `http://<IP_servidorBBDD>/phpmyadmin`, donde `<IP_servidorBBDD>` es la dirección IP de la máquina servidorBBDD en la red desde la que estemos accediendo (Red Interna o Adaptador Solo Anfitrión).

### Creación del Usuario de la Base de Datos
Para acceder a la base de datos MariaDB desde PhpMyAdmin y desde el cliente CLI en la máquina clienteBBDD, crearemos un usuario con nuestro nombre y contraseña. Despues le daremos permisos para que pueda gestionar bases de datos y tablas.

- Acceder al cliente CLI de MariaDB como usuario root:
  ```bash
  sudo mariadb
  ```

- Crear el usuario de la base de datos (cambiando `tu_usuario` y `tu_contraseña` por tu nombre de usuario y la contraseña que quieras):
  ```sql
  CREATE USER 'tu_usuario'@'%' IDENTIFIED BY 'tu_contraseña';
  ```
- Conceder todos los privilegios al usuario para que pueda gestionar bases de datos y tablas:
  ```sql
  GRANT ALL PRIVILEGES ON *.* TO 'tu_usuario'@'%';
  ```
- Aplicar los cambios de privilegios:
  ```sql
  FLUSH PRIVILEGES;
  ```
- Salir del cliente CLI de MariaDB:
```sql
  EXIT;
```

### Creación de la Base de Datos y Tablas
Para esta práctica, debereis crear una base de datos llamada `Biblioteca` con 4 tablas: `usuarios`, `libros`, `prestamos` y `autores`.

- `usuarios`: Tabla para almacenar información sobre los usuarios de la biblioteca.
  - ID de usuario como clave primaria con auto-incremento.
  - Nombre del usuario (cadena de caracteres).
  - Email del usuario (cadena de caracteres única).
  - Fecha de registro (fecha).
- `libros`: Tabla para almacenar información sobre los libros disponibles en la biblioteca.
  - ID de libro como clave primaria con auto-incremento.
  - Título del libro (cadena de caracteres).
  - Autor del libro (cadena de caracteres).
  - Año de publicación (entero).
  - Género del libro (cadena de caracteres).
- `prestamos`: Tabla para registrar los préstamos de libros a los usuarios(Relación entre usuarios y libros M:N).
  - ID de préstamo como clave primaria con auto-incremento.
  - ID de usuario (entero, clave foránea que referencia a la tabla `usuarios`).
  - ID de libro (entero, clave foránea que referencia a la tabla `libros`).
  - Fecha de préstamo (fecha).
  - Fecha de devolución (fecha).
- `autores`: Tabla para almacenar información sobre los autores de los libros.
  - ID de autor como clave primaria con auto-incremento.
  - Nombre del autor (cadena de caracteres).
  - Fecha de nacimiento (fecha).

Podeis utilizar PhpMyAdmin o el cliente CLI de MariaDB para crear la base de datos y las tablas. Os recomiendo utilizar ambas herramientas para practicar.

### Rellenar las Tablas
Una vez creadas las tablas, debereis insertar al menos 5 registros en cada tabla. Podeis utilizar PhpMyAdmin o el cliente CLI de MariaDB para insertar los registros.


### Consultas
Una vez creadas y rellenadas las tablas, debereis realizar las siguientes consultas SQL:

- Mostrar la estructura de la tabla `usuarios`.
- Listar todos los libros disponibles en la biblioteca. (mostrar título y autor)
- Listar todos los usuarios registrados en la biblioteca. (mostrar nombre y email)
- Listar todos los autores y sus fechas de nacimiento.
- Contar el número total de libros en la biblioteca.
- Listar los libros publicados después del año 2000.
- Mostrar todos los préstamos realizados, incluyendo el nombre del usuario y el título del libro prestado.

### Entrega
Para le entrega me tendreis que enviar un documento PDF con las siguientes capturas de pantalla:
- Captura de pantalla abriendo el cliente CLI de MariaDB en la máquina servidorBBDD.
- Captura de pantalla abriendo PhpMyAdmin en el navegador web de la máquina host.
- Captura de pantalla de PhpMyAdmin mostrando la base de datos `Biblioteca` y sus tablas.
- Captura de pantalla de las consultas de lectura SQL realizadas en el apartado anterior + Captura de pantalla de los resultados obtenidos.
