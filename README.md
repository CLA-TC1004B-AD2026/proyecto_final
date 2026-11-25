# Proyecto Final: Reto de IoT (TC1004B)

## 1. Contexto y objetivo del proyecto

El reto del curso consiste en diseñar e implementar, en equipo, una aplicación de Internet de las Cosas (IoT) que resuelva un problema real y actual. El sistema debe integrar hardware (sensores y/o actuadores), un backend con base de datos y servicio web, y una aplicación cliente que permita visualizar la información y, en su caso, controlar los actuadores. El cierre del reto es la presentación del prototipo funcional en la última semana.

Este documento describe los siete requerimientos obligatorios del proyecto final y la rúbrica con la que se evaluará cada uno.

## 2. Requerimientos del proyecto

### 2.1 Solución de un problema real en la actualidad por medio de una aplicación de IoT

El punto de partida del proyecto es un problema concreto y vigente (ambiental, agrícola, industrial, de seguridad, de salud, doméstico, etc.) que pueda resolverse o mitigarse mediante una solución de IoT. No basta con elegir sensores y después buscarles una justificación: el equipo debe poder explicar, con datos o referencias, por qué el problema es real y por qué una solución de IoT es pertinente para atenderlo.

### 2.2 Dos sensores y/o actuadores

El sistema debe incluir al menos dos sensores, dos actuadores, o una combinación de ambos (por ejemplo, un sensor de humedad y un actuador que active una bomba de riego). Cada uno debe estar justificado en función del problema elegido, correctamente conectado al microcontrolador, y con su lectura o control verificado de forma individual antes de integrarlo al resto del sistema.

### 2.3 Base de datos con al menos una tabla donde se guarde información de sensores

La información capturada por los sensores (y, si aplica, el estado de los actuadores) debe almacenarse en una base de datos, en al menos una tabla diseñada específicamente para ese propósito, con los tipos de datos adecuados para cada lectura (numéricos, marcas de tiempo, identificadores de dispositivo, etc.). La captura debe ser automática, es decir, alimentada en tiempo real por el sistema y no cargada manualmente.

### 2.4 Servicio web con operaciones CRUD para al menos una tabla

Sobre esa tabla (o sobre otra tabla relevante del sistema), el equipo debe implementar un servicio web tipo API REST que exponga las cuatro operaciones CRUD (crear, leer, actualizar y eliminar registros), siguiendo el mismo patrón visto en clase con Flask: rutas claras, manejo del cuerpo de la petición en JSON, y respuestas consistentes para cada operación.

### 2.5 Aplicación de escritorio o web que muestre información de sensores o controle actuadores

El sistema necesita una aplicación cliente (de escritorio o web) que consuma el servicio web descrito en el punto anterior, ya sea para mostrar la información capturada por los sensores, para controlar los actuadores, o ambas cosas. Esta aplicación es la interfaz con la que un usuario final interactuaría con el sistema, por lo que debe ser funcional y clara, sin necesidad de que sea vistosa.

### 2.6 Visualización de los datos en tiempo real y análisis, con al menos 3 indicadores distintos

Además de mostrar los datos crudos, el proyecto debe incluir un tablero de visualización en tiempo real con al menos tres indicadores distintos derivados del análisis de los datos capturados (por ejemplo: promedio de una lectura en una ventana de tiempo, valor máximo o mínimo del día, número de eventos de activación de un actuador, porcentaje de tiempo fuera de un rango esperado, tendencia reciente). Los tres indicadores deben aportar información útil para interpretar el comportamiento del sistema, no ser variaciones triviales de un mismo dato.

### 2.7 Prototipo funcional

El entregable final es un prototipo funcional, es decir, el sistema completo (sensores/actuadores, base de datos, servicio web, aplicación cliente y visualización) integrado y operando de principio a fin, no solo sus componentes por separado. El equipo debe poder hacer una demostración en vivo.

## 3. Entregable final

Para la presentación de la semana 10, cada equipo debe llevar:

- El prototipo funcional, listo para una demostración en vivo
- El código fuente del proyecto (microcontrolador, servicio web, aplicación cliente), con un README que explique cómo correrlo
- El modelo de la base de datos (diagrama o descripción de la tabla o tablas usadas)
- El tablero de visualización con los tres indicadores, accesible durante la demostración
- Una presentación breve que explique el problema resuelto, las decisiones técnicas tomadas y los resultados obtenidos

## 4. Rúbrica de evaluación

| Criterio | Puntos | Excelente | Bueno | Suficiente | No suficiente |
|---|---|---|---|---|---|
| Problema real y pertinencia de la solución IoT | 10 | El problema es real, está bien delimitado y es relevante; la solución de IoT propuesta se justifica claramente como respuesta a ese problema | El problema es real y relevante, pero la delimitación o la justificación de la solución es algo general | El problema es identificable pero vago, o se conecta débilmente con la solución de IoT propuesta | No queda claro qué problema real resuelve el proyecto, o la solución no tiene relación clara con IoT |
| Sensores y/o actuadores (mínimo 2) | 15 | Al menos dos sensores o actuadores correctamente seleccionados, justificados y funcionando de forma confiable, con manejo adecuado de errores de lectura o control | Los dos sensores o actuadores funcionan correctamente, aunque sin manejo robusto de errores o sin justificar del todo su selección | Los dos sensores o actuadores están presentes pero con funcionamiento intermitente o lecturas poco confiables | Hay menos de dos sensores o actuadores, o no funcionan de forma demostrable |
| Base de datos | 15 | La base de datos tiene al menos una tabla bien diseñada (tipos de datos adecuados, estructura clara) que almacena de forma automática y correcta la información de los sensores | La base de datos es funcional y guarda la información de los sensores, con algún aspecto de diseño mejorable | La base de datos está presente pero con errores de diseño, o no captura toda la información esperada | No hay una base de datos funcional, o los datos de los sensores no se guardan de forma confiable |
| Servicio web con operaciones CRUD | 15 | El servicio web implementa correctamente las cuatro operaciones CRUD sobre la tabla correspondiente, con manejo adecuado de errores y respuestas consistentes en JSON | Las cuatro operaciones CRUD están implementadas y funcionan, con manejo de errores limitado | El servicio web está implementado pero falta una o más operaciones CRUD, o alguna no funciona correctamente | No hay un servicio web funcional, o no expone operaciones CRUD reales sobre la base de datos |
| Aplicación de escritorio o web | 15 | La aplicación es funcional, con una interfaz clara, y muestra la información de los sensores o controla los actuadores de forma confiable, consumiendo el servicio web | La aplicación cumple su propósito, con una interfaz mejorable o alguna función limitada | La aplicación está presente pero con funcionalidad incompleta o problemas de usabilidad relevantes | No hay una aplicación funcional, o no se conecta realmente con los datos o servicios del sistema |
| Visualización en tiempo real y análisis (3 indicadores) | 15 | El tablero muestra datos en tiempo real y al menos tres indicadores distintos, bien elegidos, que aportan información útil sobre el comportamiento del sistema | Hay al menos tres indicadores funcionando en tiempo real, aunque alguno aporta poco valor analítico o se parece demasiado a otro | La visualización está presente pero con menos de tres indicadores, sin actualización realmente en tiempo real, o con indicadores poco relevantes | No hay una visualización funcional, o los datos mostrados no corresponden a información real del sistema |
| Prototipo funcional integrado | 15 | Todos los componentes (sensores/actuadores, base de datos, servicio web, aplicación, visualización) funcionan integrados de principio a fin, de forma estable, y el prototipo es demostrable en vivo | El prototipo integra todos los componentes y funciona en general, con alguna falla puntual o algo de intervención manual durante la demostración | El prototipo integra la mayoría de los componentes, pero requiere intervención frecuente o falla en partes relevantes durante la demostración | Los componentes funcionan de forma aislada, o no es posible demostrar un prototipo integrado funcionando |
| **Total** | **100** | | | | |

El equipo debe estar preparado para explicar y defender las decisiones técnicas tomadas en cada componente, ya que la presentación final forma parte de cómo se valora el prototipo, no solo su funcionamiento durante la demostración.
