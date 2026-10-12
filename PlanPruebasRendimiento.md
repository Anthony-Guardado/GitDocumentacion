# Plan de Pruebas de Rendimiento

## 1. Introducción

El rendimiento de un sistema informático constituye un factor fundamental para garantizar una experiencia de uso eficiente y una adecuada ejecución de los procesos operativos del negocio. A medida que la cantidad de información almacenada aumenta, las consultas, búsquedas, filtros y reportes pueden verse afectados si no se implementan mecanismos adecuados de optimización y acceso a los datos.

El presente Plan de Pruebas de Rendimiento tiene como finalidad evaluar el comportamiento del Sistema de Administración y Control Inventario (SACI) ante volúmenes de información representativos del entorno operativo de la Tienda y Librería Israel. Estas pruebas permitirán verificar que las operaciones más utilizadas por los usuarios mantengan tiempos de respuesta adecuados y que los recursos disponibles sean utilizados de manera eficiente.

Las actividades de validación estarán orientadas principalmente al análisis del rendimiento de consultas, búsquedas, filtros, paginación, generación de reportes y acceso a la información almacenada en PostgreSQL, así como a la identificación de posibles oportunidades de optimización en las consultas implementadas mediante Laravel, Eloquent ORM y Query Builder, según la naturaleza de cada proceso evaluado.

Asimismo, este documento servirá como guía para la planificación, ejecución y seguimiento de las pruebas de rendimiento, permitiendo documentar los resultados obtenidos y establecer criterios objetivos para evaluar el desempeño general de SACI antes de su implementación en un entorno de producción.

## 2. Objetivos de las pruebas de rendimiento

### Objetivo General

Verificar que el Sistema de Administración y Control Inventario (SACI) mantenga tiempos de respuesta adecuados y un comportamiento eficiente durante la ejecución de consultas, búsquedas, filtros, paginación y generación de reportes, utilizando volúmenes de datos representativos del entorno operativo de la Tienda y Librería Israel.

### Objetivos Específicos

- Evaluar el tiempo de respuesta de las consultas realizadas sobre los módulos principales del sistema utilizando conjuntos de datos representativos.
    
- Verificar el desempeño de los procesos de búsqueda y filtrado de información en los distintos módulos de SACI.
    
- Validar la eficiencia de los mecanismos de paginación implementados para la visualización de grandes volúmenes de registros.
    
- Comprobar que la generación de reportes mantenga tiempos de respuesta aceptables y una correcta recuperación de la información almacenada.
    
- Identificar consultas ineficientes, problemas de rendimiento o patrones de acceso a datos que puedan afectar la experiencia de uso del sistema.
    
- Evaluar el comportamiento de las relaciones implementadas mediante Eloquent ORM para detectar posibles problemas de consultas repetitivas o del tipo N+1.
    
- Verificar que la base de datos PostgreSQL responda de manera eficiente ante operaciones frecuentes de consulta y recuperación de información.
    
- Identificar oportunidades de optimización en el código de aplicación y en las consultas a la base de datos con el fin de mejorar el desempeño general de SACI.
    

## 3. Alcance

El presente Plan de Pruebas de Rendimiento comprende la evaluación del desempeño de las principales operaciones de consulta, búsqueda, filtrado, paginación y generación de reportes implementadas en el Sistema de Administración y Control Inventario (SACI).

Las pruebas estarán orientadas a verificar que el sistema mantenga tiempos de respuesta adecuados al operar con volúmenes de datos representativos del entorno operativo de la Tienda y Librería Israel, permitiendo identificar posibles oportunidades de optimización tanto en la aplicación desarrollada con Laravel como en la base de datos PostgreSQL.

Dentro del alcance de las pruebas de rendimiento se incluyen las siguientes operaciones:

- Consulta y paginación de productos.
    
- Búsqueda de productos por nombre.
    
- Búsqueda de marcas por nombre.
    
- Búsqueda de categorías por nombre.
    
- Filtrado de productos por categoría, marca y estado.
    
- Consulta y filtrado de compras.
    
- Consulta y filtrado de ventas.
    
- Consulta y filtrado de créditos.
    
- Consulta y filtrado de abonos.
    
- Consulta y filtrado de proveedores.
    
- Consulta y filtrado de lotes, incluyendo productos próximos a vencer.
    
- Consulta y filtrado de productos dañados.
    
- Consulta y filtrado de cambios de producto.
    
- Generación de reportes operativos y estadísticos mediante consultas optimizadas utilizando Query Builder sobre PostgreSQL.
    
- Recuperación de información relacionada mediante relaciones implementadas con Eloquent ORM.
    
- Procesos de acceso a datos que involucren múltiples tablas relacionadas.
    

Asimismo, se evaluará la eficiencia de las consultas ejecutadas por el sistema con el propósito de detectar posibles problemas de rendimiento asociados a consultas repetitivas, relaciones no optimizadas, ausencia de índices adecuados o recuperación innecesaria de información.

Las pruebas serán ejecutadas utilizando conjuntos de datos representativos generados para el entorno de pruebas, permitiendo simular condiciones cercanas a las que podrían presentarse durante la operación normal del sistema.

## 4. Fuera de alcance

El presente Plan de Pruebas de Rendimiento se encuentra orientado a la evaluación del desempeño de las operaciones implementadas en SACI mediante conjuntos de datos representativos del entorno operativo de la Tienda y Librería Israel.

Por tal motivo, no forman parte del alcance de este documento las pruebas de carga, estrés, escalabilidad, alta disponibilidad, recuperación ante desastres o cualquier evaluación que requiera infraestructura especializada o entornos de producción reales.

Asimismo, tampoco se contemplan pruebas avanzadas de seguridad informática ni evaluaciones sobre funcionalidades que no hayan sido implementadas en la versión actual del sistema.

Las actividades definidas en este documento se limitarán a la validación del rendimiento de consultas, búsquedas, filtros, paginación, generación de reportes y recuperación de información, con el propósito de identificar oportunidades de optimización en la aplicación y en la base de datos PostgreSQL.

## 5. Entorno de pruebas

El presente apartado describe las características del entorno utilizado para la ejecución de las pruebas de rendimiento de SACI. La información aquí documentada tiene como finalidad proporcionar contexto sobre las condiciones bajo las cuales fueron obtenidos los resultados de las pruebas.

Es importante señalar que las especificaciones de hardware y software descritas no representan los requisitos mínimos ni máximos para la ejecución del sistema. Su inclusión responde únicamente a la necesidad de documentar el entorno de evaluación utilizado durante el proceso de pruebas, permitiendo interpretar adecuadamente los resultados obtenidos y garantizar la trazabilidad de las actividades realizadas.

### 5.1. Hardware utilizado

Las pruebas de rendimiento serán ejecutadas utilizando el equipo de desarrollo disponible para el proyecto. Las especificaciones del hardware que será empleado durante la ejecución de las pruebas se presentan a continuación:

|Componente|Especificación|
|---|---|
|Procesador|AMD Ryzen 3 7320U with Radeon Graphics|
|Frecuencia base|2.40 GHz|
|Memoria RAM|8 GB DDR5 (7.24 GB utilizables)|
|Velocidad de memoria|5500 MT/s|
|Almacenamiento|SSD NVMe de 238 GB|
|Tarjeta gráfica|AMD Radeon Graphics Integrada|
|Arquitectura del sistema|64 bits|

Las pruebas serán realizadas localmente sobre este equipo con el propósito de evaluar el comportamiento de las consultas, búsquedas, filtros, paginación y generación de reportes implementados en SACI. Las características descritas permiten documentar el entorno de evaluación que será utilizado durante el proceso de pruebas y servirán como referencia para la interpretación de los resultados obtenidos posteriormente.

### 5.2. Software utilizado

Las pruebas de rendimiento serán ejecutadas utilizando el entorno de software empleado durante el desarrollo de SACI. La siguiente tabla presenta las herramientas y plataformas que formarán parte del entorno de evaluación:

|Software|Propósito|
|---|---|
|Windows 11 Pro 24H2|Sistema operativo utilizado para la ejecución de las pruebas.|
|Laravel|Framework utilizado para el desarrollo del sistema y ejecución de las funcionalidades evaluadas.|
|PHP|Lenguaje de programación y entorno de ejecución utilizado por Laravel.|
|PostgreSQL|Sistema gestor de base de datos utilizado para almacenar y consultar la información del sistema.|
|Visual Studio Code|Entorno de desarrollo utilizado para la revisión del código y análisis de posibles optimizaciones.|
|Postman|Herramienta utilizada para medir tiempos de respuesta y validar el comportamiento de los servicios API.|
|Brave|Navegador web utilizado para ejecutar pruebas sobre la interfaz de usuario del sistema.|

El software descrito anteriormente conformará el entorno base para la ejecución de las pruebas de rendimiento. Dichas herramientas permitirán evaluar el comportamiento de las consultas, búsquedas, filtros, paginación y generación de reportes implementados en SACI, así como identificar posibles oportunidades de optimización tanto en la aplicación como en la base de datos.

### 5.3. Configuración del entorno

Las pruebas de rendimiento serán ejecutadas en un entorno local de desarrollo, utilizando la misma arquitectura implementada para el funcionamiento de SACI.

La aplicación se encuentra estructurada bajo una arquitectura basada en API REST, donde el frontend consume los servicios proporcionados por el backend desarrollado en Laravel, mientras que PostgreSQL es utilizado como sistema gestor de base de datos para el almacenamiento y recuperación de la información.

La configuración utilizada para las pruebas estará compuesta por los siguientes elementos:

- Frontend conectado mediante peticiones HTTP a la API del sistema.
    
- Backend desarrollado con Laravel ejecutándose en entorno local.
    
- Base de datos PostgreSQL instalada y ejecutándose localmente.
    
- Comunicación entre frontend, backend y base de datos dentro del mismo entorno de pruebas.
    
- Conjunto de datos de prueba generado específicamente para la ejecución de las pruebas de rendimiento.
    
- Ausencia de usuarios concurrentes externos durante la ejecución de las mediciones.
    

Las pruebas serán realizadas inicialmente sobre los servicios API mediante Postman con el fin de evaluar el comportamiento del backend y de las consultas a la base de datos. Posteriormente, se efectuarán validaciones desde la interfaz de usuario para analizar el comportamiento integral de la aplicación y verificar que los tiempos de respuesta percibidos por el usuario se mantengan dentro de los criterios de aceptación definidos para el proyecto.

## 6. Datos de prueba

Las pruebas de rendimiento serán ejecutadas utilizando conjuntos de datos generados específicamente para el entorno de evaluación, con el propósito de simular distintos niveles de crecimiento de la información gestionada por la Tienda y Librería Israel.

La generación de datos será realizada mediante Laravel Seeders y Factories, permitiendo poblar la base de datos de forma controlada, reproducible y consistente para cada escenario de prueba.

Con el objetivo de analizar el comportamiento del sistema ante diferentes volúmenes de información, se utilizarán tres escenarios de crecimiento:

- **Escenario Bajo**: Representa una etapa inicial de utilización del sistema.
    
- **Escenario Medio**: Representa un crecimiento moderado de la operación.
    
- **Escenario Alto**: Representa un escenario de crecimiento considerable de la información almacenada.
    

Los volúmenes estimados para cada escenario serán los siguientes:

|Entidad|Escenario Bajo|Escenario Medio|Escenario Alto|
|---|---|---|---|
|Categorías|20|35|50|
|Marcas|20|35|50|
|Proveedores|50|100|200|
|Productos|1,000|3,000|5,000|
|Compras|1,000|2,000|3,000|
|Lotes|2,000|5,000|10,000|
|Ventas|2,000|5,000|10,000|
|Detalles de ventas|6,000|12,000|30,000|
|Créditos|300|600|1,000|
|Abonos|1,000|3,000|5,000|
|Devolución de venta|300|600|1,000|
|Detalle devolución de venta|900|1,800|4,000|
|Productos dañados|200|500|1,000|
|Cambio de producto|500|1,000|2,000|
|Notas|300|600|1,000|

La utilización de estos escenarios permitirá evaluar el comportamiento de consultas, búsquedas, filtros, paginación, relaciones entre entidades y generación de reportes conforme aumenta la cantidad de información almacenada en PostgreSQL.

Asimismo, los resultados obtenidos permitirán identificar posibles oportunidades de optimización en las consultas implementadas mediante Laravel y Eloquent ORM, verificando que el desempeño del sistema se mantenga dentro de los criterios de aceptación establecidos para el proyecto.

## 7. Métricas de aceptación

Las métricas de aceptación establecen los criterios que serán utilizados para evaluar los resultados obtenidos durante las pruebas de rendimiento de SACI. Estos criterios permitirán determinar si el sistema mantiene un desempeño adecuado al operar con diferentes volúmenes de información.

Los tiempos definidos se consideran aceptables para un sistema de administración de inventario, ventas y control de créditos orientado a las operaciones de la Tienda y Librería Israel.

|Operación evaluada|Tiempo máximo aceptable|
|---|---|
|Consultas simples (categorías, marcas, proveedores)|≤ 1 segundo|
|Consultas paginadas (productos, compras, ventas, créditos, proveedores)|≤ 2 segundos|
|Búsquedas y filtros|≤ 2 segundos|
|Recuperación de relaciones entre entidades|≤ 2 segundos|
|Consultas de lotes y control FIFO|≤ 3 segundos|
|Generación de reportes operativos|≤ 5 segundos|
|Generación de reportes estadísticos|≤ 5 segundos|
|Respuesta de endpoints API|≤ 2 segundos|

Los tiempos máximos establecidos fueron definidos considerando la naturaleza operativa de SACI y las buenas prácticas relacionadas con la experiencia de usuario en sistemas de gestión empresarial. Las operaciones de consulta, búsqueda y filtrado requieren respuestas rápidas debido a su uso frecuente durante las actividades diarias de la tienda, mientras que los procesos de generación de reportes admiten tiempos ligeramente superiores debido al procesamiento adicional de información que involucran.

Asimismo, los valores establecidos tienen como propósito servir como referencia para identificar posibles oportunidades de optimización y no representan límites absolutos de desempeño para futuros entornos de producción o infraestructuras de mayor capacidad.

Adicionalmente, durante la ejecución de las pruebas se verificará que:

- El sistema mantenga estabilidad durante la ejecución de las operaciones evaluadas.
    
- No se presenten errores relacionados con consultas, recuperación de datos o generación de reportes.
    
- Las operaciones evaluadas mantengan tiempos de respuesta consistentes entre los distintos escenarios de crecimiento definidos para las pruebas.
    
- El incremento de información en la base de datos no provoque degradaciones significativas que afecten la experiencia de uso del sistema.
    

El cumplimiento de las métricas establecidas permitirá considerar que SACI posee un desempeño adecuado para su utilización en el entorno operativo previsto para la Tienda y Librería Israel.

## 8. Estrategia de pruebas

La estrategia de pruebas de rendimiento para SACI estará orientada a evaluar el comportamiento del sistema ante diferentes volúmenes de información almacenada en la base de datos, utilizando los escenarios de crecimiento definidos en el presente documento.

Las pruebas serán ejecutadas de manera progresiva, iniciando con operaciones de baja complejidad y avanzando posteriormente hacia procesos que involucren consultas más extensas, relaciones entre entidades y generación de reportes.

Para cada fase se analizarán los tiempos de respuesta obtenidos y se compararán con las métricas de aceptación establecidas. Las consultas operativas serán evaluadas principalmente mediante Eloquent ORM, mientras que los procesos de generación de reportes utilizarán Query Builder con el propósito de optimizar la recuperación y consolidación de información proveniente de múltiples tablas relacionadas.

La evaluación se realizará inicialmente sobre los servicios API mediante Postman y posteriormente desde la interfaz de usuario, con el propósito de verificar tanto el rendimiento interno del sistema como la experiencia percibida por el usuario final.

Las pruebas se desarrollarán en cuatro fases que abarcan los principales procesos de consulta y recuperación de información implementados en SACI.

### 8.1 Escenarios de ejecución

Con el propósito de evaluar el comportamiento de SACI ante diferentes volúmenes de información, todas las pruebas de rendimiento serán ejecutadas utilizando los escenarios de crecimiento definidos en el apartado de Datos de Prueba.

Los escenarios considerados son los siguientes:

#### Escenario Bajo

Representa una etapa inicial de utilización del sistema, en la que la cantidad de registros almacenados es relativamente reducida y las operaciones diarias presentan una carga baja de información.

#### Escenario Medio

Representa un crecimiento moderado de la información almacenada, permitiendo evaluar el comportamiento del sistema bajo condiciones más cercanas a una operación constante y sostenida.

#### Escenario Alto

Representa un escenario de crecimiento considerable de la base de datos, permitiendo verificar la capacidad del sistema para mantener tiempos de respuesta adecuados ante un volumen significativamente mayor de registros.

La ejecución de las pruebas en los tres escenarios permitirá analizar la escalabilidad del sistema y determinar si el incremento de información genera degradaciones significativas en el rendimiento de las consultas y procesos evaluados.

### 8.2 Método de ejecución

Las pruebas de rendimiento serán ejecutadas siguiendo una metodología gradual que permita evaluar tanto el comportamiento interno del sistema como la experiencia percibida por el usuario final.

Inicialmente, cada operación será evaluada mediante los endpoints de la API utilizando Postman, con el objetivo de medir directamente los tiempos de respuesta del backend desarrollado en Laravel y las consultas ejecutadas sobre PostgreSQL.

Posteriormente, las mismas operaciones serán verificadas desde la interfaz de usuario desarrollada para SACI, permitiendo validar que los tiempos percibidos por el usuario final se mantengan dentro de los criterios de aceptación establecidos.

Durante la ejecución de las pruebas se registrarán los tiempos obtenidos para cada operación evaluada, considerando los escenarios Bajo, Medio y Alto definidos previamente. Los resultados serán comparados con las métricas de aceptación establecidas en este documento para determinar si el rendimiento del sistema es satisfactorio o si existen oportunidades de optimización.

En caso de identificarse consultas que no cumplan los tiempos esperados, se analizarán posibles estrategias de optimización relacionadas con el uso de Eloquent ORM, Query Builder, indexación de tablas en PostgreSQL y mejora de consultas específicas antes de realizar nuevas mediciones.

### Fase 1: Evaluación de consultas básicas

La primera fase de las pruebas de rendimiento estará enfocada en evaluar el comportamiento de las consultas correspondientes a las entidades maestras del sistema. Estas entidades representan información de apoyo utilizada por los diferentes módulos de SACI y constituyen la base para la ejecución de operaciones posteriores.

El propósito de esta fase es establecer una línea base de rendimiento que permita verificar la eficiencia de las consultas simples antes de evaluar procesos de mayor complejidad.

#### Objetivo de la fase

Verificar que las operaciones de consulta, búsqueda y recuperación de información relacionadas con categorías, marcas y proveedores mantengan tiempos de respuesta dentro de los criterios de aceptación definidos para el proyecto.

#### Operaciones a evaluar

- Consulta paginada de categorías.
    
- Búsqueda de categorías por nombre.
    
- Consulta paginada de marcas.
    
- Búsqueda de marcas por nombre.
    
- Consulta paginada de proveedores.
    
- Búsqueda de proveedores por nombre.
    

#### Criterio de aceptación

Cada una de las operaciones evaluadas deberá completar su ejecución en un tiempo igual o inferior a 1 segundo.

#### Resultados esperados

- Las consultas simples mantienen tiempos de respuesta inferiores a 1 segundo.
    
- No se presentan errores durante la recuperación de información.
    
- La paginación funciona correctamente en todos los escenarios evaluados.
    
- Las búsquedas devuelven resultados correctos y consistentes.
    
- El crecimiento de la información no genera degradaciones significativas en el rendimiento de las consultas.
    
- Se obtiene una línea base de rendimiento que servirá como referencia para las siguientes fases de evaluación.
    

### Fase 2: Evaluación de consultas operativas

La segunda fase de las pruebas de rendimiento estará orientada a evaluar el comportamiento de las consultas correspondientes a los módulos operativos principales de SACI. Estas consultas involucran un mayor volumen de información y relaciones entre múltiples entidades, por lo que representan una parte fundamental del desempeño general del sistema.

El propósito de esta fase es verificar que las operaciones de consulta y recuperación de información mantengan tiempos de respuesta adecuados conforme aumenta la cantidad de registros almacenados en la base de datos.

#### Objetivo de la fase

Evaluar el rendimiento de las consultas asociadas a los procesos de inventario, compras, ventas, créditos, abonos, lotes, productos dañados y cambios de producto, garantizando que los tiempos de respuesta se mantengan dentro de los criterios de aceptación establecidos.

#### Operaciones a evaluar

- Consulta paginada de productos.
    
- Consulta detallada de productos.
    
- Consulta paginada de compras.
    
- Consulta detallada de compras.
    
- Consulta paginada de ventas.
    
- Consulta detallada de ventas.
    
- Consulta paginada de créditos.
    
- Consulta detallada de créditos.
    
- Consulta paginada de abonos.
    
- Consulta de historial de abonos por crédito.
    
- Consulta paginada de lotes.
    
- Consulta de lotes asociados a un producto.
    
- Consulta paginada de productos dañados.
    
- Consulta detallada de productos dañados.
    
- Consulta paginada de cambios de producto.
    
- Consulta detallada de cambios de producto.
    

#### Criterio de aceptación

Las consultas operativas deberán completar su ejecución en un tiempo igual o inferior a 2 segundos.

Para las consultas relacionadas con lotes y control FIFO se aceptará un tiempo máximo de 3 segundos debido a la complejidad adicional de la información procesada.

#### Resultados esperados

- Las consultas operativas mantienen tiempos de respuesta dentro de los criterios de aceptación establecidos.
    
- Las relaciones entre entidades se recuperan correctamente sin generar degradaciones significativas en el rendimiento.
    
- El incremento del volumen de información no afecta de manera considerable la experiencia de uso del sistema.
    
- Los módulos de productos, compras, ventas, créditos, abonos, lotes, productos dañados y cambios de producto responden de forma consistente en los tres escenarios evaluados.
    
- Se identifican posibles oportunidades de optimización relacionadas con consultas, relaciones Eloquent e índices de base de datos.
    

### Fase 3: Evaluación de búsquedas, filtros y paginación

La tercera fase de las pruebas de rendimiento estará enfocada en evaluar el comportamiento de las operaciones de búsqueda, filtrado y paginación implementadas en los diferentes módulos de SACI. Estas funcionalidades son utilizadas frecuentemente por los usuarios para localizar información específica y gestionar grandes volúmenes de registros de forma eficiente.

El propósito de esta fase es verificar que las consultas mantengan tiempos de respuesta adecuados aun cuando la cantidad de información almacenada incremente significativamente.

#### Objetivo de la fase

Evaluar el rendimiento de las búsquedas, filtros y mecanismos de paginación implementados en los módulos operativos del sistema, garantizando que mantengan tiempos de respuesta aceptables y una experiencia de usuario adecuada.

#### Operaciones a evaluar

- Búsqueda de productos por nombre.
    
- Filtrado de productos por categoría.
    
- Filtrado de productos por marca.
    
- Paginación de productos.
    
- Búsqueda de proveedores por nombre.
    
- Paginación de proveedores.
    
- Búsqueda de compras por proveedor.
    
- Filtrado de compras por rango de fechas.
    
- Paginación de compras.
    
- Búsqueda de ventas por correlativo.
    
- Filtrado de ventas por rango de fechas.
    
- Paginación de ventas.
    
- Búsqueda de créditos por cliente.
    
- Filtrado de créditos por estado.
    
- Paginación de créditos.
    
- Consulta del historial de abonos asociado a un crédito.
    
- Filtrado de productos dañados por fecha.
    
- Paginación de productos dañados.
    
- Filtrado de cambios de producto por estado.
    
- Paginación de cambios de producto.
    
- Búsqueda de lotes por producto.
    
- Filtrado de lotes próximos a vencer.
    

#### Criterio de aceptación

Las operaciones de búsqueda, filtrado y paginación deberán completar su ejecución en un tiempo igual o inferior a 2 segundos.

#### Resultados esperados

- Las búsquedas retornan resultados correctos y consistentes.
    
- Los filtros aplicados muestran únicamente la información correspondiente a los criterios seleccionados.
    
- La paginación mantiene tiempos de respuesta estables independientemente del volumen de información.
    
- No se presentan degradaciones significativas al incrementar la cantidad de registros almacenados.
    
- La experiencia de navegación y consulta se mantiene fluida para el usuario final.
    
- Se identifican posibles oportunidades de optimización relacionadas con índices, filtros y consultas utilizadas por el sistema.
    

### Fase 4: Evaluación de reportes y consultas complejas

La cuarta fase de las pruebas de rendimiento estará orientada a evaluar el comportamiento de los reportes implementados en SACI. Estas operaciones requieren la consolidación de información proveniente de múltiples módulos del sistema, por lo que representan los procesos con mayor demanda de procesamiento y acceso a datos.

Con el objetivo de optimizar el rendimiento de estas operaciones, los reportes serán implementados mediante Query Builder sobre PostgreSQL, permitiendo construir consultas más eficientes para la recuperación y procesamiento de información.

#### Objetivo de la fase

Evaluar el rendimiento de los reportes del sistema, verificando que mantengan tiempos de respuesta adecuados aun cuando la base de datos alcance los escenarios de crecimiento definidos en el presente documento.

#### Operaciones a evaluar

- Generación del reporte general.
    
- Generación del reporte de ventas.
    
- Generación del reporte de compras.
    
- Generación del reporte de créditos.
    
- Generación del reporte de devoluciones de ventas.
    
- Generación del reporte de inventario.
    
- Generación del reporte de cambio de producto.
    
- Generación del reporte de productos dañados.
    
- Generación del reporte de cierre diario.
    
- Generación del reporte de productos próximos a vencer.
    

#### Criterio de aceptación

Los reportes deberán completar su ejecución en un tiempo igual o inferior a 5 segundos.

#### Resultados esperados

- Los reportes son generados correctamente y muestran información consistente.
    
- Los resultados obtenidos coinciden con la información almacenada en la base de datos.
    
- El crecimiento de la información no provoca degradaciones significativas en los tiempos de respuesta.
    
- Los procesos de consolidación de información mantienen un rendimiento estable en los diferentes escenarios evaluados.
    
- Las consultas implementadas mediante Query Builder aprovechan adecuadamente los recursos de PostgreSQL.
    
- Se identifican posibles oportunidades de optimización relacionadas con índices, agrupaciones, filtros y consolidación de datos.
    
- Los tiempos de generación de reportes permanecen dentro de los criterios de aceptación establecidos para el proyecto.
    

## 9. Casos de prueba de rendimiento

Los casos de prueba de rendimiento tienen como propósito evaluar el comportamiento de las consultas, búsquedas, filtros, paginación y reportes implementados en SACI bajo los diferentes escenarios de crecimiento definidos en el presente documento.

Cada caso de prueba permitirá registrar los tiempos de respuesta obtenidos durante la ejecución de las operaciones evaluadas y compararlos con los criterios de aceptación establecidos para determinar si el sistema mantiene un desempeño adecuado.

Para facilitar la organización y trazabilidad de las pruebas, los casos serán identificados mediante el prefijo CPR (Caso de Prueba de Rendimiento), seguido de un identificador numérico único.

Los resultados obtenidos servirán para identificar posibles oportunidades de optimización relacionadas con consultas, índices, relaciones implementadas mediante Eloquent ORM, Query Builder y configuraciones de PostgreSQL.

### Fase 1

|ID|Fase|Caso de prueba|Descripción|Escenarios|Tiempo esperado|Tiempo obtenido|Estado|
|---|---|---|---|---|---|---|---|
|CPR-001|Fase 1|Consulta paginada de categorías|Medir el tiempo de carga del listado paginado de categorías.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|
|CPR-002|Fase 1|Búsqueda de categorías por nombre|Medir el tiempo de respuesta de la búsqueda de categorías.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|
|CPR-003|Fase 1|Consulta paginada de marcas|Medir el tiempo de carga del listado paginado de marcas.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|
|CPR-004|Fase 1|Búsqueda de marcas por nombre|Medir el tiempo de respuesta de la búsqueda de marcas.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|
|CPR-005|Fase 1|Consulta paginada de proveedores|Medir el tiempo de carga del listado paginado de proveedores.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|
|CPR-006|Fase 1|Búsqueda de proveedores por nombre|Medir el tiempo de respuesta de la búsqueda de proveedores.|Bajo, Medio y Alto|≤ 1 s|Pendiente|Pendiente|

### Fase 2

|ID|Fase|Caso de prueba|Descripción|Escenarios|Tiempo esperado|Tiempo obtenido|Estado|
|---|---|---|---|---|---|---|---|
|CPR-007|Fase 2|Consulta paginada de productos|Medir el tiempo de carga del listado paginado de productos.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-008|Fase 2|Consulta detallada de productos|Medir el tiempo de carga de la información detallada de un producto junto con sus relaciones.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-009|Fase 2|Consulta paginada de compras|Medir el tiempo de carga del listado paginado de compras.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-010|Fase 2|Consulta detallada de compras|Medir el tiempo de recuperación del detalle completo de una compra.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-011|Fase 2|Consulta paginada de ventas|Medir el tiempo de carga del listado paginado de ventas.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-012|Fase 2|Consulta detallada de ventas|Medir el tiempo de recuperación del detalle completo de una venta.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-013|Fase 2|Consulta paginada de créditos|Medir el tiempo de carga del listado paginado de créditos.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-014|Fase 2|Consulta detallada de créditos|Medir el tiempo de recuperación del detalle completo de un crédito.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-015|Fase 2|Consulta paginada de abonos|Medir el tiempo de carga del listado paginado de abonos.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-016|Fase 2|Historial de abonos por crédito|Medir el tiempo de recuperación del historial de abonos asociado a un crédito.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-017|Fase 2|Consulta paginada de lotes|Medir el tiempo de carga del listado paginado de lotes.|Bajo, Medio y Alto|≤ 3 s|Pendiente|Pendiente|
|CPR-018|Fase 2|Consulta de lotes por producto|Medir el tiempo de recuperación de los lotes asociados a un producto.|Bajo, Medio y Alto|≤ 3 s|Pendiente|Pendiente|
|CPR-019|Fase 2|Consulta paginada de productos dañados|Medir el tiempo de carga del listado paginado de productos dañados.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-020|Fase 2|Consulta detallada de productos dañados|Medir el tiempo de recuperación de la información detallada de un producto dañado.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-021|Fase 2|Consulta paginada de cambios de producto|Medir el tiempo de carga del listado paginado de cambios de producto.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-022|Fase 2|Consulta detallada de cambios de producto|Medir el tiempo de recuperación de la información detallada de un cambio de producto.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|

### Fase 3

|ID|Fase|Caso de prueba|Descripción|Escenarios|Tiempo esperado|Tiempo obtenido|Estado|
|---|---|---|---|---|---|---|---|
|CPR-023|Fase 3|Búsqueda de productos por nombre|Medir el tiempo de respuesta de la búsqueda de productos por nombre.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-024|Fase 3|Filtrado de productos por categoría|Medir el tiempo de respuesta del filtrado de productos por categoría.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-025|Fase 3|Filtrado de productos por marca|Medir el tiempo de respuesta del filtrado de productos por marca.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-026|Fase 3|Paginación de productos|Medir el tiempo de carga de las páginas del listado de productos.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-027|Fase 3|Búsqueda de proveedores por nombre|Medir el tiempo de respuesta de la búsqueda de proveedores.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-028|Fase 3|Paginación de proveedores|Medir el tiempo de carga de las páginas del listado de proveedores.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-029|Fase 3|Búsqueda de compras por proveedor|Medir el tiempo de respuesta de la búsqueda de compras asociadas a un proveedor.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-030|Fase 3|Filtrado de compras por rango de fechas|Medir el tiempo de respuesta del filtrado de compras por fechas.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-031|Fase 3|Paginación de compras|Medir el tiempo de carga de las páginas del listado de compras.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-032|Fase 3|Búsqueda de ventas por correlativo|Medir el tiempo de respuesta de la búsqueda de ventas por correlativo.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-033|Fase 3|Filtrado de ventas por rango de fechas|Medir el tiempo de respuesta del filtrado de ventas por fechas.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-034|Fase 3|Paginación de ventas|Medir el tiempo de carga de las páginas del listado de ventas.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-035|Fase 3|Búsqueda de créditos por cliente|Medir el tiempo de respuesta de la consulta de créditos asociados a un cliente.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-036|Fase 3|Filtrado de créditos por estado|Medir el tiempo de respuesta del filtrado de créditos según su estado.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-037|Fase 3|Paginación de créditos|Medir el tiempo de carga de las páginas del listado de créditos.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-038|Fase 3|Historial de abonos asociado a un crédito|Medir el tiempo de recuperación del historial de abonos de un crédito.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-039|Fase 3|Filtrado de productos dañados por fecha|Medir el tiempo de respuesta del filtrado de productos dañados por fecha.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-040|Fase 3|Paginación de productos dañados|Medir el tiempo de carga de las páginas del listado de productos dañados.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-041|Fase 3|Filtrado de cambios de producto por estado|Medir el tiempo de respuesta del filtrado de cambios de producto por estado.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-042|Fase 3|Paginación de cambios de producto|Medir el tiempo de carga de las páginas del listado de cambios de producto.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-043|Fase 3|Búsqueda de lotes por producto|Medir el tiempo de respuesta de la búsqueda de lotes asociados a un producto.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|
|CPR-044|Fase 3|Filtrado de lotes próximos a vencer|Medir el tiempo de respuesta del filtrado de lotes próximos a vencer.|Bajo, Medio y Alto|≤ 2 s|Pendiente|Pendiente|

### Fase 4

|ID|Fase|Caso de prueba|Descripción|Escenarios|Tiempo esperado|Tiempo obtenido|Estado|
|---|---|---|---|---|---|---|---|
|CPR-045|Fase 4|Generación del reporte general|Medir el tiempo de generación del reporte general (compras, ventas y productos dañados).|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-046|Fase 4|Generación del reporte de ventas|Medir el tiempo de generación del reporte de ventas con filtros por fechas, tipo cliente, método de pago y estado.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-047|Fase 4|Generación del reporte de compras|Medir el tiempo de generación del reporte de compras con detalle de productos y lotes.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-048|Fase 4|Generación del reporte de créditos|Medir el tiempo de generación del reporte de créditos agrupado por cliente.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-049|Fase 4|Generación del reporte de devoluciones de ventas|Medir el tiempo de generación del reporte de devoluciones separando productos perfectos y dañados.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-050|Fase 4|Generación del reporte de inventario|Medir el tiempo de generación del reporte de inventario con filtros por sección, marca, categoría y estado.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-051|Fase 4|Generación del reporte de cambio de producto|Medir el tiempo de generación del reporte de cambio de producto separado por estado.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-052|Fase 4|Generación del reporte de productos dañados|Medir el tiempo de generación del reporte de productos dañados separado por origen.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-053|Fase 4|Generación del reporte de cierre diario|Medir el tiempo de generación del reporte consolidado de ventas del día por método de pago.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|
|CPR-054|Fase 4|Generación del reporte de productos próximos a vencer|Medir el tiempo de generación del reporte de productos perecederos cuyos lotes vencen en los próximos 15 días, con unificación de lotes duplicados.|Bajo, Medio y Alto|≤ 5 s|Pendiente|Pendiente|

## 10. Herramientas utilizadas

Para la ejecución, monitoreo y documentación de las pruebas de rendimiento del Sistema de Administración y Control Inventario (SACI), se utilizarán diversas herramientas que permitirán generar los datos de prueba, medir tiempos de respuesta, registrar resultados y analizar el comportamiento del sistema bajo diferentes volúmenes de información.

Las herramientas consideradas para el presente Plan de Pruebas de Rendimiento son las siguientes:

|Herramienta|Propósito|
|---|---|
|Laravel|Framework utilizado para ejecutar las funcionalidades y consultas evaluadas durante las pruebas.|
|PostgreSQL|Sistema gestor de base de datos utilizado para almacenar y procesar la información generada en los diferentes escenarios de prueba.|
|Laravel Factories|Generación automática de registros de prueba realistas para las entidades evaluadas durante las pruebas de rendimiento.|
|Laravel Seeders|Generación masiva de datos de prueba para poblar la base de datos en los escenarios Bajo, Medio y Alto definidos en este documento.|
|Laravel Eloquent ORM|Ejecución de consultas operativas y validación del comportamiento de las relaciones entre entidades.|
|Laravel Query Builder|Implementación y optimización de consultas complejas utilizadas en reportes y estadísticas.|
|Postman|Medición de tiempos de respuesta de los endpoints de la API y validación del rendimiento del backend.|
|Brave|Validación del comportamiento y tiempos de respuesta percibidos desde la interfaz de usuario.|
|Visual Studio Code|Revisión de código y análisis de posibles oportunidades de optimización durante la ejecución de las pruebas.|
|Google Sheets|Registro y seguimiento de los resultados obtenidos en cada caso de prueba de rendimiento.|
|Google Docs|Elaboración y documentación del Plan de Pruebas de Rendimiento y de los resultados obtenidos.|

### Uso de las herramientas

Las herramientas descritas anteriormente serán utilizadas durante las diferentes fases de las pruebas de rendimiento, permitiendo generar escenarios controlados de crecimiento de datos, medir tiempos de respuesta, registrar resultados y analizar el comportamiento general del sistema.

Asimismo, facilitarán la identificación de posibles oportunidades de optimización relacionadas con consultas, índices de base de datos, relaciones implementadas mediante Eloquent ORM y consultas complejas desarrolladas mediante Query Builder.

## 11. Resultados esperados

Al finalizar la ejecución de las pruebas de rendimiento definidas en el presente documento, se espera obtener evidencia objetiva sobre el comportamiento del Sistema de Administración y Control Inventario (SACI) bajo diferentes volúmenes de información almacenada en la base de datos.

Los resultados esperados son los siguientes:

- Las consultas simples correspondientes a categorías, marcas y proveedores mantienen tiempos de respuesta inferiores a los criterios de aceptación establecidos.
    
- Las consultas operativas relacionadas con productos, compras, ventas, créditos, abonos, lotes, productos dañados y cambios de producto presentan un comportamiento estable aun cuando la cantidad de registros almacenados aumente progresivamente.
    
- Las búsquedas, filtros y mecanismos de paginación mantienen tiempos de respuesta adecuados que permiten una experiencia de usuario fluida.
    
- Los reportes implementados mediante Query Builder generan la información requerida dentro de los tiempos establecidos para el proyecto.
    
- El crecimiento de la base de datos no provoca degradaciones significativas que afecten la operatividad normal del sistema.
    
- Las relaciones implementadas mediante Eloquent ORM utilizan adecuadamente mecanismos de optimización como Eager Loading para evitar consultas innecesarias y reducir el impacto del problema N+1.
    
- Los tiempos de respuesta obtenidos durante las pruebas permanecen dentro de los criterios de aceptación definidos para cada fase del presente plan.
    
- Se identifican oportunamente posibles oportunidades de optimización relacionadas con consultas, filtros, paginación, índices o generación de reportes.
    
- El sistema demuestra capacidad para operar de forma eficiente bajo los escenarios Bajo, Medio y Alto definidos en este documento.
    
- Los resultados obtenidos permiten validar que la arquitectura implementada en SACI es adecuada para el volumen de información proyectado para una microempresa comercial.
    

En caso de identificarse operaciones que no cumplan los criterios de aceptación establecidos, los resultados obtenidos servirán como base para la aplicación de acciones de optimización relacionadas con consultas SQL, Query Builder, Eloquent ORM, índices de PostgreSQL o mejoras en la estructura de acceso a datos.

## 12. Conclusiones

El presente Plan de Pruebas de Rendimiento establece una base metodológica clara para evaluar el comportamiento del Sistema de Administración y Control Inventario (SACI) bajo distintos volúmenes de información, permitiendo verificar si las operaciones implementadas responden de manera eficiente en el entorno operativo de la Tienda y Librería Israel.

La estructura definida para las pruebas de rendimiento facilita el análisis progresivo de las consultas básicas, las operaciones operativas, los mecanismos de búsqueda, filtrado y paginación, así como de los reportes desarrollados mediante Query Builder. Esto permite identificar de forma ordenada los puntos críticos del sistema y detectar posibles oportunidades de optimización.

Asimismo, la utilización de escenarios de crecimiento, junto con métricas de aceptación previamente definidas, proporciona criterios objetivos para valorar el desempeño del sistema y determinar si mantiene tiempos de respuesta adecuados conforme aumenta la cantidad de datos almacenados.

De igual manera, el uso de herramientas como Laravel, PostgreSQL, Laravel Factories, Laravel Seeders, Postman y Brave permite documentar y ejecutar las pruebas en un entorno controlado, garantizando trazabilidad en los resultados obtenidos y coherencia con la arquitectura implementada en SACI.

Finalmente, este Plan de Pruebas de Rendimiento constituye un apoyo fundamental para validar que el sistema posee una capacidad de respuesta adecuada para su uso, y sirve como referencia técnica para futuras mejoras en consultas, acceso a datos y generación de reportes.
