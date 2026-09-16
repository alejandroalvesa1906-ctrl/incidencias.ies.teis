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




## creación de bases de datos