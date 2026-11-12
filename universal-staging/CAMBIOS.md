# Cambios · Mi Cuenta MindTheContext

<!-- Generado al derivar el paquete desde cambios.yaml. No editar a mano. -->

Qué cambia para quien usa este saber, versión por versión. Lo que corre de verdad el servicio lo dice su herramienta `ver_cambios`; esto es la copia del paquete.

## v1.2.2 · 2026-11-11

Sin cambios en lo que responde. El paquete trae una carpeta nueva que se instala igual en Claude y en un espacio de trabajo de ChatGPT, desde una sola entrada del catálogo: antes el espacio de trabajo de ChatGPT rechazaba la versión de Claude porque su skill no declaraba su nombre.

- Herramientas: `diagnosticar_acceso`, `estado_del_servicio`, `mis_servicios`, `quien_soy`, `ver_cambios`
- Skills: `consultar-mi-cuenta`
- Datos: sin manifiesto

## v1.2.1 · 2026-09-18

Sin cambios para quien lo usa. Por dentro, el servicio ahora comprueba al arrancar que puede leer el registro de contratos y lo declara en su chequeo de salud: si no puede, el despliegue queda en rojo en vez de pasar en verde con el servicio rechazando a todo el mundo.

- Herramientas: `diagnosticar_acceso`, `estado_del_servicio`, `mis_servicios`, `quien_soy`, `ver_cambios`
- Skills: `consultar-mi-cuenta`
- Datos: sin manifiesto

## v1.2.0 · 2026-09-15

El saber dice qué cambió de una versión a otra y en qué versión está corriendo: aparece `ver_cambios`. Y si es la primera vez que te conectas —o te conectas desde una cuenta que el servicio todavía no conoce, con tu mismo correo—, tu cuenta queda reconocida en la primera consulta también cuando el servicio acaba de arrancar. Lo que ya respondía sigue igual.

- Herramientas: `diagnosticar_acceso`, `estado_del_servicio`, `mis_servicios`, `quien_soy`, `ver_cambios`
- Skills: `consultar-mi-cuenta`
- Datos: sin manifiesto

## Línea base · v1.1.1 · 2026-09-15

Así está el saber cuando empieza este registro. Responde con qué identidad reconoce MindTheContext a quien llama (`quien_soy`), qué servicios puede usar esa cuenta y cuáles no, con el motivo de cada uno (`mis_servicios`), por qué un servicio concreto no está disponible y qué hacer (`diagnosticar_acceso`), y una vista técnica de la configuración de acceso y los claims recibidos (`estado_del_servicio`). Es un servicio abierto: no exige habilitación, porque existe para que quien tiene un problema de acceso pueda averiguar cuál es. Distingue «no tienes acceso» de «no se pudo comprobar».

- Herramientas: no derivable
- Skills: `consultar-mi-cuenta`
- Datos: sin manifiesto

Antes de v1.1.1 no hay registro de cambios.
