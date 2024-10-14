# Construct-New-Laravel-App

Dependencias:
 - [PHP](https://www.php.net/downloads.php)
 - [Composer](https://getcomposer.org/)
 - [Mariadb]()

Programas a emplear:
 - [Terminal]()
 - [Visual Studio Code](https://code.visualstudio.com/)
 - [Neovim](https://github.com/neovim/neovim/blob/master/INSTALL.md)

Cada una puede ser instalada a través de los manejadores de paquetes.
Una vez instaladas las dependencias, faltan realizar una configuraciones,
antes de poder iniciar con el desarrollo de una aplicación en Laravel.

## PHP

Se debe retocar el archivo php.ini, para las distribuciones basadas en archlinux,
se encuentra en la siguiente ruta ```/etc/php/php.ini```, dentro de dicho archivo
hay que realizar la busqueda de las extensiones, con cualquier editor de código de
terminal: neovim, vim, nano, entre otros. dentro de las extensiones se deben habilitar,
las pertinentes a las bases de datos, si deseas emplear posgrest, te interesa habilitar
la extension.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/77cad4a1-2214-42a2-b285-6aa497c6f91e)

Estas son mis extensiones:

```
extension=bcmath
extension=bz2
extension=calendar
extension=curl
extension=dba
;extension=enchant
extension=exif
extension=ffi
extension=ftp
extension=gd
extension=gettext
extension=gmp
extension=iconv
extension=intl
extension=ldap
;extension=mysqli
;extension=odbc
zend_extension=opcache
;extension=pdo_dblib
extension=pdo_mysql
;extension=pdo_odbc
extension=pdo_pgsql
;extension=pdo_sqlite
extension=pgsql
;extension=pspell
extension=shmop
;extension=snmp
extension=soap
extension=sockets
;extension=sodium
;extension=sqlite3
extension=sysvmsg
extension=sysvsem
extension=sysvshm
;extension=tidy
;extension=xsl
extension=zip
```
Procede con la activación, descomenta las lineas que sean de intereses.

NOTA: cada extensión que habilites, se debe complementar con la descarga de un paquete correspondiente, Ejemplo: ```pdo_pgsql```, debes descargar e instalar el paquete ```php-pgsql```.

Con esto PHP, se encuentra operativo.

## Mariadb

Para sistemas basados en archlinux, adjunto este [Link](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04), luego de realizar la instalarción correspondiente, hace falta un comando para poder emplear mariadb, ```sudo mariadb-secure-installation```, se encuentra en el link adjunto, con esta utilidad se maneja el primer inicio del servicio Mariadb, se puede cambiar la contraseña del usuario root. En el link adjunto hay una Salida por pantalla de ejemplo, para la configuración de Mariadb. 

Nota: se deben guardar las credenciales cambiadas en este paso.

## Visual Studio Code

Como requisito para el manejo rapido de la base de datos, se emplea una extensión de visual studio code, que permite la conexión a la base de datos.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/f3b75651-2a55-4714-9ae7-48472dcf3ba5)

Se debe instalar la versión ```v4.5.12```, las versiones posteriores son de pago. En el boton de Uninstall, que aparece
En la imagen, se desplega otra opción, "Instalar otra versión", en donde se puede instalar una versión particular.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/1ce43739-8f57-4b3f-a906-345c63b63c31)

Para la conexión basta con hacer click en el boton (+), y rellenar los campos pertinentes.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/9136b4a7-5926-4051-9338-f57c993e55f3)

Si, no se modificó la contraseña del usuario root, esta por default esta vacia, para mysql, que es el gestor de base de datos tomado como ejemplo. Observese que debajo del nombre de conexión se disponene los distintos gestores.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/db0672f5-047a-4124-8f84-cc1ac5e623c7)

Una vez aqui, ya se pueden crear tablas, crear nuevas bases de datos y más.

## Para laravel

Una vez concluidos los puntos anteriores, se procede a descomprimir o crear una nueva aplicación Laravel. 

### Si se descomprime el archivo

Se procede a buscar, en la raiz del proyecto, el archivo llamado ```.env```, para posterior mente modificar las variables de entorno, que tienen que ver con la base de datos.

![image](https://github.com/ceftx/contruct-New-Laravel-App/assets/65095491/d250b3fd-aec5-46ae-b9b3-ed591ac622af)

Disponga en la variable 'DB_DATABASE', el nombre de la base de datos que creo en el paso anterior.

Luego se procede a correr en la terminal, dentro de la raiz del directorio de trabajo, el comando 
```php artisan migrate```, para crear las tablas de la base de datos, a través de las migraciones.

Por ultimo, basta con ejecutar ```php artisan serve```, para servir de manera local la aplicación, a través del puerto 8000, en la ruta de localhost (127.0.0.1:8000).
