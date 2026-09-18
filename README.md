# Manual de instalación de la app web
## desiciones de proyecto 


|Elemento|Decisión|Versión|Justificación|
|-|-|-|-|
|Servidor Web|Apache|2|Sencillo de usar|
|Base de Datos|MySQL|8 |Experiencia previa, popular|
|Lenguaje de servidor|Python|3|Uso extendido|
|FrameWork|Flask|3|sencillo de usar, pensado para Web|
|Control de versiones|Git|2|muy extendido|
|Documentación|Markdown|-|muy extendido|

## Que hace un servidor web?

Recibe peticiones HTTP y devuelve recursos al navegador

## crear repositorio en git

1. `git init`

2. `git add . `

3. `git commit -m "commit inicial con readme y página principal con formulario web"`

4. iniciar sesion para usar el copilot de VS


## Proceso de instalación  / Puesta en marcha

1. Actualizar el sistema

`sudo apt update`
`sudo apt upgrade `

2. instalar git

`sudo apt install git`


3. instalar VScode + plugins

    - Markdown all in one

4.  Instalar Apache2

`sudo apt install apache2`

5. cambiar permisos a carpeta  /var/www/html 

``` bash 
sudo chown -R $USER:$USER /var/www/html

sudo chmod -R u=rwX,go=rX /var/www/html 
```
6. crear el html de la página de incidencias

## instalar el mysql server

``` bash 
sudo apt install mysql-server
```


## creación de bases de datos
``` bash 
sudo apt install mysql-server
```
## configuración SQL
``` bash 
sudo mysql
```
``` bash 

create database incidencias;
create user "incidencias"@"localhost" identified by "incidencias";
grant all privileges on incidencias.* to "incidencias"@"localhost";
flush privileges;
```
## crear tablas 

``` bash 

use incidencias

create table registro( id int auto_increment primary key, 
aula varchar(30), 
descripcion text, 
usuario varchar (20), 
estado varchar (20) );

```

