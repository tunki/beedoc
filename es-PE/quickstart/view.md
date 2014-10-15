---
name: Vistas
sort: 5
---

# Creando vistas

Cuando creamos un controlador, usamos la línea `this.TplNames = "index.tpl"` para declarar la
plantilla a  ser renderizada. Por defecto `beego.Controller` soporta las extenciones `tpl` y
`html`. Puedes llamar a `beego.AddTemplateExt` para añadir otras extensiones. Entonces, ¿Cómo
es que las vistas(views) muestran la data que necesitamos? Beego usa por defecto template
engine nativo de Go por lo que es una plantilla de Go, plano y simple. Puedes aprender como
usar las plantilla de Go desde [*Build Web Application with Golang*](https://github.com/Unknwon/build-web-application-with-golang_EN/blob/master/eBook/07.4.md).

Veamos unm ejemplo:

```
<!DOCTYPE html>

<html>
  	<head>
    	<title>Beego</title>
    	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	</head>
  	
  	<body>
  		<header class="hero-unit" style="background-color:#A9F16C">
			<div class="container">
			<div class="row">
			  <div class="hero-text">
			    <h1>Welcome to Beego!</h1>
			    <p class="description">
			    	Beego es un web framework simple y poderoso el cual está inspirado por tornado y sinatra.
			    <br />
			    	Web oficial: <a href="http://{{.Website}}">{{.Website}}</a>
			    <br />
			    	Contact me: {{.Email}}
			    </p>
			  </div>
			</div>
			</div>
		</header>
	</body>
</html>
```

Hemos asignado la data dentro un variable `Data` tipo map en Controller. la cual es usada como
renderizadora. Por lo tanto ahora podemos acceder y emitir la data usando las claves (keys)
`.Website` y `.Email`. 

A continuación hablaremos sobre como servir archivos estáticos.
