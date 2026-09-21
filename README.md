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

## instalar pythom

`sudo aot update`
`sudo apt install python3 python3-pip python3-venv -y`

## crear el entorno virtual

`python3 -m venv venv`
`source /var/www/incidencias.ies.teis/venv/bin/activate`

## instalar flask , conector base de datos, comprobar y guardar dependecias

``` bash

pip install flask
pip install mysql-conector-python
pip list 
pip freeze > requirements.txt

```

## usar flask cada inicio

Ddesde la terminal dentro del directorio incidencias

 `source venv/bin/activate`
 `python app.py` iniciar app

 ctrol + C para terminar app 
 deactivate para salir del entorno

 ## Hacer aplicación Python/Flask

 1. crear archivo app.py 
   
``` python
 from flask import Flask

app = Flask(__name__)

@app.route('/')
def inicio():
    return render_template('index.html')
    if __name__ == '__main__':
    app.run(debug=True)
```
2. probamos la app
   
`python3 app.py`

3. para entrar a la web `http://incidencias.ies.teis:5000/`
4. pasar formulario a python flask
5. cambiar la app 
   
``` python 
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def inicio():
    return render_template('index.html')
@app.route('/incidencia', methods=['POST'])
def crear_incidencia():

     aula = request.form['aula']
     usuario = request.form['usuario']
     descripcion = request.form['descripcion']

     print("aula:" + aula)
     print("usuario:" + usuario)
     print("descripcion:" + descripcion)

     return "Incidencia recibida"
if __name__ == '__main__':
    app.run(debug=True)
    ```
