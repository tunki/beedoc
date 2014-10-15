---
name: Controller
sort: 3
---

# Lógica de control

Hemos aprendido a como distribuir los procesos de los usuarios para controlar en la sección
anterior. En esta sección aprenderemos como escribir un controlador. Empecemos con algo de
código:

```
package controllers

import (
        "github.com/astaxie/beego"
)

type MainController struct {
        beego.Controller
}

func (this *MainController) Get() {
        this.Data["Website"] = "beego.me"
        this.Data["Email"] = "astaxie@gmail.com"
        this.TplNames = "index.tpl"
}
```

Al inicio creamos el `MainController` y contiene un campo anónimo en la estructura del tipo
`beego.Controller`. Esta es llamada estructura embebida y es la manera de como Go imita la
herencia. Esto significa que `MainController` automáticamente adquiere todos los métodos de
`beego.Controller`.

`beego.Controller` tiene muchos métodos tales como `Init`, `Prepare`, `Post`, `Get`, `Delete`
y `Head`. Podemos sobreescribir estas funciones para implementarlas. En este caso,
sobreescribimos el método `GET`.

Hemos hablado sobre el echo de que Beego un -----
We talked about the fact that Beego is a RESTFul framework so our requests will run the related `req.Method` method by default. For example, if the browser sends a `GET` request, it will execute the `Get` method in `MainController`. Therefore the `Get` method and the logic we defined above will be executed.

La lógica en nuestro método `Get` solo tiene algunas salidas. Podemos obtener la data de muchas
maneras y almacenarla en `this.Data` el cual es un map[string]interface{}. Podemos asignar
cualquier tipo de dato aquí. En este caso solo asignamos dos strings.

La última cosa por hacer es renderizar la plantilla. `this.TplNames` especifica la plantilla
que será renderizada: Aquí está `index.tpl`. Si no has configurado la plantilla, esta eligirá
por defecto a `controller/method_name.tpl`. Por ejemplo,en este caso trataría de encontrar
`maincontroller/get.tpl`.

Beego llamará a la función `Render` (la cual es implementada en `beego.Controller`) automátixamente si no has configurado las plantillas por lo que no necesitas renderizarlo manualmente.

Este fue tan solo una breve introducción. Echa un vistaso a la sección Controller (controlador)
en la introducción a MVC introduction para aprender más. A continuación hablaremos acerca de como escribir models (modelos).
