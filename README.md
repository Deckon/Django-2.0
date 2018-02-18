# DJANGO 2.0

![Logo Django](imagenes/django.png)

* [Introducción](#introducción)
* [Requerimientos previos](#requerimientos-previos)
* [Pipenv](#pipenv)
    * [Instalación de Pipenv](#instalación-de-pipenv)
    * [Uso de Pipenv](#uso-de-pipenv)
* [Creación de un proyecto con Django](#creación-de-un-proyecto-con-django)
* [Hello World!](#hello-world)

## Introducción
Esta es una pequeña guia para la creación de proyectos con la ultima version de Django 2.0.X y las herramientos recomendadas para su gestion. Esta guia toma como referencia la excelente documentación creada por el profesor **[Will Vincent](https://wsvincent.com/)** en su pagina [https://djangoforbeginners.com/](https://djangoforbeginners.com/)


## Requerimientos previos
Para poder ejecutar **Django** en nuestro equipo es necesario tener instaladas unas cuantas utilerias y paquetes.

* **Python 3:** La ultima version del lenguaje de programacion sobre el cual trabaja Django 2.0.X.
* **Pip:** Gestor de paquetes Python.

## Pipenv
Anteriormente al desarrollar con **Python** era necesario usar las dos principales herramientas de este lenguaje: **Pip** como gestor de paquetes y **virtualenv*** como gestor de entornos virtuales, estas eran las herramientas recomendadas por **Python**. Actualemente estas dos herramientas han sido desplasadas por **Pipenv** el cual combina las funcionalidades de ambas.

Por un lado **Pipenv** crea un entorno virtual donde instala,desinstala y actualiza paquetes de manera aislada del sistema u otros entornos virtuales, ademas de crear un par de archivos los cuales gestionan las dependencias de nuestra aplicación permitiendonos transladar estos archivos a otro entorno y reinstalar las dependencias adecuadas para el funcionamiento de la aplicación. 

### Instalación de Pipenv
La forma mas sencilla de instalar **Pipenv** es mediane **Pip**

Comprobar que **Pip** esta instalado:
~~~sh
$ pip3 --version
pip 9.0.1 from /usr/lib/python3/dist-packages (python 3.6)
~~~

En caso de no estar instalado es necesario instalarlo
~~~sh
$ sudo apt install python3-pip
~~~

***Nota:*** *Esta instalacion se realiza en un sistema Linux con base Deb*

Instalacion de **Pipenv**
~~~sh
$ sudo -H pip3 install -U pipenv
~~~

Comprobar que **Pipenv** se instalo correctamente
~~~sh
$ pipenv --version
pipenv, version 9.0.3
~~~

### Uso de Pipenv
Instalación de una biblioteca y creación de su entorno vitual usando **Python 3**
~~~sh
# Creación de la carpeta donde se alojara el entorno y los documentos de dependencias
$ mkdir Entorno

# Creacion del venv e instalación de la biblioteca
$ pipenv --three install django
~~~
Esto crea un archivo **Pipfile** y **Pipfile.lock** los cuales gestionan las dependencias del entorno virtual. 
Los entornos virtuales se alojan en **/home/usuario/.local/share/virtualenvs** el cau lta,mbien genera un enlace sinbolico en **/home/usuario/.virtualenv**.

---

Activación del entorno virtual
~~~sh
$ pipenv shell
(django-JmZ1NTQw) $
~~~

---

Actualizar paquetes del entorno virtual
~~~sh
(django-JmZ1NTQw) $ pipenv --update
~~~

---

Ver las dependencias del entorno virtual
~~~sh
(django-JmZ1NTQw) $ pipenv graph
~~~

---

Salir del entorno virtual
~~~sh
(django-JmZ1NTQw) $ exit
$
~~~

---

Desinstalar un entorno virtual
~~~sh
$ pipenv --rm
~~~

---

Instalar las dependencias de un entorno virtual a partir de los archivos **Pipfile** y **Pipfile.lock**
~~~sh
$ pipenv install
~~~

## Creación de un proyecto con Django

~~~sh
# Creación de la carpeta donde se va a alojar el proyecto
$ mkdir Carpeta

# Cambiar al directorio del proyecto
$ cd Carpeta

# Creacion del entorno e instalación de Django con Python3
$ pipenv --three install django

# Activacion del entorno
$ pipenv shell

(django-JmZ1NTQw) $
~~~

Crear el proyecto con **Django**
~~~sh
(django-JmZ1NTQw) $ django-admin.py startproject nuevo
~~~

Ejecutar el servidor de **Django** para comprobar que todo se instala y funciona correctamente
~~~sh
# Moverse dentro de la carpeta del proyecto
(django-JmZ1NTQw) $ cd nuevo

# Ejecutar el servidor
(django-JmZ1NTQw) $ ./manage.py runserver
Performing system checks...

System check identified no issues (0 silenced).

You have 14 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.

February 18, 2018 - 01:38:44
Django version 2.0.2, using settings 'nuevo.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
~~~

Al ingresar la direccion **http://127.0.0.1:8000/** se deberia visualizar algo como lo siguiente

![Localhost](imagenes/localhost.png)

Para finalizar el servidor se precionan las teclas <kbd>Ctrl</kbd> + <kbd>C</kbd> y para salir del entorno
~~~sh
(django-JmZ1NTQw) $ exit
$
~~~

## Hello World!
