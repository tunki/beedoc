---
name: Contributing
sort: 1
---

# Contribuyendo a Beego

## Introducción

Beego es un software libre y open source, lo que significa que cualquiera puede
contribuir con su desarrollo y progreso. El código de fuente de Beego está
almacenado en github, el cual provee una forma muy fácil de hacer un fork al
proyecto y unir tu contribución.

## Pull Requests

El proceso de pull requests para para nuevas características y corrección de
bugs no son lo mismo.

### Bug fixes

Los pull request para corrección de bugs no necesitan crear un issue primero.
Si tienes una solución para un bug, por favor describe tu solución al detalle
en tu pull request.

### Mejoras en la Documentación

Puedes ayudarnos a mejorar la documentación enviando su pull request al
repositorio [beedoc](https://github.com/beego/beedoc).

### Propuesta de nuevas características o funcionalidades

Antes de enviar un pull request para nuevas características, primero debes crear
un issue con `[Proposal]` en el título, describiendo cuales con las nuevas
caraterísticas, así como el enfoque de la implementación.

La propuesta será revisada y discutida por los desarrolladores mantenedores, y
puede ser adoptado o potencialmente rechazado.

Una vez que tu propuesta sea aceptada, crea tu implementación de las nuevas
características envía tu pull request. Si las directrices no son seguidas,
el pull request será rechazado inmediatamente.

Desde que Beegi sigue el modelo de ramas de
[Git Flow](http://nvie.com/posts/a-successful-git-branching-model/),
El proceso de desarrollo ocurre en la rama `develop`. Entonces,
por favor basa tu pull requests en el HEAD de la rama `develop`.
