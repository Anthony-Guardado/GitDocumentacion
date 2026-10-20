# Parte precentacion Tony

## 3.1.14 Plan de pruebas: tipos de prueba y casos principales.
### Objetivos
#### Objetivo General
Verificar mediante la ejecución de pruebas que el Sistema de Administración y Control Inventario (SACI) funcione de acuerdo con los requisitos funcionales y reglas de negocio establecidos, garantizando la confiabilidad, integridad de todos los datos financieros o personales de los clientes y correcto desempeño de sus procesos antes de su implementación en la Tienda y Librería Israel.
#### Objetivos Espesificos
- Validar el correcto funcionamiento de los módulos que conforman el sistema, incluyendo inventario, compras, ventas, créditos, abonos, devoluciones de ventas, proveedores y gestión de usuarios.
- Comprobar que las reglas de negocio definidas para cada proceso se ejecuten de manera correcta, especialmente aquellas relacionadas con el control de inventario, manejo de lotes, ventas al crédito y registro de abonos.
- Reducir los riesgos operativos asociados a errores de software que puedan afectar los procesos de la Tienda y Librería Israel una vez que el sistema sea puesto en producción.


#### Alcance 
El alcance de las pruebas abarcó la validación funcional integral de todos los módulos de SACI, desde la seguridad y gestión de usuarios hasta el control de inventario, ventas, créditos, compras y reportes. El objetivo principal fue comprobar el estricto cumplimiento de las reglas de negocio críticas —como el control FIFO, la actualización automática de existencias y el manejo financiero— garantizando la total integridad y consistencia de los datos en cada operación de la tienda y librería.
#### Fuera Alcance
El plan se enfocó netamente en la validación funcional y de reglas de negocio. Quedaron fuera las pruebas de estrés extremo, alta disponibilidad y ciberseguridad avanzada (pentesting), ya que requieren infraestructuras especializadas fuera del entorno de desarrollo. Sin embargo, como valor agregado a la calidad, se realizaron pruebas de rendimiento básicas en un plan complementario para garantizar la eficiencia de la base de datos y las consultas.
#### Tipos de pruebas
#####  Descripción de los tipos de pruebas
Antes de ejecutar las pruebas sobre los distintos módulos de SACI, es necesario definir el propósito de cada tipo de prueba que será utilizado durante el proceso de validación del sistema.

| Tipo de prueba      | Descripción                                                                                                                                                             |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Funcional           | Verifica que cada funcionalidad del sistema opere de acuerdo con los requisitos y reglas de negocio establecidos.                                                       |
| Integración         | Evalúa la interacción entre dos o más módulos del sistema para asegurar que intercambien información correctamente y mantengan la consistencia de los datos.            |
| Seguridad           | Comprueba los mecanismos de autenticación, autorización y control de acceso, garantizando que cada usuario solo pueda acceder a las funciones permitidas según su rol.  |
| Validación de datos | Verifica la integridad, consistencia y exactitud de la información almacenada y procesada por el sistema.                                                               |
| Regresión           | Se ejecuta después de realizar correcciones o mejoras para confirmar que los cambios implementados no afecten funcionalidades que anteriormente operaban correctamente. |
| Aceptación          | Permite validar que el sistema cumple las necesidades y expectativas del usuario final antes de su puesta en producción.                                                |
### Gestion de bugs
 La gestión de bugs tiene como finalidad identificar, registrar, clasificar, dar seguimiento y verificar la corrección de los defectos detectados durante el proceso de pruebas del Sistema; Todo error identificado durante la ejecución de pruebas deberá ser documentado de forma adecuada para facilitar su análisis, corrección y posterior validación. Este proceso permitirá mantener la trazabilidad de las incidencias y garantizar la calidad de las funcionalidades implementadas.
#### Clasificación de bugs
Los defectos serán clasificados según su nivel de impacto sobre el funcionamiento del sistema.

| Prioridad | Descripción                                                                                                 |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| Crítica   | Error que impide la operación normal del sistema o genera pérdida de información importante.                |
| Alta      | Error que afecta una funcionalidad principal del sistema, pero permite continuar parcialmente la operación. |
| Media     | Error que afecta funcionalidades secundarias sin impedir la continuidad del trabajo.                        |
| Baja      | Error visual, de formato o comportamiento menor que no afecta significativamente la operación del sistema.  |

#### Estados de los bugs
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

### Herramientas utilizadas
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
#### Criterios de entrada
Para iniciar el proceso de pruebas, se exigió un entorno 100% controlado. Esto incluyó: sistema desplegado, base de datos PostgreSQL integrada y poblada con datos de prueba representativos, módulos completamente implementados, usuarios y roles configurados (Admin/Vendedor), herramientas de validación listas y la aprobación formal del plan. Nada se probó sin antes asegurar estas condiciones.
#### Criterios de salida
Consideramos las pruebas como finalizadas exitosamente tras cumplir 7 condiciones clave: ejecución total de casos, documentación de resultados, clasificación de incidencias, corrección y verificación de fallos críticos, pruebas de regresión, recolección de evidencias y la confirmación de un sistema estable y alineado a los requerimientos del negocio.
#### Resultados esperados
Los resultados esperados se centraron en 4 pilares:

1. **Exactitud:** Cálculos financieros y de inventario 100% precisos.
    
2. **Integridad:** Actualización de stock automática y consistente (FIFO).
    
3. **Seguridad:** Control de acceso estricto por roles.
    
4. **Confiabilidad:** Detección temprana de fallos, recolección de evidencias y garantía de un software estable y listo para producción.
#### Conclusion

- **Validación Integral:** Se comprobó el correcto funcionamiento de todos los módulos (inventario, ventas, compras, etc.) frente a los requisitos y reglas de negocio.
    
- **Mitigación de Riesgos:** Permitió detectar y corregir fallos tempranos, asegurando la integridad de los datos financieros.
    
- **Garantía de Calidad:** La aplicación de múltiples tipos de pruebas (seguridad, regresión, integración) asegura un software confiable.
    
- **Base para el Futuro:** Proporciona una estructura sólida para la implementación, mantenimiento y evolución del sistema en la tienda.

- https://docs.google.com/spreadsheets/d/1hHmjK2Ks9RlwG2Vjg6rTNLfZ4L9AWA0y/edit?usp=sharing&ouid=110986543859065183212&rtpof=true&sd=true

### Capítulo IV. Análisis de resultados.
#### 4.1 Cumplimiento de objetivos: cada objetivo específico con su evidencia.
El sistema SACI cumple cabalmente con los objetivos planteados, demostrado a través de la aprobación del 100% de las 161 pruebas funcionales. A nivel general, se consolida como una solución integral que automatiza las ventas, sistematiza el inventario y centraliza la administración financiera. Específicamente, el control de inventario se logra mediante actualizaciones automáticas en tiempo real, el manejo estricto del método FIFO y herramientas de ajuste; la automatización de ventas se evidencia en la generación de tickets y el cálculo exacto de vueltos, eliminando el error humano; y la gestión financiera se cumple al integrar el control de créditos, abonos, cierres de caja diarios y reportes de ganancias exactas. Con esto, el sistema resuelve la dependencia de procesos manuales, garantizando precisión total y control operativo para la Tienda y Librería Israel.

#### 4.2 Evaluación del sistema: resultados de encuestas o satisfacción de usuarios.
La evaluación del sistema se realizó mediante una triangulación entre los requerimientos, las pruebas ejecutadas y los resultados obtenidos, demostrando que SACI cumple con el 100% de los 17 requerimientos funcionales y los 6 no funcionales. Funcionalmente, se garantizó la integridad financiera y de inventario absoluta (sin vacíos), el respeto a las reglas de negocio críticas y una tasa de éxito del 100% en las 157 pruebas ejecutadas. Técnicamente, el sistema demostró un rendimiento sobresaliente en las operaciones diarias (milisegundos) y altos estándares de seguridad y respaldo. Aunque se identificó un límite físico en la generación de reportes masivos (por consumo de RAM al generar PDFs de más de 147 páginas en escenarios de estrés), se concluyó que esto no afecta la lógica del negocio ni el uso real de la microempresa, confirmando que el sistema es confiable, seguro y está listo para su implementación.
#### 4.3 Resultados de pruebas: casos ejecutados y su resultado.
##### Prueba funcional
 CP-121 — Generar reporte general con compras, ventas y dañados

**Precondición:** Existen registros en el período

**Datos de entrada:** Rango de fechas válido

**Pasos:** Generar reporte

**Resultado esperado:** El reporte muestra secciones de compras, ventas y productos dañados, con sus totales

 **Resultados obtenidos**

El reporte muestra correctamente estas secciones con sus totals validos.

**Estado**

Aprobado

**Evidencia**

Tablas

<img width="274" height="247" alt="image" src="https://github.com/user-attachments/assets/1359795a-3779-42f4-8f70-e25e64100fba" />
<img width="467" height="243" alt="image" src="https://github.com/user-attachments/assets/c6c9b768-6c8a-44b6-99ab-488c45eece7f" />
<br/>
Totales
<br/>
<img width="705" height="219" alt="image" src="https://github.com/user-attachments/assets/96845634-dcfb-48d5-a1b0-aa3859b5a9ac" />
##### Prueba de rendimiento
| Entidad<br>                 | Escenario Bajo | Escenario Medio | Escenario Alto |
| :-------------------------- | -------------- | --------------- | -------------- |
| Categorías                  | 20             | 35              | 50             |
| Marcas                      | 20             | 35              | 50             |
| Proveedores                 | 50             | 100             | 200            |
| Productos                   | 1,000          | 3,000           | 5,000          |
| Compras                     | 1,000          | 2,000           | 3,000          |
| Lotes                       | 2,000          | 5,000           | 10,000         |
| Ventas                      | 2,000          | 5,000           | 10,000         |
| Detalles de ventas          | 6,000          | 12,000          | 30,000         |
| Créditos                    | 300            | 600             | 1,000          |
| Abonos                      | 1,000          | 3,000           | 5,000          |
| Devolución de venta         | 300            | 600             | 1,000          |
| Detalle devolución de venta | 900            | 1,800           | 4,000          |
| Productos dañados           | 200            | 500             | 1,000          |
| Cambio de producto          | 500            | 1,000           | 2,000          |
| Notas                       | 300            | 600             | 1,000          |
 CPR-011 — Consulta paginada de ventas

**Descripción:** Medir el tiempo de carga del listado paginado de ventas.

**Tiempo esperado:** ≤ 2 s

| Escenario | Tiempo obtenido | Estado   | Observaciones |
| --------- | --------------- | -------- | ------------- |
| Bajo      | 0,27 s          | Aprobado |               |
| Medio     | 0,27 s          | Aprobado |               |
| Alto      | 0,24 s          | Aprobado |               |

CPR-012 — Consulta detallada de ventas

**Descripción:** Medir el tiempo de recuperación del detalle completo de una venta.

**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo|0,12 s|Aprobado||
|Medio|0,13 s|Aprobado||
|Alto|0,13 s|Aprobado||
#### 4.4 Comparación con lo planificado: tiempo y costo real frente al estimado.
 **Comparación: Tiempo y Costo Real vs Estimado**

- **Alcance:** Se estimó cubrir 17 requerimientos. En la realidad, se entregó el 100% de ellos + 7 funcionalidades extra (Cambio de producto, Ajustes, etc.).
    
- **Esfuerzo/Tiempo real:** El tiempo de desarrollo fue mayor al estimado inicialmente debido a la ampliación del alcance (más módulos y validaciones complejas como el método FIFO y validación de DUI).
    
- **Costo/Beneficio:** Aunque el esfuerzo real superó lo planificado, se tradujo en un software robusto, sin vacíos financieros y con estándares internacionales, evitando gastos futuros en correcciones o pérdidas de inventario.
    
- **Resultado:** Un sistema que no solo cumplió, sino que **superó las expectativas**, entregando un valor agregado al negocio.
