# Formato de Registro de Resultados de Pruebas de Rendimiento

## Datos Generales

**Proyecto:** Sistema de Administración y Control de Inventario (SACI)  
**Empresa:** Tienda y Librería Israel  
**Documento:** Resultados de Pruebas de Rendimiento  
**Versión del sistema evaluada:** [Indicar versión o commit]  
**Fecha de ejecución:** [dd/mm/aaaa]  
**Responsable de ejecución:** [Nombre del responsable]  
**Entorno utilizado:** Local — AMD Ryzen 3 7320U, 8 GB RAM, SSD NVMe, Windows 11 Pro 24H2  
**Herramientas utilizadas:** Laravel, PostgreSQL, Postman, Brave, VS Code, Google Sheets

## Objetivo del Documento

Registrar los tiempos de respuesta obtenidos durante la ejecución de las pruebas de rendimiento definidas en el Plan de Pruebas de Rendimiento de SACI, comparándolos con las métricas de aceptación establecidas, con el fin de documentar el desempeño del sistema y las observaciones detectadas.

## Metodología de Registro

- Cada caso de prueba se ejecutará en los tres escenarios definidos: **Bajo**, **Medio** y **Alto**.
    
- Se registrarán los tiempos obtenidos en cada escenario.
    
- Se compararán los resultados con el tiempo máximo aceptable definido por fase.
    
- Se anotarán las observaciones correspondientes en caso de presentar desviaciones.
    
- El estado se marcará como:
    
    - **Aprobado:** El tiempo está dentro del rango aceptable.
        
    - **Revisar:** El tiempo está en el límite o cerca del máximo permitido.
        
    - **Fallido:** El tiempo supera el máximo aceptable o se presenta un error.
        

## Resumen General de Cumplimiento

|Fase|Casos Totales|Aprobados|A Revisar|Fallidos|Cumplimiento|
|---|---|---|---|---|---|
|Fase 1 — Consultas básicas|6|||||
|Fase 2 — Consultas operativas|14|||||
|Fase 3 — Búsquedas, filtros y paginación|20|||||
|Fase 4 — Reportes|10|||||
|**Total**|**50**|||||

---

# Fase 1: Evaluación de Consultas Básicas

**Criterio de aceptación:** Cada operación debe completarse en un tiempo ≤ 1 segundo.

## CPR-001 — Consulta paginada de categorías

**Descripción:** Medir el tiempo de carga del listado paginado de categorías.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-002 — Búsqueda de categorías por nombre

**Descripción:** Medir el tiempo de respuesta de la búsqueda de categorías.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-003 — Consulta paginada de marcas

**Descripción:** Medir el tiempo de carga del listado paginado de marcas.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-004 — Búsqueda de marcas por nombre

**Descripción:** Medir el tiempo de respuesta de la búsqueda de marcas.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-005 — Consulta paginada de proveedores

**Descripción:** Medir el tiempo de carga del listado paginado de proveedores.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-006 — Búsqueda de proveedores por nombre

**Descripción:** Medir el tiempo de respuesta de la búsqueda de proveedores.  
**Tiempo esperado:** ≤ 1 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

---

# Fase 2: Evaluación de Consultas Operativas

**Criterio de aceptación:** Las operaciones deben completarse en un tiempo ≤ 2 segundos, excepto las consultas de lotes y FIFO que admiten ≤ 3 segundos.

## CPR-007 — Consulta paginada de productos

**Descripción:** Medir el tiempo de carga del listado paginado de productos.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-008 — Consulta detallada de productos

**Descripción:** Medir el tiempo de carga de la información detallada de un producto junto con sus relaciones.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-009 — Consulta paginada de compras

**Descripción:** Medir el tiempo de carga del listado paginado de compras.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-010 — Consulta detallada de compras

**Descripción:** Medir el tiempo de recuperación del detalle completo de una compra.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-011 — Consulta paginada de ventas

**Descripción:** Medir el tiempo de carga del listado paginado de ventas.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-012 — Consulta detallada de ventas

**Descripción:** Medir el tiempo de recuperación del detalle completo de una venta.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-013 — Consulta paginada de créditos

**Descripción:** Medir el tiempo de carga del listado paginado de créditos.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-014 — Consulta detallada de créditos

**Descripción:** Medir el tiempo de recuperación del detalle completo de un crédito.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-015 — Consulta paginada de abonos

**Descripción:** Medir el tiempo de carga del listado paginado de abonos.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-016 — Historial de abonos por crédito

**Descripción:** Medir el tiempo de recuperación del historial de abonos asociado a un crédito.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-017 — Consulta paginada de productos dañados

**Descripción:** Medir el tiempo de carga del listado paginado de productos dañados.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-018 — Consulta detallada de productos dañados

**Descripción:** Medir el tiempo de recuperación de la información detallada de un producto dañado.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-019 — Consulta paginada de cambios de producto

**Descripción:** Medir el tiempo de carga del listado paginado de cambios de producto.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-020 — Consulta detallada de cambios de producto

**Descripción:** Medir el tiempo de recuperación de la información detallada de un cambio de producto.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

---

# Fase 3: Evaluación de Búsquedas, Filtros y Paginación

**Criterio de aceptación:** Las operaciones deben completarse en un tiempo ≤ 2 segundos.

## CPR-021 — Búsqueda de productos por nombre

**Descripción:** Medir el tiempo de respuesta de la búsqueda de productos por nombre.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-022 — Filtrado de productos por categoría

**Descripción:** Medir el tiempo de respuesta del filtrado de productos por categoría.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-023 — Filtrado de productos por marca

**Descripción:** Medir el tiempo de respuesta del filtrado de productos por marca.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-024 — Paginación de productos

**Descripción:** Medir el tiempo de carga de las páginas del listado de productos.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-025 — Búsqueda de proveedores por nombre

**Descripción:** Medir el tiempo de respuesta de la búsqueda de proveedores.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-026 — Paginación de proveedores

**Descripción:** Medir el tiempo de carga de las páginas del listado de proveedores.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-027 — Filtrado de compras por rango de fechas

**Descripción:** Medir el tiempo de respuesta del filtrado de compras por fechas.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-028 — Paginación de compras

**Descripción:** Medir el tiempo de carga de las páginas del listado de compras.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-029 — Filtrado de ventas por rango de fechas

**Descripción:** Medir el tiempo de respuesta del filtrado de ventas por fechas.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-030 — Paginación de ventas

**Descripción:** Medir el tiempo de carga de las páginas del listado de ventas.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-031 — Búsqueda de créditos por cliente

**Descripción:** Medir el tiempo de respuesta de la consulta de créditos asociados a un cliente.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-032 — Filtrado de créditos por estado

**Descripción:** Medir el tiempo de respuesta del filtrado de créditos según su estado.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-033 — Paginación de créditos

**Descripción:** Medir el tiempo de carga de las páginas del listado de créditos.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-034 — Historial de abonos asociado a un crédito

**Descripción:** Medir el tiempo de recuperación del historial de abonos de un crédito.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-035 — Filtrado de productos dañados por fecha

**Descripción:** Medir el tiempo de respuesta del filtrado de productos dañados por fecha.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-036 — Paginación de productos dañados

**Descripción:** Medir el tiempo de carga de las páginas del listado de productos dañados.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-037 — Filtrado de cambios de producto por estado

**Descripción:** Medir el tiempo de respuesta del filtrado de cambios de producto por estado.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-038 — Paginación de cambios de producto

**Descripción:** Medir el tiempo de carga de las páginas del listado de cambios de producto.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-039 — Búsqueda de lotes por producto

**Descripción:** Medir el tiempo de respuesta de la búsqueda de lotes asociados a un producto.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-040 — Filtrado de lotes próximos a vencer

**Descripción:** Medir el tiempo de respuesta del filtrado de lotes próximos a vencer.  
**Tiempo esperado:** ≤ 2 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

---

# Fase 4: Evaluación de Reportes y Consultas Complejas

**Criterio de aceptación:** Los reportes deben generarse en un tiempo ≤ 5 segundos.

## CPR-041 — Reporte general

**Descripción:** Medir el tiempo de generación del reporte general (compras, ventas y productos dañados).  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-042 — Reporte de ventas

**Descripción:** Medir el tiempo de generación del reporte de ventas con filtros por fechas, tipo cliente, método de pago y estado.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-043 — Reporte de compras

**Descripción:** Medir el tiempo de generación del reporte de compras con detalle de productos y lotes.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-044 — Reporte de créditos

**Descripción:** Medir el tiempo de generación del reporte de créditos agrupado por cliente.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-045 — Reporte de devoluciones de ventas

**Descripción:** Medir el tiempo de generación del reporte de devoluciones separando productos perfectos y dañados.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-046 — Reporte de inventario

**Descripción:** Medir el tiempo de generación del reporte de inventario con filtros por sección, marca, categoría y estado.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-047 — Reporte de cambio de producto

**Descripción:** Medir el tiempo de generación del reporte de cambio de producto separado por estado.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-048 — Reporte de productos dañados

**Descripción:** Medir el tiempo de generación del reporte de productos dañados separado por origen.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-049 — Reporte de cierre diario

**Descripción:** Medir el tiempo de generación del reporte consolidado de ventas del día por método de pago.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

## CPR-050 — Reporte de productos próximos a vencer

**Descripción:** Medir el tiempo de generación del reporte de productos perecederos cuyos lotes vencen en los próximos 15 días, con unificación de lotes duplicados.  
**Tiempo esperado:** ≤ 5 s

|Escenario|Tiempo Obtenido|Estado|Observaciones|
|---|---|---|---|
|Bajo||||
|Medio||||
|Alto||||

---

# Observaciones y Hallazgos

## Observaciones Generales

- [Anotar cualquier observación detectada durante la ejecución de las pruebas]
    

## Incidencias Detectadas

|ID|Caso afectado|Descripción|Prioridad|Estado|
|---|---|---|---|---|
||||||

## Recomendaciones

- [Anotar recomendaciones de optimización, ajustes necesarios o mejoras sugeridas]
    

---

# Conclusiones

- Los resultados obtenidos demuestran que el sistema [cumple / no cumple] con las métricas de aceptación definidas en el Plan de Pruebas de Rendimiento.
    
- Se identificaron [cantidad] casos que requieren revisión u optimización.
    
- Se confirma que el sistema mantiene un desempeño adecuado bajo los escenarios Bajo, Medio y Alto definidos para una microempresa comercial.
    
- [Agregar conclusiones específicas según los resultados obtenidos]
    

---

**Elaborado por:** [Nombre]  
**Revisado por:** [Nombre]  
**Fecha de entrega:** [dd/mm/aaaa]
