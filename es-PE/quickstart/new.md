---
name: Creando un nuevo proyecto
sort: 1
---

# Creando un proyecto

Muchos de los proyecto beego son creados con el comando bee. Antes de empezar cualquier cosa, por favor asegúrate de tener instalado la herramienta `bee` y el paquete `beego`. Si no lo tienes aún, por favor lee [Instalando beego](../install) y [Instalando la herramienta bee](../install/bee.md) antes de proceder.

Cuando estés listo, comienza. Abre la terminal y ve a tu carpeta `GOPATH` y tipea `bee new quickstart`:

	➜  src  bee new quickstart
	[INFO] Creating application...
	/gopath/src/quickstart/
	/gopath/src/quickstart/conf/
	/gopath/src/quickstart/controllers/
	/gopath/src/quickstart/models/
	/gopath/src/quickstart/static/
	/gopath/src/quickstart/static/js/
	/gopath/src/quickstart/static/css/
	/gopath/src/quickstart/static/img/
	/gopath/src/quickstart/views/
	/gopath/src/quickstart/conf/app.conf
	/gopath/src/quickstart/controllers/default.go
	/gopath/src/quickstart/views/index.tpl
	/gopath/src/quickstart/main.go
	13-11-26 10:34:10 [SUCC] New application successfully created!
	
La herramienta bee crea un nuevo proyecto beego para ti. Aquí está la estructura:

	quickstart
	├── conf
	│   └── app.conf
	├── controllers
	│   └── default.go
	├── main.go
	├── models
	├── static
	│   ├── css
	│   ├── img
	│   └── js
	└── views
	    └── index.tpl	

Podemos decir que es una típica aplicaión MVC. `main.go` es el archivo iniciador de proyecto.

## Corriendo el proyecto

Después de crear el proyecto, podemos correr nuestro proyecto. Ve a la ruta de tu proyecto recién creado y ejecuta `bee run` para correr el proyecto. Adicionalmente compilará el proyecto.

	➜  src  cd quickstart
	➜  quickstart  bee run
	13-11-26 10:43:14 [INFO] Uses 'quickstart' as 'appname'
	13-11-26 10:43:14 [INFO] Initializing watcher...
	13-11-26 10:43:14 [TRAC] Directory(/gopath/src/quickstart/controllers)
	13-11-26 10:43:14 [TRAC] Directory(/gopath/src/quickstart/models)
	13-11-26 10:43:14 [TRAC] Directory(/gopath/src/quickstart)
	13-11-26 10:43:14 [INFO] Start building...

Tenemos una aplicación web corriendo en el puerto `8080` (el puerto por defecto de Beego). Es facinante, ¿cierto? ¿Porqué lo podemos hacer sin nginx o apache?. Sí, estás en lo cierto. Go tiene ya implementado todas las funciones que necesitamos para la capa de red y beego las encapsula por lo que no necesitamos ni a nginx ni a apache aquí. Veamos la aplicación en el navegador ahora:

![](../images/beerun.png)

¿Estás emocionado? ¿No es suficientemente fácil crear una aplicación web? Sumerjámonos más dentro del proyecto y veamos como se hace todo el trabajo.
