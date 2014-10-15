---
name: Archivos estáticos
sort: 6
---

# Manipulación de archivos estáticos

Hemos habaldo de como renderizar una vista. Usualemente hay muchos archivos estáticos incluyendo imágenes, js, css y así sucesivamente. El esqueleto de nuestro proyecto Beego ya tiene incluído carpetas para estos.

```
├── static
	│   ├── css
	│   ├── img
	│   └── js
```

Beego regista la carpeta static como ruta estática. Registrando una regla: el prefijo URL con
mapeo de directorio.

	StaticDir["/static"] = "static"
	
Puedes regustar muchos directorios estáticos. Por ejemplo si requieres dos carpetas de descarga
`download1` y `download2` puedes coonfigurarlas así:

	beego.SetStaticPath("/down1", "download1")	
	beego.SetStaticPath("/down2", "download2")	
	
Visitando la URL `http://localhost/down1/123.txt` consultará el archivo `123.txt` en la carpeta
`download1` directory.

