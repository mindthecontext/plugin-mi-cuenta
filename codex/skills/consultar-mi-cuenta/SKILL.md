---
name: consultar-mi-cuenta
description: Consulta qué identidad reconoce MindTheContext para esta cuenta y qué servicios tiene habilitados, y diagnostica por qué un servicio no está disponible.
---

Usa esta habilidad cuando alguien pregunte con qué cuenta está conectado, qué servicios de MindTheContext tiene contratados, o cuando no pueda acceder a uno y haya que averiguar por qué.

Es de solo lectura: informa, no cambia habilitaciones. Para dar de alta a alguien o cambiar su plan hay que hacerlo desde la administración de la cuenta de la organización.

## Herramientas

| Herramienta | Responde |
|---|---|
| `quien_soy` | Correo, nombre, organización, roles y vencimiento de la sesión. |
| `mis_servicios` | Qué servicios puede usar esta cuenta y cuáles no, con el motivo de cada uno. |
| `diagnosticar_acceso` | Por qué un servicio concreto no está disponible y qué hacer para conseguirlo. |
| `estado_del_servicio` | Vista técnica: qué claims llegaron en el token y qué exige la puerta de entrada. |
| `ver_cambios` | Qué cambió en el servicio de una versión a otra y en qué versión corre. Antes de su línea base no hay registro: dilo así. |

## Invoca la herramienta, no respondas por inferencia

La regla más importante de esta habilidad.

Ante «quién soy», «qué servicios tengo» o «no puedo entrar a X», **llama a la herramienta**. No respondas a partir del nombre de la carpeta de trabajo, del correo de la cuenta del cliente ni de nada que ya esté en la conversación.

> **Por qué.** Una respuesta inferida a estas preguntas suena razonable y es indistinguible de una consulta real. Aquí eso significa afirmarle a alguien que tiene —o no tiene— acceso a algo por el que paga, sin haberlo comprobado.

La identidad que devuelve el servicio puede ser **distinta** de la cuenta con la que la persona entró a su cliente. Son dos identidades separadas, y esa diferencia suele explicar el problema.

## Cómo presentar los resultados

Al listar servicios, distingue siempre **habilitados** de **no habilitados**, y da el motivo de estos últimos: no es lo mismo «tu plan no lo incluye» que «ese servicio no existe».

Cuando el motivo mencione un rol que falta, explícalo en términos de negocio —qué servicio da ese rol y a quién pedirlo— en vez de repetir el identificador técnico a secas.

Si `diagnosticar_acceso` indica que el servicio no está en el catálogo, dilo como lo que es: **un identificador que no existe, no una denegación de permiso**. Confundirlos lleva a explicar un problema de acceso que nunca ocurrió.

## Cuando el propio servicio rechaza

Las respuestas de error traen el motivo; léelo y tradúcelo en vez de sugerir «reintenta»:

- **`invalid_token`** — el token no vale para este servicio. Suele ser configuración del lado del proveedor de identidad, no algo que la persona pueda arreglar.
- **`access_denied`** — autenticado, pero sin acceso: dominio no autorizado o falta una habilitación. El mensaje dice cuál.

Un `401` antes de iniciar sesión no es un fallo: es el primer paso del flujo, y el cliente debe resolverlo solo.

## Criterios de respuesta

- Muestra los valores tal como llegaron, sin completarlos ni normalizarlos.
- Si una herramienta no está disponible, dilo explícitamente en vez de responder con lo que sabes por contexto.
- No prometas cambios: esta habilidad no habilita servicios ni modifica cuentas.
