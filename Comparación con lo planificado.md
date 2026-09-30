# 4.4 Comparación con lo Planificado

El presente apartado tiene como finalidad contrastar los requerimientos funcionales y no funcionales definidos durante la fase de análisis del proyecto con las funcionalidades efectivamente implementadas en el sistema SACI. La comparación permite identificar el nivel de cumplimiento del alcance planificado, las ampliaciones realizadas durante el desarrollo y las funcionalidades adicionales incorporadas para fortalecer la solución.

El alcance original del proyecto consistió en el **desarrollo completo de un sistema integral de gestión comercial** para la Tienda y Librería Israel, cubriendo los 17 requerimientos funcionales y los 6 requerimientos no funcionales definidos. Durante el desarrollo se mantuvo la esencia del alcance planificado, incorporando ajustes y ampliaciones que respondieron a necesidades reales detectadas por el equipo, sugerencias del ingeniero asesor y escenarios operativos de la propietaria del negocio.

## 4.4.1 Requerimientos Funcionales Cumplidos

La siguiente tabla resume el estado de cumplimiento de cada requerimiento funcional planificado:

|ID|Requerimiento|Estado|Observación|
|---|---|---|---|
|RF01|Registro de Venta|Cumplido con ampliaciones|Se implementó venta al detalle y mayorista, FIFO en perecederos, venta a crédito, anulación de ventas y actualización automática del estado del producto|
|RF02|Gestión de Precio en Compra|Cumplido con cambios de enfoque|Se mantiene el margen de ganancia para detalle y mayorista, pero el cálculo se realiza sobre el Costo Promedio Ponderado (CPP) recalculado en cada compra|
|RF03|Generación de Ticket de Venta|Cumplido con ampliaciones|Se generan tres tipos de ticket (efectivo, transferencia y crédito), incluyendo datos del cliente cuando aplica|
|RF04|Registro de Crédito|Cumplido tal como se planificó|Generación automática del crédito desde la venta, asociación al cliente y control de saldo|
|RF05|Gestión de Pagos|Cumplido tal como se planificó|Cálculo de vuelto en efectivo y omisión en transferencia|
|RF06|Gestión y Registro de Productos|Cumplido con ampliaciones|Se agregó manejo de lotes múltiples, reactivación automática y ajuste de inventario|
|RF07|Control de Vencimiento de Productos|Cumplido con ampliaciones|Alerta visual en el panel principal (dashboard) mediante el módulo de vencimientos próximos|
|RF08|Alerta de Stock Mínimo|Cumplido tal como se planificó|Alerta visual en el dashboard y reporte de inventario|
|RF09|Registro de Compras|Cumplido con ampliaciones|Cálculo automático del CPP, factor de conversión y trazabilidad mediante lotes|
|RF10|Recordatorio de Pedidos a Proveedores|Cumplido con ampliaciones|Panel de proveedores en el dashboard con conteo de días previos a la visita|
|RF11|Cierre de Caja Diario|Cumplido con ampliaciones|Se agregó el vendedor responsable por venta|
|RF12|Reportes Históricos|Cumplido con ampliaciones significativas|Se desarrollaron 9 reportes específicos: general, ventas, compras, créditos, devoluciones, inventario, cambio de producto, productos dañados y cierre diario|
|RF13|Notas del Negocio|Cumplido tal como se planificó|CRUD de notas asociadas al usuario|
|RF14|Gestión de Proveedores|Cumplido tal como se planificó|CRUD completo con validaciones de unicidad|
|RF15|Registro de Abonos|Cumplido tal como se planificó|Abonos parciales y totales, actualización automática del saldo y anulación|
|RF16|Devolución de Ventas|Cumplido con ampliaciones significativas|Se agregó separación PERFECTO/DAÑADO, máximo 2 condiciones por producto, reactivación de lotes y descuento parcial del crédito|
|RF17|Gestión de Productos Dañados|Cumplido con ampliaciones significativas|Separación por origen, estados, columna de lote y anulación con restauración de stock|

## 4.4.2 Requerimientos Funcionales Ampliados

Algunos requerimientos fueron ampliados durante el desarrollo con el objetivo de robustecer el sistema y cubrir escenarios operativos que no estaban contemplados inicialmente. Las ampliaciones más relevantes fueron:

### RF02 — Enfoque de cálculo de precios

El requerimiento original contemplaba el uso de márgenes de ganancia para calcular el precio de venta. Durante el desarrollo se mantuvo el uso de márgenes, pero se incorporó el **Costo Promedio Ponderado (CPP)** como base para dicho cálculo, permitiendo que el precio de venta se ajuste automáticamente cuando ingresa una nueva compra con distinto costo unitario.

El sistema calcula el CPP mediante la fórmula:

text

CPP = ((stock_anterior × cpp_anterior) + (cantidad_nueva × precio_unitario_base)) / (stock_anterior + cantidad_nueva)

Y a partir de ese CPP calcula:

text

precio_detalle = CPP × (1 + margen_detalle / 100)
precio_mayor   = CPP × (1 + margen_mayor / 100)

Esta ampliación responde a la necesidad real del negocio de mantener precios de venta coherentes con los costos reales de adquisición, algo que el planteamiento original no contemplaba explícitamente.

### RF03 — Ticket de venta a crédito

El ticket de venta se amplió para incluir los datos del cliente cuando la venta es a crédito, mostrando nombre y DUI (o solo nombre si no se registró DUI). Esto mejora el respaldo físico para el cliente fiado y facilita la identificación de la deuda.

### RF07 — Alerta de vencimiento

Se implementó un panel de alertas en el dashboard principal que muestra los productos perecederos cuyos lotes están próximos a vencer, permitiendo a la dueña tomar decisiones oportunas.

### RF12 — Reportes ampliados

El requerimiento original contemplaba reportes de ventas, compras y ganancias. Durante el desarrollo se identificó la necesidad de reportes específicos por módulo, desarrollándose finalmente **nueve reportes**:

1. Reporte General (compras + ventas + productos dañados con ganancia neta)
    
2. Reporte de Ventas (con filtros por tipo de cliente, método de pago y estado)
    
3. Reporte de Compras (con detalle de productos y lotes)
    
4. Reporte de Créditos (agrupado por cliente)
    
5. Reporte de Devoluciones de Ventas (separando perfectos y dañados)
    
6. Reporte de Inventario (con filtros y alerta de stock mínimo)
    
7. Reporte de Cambio de Producto (separado por estado)
    
8. Reporte de Productos Dañados (separado por origen)
    
9. Reporte de Cierre Diario (consolidado por método de pago)
    

Cada uno con filtros por rango de fechas y filtros adicionales según su naturaleza.

### RF16 — Devolución de ventas con lógica diferenciada

El requerimiento original describía la devolución de ventas con reintegración al inventario cuando el producto estaba en buen estado y registro en productos dañados cuando no lo estaba. Durante el desarrollo se amplió con:

- Separación explícita de condiciones **PERFECTO** y **DAÑADO** dentro de una misma devolución.
    
- Posibilidad de agregar múltiples detalles del mismo producto (uno perfecto y otro dañado).
    
- Máximo dos condiciones por producto.
    
- Motivo obligatorio con mínimo 5 caracteres.
    
- Reactivación automática del lote si estaba inactivo.
    
- Descuento parcial del crédito cuando la devolución no era completa.
    
- Prohibición de devolver ventas ya en estado DEVOLUCION.
    
- Anulación de devoluciones con reversión completa de efectos.
    

### RF17 — Productos dañados con origen y estados

El requerimiento original pedía registrar productos dañados y mantener historial. Durante el desarrollo se amplió con:

- Clasificación por **origen**: VENTA (devolución), DIRECTO (manual), VENCIMIENTO, PROVEEDOR.
    
- Estados: REGISTRADO, RECHAZADO, DEVOLUCION, ANULADO.
    
- Asociación con el **lote** del producto cuando aplica.
    
- Acciones de anulación con restauración de stock.
    
- Separación visual por origen en el reporte.
    

## 4.4.3 Funcionalidades Adicionales No Planificadas

Durante el desarrollo surgieron necesidades operativas que dieron lugar a funcionalidades adicionales que no estaban contempladas en los requerimientos originales. Estas funcionalidades representan un valor agregado al sistema.

### Cambio de Producto

El módulo de **Cambio de Producto** no estaba contemplado en los requerimientos originales. Inicialmente se había pensado en una "devolución de productos vencidos" a proveedores, pero tras una revisión con el ingeniero asesor se determinó que **no era posible aplicar una devolución fiscal** porque la propietaria no es contribuyente de IVA y no cumple con los requisitos de facturación electrónica establecidos por Hacienda.

La solución adoptada fue desarrollar un módulo de **cambio de producto**, que refleja el escenario real del negocio: el proveedor reemplaza el producto vencido o dañado por uno nuevo en lugar de emitir una nota de crédito. Este módulo contempla:

- Estados: PENDIENTE, ACEPTADO, RECHAZADO, ANULADO.
    
- Producto de reemplazo opcional (puede ser el mismo producto o uno diferente).
    
- Registro de lote y fecha.
    
- Anulación con reversión de stock.
    
- Reporte específico separado por estado.
    

### Ajuste de Inventario

El módulo de **Ajuste de Inventario** surgió como sugerencia del ingeniero asesor, quien planteó el escenario de que el producto físico en bodega no coincida con el stock del sistema. El equipo desarrolló la solución incorporando:

- Campo de motivo del ajuste (mínimo 4 caracteres, máximo 255).
    
- Selección de lote obligatoria para productos perecederos.
    
- Registro de cada movimiento en una tabla de auditoría (`ajustes_stock`) con tipo, cantidad, stock anterior, stock nuevo y motivo.
    
- Inactivación automática del producto al quedar en stock 0.
    
- Reactivación automática al incrementar el stock.
    
- Recalculo del stock total basado en lotes para perecederos.
    

### Gestión Avanzada de Usuarios

Aunque no existía un requerimiento explícito, se implementó un módulo de gestión de usuarios con:

- Roles ADMIN y VENDEDOR.
    
- Contraseña temporal enviada por correo electrónico.
    
- Activación de cuenta obligatoria por correo.
    
- Protección contra inactivación del usuario ADMIN.
    
- Bloqueo del cambio de rol propio.
    
- Validación de que el usuario debe estar activo para iniciar sesión.
    

Esta funcionalidad surgió por la necesidad de escalabilidad futura, ya que si la propietaria contrata vendedores necesitará poder gestionar sus cuentas de forma segura.

### Validación de DUI con Dígito Verificador

La validación del DUI salvadoreño (formato `00000000-0` con verificación del dígito calculado mediante el algoritmo oficial) fue sugerida por el ingeniero asesor, dado que los evaluadores académicos son rigurosos con las validaciones de datos personales. También se implementó validación de teléfono con máscaras por país.

### Estados de Venta Ampliados

El requerimiento original solo contemplaba los estados PAGADA y CREDITO. Durante el desarrollo se agregaron:

- **ANULADA**: para ventas anuladas por error humano.
    
- **DEVOLUCION**: para ventas que tuvieron una devolución asociada, manteniendo trazabilidad completa.
    

Estos estados surgieron de escenarios operativos reales y de la necesidad de reflejar con precisión el ciclo de vida de una venta.

### Ajustes en el Reporte General

Durante el desarrollo de los reportes se determinó que el Reporte General no debía incluir las devoluciones de ventas de forma explícita, ya que los productos devueltos en estado PERFECTO reingresan al inventario y los DAÑADOS se reflejan en el módulo de productos dañados. Incluir las devoluciones como sección separada generaba duplicación de pérdidas en el cálculo financiero. Esta decisión fue tomada por el equipo para garantizar la coherencia del reporte.

## 4.4.4 Cumplimiento de Requerimientos No Funcionales

|ID|Requerimiento|Estado|Evidencia|
|---|---|---|---|
|RNF01|Tiempo de respuesta ≤ 2 segundos|Cumplido|Validado mediante plan de pruebas de rendimiento (documento complementario)|
|RNF02|Autenticación de acceso|Cumplido|Login con JWT, validación de usuario activo, roles con Spatie Permission|
|RNF03|Notificación de fallo en transacción|Cumplido con cambio|El sistema notifica mediante toasts de error y revierte la transacción con `DB::rollBack()` para que el usuario pueda reingresar los datos|
|RNF04|Diseño intuitivo y UX|Cumplido con ajustes|Se implementó un diseño responsivo con iconos representativos (carrito, caja, camión, etc.) y una paleta basada en verde y rojo como colores preferidos|
|RNF05|Respaldo automático de datos|Cumplido|Sistema de backups automáticos con cifrado AES-256, subida a MEGA, retención de 5 copias y scheduler cada 3 días|
|RNF06|Interfaz responsiva|Cumplido|Validado en navegador de escritorio y dispositivos móviles con Tailwind y clases responsivas|

### Detalle del RNF05 — Sistema de backups

El respaldo automático fue desarrollado por un integrante del equipo y validado con 10 pruebas automáticas aprobadas y 82 comprobaciones. El sistema:

- Ejecuta `php artisan database:backup` de forma automática cada 3 días mediante el Scheduler de Laravel.
    
- Genera el dump con `pg_dump` en formato custom.
    
- Cifra el archivo con OpenSSL AES-256-CBC + PBKDF2.
    
- Sube el archivo cifrado a MEGA mediante `rclone`.
    
- Conserva las 5 copias más recientes en local y en MEGA.
    
- Si cualquier paso falla, no elimina ninguna copia previa.
    
- Guarda las contraseñas en variables de entorno, nunca en argumentos o logs.
    

Este componente satisface completamente el requerimiento RNF05 y refuerza la confiabilidad del sistema.

## 4.4.5 Cambios de Enfoque Durante el Desarrollo

Además de las ampliaciones y funcionalidades adicionales, se presentaron algunos cambios de enfoque respecto a lo planificado:

|Aspecto|Planificado|Implementado|Razón|
|---|---|---|---|
|Cálculo de precios|Margen directo sobre costo unitario|CPP recalculado en cada compra + margen|Reflejar el costo real del inventario|
|Devolución de productos vencidos a proveedor|Devolución fiscal con nota de crédito|Cambio de producto|Restricciones fiscales de Hacienda|
|Estados de venta|PAGADA y CREDITO|PAGADA, CREDITO, ANULADA, DEVOLUCION|Escenarios operativos reales|
|Cierre diario|Total por método de pago|Total por método de pago + vendedor|Facilita la trazabilidad para reclamos|
|Reportes|3 reportes generales|9 reportes específicos|Necesidades detectadas durante el desarrollo|

## 4.4.6 Conclusión de la Comparación

El sistema SACI **cumplió con el 100% de los requerimientos funcionales y no funcionales planificados**, incorporando además ampliaciones que responden a escenarios operativos reales del negocio y a sugerencias del ingeniero asesor.

El alcance planificado no solo fue cubierto en su totalidad, sino que fue **superado mediante la incorporación de funcionalidades adicionales** que no estaban contempladas originalmente:

- Módulo de cambio de producto.
    
- Módulo de ajuste de inventario con trazabilidad completa.
    
- Gestión avanzada de usuarios con roles, contraseña temporal y activación por correo.
    
- Validación de DUI con dígito verificador y teléfonos por país.
    
- Sistema de backups automáticos con cifrado y subida a la nube.
    

Estas ampliaciones fortalecen la propuesta del sistema y demuestran que el equipo no se limitó a cumplir con lo mínimo requerido, sino que buscó ofrecer una solución integral, segura y sostenible.

---

# 4.4.7 Sistema Listo para Implementación

## ¿Está el sistema listo para ser implementado?

**Sí.** El sistema SACI se encuentra en condiciones óptimas para su implementación en el entorno operativo de la Tienda y Librería Israel. Esta conclusión se fundamenta en los siguientes criterios:

### Cumplimiento de objetivos

El sistema cumple con el objetivo general y los tres objetivos específicos definidos en la fase de investigación, verificados mediante la ejecución de 157 casos de prueba funcionales, todos aprobados.

### Cumplimiento de requerimientos

Los 17 requerimientos funcionales y los 6 requerimientos no funcionales fueron implementados, validados y aprobados. Se incorporaron además funcionalidades adicionales que amplían el valor del sistema.

### Estándares internacionales de desarrollo

El proyecto sigue buenas prácticas reconocidas internacionalmente:

- **Arquitectura MVC**: separación clara entre modelos, vistas y controladores.
    
- **API REST**: comunicación estandarizada entre frontend y backend mediante JSON.
    
- **Autenticación JWT**: tokens firmados con expiración y refresh.
    
- **Autorización por roles**: Spatie Laravel Permission con middleware específico.
    
- **Migraciones y seeders**: control de versiones del esquema de base de datos.
    
- **Form Requests**: validación centralizada de datos de entrada.
    
- **Transacciones de base de datos**: uso de `DB::beginTransaction()` y `DB::rollBack()` para garantizar atomicidad.
    
- **Manejo de errores centralizado**: respuestas HTTP con códigos apropiados y mensajes claros.
    
- **Documentación técnica**: manuales de uso, plan de pruebas, plan de rendimiento, informe de backups.
    
- **Pruebas automatizadas**: PHPUnit para el módulo de backups (10 pruebas aprobadas).
    
- **Control de versiones**: uso de Git con ramas por integrante y commits descriptivos.
    

### Estructura del proyecto

El proyecto se encuentra organizado de forma profesional:

- **Backend**: estructura estándar de Laravel 12 con separación por capas (`app/Http/Controllers`, `app/Models`, `app/Http/Requests`, `app/Services`, `database/migrations`).
    
- **Frontend**: estructura modular con Vue 3 (`components`, `views`, `stores`, `services`, `utils`) organizada por funcionalidad.
    
- **Base de datos**: PostgreSQL con migraciones versionadas y respaldos automatizados.
    
- **Documentación**: carpeta `docs/` con manuales técnicos.
    
- **Seguridad**: variables de entorno, cifrado de backups, protección de archivos sensibles.
    

### Confiabilidad operativa

- **Integridad financiera**: validada mediante pruebas que confirman la ausencia de vacíos financieros en todos los flujos.
    
- **Trazabilidad completa**: cada operación queda registrada con fecha, usuario, cantidades, montos y motivos.
    
- **Reversibilidad**: todas las operaciones críticas (ventas, compras, devoluciones, abonos, cambios, ajustes) cuentan con mecanismos de anulación que revierten correctamente sus efectos.
    
- **Respaldo y recuperación**: sistema automático de backups con cifrado y almacenamiento en la nube, verificado mediante pruebas reales de restauración.
    

### Posibles mejoras futuras

Aunque el sistema está listo para su implementación, se identifican mejoras que podrían aplicarse en versiones futuras:

- **Facturación electrónica**: en caso de que el negocio pase a ser contribuyente de IVA.
    
- **Presentaciones de productos**: para venta por paquetes, cajas o presentaciones específicas.
    
- **Registro de marcas, categorías y proveedores desde el módulo de compras**: para agilizar la operación.
    
- **Reporte de productos próximos a vencer**: complementario al panel de alertas del dashboard.
    
- **Contenedor Docker con scheduler**: para garantizar la ejecución de los backups automáticos sin depender de un proceso manual.
    
- **Escalabilidad a múltiples sucursales**: en caso de expansión del negocio.
    

Estas mejoras no son requisitos del sistema actual y su implementación dependería de nuevos requerimientos del negocio.

### Conclusión final

El sistema SACI **cumple con los estándares internacionales de desarrollo**, presenta una **estructura de proyecto profesional**, ha sido **validado exhaustivamente mediante 157 pruebas funcionales aprobadas**, cuenta con **respaldos automáticos y cifrados**, y ha **superado el alcance planificado** incorporando funcionalidades adicionales de valor.

En consecuencia, el sistema se encuentra **listo para su implementación en la Tienda y Librería Israel**, constituyendo una solución integral, segura, trazable y sostenible que responde a las necesidades operativas y financieras del negocio.
