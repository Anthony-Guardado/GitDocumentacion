# Plan de Pruebas SACI

## 1. Introducción

El presente Plan de Pruebas ha sido elaborado para el Sistema de Administración y Control de Inventario (SACI), una solución informática desarrollada para apoyar la gestión operativa de la Tienda y Librería Israel. Este sistema tiene como finalidad automatizar y optimizar los procesos relacionados con el control de inventario, compras, ventas, créditos, abonos, devoluciones de ventas, gestión de proveedores, administración de usuarios y demás actividades esenciales para el funcionamiento del negocio.

La implementación de SACI busca mejorar la organización de la información, fortalecer el control de las operaciones diarias y proporcionar herramientas que faciliten la toma de decisiones mediante el registro y seguimiento adecuado de los procesos comerciales. Debido a la importancia de la información que administra el sistema y al impacto que sus funcionalidades tienen sobre las operaciones del negocio, es fundamental garantizar su correcto funcionamiento antes de su puesta en producción.

Por tal motivo, este Plan de Pruebas establece las actividades, criterios y procedimientos necesarios para evaluar la calidad del sistema, verificar el cumplimiento de los requisitos definidos y detectar posibles defectos que puedan afectar su desempeño. A través de la ejecución de las pruebas correspondientes, se busca asegurar que SACI opere de manera confiable, segura y acorde con las necesidades de la Tienda y Librería Israel, contribuyendo así a una implementación exitosa del sistema.

## 2. Objetivos de las pruebas

### Objetivo General

Verificar mediante la ejecución de pruebas que el Sistema de Administración y Control Inventario (SACI) funcione de acuerdo con los requisitos funcionales y reglas de negocio establecidos, garantizando la confiabilidad, integridad de todos los datos financieros o personales de los clientes y correcto desempeño de sus procesos antes de su implementación en la Tienda y Librería Israel.

### Objetivos Específicos

1. Validar el correcto funcionamiento de los módulos que conforman el sistema, incluyendo inventario, compras, ventas, créditos, abonos, devoluciones de ventas, proveedores y gestión de usuarios.
    
2. Comprobar que las reglas de negocio definidas para cada proceso se ejecuten de manera correcta, especialmente aquellas relacionadas con el control de inventario, manejo de lotes, ventas al crédito y registro de abonos.
    
3. Identificar y documentar defectos, inconsistencias o comportamientos no esperados que puedan afectar el funcionamiento del sistema.
    
4. Verificar la integridad y consistencia de la información almacenada y procesada por el sistema durante las operaciones diarias.
    
5. Evaluar que los controles de acceso y autenticación funcionen de acuerdo con los permisos establecidos para los usuarios del sistema.
    
6. Reducir los riesgos operativos asociados a errores de software que puedan afectar los procesos de la Tienda y Librería Israel una vez que el sistema sea puesto en producción.


## 3. Alcance de las pruebas

El presente Plan de Pruebas comprende la validación funcional de los principales módulos que conforman el Sistema de Administración y Control Inventario (SACI), con el propósito de verificar que los procesos implementados operen de acuerdo con los requisitos definidos y las reglas de negocio establecidas para la Tienda y Librería Israel.

Las pruebas contemplarán la evaluación de los módulos de autenticación y gestión de usuarios, inventario, productos, categorías, marcas, compras, ventas, créditos, abonos, control de lotes, devoluciones de ventas, gestión de proveedores, cronograma de proveedores, cambio de productos, productos dañados y administración de notas.

Asimismo, se verificará el correcto funcionamiento de las reglas de negocio críticas del sistema, incluyendo la actualización automática de existencias, el manejo de productos perecederos mediante el método FIFO, el control de créditos y abonos, la generación de registros de devolución de ventas y la integridad de la información almacenada durante las operaciones que realiza la tienda y librería.

Las pruebas serán ejecutadas sobre las funcionalidades implementadas en la versión actual del sistema, enfocándose principalmente en la validación de procesos funcionales y la consistencia de los datos generados por cada operación.

### Fuera de Alcance

El presente Plan de Pruebas se encuentra enfocado principalmente en la validación funcional de los módulos implementados en la versión actual del Sistema de Administración y Control Inventario (SACI). Por tal motivo, no se contemplan actividades relacionadas con pruebas especializadas que requieren infraestructura, herramientas o entornos de ejecución distintos a los disponibles para el desarrollo del proyecto.

Dentro de las actividades que no forman parte del presente plan se encuentran:

- Pruebas de carga orientadas a evaluar el comportamiento del sistema bajo una alta concurrencia de usuarios simultáneos.
    
- Pruebas de estrés destinadas a determinar los límites máximos de operación del sistema ante volúmenes extremos de transacciones o condiciones de sobrecarga.
    
- Pruebas de disponibilidad y recuperación ante fallos de hardware, interrupciones de red o caídas de servicios externos.
    
- Pruebas avanzadas de seguridad informática, tales como pruebas de penetración (Pentesting), auditorías de vulnerabilidades o simulación de ataques cibernéticos.
    
- Validaciones relacionadas con funcionalidades que no hayan sido implementadas en la versión actual del sistema.


No obstante, como parte del proceso de aseguramiento de la calidad, se realizarán validaciones básicas de rendimiento sobre la versión actual de SACI utilizando conjuntos de datos representativos. Estas actividades tendrán como objetivo verificar la eficiencia de consultas, búsquedas, paginación, generación de reportes y acceso a la información almacenada, así como identificar posibles oportunidades de optimización en la aplicación y en la base de datos PostgreSQL.

Las pruebas de rendimiento serán documentadas en un plan complementario independiente al presente Plan de Pruebas Funcionales.

Asimismo, todas las funcionalidades operativas implementadas en SACI, incluyendo los módulos de inventario, compras, ventas, créditos, abonos, devoluciones de ventas, cambio de productos con proveedores, proveedores, productos dañados, usuarios, control de lotes y reportes, forman parte del alcance funcional de las pruebas definidas en este documento.

## 4. Riesgos identificados

Durante el proceso de análisis del Sistema de Administración y Control Inventario (SACI), se identificaron diversos riesgos que podrían afectar el funcionamiento del sistema y las operaciones de la Tienda y Librería Israel en caso de presentarse defectos durante la ejecución de los procesos críticos.

Entre los principales riesgos identificados se encuentran:

- Errores en la actualización de existencias del inventario como consecuencia de operaciones de compra, venta, devoluciones de ventas o registro de productos dañados.
    
- Fallo en cálculos de las ventas y las compras.
    
- Fallos en la aplicación del método FIFO para la selección y descuento de lotes de productos perecederos.
    
- Reportes que no tengan los datos actualizados de las ventas y las compras.
    
- Inconsistencias en el registro y control de ventas realizadas al crédito.
    
- Errores en el procesamiento de abonos que afecten el saldo pendiente de los créditos registrados.
    
- Fallos en el proceso de devoluciones de ventas que provoquen inconsistencias en la información financiera o de inventario.
    
- Accesos indebidos a funcionalidades restringidas debido a errores en la administración de usuarios, roles y permisos.
    
- Pérdida de integridad de la información almacenada en la base de datos debido a registros incompletos o incorrectos.


Debido al impacto que estos riesgos pueden generar sobre la operación del negocio, los módulos relacionados con inventario, ventas, créditos, abonos, devoluciones de ventas y control de lotes recibirán una atención prioritaria durante la ejecución de las pruebas.

## 5. Módulos del sistema a probar

El presente Plan de Pruebas contempla la validación de los módulos funcionales implementados en el Sistema de Administración y Control Inventario (SACI), los cuales forman parte de los procesos operativos de la Tienda y Librería Israel.

Los módulos incluidos dentro del proceso de pruebas son los siguientes:

### Módulo de Seguridad y Acceso

- Autenticación de usuarios.
    
- Gestión de usuarios.
    
- Gestión de roles.


### Módulo de Inventario

- Gestión de productos.
    
- Gestión de categorías.
    
- Gestión de marcas.
    
- Control de existencias.


### Módulo de Compras

- Registro de compras.
    
- Administración de detalles de compra.
    
- Gestión de proveedores.


### Módulo de Lotes

- Registro de lotes.
    
- Control de cantidades disponibles.
    
- Gestión de vencimientos.
    
- Aplicación del método FIFO.


### Módulo de Ventas

- Ventas al detalle.
    
- Ventas al por mayor.
    
- Generación de comprobantes.
    
- Actualización de inventario.


### Módulo de Créditos

- Registro y control de créditos.
    
- Seguimiento de saldos pendientes.
    
- Cancelación de créditos.


### Módulo de Abonos

- Registro de abonos.
    
- Historial de pagos realizados.
    
- Actualización de saldos.


### Módulo de Devoluciones de Ventas

- Registro de devoluciones de ventas.
    
- Reincorporación de productos al inventario cuando corresponda.
    
- Registro de productos dañados asociados a la devolución.


### Módulo de Cambio de Productos

- Registro de cambios de productos con proveedores.
    
- Control de productos vencidos o dañados que serán reemplazados.


### Módulo de Productos Dañados

- Registro de productos dañados.
    
- Control de pérdidas.
    
- Actualización de existencias.


### Módulo de Proveedores

- Gestión de proveedores.
    
- Cronograma de proveedores.


### Módulo de Notas

- Registro y administración de notas.


Todos los módulos descritos anteriormente serán considerados dentro de las actividades de validación funcional definidas en el presente Plan de Pruebas.

## 6. Estrategia de pruebas

La estrategia de pruebas definida para el Sistema de Administración y Control Inventario (SACI) se basa en un enfoque orientado al riesgo y a la criticidad de los procesos del negocio, priorizando aquellas funcionalidades que tienen un mayor impacto sobre las operaciones de la Tienda y Librería Israel.

Las actividades de prueba serán ejecutadas de forma progresiva, iniciando por los módulos fundamentales para el funcionamiento del sistema y continuando con aquellos que dependen de procesos previamente validados. Esta estrategia permitirá detectar defectos de manera temprana y reducir el impacto de posibles errores en módulos relacionados.

El proceso de pruebas comenzará con la validación de los mecanismos de autenticación, gestión de usuarios y roles. Posteriormente, se evaluarán los módulos de inventario, productos, categorías y marcas, continuando con los procesos de compras, generación de lotes y control de existencias.

Una vez verificados los procesos de abastecimiento e inventario, se procederá a validar las operaciones de ventas, créditos, abonos, devoluciones de ventas, cambio de productos, productos dañados y gestión de proveedores. Finalmente, se realizarán pruebas de integración para verificar la correcta interacción entre los distintos módulos del sistema y la consistencia de la información generada durante las operaciones.

Durante la ejecución de las pruebas se registrarán los resultados obtenidos, las incidencias identificadas y las evidencias correspondientes, con el propósito de garantizar la trazabilidad y el seguimiento adecuado de los defectos detectados.

## 7. Tipos de pruebas

### 7.1 Descripción de los tipos de pruebas

Antes de ejecutar las pruebas sobre los distintos módulos de SACI, es necesario definir el propósito de cada tipo de prueba que será utilizado durante el proceso de validación del sistema.

| Tipo de prueba      | Descripción                                                                                                                                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Funcional           | Verifica que cada funcionalidad del sistema opere de acuerdo con los requisitos y reglas de negocio establecidos. Permite comprobar que las entradas, procesos y resultados generados sean correctos. |
| Integración         | Evalúa la interacción entre dos o más módulos del sistema para asegurar que intercambien información correctamente y mantengan la consistencia de los datos.                                          |
| Seguridad           | Comprueba los mecanismos de autenticación, autorización y control de acceso, garantizando que cada usuario solo pueda acceder a las funciones permitidas según su rol.                                |
| Validación de datos | Verifica la integridad, consistencia y exactitud de la información almacenada y procesada por el sistema.                                                                                             |
| Regresión           | Se ejecuta después de realizar correcciones o mejoras para confirmar que los cambios implementados no afecten funcionalidades que anteriormente operaban correctamente.                               |
| Aceptación          | Permite validar que el sistema cumple las necesidades y expectativas del usuario final antes de su puesta en producción.                                                                              |

### 7.2 Aplicación de los tipos de pruebas en SACI

Con el objetivo de garantizar la calidad del Sistema de Administración y Control Inventario (SACI), se aplicarán distintos tipos de pruebas sobre los módulos y procesos que conforman el sistema. Estas pruebas permitirán verificar el correcto funcionamiento de las funcionalidades implementadas, la interacción entre módulos, la integridad de los datos y el cumplimiento de las reglas de negocio establecidas para la Tienda y Librería Israel.

Las pruebas serán ejecutadas de acuerdo con la naturaleza de cada módulo, permitiendo validar tanto el comportamiento individual de las funcionalidades como su integración con el resto del sistema.

|Módulo|Tipo de prueba|Objetivo de la prueba|
|---|---|---|
|Seguridad y acceso|Funcional / Seguridad|Verificar el inicio de sesión, validación de credenciales, autenticación y control de acceso al sistema.|
|Gestión de usuarios|Funcional|Comprobar la creación, edición, activación y desactivación de usuarios.|
|Gestión de roles|Funcional / Seguridad|Validar la asignación de permisos y restricciones de acceso según el rol correspondiente.|
|Inventario|Funcional / Validación de datos|Verificar el registro y actualización de productos, categorías, marcas y existencias.|
|Compras|Funcional / Integración / Validación de datos|Validar el registro de compras, detalles de compra y actualización automática del inventario.|
|Lotes y control FIFO|Funcional / Integración / Validación de datos|Comprobar la correcta administración de lotes, fechas de vencimiento y aplicación del método FIFO para productos perecederos.|
|Control de lotes vencidos|Funcional / Integración / Validación de datos|Validar que cuando un lote venza, el sistema descuente automáticamente del stock los productos que aún conserven ese lote y mantenga el historial correspondiente.|
|Ventas al detalle|Funcional / Integración|Verificar el proceso de venta al detalle, cálculo de subtotales, totales y actualización de existencias.|
|Ventas al por mayor|Funcional / Integración|Validar la aplicación correcta de precios al por mayor y la actualización del inventario.|
|Créditos|Funcional / Validación de datos|Comprobar el registro de créditos, cálculo del saldo pendiente, asignación del cliente y asociación con la venta correspondiente.|
|Abonos|Funcional / Integración|Validar el registro de abonos, actualización de saldos y conservación del historial de pagos realizados.|
|Devoluciones de ventas|Funcional / Integración|Verificar el registro de devoluciones de ventas y la correcta reincorporación de productos al inventario cuando corresponda.|
|Cambio de productos|Funcional / Integración|Validar el registro de cambios de productos con proveedores, especialmente productos vencidos o dañados que serán reemplazados.|
|Productos dañados|Funcional / Validación de datos|Comprobar el registro de pérdidas por productos dañados y la disminución correspondiente del stock.|
|Proveedores|Funcional|Verificar el registro, modificación y consulta de información de proveedores.|
|Cronograma de proveedores|Funcional|Validar el registro y seguimiento de actividades programadas con proveedores.|
|Notas|Funcional|Comprobar la creación, modificación, asignación por usuario y consulta de notas.|
|Reportes|Funcional / Validación de datos|Verificar que la información mostrada en reportes de ventas, compras, créditos, abonos, ganancias e inventario sea correcta, consistente y actualizada.|
|Integración general del sistema|Integración|Validar que los módulos interactúen correctamente entre sí y mantengan la consistencia de la información procesada.|
|Correcciones y mejoras realizadas|Regresión|Comprobar que las modificaciones efectuadas no afecten funcionalidades previamente validadas.|
|Validación con el usuario final|Aceptación|Verificar que el sistema cumpla las necesidades operativas de la Tienda y Librería Israel antes de su implementación definitiva.|

La aplicación de estos tipos de pruebas permitirá evaluar de manera integral todos los módulos y procesos que conforman SACI, garantizando que las operaciones relacionadas con inventario, compras, ventas, créditos, abonos, devoluciones de ventas, cambio de productos, proveedores y control de productos funcionen correctamente y cumplan con los requerimientos establecidos. Asimismo, se buscará asegurar la integridad de los datos, la correcta interacción entre módulos y la confiabilidad del sistema antes de su puesta en producción.

## 8. Gestión de pruebas

La gestión de pruebas del Sistema de Administración y Control Inventario (SACI) tiene como finalidad planificar, organizar, ejecutar y controlar las actividades relacionadas con el proceso de validación del sistema, garantizando que todas las funcionalidades sean evaluadas de forma estructurada y documentada.

El proceso de pruebas se desarrollará de manera progresiva, siguiendo el orden lógico de los módulos y procesos que conforman el sistema. Cada prueba ejecutada contará con su respectivo caso de prueba, resultado obtenido y evidencia correspondiente, permitiendo mantener la trazabilidad de las validaciones realizadas.

Las actividades de gestión de pruebas comprenderán las siguientes etapas:

### Planificación de pruebas

Consiste en la definición de los módulos que serán evaluados, los tipos de pruebas que se aplicarán y los recursos necesarios para su ejecución.

### Diseño de casos de prueba

Se elaborarán casos de prueba específicos para cada módulo del sistema, definiendo objetivos, precondiciones, pasos de ejecución, datos de prueba y resultados esperados.

### Ejecución de pruebas

Los casos de prueba serán ejecutados sobre el sistema con el propósito de verificar el correcto funcionamiento de las funcionalidades implementadas y detectar posibles defectos.

### Registro de resultados

Cada prueba realizada deberá documentar su resultado, indicando si fue aprobada, rechazada o si requiere correcciones adicionales.

### Gestión de incidencias

Los defectos identificados durante la ejecución de las pruebas serán registrados y clasificados según su impacto sobre el funcionamiento del sistema.

### Reejecución de pruebas

Una vez corregidos los defectos reportados, se realizarán nuevas ejecuciones para verificar que las incidencias hayan sido solucionadas y que las modificaciones no afecten otras funcionalidades previamente validadas.

### Evidencias de prueba

Se conservarán capturas de pantalla, registros del sistema y demás evidencias necesarias para respaldar los resultados obtenidos durante el proceso de validación.

## 9. Monitoreo y control

El monitoreo y control de pruebas tiene como propósito supervisar el avance de las actividades definidas en el presente Plan de Pruebas, verificando que la ejecución se realice conforme a los objetivos, alcance y estrategias establecidas para el Sistema de Administración y Control Inventario (SACI).

Durante el proceso de validación se realizará un seguimiento continuo del estado de las pruebas ejecutadas, permitiendo identificar oportunamente retrasos, incidencias, riesgos o desviaciones que puedan afectar la calidad del sistema antes de su implementación en la Tienda y Librería Israel.

Para llevar a cabo el monitoreo y control de las pruebas se utilizarán los siguientes mecanismos:

### Seguimiento del avance de pruebas

Se registrará el estado de cada caso de prueba, permitiendo identificar cuáles han sido ejecutados, cuáles se encuentran pendientes y cuáles requieren correcciones antes de ser considerados aprobados.

### Control de resultados

Los resultados obtenidos durante la ejecución de las pruebas serán documentados y comparados con los resultados esperados definidos en cada caso de prueba, con el fin de determinar el cumplimiento de los requisitos establecidos.

### Seguimiento de incidencias

Los defectos detectados serán monitoreados desde su identificación hasta su resolución, registrando su estado, prioridad e impacto sobre el funcionamiento del sistema.

### Verificación de correcciones

Una vez implementadas las correcciones correspondientes, se ejecutarán nuevamente las pruebas afectadas y las pruebas iniciales para comprobar que los errores hayan sido solucionados de manera satisfactoria y que no se presente un error lo que antes funciono.

### Control de cobertura de pruebas

Se verificará que todos los módulos incluidos dentro del alcance del presente plan hayan sido sometidos a las pruebas correspondientes, garantizando una cobertura adecuada de las funcionalidades del sistema.

### Gestión de riesgos durante las pruebas

Se dará seguimiento a los riesgos identificados en el presente documento para determinar si alguno de ellos se materializa durante la ejecución de las pruebas y aplicar las acciones necesarias para minimizar su impacto.

---

### Indicadores de seguimiento

Para evaluar el avance del proceso de pruebas se utilizarán los siguientes indicadores:

| Indicador                  | Descripción                                                                            |
| -------------------------- | -------------------------------------------------------------------------------------- |
| Casos de prueba ejecutados | Cantidad de casos de prueba realizados respecto al total planificado.                  |
| Casos de prueba aprobados  | Número de pruebas que cumplen satisfactoriamente con el resultado esperado.            |
| Casos de prueba fallidos   | Número de pruebas que presentan diferencias entre el resultado esperado y el obtenido. |
| Incidencias detectadas     | Total de defectos identificados durante la ejecución de pruebas.                       |
| Incidencias corregidas     | Cantidad de errores solucionados después de su reporte.                                |
| Cobertura de pruebas       | Porcentaje de módulos y funcionalidades evaluadas respecto al alcance definido.        |

---

### Cierre del monitoreo

El proceso de monitoreo y control finalizará una vez que todos los casos de prueba definidos hayan sido ejecutados, los defectos críticos hayan sido corregidos y las funcionalidades incluidas en el alcance del presente Plan de Pruebas cumplan con los criterios establecidos para su aceptación.

## 10. Gestión de bugs

La gestión de bugs tiene como finalidad identificar, registrar, clasificar, dar seguimiento y verificar la corrección de los defectos detectados durante el proceso de pruebas del Sistema de Administración y Control Inventario (SACI).

Todo error identificado durante la ejecución de pruebas deberá ser documentado de forma adecuada para facilitar su análisis, corrección y posterior validación. Este proceso permitirá mantener la trazabilidad de las incidencias y garantizar la calidad de las funcionalidades implementadas.

## Registro de bugs

Cada defecto detectado deberá registrarse con la siguiente información mínima:

- Identificador del bug.
    
- Fecha de detección.
    
- Módulo afectado.
    
- Descripción del problema.
    
- Pasos para reproducir el error.
    
- Resultado esperado.
    
- Resultado obtenido.
    
- Evidencia del defecto.
    
- Estado actual.
    
- Prioridad asignada.


## Clasificación de bugs

Los defectos serán clasificados según su nivel de impacto sobre el funcionamiento del sistema.

| Prioridad | Descripción                                                                                                 |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| Crítica   | Error que impide la operación normal del sistema o genera pérdida de información importante.                |
| Alta      | Error que afecta una funcionalidad principal del sistema, pero permite continuar parcialmente la operación. |
| Media     | Error que afecta funcionalidades secundarias sin impedir la continuidad del trabajo.                        |
| Baja      | Error visual, de formato o comportamiento menor que no afecta significativamente la operación del sistema.  |

## Estados de los bugs

Durante su ciclo de vida, los defectos podrán encontrarse en alguno de los siguientes estados:

| Estado        | Descripción                                                           |
| ------------- | --------------------------------------------------------------------- |
| Abierto       | El defecto ha sido identificado y registrado.                         |
| En análisis   | El defecto está siendo revisado para determinar su causa.             |
| En corrección | El equipo de desarrollo trabaja en la solución del problema.          |
| Corregido     | Se ha implementado una solución para el defecto reportado.            |
| En validación | El área de pruebas verifica que la corrección funcione adecuadamente. |
| Cerrado       | El defecto ha sido solucionado y validado satisfactoriamente.         |
| Reabierto     | El problema persiste o vuelve a presentarse después de la corrección. |

## Validación de correcciones

Una vez que un defecto haya sido corregido, se ejecutarán nuevamente las pruebas relacionadas para verificar que:

- El error haya sido solucionado.
    
- No existan efectos secundarios sobre otras funcionalidades.
    
- Se mantenga la integridad de los datos procesados por el sistema.

## Gestión de defectos críticos

Los defectos clasificados como críticos o de alta prioridad deberán ser atendidos antes de la liberación del sistema, especialmente aquellos relacionados con:

- Inventario.
    
- Compras.
    
- Ventas.
    
- Créditos.
    
- Abonos.
    
- Control de lotes.
    
- Aplicación del método FIFO.
    
- Seguridad y control de acceso.

## Cierre de incidencias

Un bug será considerado cerrado únicamente cuando la corrección haya sido implementada, validada mediante pruebas y no presente nuevos comportamientos inesperados asociados al defecto original.

## 11. Herramientas utilizadas

Para la ejecución y gestión de las pruebas del Sistema de Administración y Control Inventario (SACI), se utilizarán diversas herramientas que permitirán documentar los casos de prueba, registrar incidencias, almacenar evidencias y dar seguimiento a los resultados obtenidos durante el proceso de validación.

Las herramientas consideradas para el presente Plan de Pruebas son las siguientes:

|Herramienta|Propósito|
|---|---|
|Google Docs|Elaboración y documentación del Plan de Pruebas.|
|Google Sheets|Registro y seguimiento de casos de prueba, incidencias y resultados obtenidos.|
|Visual Studio Code|Revisión del código fuente, análisis de incidencias y apoyo en la identificación de defectos detectados durante las pruebas.|
|Laravel|Framework utilizado para el desarrollo de SACI y apoyo en la verificación del funcionamiento de las reglas de negocio implementadas.|
|PostgreSQL|Verificación de la integridad, consistencia y almacenamiento de la información gestionada por el sistema.|
|Postman|Validación de servicios API y pruebas de comunicación entre el frontend y backend del sistema.|
|Navegador Web (Brave)|Ejecución de pruebas funcionales sobre la interfaz de usuario del sistema.|
|Herramientas de captura de pantalla de Windows|Obtención de evidencias visuales de los resultados de las pruebas realizadas.|
|Laravel Tinker|Generación y manipulación de datos de prueba para la preparación de escenarios de validación.|

## Uso de las herramientas

Las herramientas descritas anteriormente serán utilizadas durante las diferentes etapas del proceso de pruebas, permitiendo planificar actividades, ejecutar validaciones, registrar incidencias y conservar evidencias que respalden los resultados obtenidos.

Asimismo, facilitarán la trazabilidad de las pruebas ejecutadas y contribuirán al control y seguimiento de los defectos detectados durante la validación del sistema.

## 12. Criterios de entrada y salida

### Criterios de entrada

Para dar inicio al proceso de pruebas del Sistema de Administración y Control Inventario (SACI), es necesario que se cumplan determinadas condiciones previas que garanticen que el sistema se encuentra en un estado adecuado para su validación. Estas condiciones permiten asegurar que las pruebas se realicen de forma ordenada, completa y con resultados confiables.

Los criterios de entrada para este plan de pruebas son los siguientes:

- El sistema debe encontrarse desplegado y disponible en un ambiente de pruebas.
    
- La base de datos del sistema debe encontrarse disponible y correctamente integrada con la aplicación para permitir el almacenamiento, consulta y actualización de la información durante la ejecución de las pruebas.
    
- Los módulos funcionales incluidos dentro del alcance deben encontrarse implementados en la versión a validar.
    
- Deben existir usuarios y roles previamente creados para realizar las pruebas de acceso y permisos.
    
- Deben estar preparados los datos de prueba necesarios para validar los distintos escenarios del sistema.
    
- Los casos de prueba deben encontrarse definidos y organizados antes de la ejecución.
    
- Debe estar disponible el acceso a las herramientas de validación y documentación establecidas en el presente plan.
    
- Debe existir aprobación para iniciar la ejecución de las pruebas sobre la versión seleccionada del sistema.

### Criterios de salida

El proceso de pruebas del Sistema de Administración y Control Inventario (SACI) se dará por finalizado cuando se cumplan las condiciones que indiquen que el sistema ha sido validado de forma satisfactoria dentro del alcance definido en este documento.

Los criterios de salida para este plan de pruebas son los siguientes:

- Se hayan ejecutado los casos de prueba definidos para los módulos incluidos en el alcance.
    
- Se hayan documentado los resultados obtenidos en cada prueba realizada.
    
- Se hayan registrado y clasificado los defectos detectados durante la validación.
    
- Los defectos de mayor prioridad hayan sido corregidos y verificados.
    
- Se haya comprobado que las correcciones aplicadas no afectaron otras funcionalidades previamente validadas.
    
- Se cuente con evidencia suficiente de la ejecución de las pruebas realizadas.
    
- El sistema presente un comportamiento estable y coherente con los requerimientos funcionales definidos para la Tienda y Librería Israel.

## 13. Casos de prueba asociados

Con el propósito de validar el correcto funcionamiento del Sistema de Administración y Control Inventario (SACI), se definirán y ejecutarán casos de prueba asociados a cada uno de los módulos incluidos dentro del alcance del presente Plan de Pruebas.

Los casos de prueba tendrán como objetivo verificar el cumplimiento de los requisitos funcionales, las reglas de negocio y la correcta interacción entre los distintos componentes del sistema.

A continuación, se presentan las áreas funcionales sobre las cuales se elaborarán los casos de prueba correspondientes:

|Módulo|Casos de prueba asociados|
|---|---|
|Seguridad y acceso|Inicio de sesión, validación de credenciales, cierre de sesión y control de acceso.|
|Gestión de usuarios|Creación, modificación, activación y desactivación de usuarios.|
|Gestión de roles|Asignación de roles y validación de permisos.|
|Inventario|Registro, modificación, consulta y control de existencias.|
|Compras|Registro de compras, actualización de inventario y generación de lotes.|
|Lotes y FIFO|Control de vencimientos, descuento de existencias y aplicación del método FIFO.|
|Ventas|Ventas al detalle, ventas al por mayor y actualización de stock.|
|Créditos|Registro de créditos, cálculo de saldo y cancelación de deuda.|
|Abonos|Registro de pagos, actualización de saldo e historial de abonos.|
|Devoluciones de ventas|Registro de devoluciones, reincorporación de productos y control de stock.|
|Cambio de productos|Registro de cambios con proveedores y control de productos reemplazados.|
|Productos dañados|Registro de pérdidas y actualización de inventario.|
|Proveedores|Registro, modificación y consulta de proveedores.|
|Cronograma de proveedores|Registro y seguimiento de actividades programadas.|
|Notas|Creación, modificación y consulta de notas.|
|Reportes|Generación y validación de información consolidada del sistema.|

Los casos de prueba detallados, junto con sus datos de entrada, pasos de ejecución, resultados esperados y evidencias, serán documentados en la matriz de casos de prueba correspondiente, la cual formará parte de la documentación complementaria del proceso de validación.

## 14. Resultados esperados

Como resultado de la ejecución del presente Plan de Pruebas, se espera obtener evidencia objetiva que demuestre el correcto funcionamiento del Sistema de Administración y Control Inventario (SACI), verificando que las funcionalidades implementadas cumplen con los requisitos establecidos y las necesidades operativas de la Tienda y Librería Israel.

Los resultados esperados son los siguientes:

- Verificar que todos los módulos incluidos dentro del alcance funcionen de acuerdo con las reglas de negocio definidas.
    
- Confirmar que los procesos de compras, ventas, créditos, abonos, devoluciones de ventas, cambio de productos, productos dañados y control de inventario operen correctamente.
    
- Comprobar que la actualización de existencias se realice de forma automática y consistente en cada operación que afecte el inventario.
    
- Validar la correcta administración de lotes y la aplicación del método FIFO para productos perecederos.
    
- Verificar que los cálculos relacionados con compras, ventas, créditos, abonos y pérdidas por productos dañados sean precisos.
    
- Confirmar que la información almacenada en la base de datos mantenga su integridad y consistencia durante la ejecución de las operaciones del sistema.
    
- Validar que los mecanismos de autenticación, gestión de usuarios y control de acceso funcionen conforme a los permisos definidos para cada rol.
    
- Detectar y documentar los defectos identificados durante el proceso de pruebas para su posterior corrección y seguimiento.
    
- Obtener evidencia suficiente que respalde los resultados de las pruebas ejecutadas.
    
- Garantizar que el sistema alcance un nivel adecuado de calidad y confiabilidad antes de su utilización en el entorno operativo de la Tienda y Librería Israel.

Asimismo, se espera que los resultados obtenidos permitan identificar oportunidades de mejora y contribuir a la reducción de riesgos operativos asociados al uso del sistema.

## 15. Conclusiones

El presente Plan de Pruebas establece las actividades, estrategias, criterios y lineamientos necesarios para validar el correcto funcionamiento del Sistema de Administración y Control Inventario (SACI) antes de su implementación en la Tienda y Librería Israel.

La ejecución de las pruebas definidas permitirá verificar que los módulos de inventario, compras, ventas, créditos, abonos, control de lotes, productos dañados, proveedores, usuarios y demás funcionalidades del sistema operen de acuerdo con los requisitos establecidos y las reglas de negocio definidas durante el análisis y diseño del proyecto.

Asimismo, el proceso de pruebas contribuirá a la detección temprana de defectos, inconsistencias y posibles riesgos operativos que puedan afectar la confiabilidad de la información o el desarrollo normal de las actividades del negocio. Esto permitirá realizar las correcciones necesarias antes de que el sistema sea utilizado en un entorno real.

Mediante la aplicación de pruebas funcionales, de integración, seguridad, validación de datos, regresión y aceptación, se busca garantizar la calidad del software, la integridad de la información almacenada y la correcta interacción entre los diferentes módulos que conforman SACI.

Finalmente, este Plan de Pruebas constituye una herramienta fundamental para asegurar que el sistema cumpla con las necesidades operativas de la Tienda y Librería Israel, proporcionando una base sólida para su implementación, mantenimiento y futura evolución.
