---
name: Configuración de enrrutamiento
sort: 2
---

# Configuración de enrrutamiento del proyecto

Entonces, hemos creado y corrido un proyecto en la sección previa. ¿Pero cómo hace el trabajo? Investiguemos desde el archivo de inicio(main.go).

	package main
	
	import (
	        _ "quickstart/routers"
	        "github.com/astaxie/beego"
	)
	
	func main() {
	        beego.Run()
	}
	
Podemos ver dos líneas muy simples. La primera registra la ruta al llamar a `beego.Router` y la
segunda es `beego.Run`. ¿Qué hicieron estas dos líneas?

1. En realidad, beego.Router registró una dirección. El primer argumento es la uri consultada
que en este caso es `/` lo que significa que la consulta no tiene uri. El segundo argumento es
el Controlador que manipulará la consulta para esta uri. También podemos registrar la ruta así:

		beego.Router("/usuario", &controllers.UserController{})	

Entonces el usuario puede visitar /usuario para procesar la lógica en UserController. Este es
nuestro enrrutamiento simple. Para más información en el uso de enrrutamiento, mira
[configuración de enrrutamiento de beego](../mvc/controller/router.md).
	
2. Después de la ejecución de `beego.Run`, Solo hemos visto que solo está escuchando el puerto.
En realidad ha hecho mucho más que eso.

  - Interpretanto el archivo de configuración
	
    Beego interpretará el archivo de configuración `app.conf` en el folder conf. Ahí podemos cambiar el puerto, habilitar la sesión y cambiar el nombre de la aplicación modificando los parámetros en el archivo de configuración.

	- Habilitanto la sesión
    Beego habilitará o deshabilitará la sesión por configuración en el archivo de configuración.

	- Compilando las vistas 
    Beego compilará las vistas en la carpeta views cuando esté iniciando para evitar compilarlo muchas veces; lo que es, definitivamente, más eficiente.
	
  - Iniciando el módulo de supervisión
    Beego tiene muchos módulos geniales que son llamados módulos supervisores. Podemos ver los QPS, cpu, memoria, GC, gorutine, información de hilos visitando el puerto 8088.

  - Escuchando en el puerto de servicio.
    En este último paso se le indica a beego que escuche las consultas http en el puerto 8080 . En realida, se aprovecha los gorutines haciendo llamandos a `ListenAndServe`.
	
  - Depués que todo esté corriendo, nuestro servidor hará el servicio de consulta de entrada desde el puerto 8080 y supervisando desde el puerto 8088.
	
Hemos visto el proceso entero de correr el proyecto beego y algunas otras funciones. Empecemos a ver como funciona el controlador (Controller).
