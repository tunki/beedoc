---
name: Modelos
sort: 4
---

# Creando un modelo

Sabemos que estamos usando muchas bases de datos en las aplicaciones web por lo que los modelos
son la forma ususal de manejar este tipo de tareas. No hay ningún demo de models en nuestro
proyecto `bee new`, pero hay demos de como implementarlos y usarlos en proyecto `bee api`.
Básicamente, si tu aplicación es lo suficientemente simple el Controller (controlador) puede
manipular cualquier cosa. Sin embargo, si hay alguna lógica reusable podemos contruirla dentro
de un módulo. El modelo es el resultado de la extracción de la lógica. Usualmente el modelo
manupulará alguna información leyéndola y/ escribiéndola. Aquí algunos ejemplo:

```
package models

import (
	"loggo/utils"
	"path/filepath"
	"strconv"
	"strings"
)

var (
	NotPV []string = []string{"css", "js", "class", "gif", "jpg", "jpeg", "png", "bmp", "ico", "rss", "xml", "swf"}
)

const big = 0xFFFFFF

func LogPV(urls string) bool {
	ext := filepath.Ext(urls)
	if ext == "" {
		return true
	}
	for _, v := range NotPV {
		if v == strings.ToLower(ext) {
			return false
		}
	}
	return true
}
```

Entonces, si tu aplicación es lo suficientemente simple, puedes no necesitar modelos del todo.
Pero cuando tu apliación crece demasiado y quieres más código reusable y necesitas una
separación de lógica, debes usar modelos. En la siguiente sección hablaremos de como usar las
vistas (View).
