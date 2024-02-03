# contruct-New-Laravel-App
Dependencias:
 - [PHP](https://www.php.net/downloads.php)
 - [Composer](https://getcomposer.org/)
 - [Mariadb]()

Cada una puede ser instalada a través de los manejadores de paquetes.
Una vez instaladas de dependencias, faltan realizar una configuraciones,
antes de poder iniciar con el desarrollo de una aplicación en Laravel.

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
