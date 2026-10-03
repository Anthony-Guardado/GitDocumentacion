El presente apartado tiene como finalidad demostrar, mediante evidencia funcional respaldada por los resultados de las pruebas ejecutadas, que el sistema SACI cumple con el objetivo general y los objetivos específicos definidos en la fase de investigación del proyecto. La verificación se apoya en la Matriz de Casos de Prueba, donde cada objetivo se relaciona con requerimientos funcionales, no funcionales y casos de prueba que fueron ejecutados y aprobados.

## Objetivo General

**Implementar un sistema integral de gestión comercial que automatice los procesos de ventas, sistematice el control de inventarios y centralice la administración financiera, con el fin de optimizar la eficiencia operativa y fortalecer la organización económica del negocio.**

El sistema SACI integra en una sola plataforma los módulos de ventas, inventario, compras, créditos, abonos, devoluciones, productos dañados, cambio de producto, proveedores, cronograma, notas, reportes y ajuste de inventario. La totalidad de las 161 pruebas funcionales ejecutadas fueron aprobadas, evidenciando que el sistema cubre de forma integral los procesos operativos y financieros de la Tienda y Librería Israel, cumpliendo con el objetivo general planteado.

## Objetivo Específico 1

**Sistematizar el control de inventarios mediante un registro digital de entradas y salidas de productos para conocer las existencias en tiempo real y optimizar la reposición de artículos con los proveedores.**

### Requerimientos funcionales asociados

|ID|Requerimiento|
|---|---|
|RF06|Gestión y Registro de Productos|
|RF07|Control de Vencimiento de Productos|
|RF08|Alerta de Stock Mínimo|
|RF09|Registro de Compras|
|RF14|Gestión de Proveedores|
|RF17|Gestión de Productos Dañados|

### Requerimientos no funcionales asociados

|ID|Requerimiento|
|---|---|
|RNF01|Tiempo de respuesta|
|RNF03|Notificación de fallo durante la transacción|
|RNF06|Interfaz responsiva|

### Casos de prueba que evidencian el cumplimiento

|Fase|Casos|Estado|
|---|---|---|
|Fase 2 — Inventario|CP-012 a CP-036|Aprobados|
|Fase 3 — Compras y Lotes|CP-037 a CP-057|Aprobados|
|Fase 5 — Complementarios|CP-101 a CP-108|Aprobados|
|Fase 6 — Reportes|CP-135 a CP-137, CP-141, CP-142, CP-147 a CP-157, CP-159 a CP-161|Aprobados|

### Evidencia del cumplimiento

- **Registro digital de productos**: se validó el registro de productos normales y perecederos con todos sus atributos (nombre, precios, sección, categoría, marca, stock, lote), así como las validaciones de campos obligatorios, stock negativo, stock decimal y coherencia de precios (CP-020 a CP-025).
    
- **Control de existencias en tiempo real**: cada operación (compra, venta, devolución, ajuste, anulación) actualiza automáticamente el stock del producto y del lote, reflejándose de inmediato en la base de datos y en los reportes (CP-031, CP-052, CP-068, CP-088, CP-094, CP-095).
    
- **Manejo de productos perecederos y lotes**: se validó el registro de múltiples lotes por producto, la aplicación del método FIFO en ventas, la reactivación de lotes al devolverse productos perfectos y la inactivación automática al agotarse (CP-026, CP-027, CP-036, CP-054, CP-055, CP-088, CP-095).
    
- **Alertas de stock mínimo**: el sistema genera alertas visuales en el panel principal para productos cuyo stock es igual o menor al stock mínimo definido (CP-032, CP-142).
    
- **Registro de compras y actualización de inventario**: se validó el registro de compras, cálculo de subtotales y total, cálculo del costo promedio ponderado (CPP), factor de conversión, generación de lotes y anulación de compras con reversión de stock (CP-042 a CP-057).
    
- **Optimización de reposición con proveedores**: el sistema permite registrar proveedores, consultar su historial de compras, asociarlos a compras y programar recordatorios de pedido mediante el cronograma de proveedores (CP-037 a CP-041, CP-106 a CP-108).
    
- **Gestión de productos dañados**: el sistema registra productos dañados, descuenta el stock, calcula la pérdida económica y permite anular el registro restaurando existencias (CP-101 a CP-105).
    
- **Ajuste de inventario**: se implementó y validó una funcionalidad específica para corregir el stock cuando se detectan diferencias físicas, registrando el motivo, tipo de ajuste (incremento/decremento), stock anterior y nuevo, garantizando la trazabilidad completa (CP-147 a CP-157).
    
- **Reporte de productos próximos a vencer**: se implementó y validó un reporte que muestra los productos perecederos cuyos lotes vencen en los próximos 15 días, excluyendo automáticamente lotes inactivos, agotados y ya vencidos. Adicionalmente, se validó la unificación de lotes duplicados generados por la excepción de trazabilidad (mismo producto + mismo código + misma fecha), mostrando la cantidad total sumada como un solo registro, así como el cálculo exacto de los totales globales (productos, lotes y unidades) (CP-159 a CP-161).
    

**Conclusión del objetivo específico 1:** el sistema cumple con el objetivo al ofrecer un control de inventario digital, en tiempo real, con trazabilidad completa, manejo de lotes, FIFO, alertas de stock mínimo, herramientas de ajuste y un reporte específico de productos próximos a vencer que permiten mantener la precisión del inventario ante cualquier diferencia detectada en bodega.

## Objetivo Específico 2

**Automatizar el proceso de facturación y ventas diarias para emitir comprobantes básicos a los clientes, reduciendo errores humanos en el cálculo del cambio y asegurando que los despachos de productos estén completos.**

### Requerimientos funcionales asociados

|ID|Requerimiento|
|---|---|
|RF01|Registro de Venta|
|RF02|Gestión de Precio en Compra|
|RF03|Generación de Ticket de Venta|
|RF05|Gestión de Pagos|

### Requerimientos no funcionales asociados

|ID|Requerimiento|
|---|---|
|RNF01|Tiempo de respuesta|
|RNF03|Notificación de fallo durante la transacción|
|RNF04|Diseño intuitivo y experiencia de usuario|

### Casos de prueba que evidencian el cumplimiento

|Fase|Casos|Estado|
|---|---|---|
|Fase 4 — Ventas|CP-058 a CP-066, CP-068, CP-069, CP-085 a CP-089, CP-158|Aprobados|
|Fase 6 — Reportes|CP-126 a CP-130|Aprobados|

### Evidencia del cumplimiento

- **Registro de ventas al detalle y mayorista**: se validó el registro de ventas con aplicación automática de precios según el tipo de cliente, actualización de inventario y aplicación del método FIFO en productos perecederos (CP-058, CP-064, CP-065).
    
- **Cálculo automático del vuelto**: el sistema calcula automáticamente el vuelto en pagos en efectivo y omite ese cálculo en pagos por transferencia. Se validaron los escenarios de pago con vuelto, pago exacto y pago por transferencia (CP-060, CP-061, CP-062).
    
- **Validación del monto recibido**: el sistema impide confirmar la venta cuando el monto recibido es inferior al total, eliminando errores humanos en el cobro (CP-060).
    
- **Generación de tickets**: el sistema genera correctamente los tres tipos de ticket (efectivo con vuelto, transferencia sin vuelto y venta a crédito), incluyendo correlativo, fecha, vendedor, método de pago, tipo de cliente, productos, cantidades, precios, subtotales y total (CP-066).
    
- **Prevención de despachos incompletos**: el sistema valida que no se pueda vender más cantidad que el stock disponible, garantizando que los productos despachados estén completos (CP-063).
    
- **Validación de detalles y totales**: se confirmó que los subtotales y totales calculados por el sistema coinciden con los valores matemáticos esperados, garantizando exactitud financiera (CP-065, CP-089).
    
- **Anulación de ventas**: el sistema anula ventas y restaura automáticamente el inventario, dejando constancia del estado anulado para auditoría (CP-069, CP-070).
    
- **Edición del método de pago**: se implementó y validó la funcionalidad que permite corregir el método de pago de una venta registrada en estado PAGADA, cuando por error humano se registró con uno distinto al que efectivamente se utilizó. Al realizar el cambio, el sistema limpia automáticamente el monto recibido para mantener la coherencia con el nuevo método (CP-158).
    

**Conclusión del objetivo específico 2:** el sistema cumple con el objetivo al automatizar completamente el proceso de venta, eliminar los errores humanos en el cálculo del vuelto, generar comprobantes básicos de la transacción y garantizar que los productos despachados correspondan a la venta registrada con el inventario descontado, permitiendo además corregir el método de pago cuando sea necesario.

## Objetivo Específico 3

**Establecer un módulo de gestión financiera que registre los ingresos, egresos, deudas de clientes fiados y un calendario de pagos a proveedores, para así mejorar la organización económica del negocio.**

### Requerimientos funcionales asociados

|ID|Requerimiento|
|---|---|
|RF04|Registro de Crédito|
|RF10|Recordatorio de Pedidos a Proveedores|
|RF11|Cierre de Caja Diario|
|RF12|Reportes Históricos|
|RF13|Notas del Negocio|
|RF15|Registro de Abonos|
|RF16|Devolución de ventas|

### Requerimientos no funcionales asociados

|ID|Requerimiento|
|---|---|
|RNF02|Autenticación de acceso|
|RNF04|Diseño intuitivo y experiencia de usuario|
|RNF05|Respaldo automático de datos|

### Casos de prueba que evidencian el cumplimiento

|Fase|Casos|Estado|
|---|---|---|
|Fase 4 — Créditos, Abonos y Devoluciones|CP-067, CP-071 a CP-084, CP-091 a CP-100|Aprobados|
|Fase 5 — Complementarios|CP-109 a CP-120|Aprobados|
|Fase 6 — Reportes|CP-121 a CP-146|Aprobados|

### Evidencia del cumplimiento

- **Registro de ingresos por ventas**: el sistema registra todas las ventas pagadas y genera el cierre diario consolidado por método de pago (efectivo, transferencia, crédito), incluyendo el vendedor responsable (CP-143).
    
- **Registro de egresos por compras**: cada compra registrada actualiza el costo promedio ponderado y el total de egresos, reflejándose en el reporte general y en el reporte de compras (CP-052, CP-131, CP-132).
    
- **Deudas de clientes fiados**: el sistema registra créditos automáticamente cuando una venta es al crédito, asocia el cliente, controla el saldo y permite cancelar el crédito mediante abonos (CP-071, CP-072, CP-078, CP-079).
    
- **Control de abonos**: se validó el registro de abonos parciales y totales, la actualización automática del saldo y la anulación de abonos con restauración del saldo (CP-078 a CP-083).
    
- **Recalculo del crédito por devoluciones**: cuando se realiza una devolución parcial de una venta al crédito, el sistema descuenta automáticamente el monto devuelto del saldo del crédito (CP-093).
    
- **Calendario de pagos a proveedores**: el sistema permite registrar y editar actividades en el cronograma de proveedores, con validación de fechas, cumpliendo con el recordatorio de pedidos (CP-106 a CP-108).
    
- **Reportes históricos financieros**: el sistema genera reportes por rango de fechas de ventas, compras, créditos, devoluciones, cierre diario, productos dañados, cambio de producto, inventario y reporte general, con cálculos financieros exactos (CP-121 a CP-146).
    
- **Cálculo exacto de ganancia neta**: el reporte general calcula correctamente la ganancia neta como Ventas − Compras − Pérdidas por daños (CP-124).
    
- **Cálculo exacto de total financiero**: el reporte de ventas calcula correctamente el total financiero como Ventas − Devoluciones (CP-128).
    
- **Control de dinero pendiente en créditos**: el sistema muestra el monto pendiente total de créditos en el reporte de ventas (CP-129).
    
- **Notas del negocio**: el sistema permite registrar, editar y consultar notas asociadas al usuario, contribuyendo a la organización interna del negocio (CP-109 a CP-111).
    
- **Respaldo automático**: la configuración del sistema contempla respaldos automáticos de la base de datos cada 3 días (RNF05), garantizando la continuidad de la información financiera.
    

**Conclusión del objetivo específico 3:** el sistema cumple con el objetivo al centralizar la administración financiera del negocio en un solo módulo que integra ingresos, egresos, deudas de clientes fiados, abonos, devoluciones, cierre diario, reportes históricos y cronograma de proveedores, garantizando la organización económica y la trazabilidad de todas las operaciones.

## Conclusión del Cumplimiento de Objetivos

Los tres objetivos específicos y el objetivo general del proyecto fueron cumplidos de forma comprobable mediante la ejecución de 161 casos de prueba funcionales, todos aprobados, y respaldados por los requerimientos funcionales y no funcionales definidos durante la fase de análisis.

El sistema SACI no solo cubre los requisitos mínimos planteados, sino que incorpora módulos adicionales como devoluciones de ventas, cambio de producto, ajuste de inventario, gestión avanzada de productos dañados y reporte de productos próximos a vencer, fortaleciendo aún más el control operativo y financiero del negocio.

Se concluye que el sistema implementado constituye una solución integral que resuelve la falta de control operativo y la dependencia de procesos manuales identificados en la pregunta de investigación, garantizando precisión en las ventas, optimización del inventario y centralización de la administración financiera de la Tienda y Librería Israel.
