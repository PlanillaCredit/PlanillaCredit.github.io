# PLANILLACREDIT
## Documento Integral de Proyecto
### Plataforma de Crédito Descontado por Planilla

---

**Cliente:** Empresa de Préstamos y Cobranza (Bolivia)  
**Elaborado por:** Uplabs AI  
**Fecha:** Mayo 2026  
**Versión:** 1.0 — Confidencial  

---

## TABLA DE CONTENIDOS

1. Resumen Ejecutivo
2. Marco Legal y Regulatorio
3. Modelo de Negocio
4. Análisis de Factibilidad
5. Descripción de la Plataforma
6. Arquitectura Técnica
7. Plan de Implementación
8. Equipo de Trabajo
9. Presupuesto de Desarrollo
10. Proyecciones Financieras
11. Gestión de Riesgos
12. Próximos Pasos

---

---

# 1. RESUMEN EJECUTIVO

**PlanillaCredit** es una plataforma digital SaaS (Software as a Service) que conecta tres actores dentro de un ecosistema de crédito: empresas empleadoras que afilian su planilla, empresas proveedoras de bienes y servicios a crédito, y empleados como beneficiarios finales del crédito.

El diferenciador central y la ventaja competitiva clave del modelo es el **descuento automático de cuotas directamente de la planilla de salarios**, lo que elimina prácticamente el riesgo de incobrabilidad para el proveedor de crédito y elimina la carga de gestión del pago para el empleado.

La plataforma es operada por la empresa cliente, entidad financiera ya regulada ante la **Autoridad de Supervisión del Sistema Financiero (ASFI) de Bolivia**, lo cual habilita legalmente la intermediación de créditos en efectivo y la oferta de productos financieros a través de la plataforma.

### Propuesta de Valor por Actor

| Actor | Problema que Resuelve | Beneficio Obtenido |
|-------|----------------------|-------------------|
| **Empleado** | Sin acceso a crédito bancario formal o con tasas prohibitivas | Crédito accessible, sin trámites, descuento automático sin gestión personal |
| **Empresa Empleadora** | Empleados con estrés financiero afectan la productividad | Beneficio laboral diferenciador sin costo para la empresa |
| **Empresa Proveedora** | Alto riesgo de mora e incobrabilidad en ventas a crédito | Cartera garantizada, cobro delegado a la planilla, más ventas |
| **Operador (cliente)** | — | Comisiones por intermediación (plataforma 100% gratuita) |

### Indicadores Clave del Proyecto

| Indicador | Valor |
|-----------|-------|
| País de operación inicial | Bolivia |
| Mercado objetivo inicial | Empresas medianas con planilla formal |
| Proyección usuarios (12 meses) | 500 - 800 empleados activos |
| Tiempo al MVP | 4 meses |
| Inversión total (proyecto completo) | USD 40,000 – 51,000 |
| ROI estimado operador (Año 2) | 180% – 240% |

---

---

# 2. MARCO LEGAL Y REGULATORIO

Esta sección es crítica. Bolivia tiene un marco financiero regulado que impacta directamente en cómo la plataforma puede operar, quién puede ofrecer crédito y qué contratos son necesarios.

## 2.1 Marco Regulatorio Principal

### Ley de Servicios Financieros N° 393 (2013)
Es la norma marco que regula toda actividad financiera en Bolivia. Define las entidades autorizadas a captar recursos del público y otorgar créditos. Los puntos relevantes para este proyecto son:

- **Artículo 87:** Solo entidades autorizadas por ASFI pueden otorgar créditos en efectivo de forma habitual.
- **Artículo 73:** Las cooperativas, mutuales y entidades de intermediación financiera deben operar bajo supervisión de ASFI.
- **Implicación para PlanillaCredit:** El operador (cliente) ya cuenta con licencia ASFI. Las empresas proveedoras de crédito en efectivo que operen dentro de la plataforma deben ser también entidades reguladas o bien la plataforma debe actuar como canal exclusivo del operador.

### Regulación sobre Descuentos de Planilla
Bolivia no tiene una ley específica sobre descuentos de planilla para créditos de terceros, pero el **Código de Trabajo** establece:

- Los descuentos del salario requieren autorización escrita del trabajador.
- El salario mínimo nacional (SMN) es inembargable. Los descuentos no pueden llevar el salario neto por debajo del SMN.
- **Acción requerida:** Cada empleado debe firmar un consentimiento explícito de descuento de planilla al momento de solicitar el crédito.

### Protección de Datos Personales
Bolivia cuenta con la **Ley N° 164 de Telecomunicaciones y TIC** y disposiciones de protección de datos dentro del marco financiero de ASFI:

- Los datos de empleados (salario, CI, información financiera) son datos sensibles.
- Se requiere política de privacidad clara y consentimiento para tratamiento de datos.
- Los datos no pueden transferirse a terceros sin consentimiento del titular.

### Ley de Servicios de Pago y Dinero Electrónico (Decretos ASFI 2019-2023)
Regula las plataformas que intermedian pagos entre partes. Relevante para el flujo de dinero empresa-plataforma-proveedor.

## 2.2 Estructura Legal Recomendada

Dado que la plataforma conecta múltiples actores, se necesitan tres capas de contratos:

### Capa 1 — Contrato de Afiliación (Empresa Empleadora ↔ Plataforma)
**Contenido mínimo obligatorio:**
- Obligación de la empresa de descontar cuotas de planilla antes del pago al empleado.
- Obligación de transferir los fondos descontados a la plataforma dentro de X días hábiles del pago de planilla.
- Consecuencias del incumplimiento (multas, suspensión del servicio, acciones legales).
- Autorización para que la plataforma comparta información de empleados con empresas proveedoras (bajo confidencialidad).
- Cláusula de vigencia y resolución anticipada.
- Responsabilidad ante la baja o despido de empleados con crédito activo.

### Capa 2 — Contrato de Proveedor (Empresa Proveedora ↔ Plataforma)
**Contenido mínimo obligatorio:**
- Condiciones de oferta de productos/créditos en la plataforma.
- Comisiones que cobra la plataforma sobre cada transacción.
- Flujo de liquidación de pagos (plazos, cuentas bancarias).
- Si el proveedor ofrece crédito en efectivo: verificación de que cuenta con habilitación legal para hacerlo, o bien que actúa bajo el paraguas del operador.
- Responsabilidad por información de productos publicada.

### Capa 3 — Contrato/Consentimiento del Empleado (Empleado ↔ Plataforma ↔ Empresa Empleadora)
**Contenido mínimo obligatorio:**
- Consentimiento expreso e informado para el descuento de planilla.
- Información clara de la tasa de interés, plazo y monto total a pagar (en cumplimiento de ASFI).
- Reconocimiento de que el empleado es el deudor y la empresa empleadora es el canal de pago.
- Cláusula de qué ocurre si el empleado deja de trabajar en la empresa (opciones: refinanciación, cobro directo, cesión de deuda).
- Política de privacidad y uso de datos.

### Capa 4 — Contrato de Crédito (Empleado ↔ Empresa Proveedora u Operador)
- Contrato formal de crédito conforme a regulación ASFI.
- Plan de pagos detallado.
- Tasa efectiva anual (TEA) informada según normativa ASFI.
- Firma electrónica con valor legal (verificar compatibilidad con Ley de Firma Electrónica N° 164).

## 2.3 Punto Crítico: Empresas Proveedoras de Crédito en Efectivo

**Este es el punto legal más sensible del proyecto.**

Existen dos modelos posibles y tienen implicaciones muy distintas:

**Modelo A — Plataforma como Canal Exclusivo del Operador (Más Simple)**
- Solo el operador (cliente, entidad ASFI) otorga créditos en efectivo.
- Las empresas proveedoras solo ofrecen productos físicos/servicios a crédito (no efectivo).
- Menor complejidad regulatoria, más control del operador.
- Limitación: el catálogo de "crédito en efectivo" queda centralizado en el operador.

**Modelo B — Marketplace de Crédito (Más Complejo)**
- Otras entidades financieras reguladas pueden ofrecer créditos en efectivo en la plataforma.
- La plataforma actúa como intermediario/conector.
- Requiere verificación de que cada empresa proveedora de crédito tiene habilitación ASFI.
- Mayor potencial de negocio pero mayor complejidad legal y de compliance.

**Recomendación:** Arrancar con Modelo A para el MVP y preparar la arquitectura para Modelo B en Fase 3.

## 2.4 Firma Electrónica en Bolivia

La **Ley N° 164** y el **Decreto Supremo N° 1793** reconocen la validez de la firma electrónica en Bolivia. Para que los contratos firmados digitalmente en la plataforma tengan plena validez legal:

- Se recomienda integración con un proveedor de firma electrónica certificado en Bolivia (Ej: ADSIB — Agencia para el Desarrollo de la Sociedad de la Información en Bolivia, que emite certificados digitales).
- Como alternativa de menor costo: firma OTP (código enviado por SMS/WhatsApp que el usuario ingresa para confirmar su aceptación) con registro de IP, timestamp y datos biométricos básicos.

## 2.5 Acciones Legales Requeridas Antes del Lanzamiento

| Acción | Responsable | Plazo |
|--------|------------|-------|
| Consulta con abogado especialista ASFI sobre modelo de proveedores | Cliente | Antes de inicio del proyecto |
| Redacción de contratos de afiliación (empresa empleadora y proveedora) | Abogado del cliente | Mes 1 |
| Redacción de contrato/consentimiento del empleado | Abogado del cliente | Mes 1 |
| Definición de mecanismo de firma electrónica con validez legal | Uplabs AI + abogado | Mes 2 |
| Política de privacidad y términos de uso de la plataforma | Abogado del cliente | Mes 2 |
| Revisión de cumplimiento ASFI del flujo de pagos | Abogado + cliente | Mes 3 |

---

---

# 3. MODELO DE NEGOCIO

## 3.1 Descripción del Modelo

PlanillaCredit opera un modelo de negocio de plataforma de doble cara (two-sided marketplace) con una capa adicional de servicios financieros. El modelo se diferencia por ser **100% gratuito** para las empresas (empleadoras y proveedoras), eliminando completamente las barreras de entrada y acelerando la adopción.

El operador genera ingresos exclusivamente a través de una **comisión sobre cada crédito originado**, la cual se cobra **ANTES del desembolso** al proveedor. Esto significa que:

- ✅ **Cero riesgo de incobrabilidad** de comisiones (se descuenta antes de transferir).
- ✅ **Incentivo alineado**: solo ganamos cuando generamos valor (un crédito exitoso).
- ✅ **Propuesta comercial imbatible**: "Únete gratis, paga solo cuando vendas/prestes".

## 3.2 Fuentes de Ingreso

### Ingreso Principal — Comisión por Transacción (Variable)
Porcentaje aplicado sobre el monto de cada crédito originado en la plataforma, **cobrado ANTES del desembolso al proveedor**.

| Tipo de Crédito | Comisión de la Plataforma | Ejemplo |
|----------------|--------------------------|---------|
| Productos físicos a crédito | 2.0% – 3.5% del monto del crédito | Crédito de USD 1,000 → Comisión USD 25 (2.5%) → Proveedor recibe USD 975 |
| Préstamos en efectivo | 1.5% – 2.5% del monto desembolsado | Préstamo de USD 500 → Comisión USD 12.50 (2.5%) → Proveedor recibe USD 487.50 |

**Ventaja clave del modelo:**
- La plataforma retiene automáticamente su comisión del flujo de pago, antes de transferir el saldo al proveedor.
- No hay facturación mensual, cobros pendientes ni gestión de morosidad de clientes.
- El flujo es: `Empresa Empleadora → Plataforma retiene comisión → Proveedor recibe neto`.

### Ingreso Secundario — Comisión de Cobranza (Condicional — Fase 3)
Si el operador asume la gestión activa de cobranza para casos de empleados que abandonan la empresa antes de terminar de pagar:

- 8% – 15% sobre el monto recuperado en gestión extrajudicial.
- 15% – 25% sobre el monto recuperado en gestión prejudicial/judicial.

### Ingreso Futuro — Módulos Premium (Fase 3+)
- Scoring crediticio avanzado con historial de la plataforma: USD 0.30 – 0.50 por consulta.
- Consultas a INFOCRED (Buró de Crédito Bolivia): según tarifa INFOCRED + margen.
- API de integración para sistemas externos: Modelo por uso o tarifa fija según volumen.

## 3.3 Estructura de Costos del Operador

| Costo | Tipo | Estimación Mensual |
|-------|------|-------------------|
| Infraestructura cloud (AWS/Railway) | Fijo | USD 150 – 350 |
| Servicios de notificación (SMS/WhatsApp) | Variable | USD 0.03 – 0.08 por mensaje |
| Mantenimiento y soporte plataforma | Fijo | USD 800 – 1,500 |
| Soporte al cliente | Variable/Fijo | USD 300 – 600 |
| Licencias de software de terceros | Fijo | USD 100 – 200 |
| **Total costos operativos/mes** | | **USD 1,350 – 2,650** |

## 3.4 Punto de Equilibrio

Con el modelo de comisiones puro (sin ingresos SaaS), el punto de equilibrio depende exclusivamente del **volumen de créditos originados**:

**Cálculo conservador:**
- Costos operativos mensuales: USD 1,500 – 2,000
- Ticket promedio de crédito: USD 500
- Comisión promedio: 2.5%
- Comisión por crédito: USD 12.50

**Créditos necesarios para equilibrio:** 120 – 160 créditos/mes

**Escenario realista:**
Con 6-10 empresas empleadoras afiliadas (promedio 80 empleados cada una = 480-800 empleados totales) y una tasa de penetración del 20-25% (empleados que toman al menos un crédito al año), se generan aproximadamente:

- **100-150 créditos/mes** en los primeros 6-8 meses.
- Punto de equilibrio alcanzado en **mes 8-12** desde el lanzamiento.

**Ventaja del modelo gratuito:**
- Las empresas se afilian sin fricción (no pagan nada por estar en la plataforma).
- La adopción comercial es significativamente más rápida que con un modelo SaaS.
- A partir del mes 10-14, con 10-15 empresas, la plataforma genera margen positivo consistente de USD 1,000-2,500/mes.

---

---

# 4. ANÁLISIS DE FACTIBILIDAD

## 4.1 Factibilidad Legal ✅ VIABLE (con acciones previas)

| Factor | Estado | Riesgo |
|--------|--------|--------|
| Operador con licencia ASFI | ✅ Confirmado | Ninguno |
| Marco legal para descuento de planilla | ✅ Viable con contratos adecuados | Bajo |
| Firma electrónica válida en Bolivia | ✅ Viable (Ley 164) | Bajo |
| Modelo de empresas proveedoras de crédito | ⚠️ Requiere consulta legal | Medio |
| Protección de datos de empleados | ✅ Viable con política de privacidad | Bajo |

**Veredicto:** Factible. La única acción bloqueante es definir el modelo legal de las empresas proveedoras de crédito antes de iniciar el desarrollo.

## 4.2 Factibilidad Técnica ✅ VIABLE

| Factor | Estado | Riesgo |
|--------|--------|--------|
| Integración con planillas vía Excel | ✅ Estándar, bajo costo | Bajo |
| Integración vía API con sistemas RRHH | ✅ Viable, requiere esfuerzo por sistema | Medio |
| Cálculo automatizado de capacidad crediticia | ✅ Lógica matemática simple | Bajo |
| Procesamiento de múltiples empresas (multi-tenant) | ✅ Arquitectura conocida | Bajo |
| Flujo de pagos y distribución automática | ✅ Viable, requiere integración bancaria | Medio |
| Firma electrónica digital | ✅ Integración con ADSIB o sistema OTP | Bajo |

**Veredicto:** Totalmente factible. El mayor desafío técnico es la integración bancaria para el flujo de pagos, que depende de la entidad bancaria del cliente.

## 4.3 Factibilidad Comercial ✅ VIABLE (riesgo medio en adopción)

| Factor | Estado | Riesgo |
|--------|--------|--------|
| Propuesta de valor clara para empleados | ✅ Alta | Bajo |
| Propuesta de valor para empresas empleadoras | ✅ Alta (beneficio laboral sin costo) | Bajo |
| Propuesta de valor para empresas proveedoras | ✅ Alta (cartera garantizada) | Bajo |
| Adopción inicial (primeras empresas) | ⚠️ El principal reto comercial | Medio |
| Competencia directa en Bolivia | ✅ Mercado no saturado | Bajo |
| Disposición a pagar de empresas | ✅ Modelo SaaS aceptado en el mercado | Bajo |

**Veredicto:** La propuesta de valor es sólida. El reto comercial principal es conseguir las primeras 3-5 empresas. Se recomienda fuertemente empezar con el portafolio existente del cliente.

## 4.4 Factibilidad Financiera ✅ VIABLE

| Factor | Detalle |
|--------|---------|
| Inversión inicial de desarrollo | USD 28,000 – 37,000 (Fases 1+2) |
| Tiempo de recuperación de inversión | 18 – 24 meses desde lanzamiento |
| Ingresos desde el inicio | Sí (comisiones por transacción) |
| Escalabilidad sin costos lineales | Sí — el costo marginal de agregar un usuario es mínimo |

**Veredicto:** La inversión es recuperable. El modelo de plataforma gratuita acelera la adopción y los ingresos crecen proporcionalmente al volumen de créditos.

## 4.5 Factibilidad Operativa ✅ VIABLE

El operador (cliente) ya cuenta con:
- Experiencia en cobranza y gestión de créditos.
- Relaciones con empresas del mercado boliviano.
- Conocimiento del marco regulatorio ASFI.
- Capacidad para gestionar casos especiales (mora, refinanciación, acuerdos).

Lo que debe desarrollar operativamente:
- Proceso de onboarding de nuevas empresas a la plataforma.
- Protocolo de soporte al empleado (canal de atención).
- Proceso de conciliación de pagos (empresa → plataforma → proveedor).

---

---

# 5. DESCRIPCIÓN DE LA PLATAFORMA

## 5.1 Visión General del Sistema

PlanillaCredit es un sistema web con app móvil complementaria. Tiene cinco portales diferenciados según el actor:

```
┌─────────────────────────────────────────────────────────┐
│              PANEL ADMINISTRADOR DE PLATAFORMA          │
│         (Operador — empresa cliente de Uplabs AI)       │
└───────────────┬────────────────────────────┬────────────┘
                │                            │
    ┌───────────▼──────────┐     ┌───────────▼──────────┐
    │  PORTAL EMPRESA      │     │  PORTAL EMPRESA      │
    │  EMPLEADORA          │     │  PROVEEDORA          │
    │  (RRHH / Gerencia)   │     │  (Comercial / Admin) │
    └───────────┬──────────┘     └───────────┬──────────┘
                │                            │
    ┌───────────▼──────────────────────────────────────┐
    │           PORTAL / APP DEL EMPLEADO              │
    │         (Web responsiva + App móvil)             │
    └──────────────────────────────────────────────────┘
```

## 5.2 Flujo de Vida Completo de un Crédito

```
1. EMPRESA EMPLEADORA se registra y carga su planilla (Excel o API)
        ↓
2. SISTEMA calcula la capacidad crediticia de cada empleado
   (% del salario neto configurable por empresa - cuotas ya comprometidas)
        ↓
3. EMPLEADO ingresa al portal, ve su capacidad disponible
   y navega el catálogo de productos o solicita préstamo
        ↓
4. EMPLEADO elige producto/préstamo y simula cuotas
   Firma digitalmente el contrato → Solicitud enviada
        ↓
5. EMPRESA PROVEEDORA recibe la solicitud
   Revisa y aprueba (o rechaza con motivo)
        ↓
6. Si es producto físico: coordina entrega
   Si es préstamo en efectivo: desembolsa
        ↓
7. FIN DE MES: Sistema genera reporte de descuentos
   Empresa Empleadora descuenta de planilla de cada empleado
        ↓
8. EMPRESA EMPLEADORA transfiere monto total a cuenta de la plataforma
        ↓
9. PLATAFORMA distribuye automáticamente a cada proveedor
   Retiene su comisión
        ↓
10. Ciclo se repite mensualmente hasta cancelación del crédito
```

## 5.3 Módulos del Sistema

---

### MÓDULO 1 — ONBOARDING DE EMPRESAS

**Subproceso: Alta de Empresa Empleadora**
- Formulario de registro con datos legales (Razón Social, NIT, representante legal, datos de contacto RRHH).
- Subida de documentos de verificación (NIT, matrícula de comercio, poder del representante).
- Revisión y aprobación por el administrador de plataforma.
- Configuración de parámetros de crédito:
  - Porcentaje máximo del salario neto comprometible (ej: 25%).
  - Ciclo de pago (mensual / quincenal).
  - Cuenta bancaria para recepción del reporte de descuentos.
- Firma digital del contrato de afiliación.
- Acceso al portal RRHH.

**Subproceso: Alta de Empresa Proveedora**
- Formulario de registro con datos legales y tipo de oferta (productos físicos / préstamos / ambos).
- Documentación de habilitación legal (para prestamistas: licencia ASFI o equivalente).
- Configuración de:
  - Tasas de interés y plazos disponibles.
  - Tipos de productos o montos de préstamo.
  - Cuenta bancaria para recepción de pagos.
- Firma digital del contrato de proveedor.
- Acceso al portal proveedor.

---

### MÓDULO 2 — GESTIÓN DE PLANILLA E INTEGRACIÓN

**Integración vía Excel:**
- Template Excel descargable con campos requeridos:
  - CI del empleado, Nombre completo, Cargo, Salario Bruto, Salario Neto, Fecha de ingreso.
- Carga mensual o bajo demanda desde el portal RRHH.
- Validación automática al subir:
  - Detección de empleados nuevos (altas).
  - Detección de empleados ausentes del archivo anterior (bajas).
  - Alerta de cambios significativos de salario.
  - Errores de formato o datos faltantes.
- Historial de todas las versiones de planilla cargadas.

**Integración vía API:**
- REST API documentada con Swagger/OpenAPI.
- Autenticación con API Key o OAuth2.
- Endpoints principales:
  - `POST /planilla/sync` — Sincronización completa de empleados.
  - `POST /planilla/update` — Actualización de empleados individuales.
  - `GET /empleado/{ci}/capacidad` — Consultar capacidad crediticia de un empleado.
  - `POST /planilla/baja` — Notificar baja de empleado.
- Webhook para que el sistema RRHH del cliente notifique cambios en tiempo real.
- Ambiente sandbox para pruebas de integración.
- Documentación técnica de integración.

**Motor de Cálculo de Capacidad Crediticia:**
```
Capacidad bruta         = Salario Neto × % configurado por empresa
Cuotas comprometidas    = Suma de cuotas mensuales de créditos activos
Capacidad disponible    = Capacidad bruta - Cuotas comprometidas

Restricciones:
  - El salario resultante después del descuento no puede ser < Salario Mínimo Nacional
  - El sistema bloquea automáticamente nuevas solicitudes si la capacidad disponible es $0
  - Alerta al empleado cuando llega al 80% de su capacidad
```

El porcentaje configurable por empresa permite que cada empleadora defina su política (ej: una empresa puede permitir hasta 30% del neto, otra solo 20%).

---

### MÓDULO 3 — PORTAL DEL EMPLEADO

**Acceso y Registro:**
- Registro inicial con CI + número de teléfono (verificado por OTP SMS/WhatsApp).
- Vinculación automática con la empresa empleadora al hacer match del CI en la planilla.
- Si el empleado trabaja en varias empresas afiliadas, puede vincular todas.

**Dashboard del Empleado:**
- Capacidad crediticia disponible (en Bs y USD si aplica).
- Créditos activos con detalle: proveedor, saldo pendiente, próxima cuota, fecha de cobro.
- Historial de créditos pagados.
- Próximo descuento de planilla (fecha y monto).

**Catálogo de Productos y Proveedores:**
- Listado de empresas proveedoras afiliadas.
- Catálogo de productos con foto, descripción, precio y opciones de plazo.
- Filtros por categoría (electrodomésticos, tecnología, ropa, servicios, etc.).
- Filtros por cuota mensual máxima (el empleado ve solo lo que puede pagar).

**Simulador de Crédito:**
- El empleado ingresa: monto deseado + plazo → el sistema muestra cuota mensual, TEA, monto total a pagar.
- El empleado ingresa: cuota mensual máxima que quiere pagar → el sistema muestra montos y plazos disponibles.
- Validación en tiempo real contra la capacidad disponible.

**Solicitud de Crédito:**
- Selección de producto o monto de préstamo.
- Confirmación de plan de pagos.
- Lectura y aceptación del contrato digital (con firma OTP o firma electrónica certificada).
- Envío de solicitud.
- Notificación inmediata al empleado del estado (pendiente de aprobación).

**Seguimiento:**
- Notificaciones en cada etapa: solicitud enviada, en revisión, aprobada/rechazada, producto entregado, cobro realizado.
- Canales: notificación en app + email + WhatsApp/SMS (configurable por empleado).
- Estado en tiempo real desde el portal.

---

### MÓDULO 4 — PORTAL DE EMPRESA PROVEEDORA

**Dashboard Proveedor:**
- Solicitudes pendientes de revisión.
- Cartera activa: total de créditos vigentes, saldo pendiente global.
- Cobros del mes actual (proyectado vs confirmado).
- Rendimiento por empresa empleadora.

**Gestión de Solicitudes:**
- Bandeja de solicitudes entrantes con datos del empleado (CI, empresa, salario neto, capacidad disponible, créditos activos).
- Aprobación con un clic (si la capacidad valida automáticamente).
- Rechazo con motivo seleccionable (para retroalimentación al empleado).
- Vista de historial crediticio del empleado dentro de la plataforma.

**Gestión de Cartera:**
- Listado de todos los créditos activos por empresa empleadora.
- Estado de cada cuota (pendiente, confirmada, mora).
- Alertas de pagos no recibidos.
- Gestión de casos especiales (empleado dado de baja).

**Catálogo de Productos (para proveedores de bienes):**
- Alta, edición y baja de productos.
- Gestión de stock y disponibilidad.
- Configuración de plazos y tasas por producto o categoría.

**Reportes Financieros:**
- Estado de cuenta mensual de cobros recibidos de la plataforma.
- Comisiones cobradas por la plataforma.
- Proyección de flujo de caja de cobros futuros.
- Exportación en Excel y PDF.

---

### MÓDULO 5 — PORTAL RRHH / EMPRESA EMPLEADORA

**Dashboard RRHH:**
- Resumen de empleados con crédito activo.
- Total a descontar en la próxima planilla (por empleado y total).
- Estado de transferencias anteriores a la plataforma.

**Gestión de Planilla:**
- Carga de planilla (Excel o sincronización API).
- Vista de cambios detectados (altas, bajas, cambios de salario).
- Confirmación de cambios antes de aplicar.
- Historial de versiones.

**Reporte de Descuentos:**
- Generado automáticamente al cierre de cada ciclo.
- Lista de empleados con monto exacto a descontar.
- Formato compatible con los principales sistemas de planilla bolivianos.
- Exportación en Excel/PDF para el proceso de pago de salarios.
- Botón de confirmación "Planilla procesada" — activa el plazo para transferir a la plataforma.

**Gestión de Transferencias:**
- Registro de la transferencia realizada a la plataforma (número de operación, fecha, monto).
- Conciliación automática o manual.
- Alertas de plazos de pago vencidos.

**Gestión de Casos Especiales:**
- Reporte de empleados dados de baja con deuda activa.
- Opciones configurables: notificación al proveedor, gestión de acuerdo directo, derivación a cobranza.

---

### MÓDULO 6 — PANEL ADMINISTRADOR DE PLATAFORMA

**Gestión de Empresas:**
- Listado y estado de todas las empresas (empleadoras y proveedoras).
- Activar / Suspender / Configurar cada empresa.
- Ver historial de pagos y cumplimiento de cada empresa.
- Comunicación directa desde el panel (notificaciones, alertas).

**Gestión de Créditos Global:**
- Vista global de toda la cartera de la plataforma.
- Filtros por empresa, estado, vencimiento, monto.
- Intervención manual en casos especiales.

**Gestión de Pagos y Conciliación:**
- Registro de todas las transferencias recibidas de empresas empleadoras.
- Distribución automática (o con confirmación manual) a proveedores.
- Retención automática de la comisión de la plataforma.
- Estado de cuenta de cada actor.
- Alertas de pagos vencidos o incompletos.

**Facturación y Cobro SaaS:**
- Generación automática de facturas mensuales a empresas afiliadas.
- Registro de pagos del SaaS.
- Suspensión automática por mora en el pago del SaaS.

**Reportes de Plataforma:**
- Volumen total de créditos originados.
- Comisiones generadas por período.
- Tasa de mora de la plataforma.
- Crecimiento de empresas y empleados activos.
- Reportes para auditoría interna y cumplimiento ASFI.

**Configuración Global:**
- Parámetros por defecto de nuevas empresas.
- Tasas de comisión configurables.
- Plantillas de contratos y notificaciones.
- Gestión de usuarios administradores y roles.

---

### MÓDULO 7 — NOTIFICACIONES Y COMUNICACIONES

**Canales de Notificación:**
- Email transaccional (obligatorio para todos los actores).
- WhatsApp Business API (preferido para empleados en Bolivia).
- SMS (fallback cuando WhatsApp no disponible).
- Notificaciones push en app móvil.
- Notificaciones en el panel web (bandeja interna).

**Eventos que Generan Notificación:**

| Evento | Destinatario | Canal |
|--------|-------------|-------|
| Solicitud de crédito recibida | Proveedor | Email + Panel |
| Solicitud aprobada | Empleado | WhatsApp + Email |
| Solicitud rechazada | Empleado | WhatsApp + Email |
| Recordatorio de pago de planilla | RRHH de empresa empleadora | Email |
| Planilla procesada confirmada | Administrador | Panel |
| Transferencia recibida | Administrador + Proveedor | Email |
| Empleado dado de baja con deuda | Proveedor + Administrador | Email + Panel |
| Cuota próxima a vencer | Empleado | WhatsApp |
| Capacidad crediticia al 80% | Empleado | WhatsApp |
| Nueva empresa afiliada | Administrador | Panel |

---

## 5.4 Aplicación Móvil (Fase 2)

La app móvil está orientada principalmente al **empleado**, complementando el portal web con:

- Acceso rápido al balance de capacidad crediticia.
- Catálogo de productos con búsqueda y filtros.
- Solicitud de crédito simplificada (flujo de 3 pasos).
- Historial y estado de créditos.
- Notificaciones push.
- Biometría para login (huella/Face ID).
- Descarga de comprobantes en PDF.

**Plataformas:** iOS y Android.  
**Desarrollo:** React Native (código compartido ~80% entre plataformas).

---

---

# 6. ARQUITECTURA TÉCNICA

## 6.1 Stack Tecnológico

| Capa | Tecnología | Versión | Justificación |
|------|-----------|---------|---------------|
| **Frontend Web** | Next.js + TypeScript | 14+ | SSR/SSG, performance, un solo equipo para todos los portales |
| **Estilos** | Tailwind CSS + shadcn/ui | — | Velocidad de desarrollo, consistencia visual |
| **App Móvil** | React Native + Expo | SDK 51+ | Código compartido iOS/Android, mismo stack JS del equipo |
| **Backend** | NestJS (Node.js) + TypeScript | 10+ | Arquitectura modular, inyección de dependencias, escalable |
| **API** | REST + OpenAPI/Swagger | — | Documentación automática, integración con sistemas externos |
| **Base de Datos** | PostgreSQL | 16+ | ACID completo para transacciones financieras |
| **ORM** | Prisma | — | Type-safe, migraciones controladas |
| **Cache / Cola** | Redis + BullMQ | — | Sesiones, jobs asíncronos (planillas, notificaciones) |
| **Almacenamiento** | AWS S3 / Cloudflare R2 | — | Documentos, contratos, archivos Excel |
| **Autenticación** | JWT + Refresh Tokens | — | Multi-tenant seguro, sesiones largas controladas |
| **Email** | Resend | — | Alta entregabilidad, API simple |
| **WhatsApp/SMS** | Twilio o Meta Business API | — | Notificaciones a empleados |
| **Hosting** | Railway o AWS ECS | — | Región Latinoamérica, escalabilidad automática |
| **CI/CD** | GitHub Actions | — | Deploy automático en cada merge a producción |
| **Monitoreo** | Sentry + Grafana | — | Errores en tiempo real, métricas de performance |

## 6.2 Arquitectura de Despliegue

```
┌──────────────────────────────────────────────────────────┐
│                    CDN / Cloudflare                       │
│              (Cache, DDoS protection, SSL)                │
└───────────────────────┬──────────────────────────────────┘
                        │
┌───────────────────────▼──────────────────────────────────┐
│                  Load Balancer (AWS ALB)                  │
└──────┬──────────────────────────────┬────────────────────┘
       │                              │
┌──────▼──────┐               ┌───────▼──────┐
│  Next.js    │               │   NestJS     │
│  Frontend   │               │   Backend    │
│  (2+ pods)  │               │   (2+ pods)  │
└─────────────┘               └───────┬──────┘
                                      │
              ┌───────────────────────┼───────────────────┐
              │                       │                   │
       ┌──────▼──────┐        ┌───────▼────┐     ┌───────▼────┐
       │ PostgreSQL  │        │   Redis    │     │  AWS S3    │
       │  (Primary + │        │  (Cache +  │     │ (Archivos) │
       │   Replica)  │        │   Queue)   │     └────────────┘
       └─────────────┘        └────────────┘
```

## 6.3 Arquitectura Multi-Tenant

El sistema usa un modelo de multi-tenancy con **aislamiento lógico de datos por empresa**:

- Una sola base de datos con campo `tenant_id` en todas las tablas relevantes.
- Middleware de autenticación que inyecta el contexto del tenant en cada request.
- Políticas de Row Level Security (RLS) en PostgreSQL como capa adicional de seguridad.
- Subdominio personalizable: `nombreempresa.planillacredit.bo`.

## 6.4 Seguridad

| Capa | Medida de Seguridad |
|------|---------------------|
| **Transporte** | TLS 1.3 obligatorio, HSTS, certificados SSL auto-renovables |
| **Autenticación** | JWT con expiración corta (15 min) + Refresh Token (30 días) |
| **Autorización** | RBAC (Role-Based Access Control) por portal y acción |
| **2FA** | Obligatorio para administradores y personal RRHH |
| **Base de datos** | Datos financieros sensibles encriptados en reposo (AES-256) |
| **Secretos** | Variables de entorno gestionadas con AWS Secrets Manager |
| **Rate Limiting** | Por IP y por usuario para todos los endpoints |
| **Auditoría** | Log inmutable de todas las transacciones financieras y cambios críticos |
| **Vulnerabilidades** | Checklist OWASP Top 10 en cada release; dependencias auditadas con `npm audit` |
| **Backups** | Backup automático diario de base de datos con retención de 30 días |

## 6.5 Integraciones Externas

| Sistema | Tipo | Propósito | Fase |
|---------|------|-----------|------|
| Sistemas de planilla bolivianos | API / Excel | Sincronización de empleados | 1 (Excel) / 2 (API) |
| Bancos bolivianos | API bancaria o webhook manual | Conciliación de transferencias | 1 (manual) / 2 (automático) |
| ADSIB Bolivia | API firma electrónica | Validez legal de contratos | 1-2 |
| INFOCRED (Buró de Crédito) | API | Consulta historial crediticio | 3 |
| Twilio / Meta API | API | WhatsApp y SMS | 1 |
| Resend | API | Email transaccional | 1 |

---

---

# 7. PLAN DE IMPLEMENTACIÓN

## 7.1 Metodología de Trabajo

- **Metodología:** Scrum adaptado — sprints de 2 semanas.
- **Entregas:** Demo funcional al final de cada sprint.
- **Comunicación:** Reunión semanal de avance con el cliente (30 min).
- **Control de versiones:** GitHub con estrategia de ramas (main/develop/feature).
- **Gestión:** Tablero de tareas en Linear o Notion (a definir con el cliente).
- **Ambiente de pruebas:** Ambiente de staging siempre disponible para revisión del cliente.

## 7.2 Fases y Sprints

---

### FASE 1 — MVP (16 semanas / 4 meses)

**Objetivo:** Plataforma funcional lista para las primeras empresas reales.

| Sprint | Semanas | Entregables |
|--------|---------|-------------|
| **Sprint 1** | 1-2 | Arquitectura base, infraestructura cloud, base de datos, sistema de autenticación y roles, CI/CD básico |
| **Sprint 2** | 3-4 | Onboarding de empresa empleadora (formulario, documentos, aprobación), panel admin básico |
| **Sprint 3** | 5-6 | Carga de planilla vía Excel, validaciones, motor de cálculo de capacidad crediticia, historial |
| **Sprint 4** | 7-8 | Onboarding empresa proveedora, catálogo de productos básico, configuración de tasas y plazos |
| **Sprint 5** | 9-10 | Portal del empleado: registro, dashboard, simulador de crédito, solicitud de crédito |
| **Sprint 6** | 11-12 | Flujo de aprobación/rechazo por proveedor, generación de contrato digital, firma OTP |
| **Sprint 7** | 13-14 | Módulo de descuentos RRHH, reporte de planilla, registro de transferencias, distribución a proveedores |
| **Sprint 8** | 15-16 | Notificaciones (email + WhatsApp), reportes básicos, testing integral, correcciones, deploy producción |

**Criterio de aceptación MVP:**
- 2 empresas empleadoras con planilla cargada y activa.
- 1 empresa proveedora con catálogo.
- 10+ empleados con acceso al portal.
- Al menos 1 ciclo completo de crédito (solicitud → aprobación → descuento → pago → distribución).

---

### FASE 2 — CONSOLIDACIÓN (12 semanas / 3 meses)

**Objetivo:** Madurar la plataforma para escalar a 5-10 empresas y lanzar la app móvil.

| Sprint | Semanas | Entregables |
|--------|---------|-------------|
| **Sprint 9** | 1-2 | API de integración de planilla (documentación + endpoints + sandbox) |
| **Sprint 10** | 3-4 | Gestión de casos especiales: baja de empleados, mora, refinanciación |
| **Sprint 11** | 5-6 | App móvil — empleado: login, dashboard, solicitud de crédito, notificaciones push |
| **Sprint 12** | 7-8 | App móvil — pulido, biometría, testing en dispositivos físicos iOS/Android |
| **Sprint 13** | 9-10 | Reportes avanzados: dashboard ejecutivo, análisis de cartera, proyecciones |
| **Sprint 14** | 11-12 | Pruebas de carga y optimización, seguridad (auditoría OWASP), documentación de usuario |

**Criterio de aceptación Fase 2:**
- API de planilla documentada y con al menos 1 integración real.
- App móvil publicada en App Store y Google Play.
- Sistema procesando el ciclo de pago completo sin intervención manual.
- 5+ empresas activas, 300+ empleados.

---

### FASE 3 — ESCALAMIENTO (16 semanas / 4 meses)

**Objetivo:** Diferenciación con scoring propio, integración con buró de crédito y apertura de la API.

| Sprint | Semanas | Entregables |
|--------|---------|-------------|
| **Sprint 15-16** | 1-4 | Integración INFOCRED (consulta de historial crediticio boliviano) |
| **Sprint 17-18** | 5-8 | Motor de scoring interno basado en historial de la plataforma |
| **Sprint 19-20** | 9-12 | API pública documentada para que empresas externas integren PlanillaCredit |
| **Sprint 21-22** | 13-16 | Módulo de ofertas segmentadas, preparación multi-país, optimizaciones finales |

---

## 7.3 Cronograma General

```
2026     MAY    JUN    JUL    AGO    SEP    OCT    NOV    DIC
         ├──────────────────────────────────────────────────┤
FASE 1   [████████████████ MVP (4 meses) ████████████████]
                                   [██████ FASE 2 ██████████████]
                                                       [████ FASE 3 ...
```

---

---

# 8. EQUIPO DE TRABAJO

## 8.1 Roles y Dedicación

| Rol | Descripción | Dedicación | Fase |
|-----|-------------|-----------|------|
| **Tech Lead / Arquitecto** | Decisiones de arquitectura, code review, integración entre módulos, punto de contacto técnico con el cliente | 100% | Completo |
| **Backend Developer Senior** | NestJS, lógica de negocio, APIs, integraciones, seguridad | 100% | Completo |
| **Frontend Developer Senior** | Next.js, todos los portales web, UI/UX implementation | 100% | Completo |
| **Mobile Developer** | React Native, app del empleado | 100% | Fase 2-3 |
| **QA Engineer** | Plan de pruebas, testing manual y automatizado, regresión | 50% | Completo |
| **DevOps / Infraestructura** | CI/CD, cloud, monitoreo, backups, seguridad de infraestructura | 25% | Completo |
| **UI/UX Designer** | Diseño de interfaces, flujos de usuario, sistema de diseño | 100% | Fase 1 / 50% Fase 2 |
| **Project Manager** | Coordinación, comunicación con cliente, control de avance | 25% | Completo |

## 8.2 Responsabilidades del Cliente (No Uplabs AI)

Para que el proyecto avance sin bloqueos, el cliente debe garantizar:

| Responsabilidad | Plazo |
|----------------|-------|
| Definición del modelo legal con su abogado | Antes de Sprint 1 |
| Provisión de contratos en borrador para integrar en la plataforma | Antes de Sprint 6 |
| Acceso a datos de planilla de empresa piloto (para pruebas) | Antes de Sprint 3 |
| Cuenta bancaria y datos de integración para flujo de pagos | Antes de Sprint 7 |
| Disponibilidad para revisión de demos cada 2 semanas | Durante todo el proyecto |
| Definición de logos, colores y nombre final de la plataforma | Antes de Sprint 2 |
| Acceso a cuenta de WhatsApp Business | Antes de Sprint 8 |

---

---

# 9. PRESUPUESTO DE DESARROLLO

## 9.1 Opción A — Por Fases (Recomendada)

Esta opción permite al cliente validar el modelo de negocio con el MVP antes de comprometer la inversión total.

### Fase 1 — MVP

| Componente | Descripción | Precio USD |
|-----------|-------------|-----------|
| Diseño UI/UX | Sistema de diseño, wireframes, prototipos de todos los portales | 2,500 |
| Arquitectura y setup | Infraestructura cloud, CI/CD, base de datos, seguridad base | 2,000 |
| Backend — Core | Auth, multi-tenant, módulo de planilla, motor crediticio | 4,500 |
| Backend — Flujos | Créditos, pagos, distribución, notificaciones | 3,500 |
| Frontend Web | 5 portales web completos (admin, empleadora, proveedora, empleado, RRHH) | 5,500 |
| QA y Testing | Plan de pruebas, testing integral, reporte de bugs | 1,500 |
| Deploy y documentación | Despliegue en producción, documentación técnica y de usuario | 1,000 |
| **Total Fase 1 — MVP** | | **USD 20,500** |

*Rango de mercado: USD 18,000 – 23,000 según ajustes de alcance.*

---

### Fase 2 — Consolidación

| Componente | Descripción | Precio USD |
|-----------|-------------|-----------|
| API de integración de planilla | Documentación, endpoints, sandbox, guía de integración | 2,500 |
| App móvil iOS + Android | Portal del empleado completo (React Native) | 6,000 |
| Gestión de casos especiales | Baja de empleados, mora, refinanciación | 1,500 |
| Reportes avanzados | Dashboard ejecutivo, análisis de cartera | 2,000 |
| Pruebas de carga y seguridad | Auditoría, optimización, testing de stress | 1,500 |
| **Total Fase 2** | | **USD 13,500** |

*Rango de mercado: USD 12,000 – 15,000.*

---

### Fase 3 — Escalamiento

| Componente | Descripción | Precio USD |
|-----------|-------------|-----------|
| Integración INFOCRED | Consulta historial crediticio boliviano | 2,500 |
| Motor de scoring interno | Algoritmo basado en historial de plataforma | 3,500 |
| API pública | Para integración de sistemas externos de terceros | 2,500 |
| Módulo de ofertas y marketing | Segmentación, campañas de proveedores | 1,500 |
| Preparación multi-país | Adaptación de arquitectura para expansión | 2,000 |
| **Total Fase 3** | | **USD 12,000** |

*Rango de mercado: USD 10,000 – 14,000.*

---

### Resumen Inversión Total

| | Precio |
|-|--------|
| **Fase 1 — MVP** | **USD 20,500** |
| **Fase 2 — Consolidación** | **USD 13,500** |
| **Fase 3 — Escalamiento** | **USD 12,000** |
| **TOTAL PROYECTO COMPLETO** | **USD 46,000** |

---

## 9.2 Opción B — Proyecto Llave en Mano (Fases 1 + 2)

Para clientes que prefieren comprometer el alcance completo desde el inicio con un precio cerrado.

| Concepto | Precio USD |
|---------|-----------|
| Desarrollo completo Fases 1 y 2 | **USD 30,000** |
| *Ahorro vs. precio por fases* | *USD 4,000 (13%)* |

---

## 9.3 Costos Recurrentes Post-Lanzamiento (a cargo del cliente)

Estos costos son del operador de la plataforma una vez en producción, no son costos de Uplabs AI:

| Concepto | Estimación Mensual |
|---------|-------------------|
| Infraestructura cloud (AWS o Railway) | USD 150 – 400 |
| WhatsApp Business API (por mensaje) | USD 0.03 – 0.08 / mensaje |
| SMS fallback (por mensaje) | USD 0.05 – 0.10 / mensaje |
| Email transaccional (Resend) | USD 0 – 20 (hasta 100K emails/mes gratis) |
| Dominio + SSL | USD 15 – 30 / año |
| Mantenimiento Uplabs AI (opcional) | USD 800 – 1,500 / mes |
| **Total estimado (sin mantenimiento)** | **USD 200 – 500 / mes** |

---

## 9.4 Estructura de Pagos Sugerida

**Para Opción A (por fases):**

| Hito | % | Monto Fase 1 |
|------|---|-------------|
| Firma de contrato e inicio | 35% | USD 7,175 |
| Entrega de Sprint 4 (mitad del MVP) | 30% | USD 6,150 |
| Entrega y aceptación del MVP | 25% | USD 5,125 |
| Correcciones y cierre de Fase 1 | 10% | USD 2,050 |

**Para Opción B (llave en mano Fases 1+2):**

| Hito | % | Monto |
|------|---|-------|
| Inicio | 30% | USD 9,000 |
| Entrega MVP (Fase 1 completa) | 35% | USD 10,500 |
| Entrega app móvil y API (Fase 2) | 25% | USD 7,500 |
| Cierre y estabilización | 10% | USD 3,000 |

---

---

# 10. PROYECCIONES FINANCIERAS

## 10.1 Proyección de Ingresos del Operador (Año 1)

Proyección conservadora basada en la expectativa inicial de 5-10 empresas y ~500 empleados. **Solo comisiones, plataforma gratuita.**

| Mes | Empresas Empleadoras | Empresas Proveedoras | Empleados Activos | Créditos Otorgados | Ticket Promedio | Comisión Prom. | Total Ingresos (USD) |
|-----|---------------------|---------------------|------------------|-------------------|-----------------|---------------|---------------------|
| 1-2 | 0 | 0 | 0 | 0 | — | — | 0 *(desarrollo)* |
| 3-4 | 1-2 | 1 | 50 | 8 | USD 400 | 2.5% | ~80 |
| 5 | 2-3 | 2 | 100 | 20 | USD 450 | 2.5% | ~225 |
| 6 | 3-4 | 2-3 | 180 | 40 | USD 500 | 2.5% | ~500 |
| 7-8 | 4-6 | 3-4 | 280 | 70 | USD 500 | 2.5% | ~875 |
| 9-10 | 6-8 | 4-5 | 400 | 120 | USD 550 | 2.5% | ~1,650 |
| 11-12 | 8-12 | 5-7 | 600 | 180 | USD 600 | 2.5% | ~2,700 |

**Ingreso acumulado estimado Año 1:** USD 18,000 – 28,000

**Notas:**
- Los créditos otorgados asumen una tasa de penetración inicial del 15-25% de los empleados activos.
- El ticket promedio aumenta gradualmente a medida que los empleados ganan confianza en la plataforma.
- La comisión promedio de 2.5% es un promedio ponderado entre productos (2.5-3.5%) y préstamos (1.5-2.5%).

## 10.2 Proyección Año 2 (Operación Estabilizada)

Con 15-25 empresas afiliadas y 1,000-2,000 empleados activos:

| Concepto | Estimación Mensual |
|---------|-------------------|
| Créditos mensuales | 250 – 450 |
| Ticket promedio | USD 600 – 800 |
| Volumen total mensual | USD 150,000 – 360,000 |
| Comisión promedio | 2.5% |
| **Total ingresos mensuales** | **USD 3,750 – 9,000** |
| Costos operativos mensuales | USD 1,800 – 3,200 |
| **Margen operativo mensual** | **USD 2,000 – 5,800** |

**Ingreso anual estimado Año 2:** USD 45,000 – 108,000

## 10.3 Punto de Equilibrio de la Inversión

| Escenario | Inversión (Fases 1+2) | Volumen Mensual Necesario | Tiempo Estimado |
|-----------|----------------------|--------------------------|-----------------|
| Conservador | USD 30,000 | USD 60,000 en créditos (~USD 1,500 comisiones) | 18-20 meses |
| Moderado | USD 30,000 | USD 120,000 en créditos (~USD 3,000 comisiones) | 12-14 meses |
| Optimista | USD 30,000 | USD 200,000 en créditos (~USD 5,000 comisiones) | 8-10 meses |

**Ventaja del modelo gratuito:** Aunque los ingresos iniciales son más bajos que en un modelo SaaS+comisión, la **velocidad de adopción es significativamente mayor** al eliminar la fricción del pago mensual. El punto de equilibrio se alcanza con menor cantidad de empresas, pero mayor volumen transaccional.

---

---

# 11. GESTIÓN DE RIESGOS

## 11.1 Matriz de Riesgos

| # | Riesgo | Probabilidad | Impacto | Nivel |
|---|--------|-------------|---------|-------|
| R1 | Modelo legal de proveedores no viable sin licencia ASFI | Baja | Crítico | **ALTO** |
| R2 | Baja adopción inicial de empresas empleadoras | Media | Alto | **ALTO** |
| R3 | Empresa empleadora no transfiere los fondos descontados | Media | Alto | **ALTO** |
| R4 | Empleado abandona empresa con deuda activa | Alta | Medio | **MEDIO** |
| R5 | Retraso en integraciones bancarias | Media | Medio | **MEDIO** |
| R6 | Cambio regulatorio de ASFI durante el proyecto | Baja | Alto | **MEDIO** |
| R7 | Brecha de seguridad o acceso no autorizado a datos | Baja | Crítico | **MEDIO** |
| R8 | Retraso en entregas por dependencias del cliente | Media | Medio | **MEDIO** |
| R9 | Resistencia de empleados a compartir datos de salario | Baja | Bajo | **BAJO** |
| R10 | Competidor similar lanza en Bolivia durante el desarrollo | Muy Baja | Medio | **BAJO** |

## 11.2 Plan de Mitigación

**R1 — Modelo legal de proveedores:**
- Mitigación: Consulta legal antes de iniciar el proyecto. Arrancar con Modelo A (plataforma como canal exclusivo del operador para crédito en efectivo; proveedores solo productos físicos/servicios).
- Contingencia: Si el Modelo B es inviable, el negocio sigue funcionando con Modelo A.

**R2 — Baja adopción inicial:**
- Mitigación: Usar el portafolio de clientes existentes del operador como empresas piloto. La plataforma es 100% gratuita, eliminando la principal barrera de entrada. Ofrecer soporte de onboarding personalizado a las primeras 5-10 empresas.
- Contingencia: Estrategia comercial activa con visitas presenciales, demos personalizadas y casos de éxito documentados.

**R3 — Empresa empleadora no transfiere fondos:**
- Mitigación: Contrato con penalidades claras. Suspensión automática del servicio ante mora. Descuento solo se hace efectivo cuando la empresa confirma en el sistema el pago de planilla.
- Contingencia: Acción legal con el contrato de afiliación como respaldo.

**R4 — Empleado abandona empresa con deuda:**
- Mitigación: Contrato tripartito que establece las opciones: (a) la empresa empleadora retiene la deuda del sueldo final, (b) el empleado firma acuerdo de pago directo al momento del crédito, (c) gestión de cobranza del operador.
- Contingencia: El operador activa su proceso de cobranza existente.

**R5 — Retraso en integraciones bancarias:**
- Mitigación: MVP con conciliación manual (empresa sube comprobante de transferencia, admin confirma). Automatización bancaria en Fase 2.

**R6 — Cambio regulatorio ASFI:**
- Mitigación: Arquitectura flexible que permite modificar flujos de negocio sin reescribir el sistema. Monitoreo de normativa ASFI durante el proyecto.

**R7 — Brecha de seguridad:**
- Mitigación: Auditoría de seguridad (OWASP) antes del lanzamiento de cada fase. 2FA obligatorio para roles críticos. Logs de auditoría inmutables. Backups diarios.
- Contingencia: Plan de respuesta a incidentes definido antes del lanzamiento.

**R8 — Dependencias del cliente:**
- Mitigación: Lista de entregables del cliente con fechas en el contrato de desarrollo. Sprint bloqueado = sprint de recuperación sin costo adicional si el bloqueo es del cliente.

---

---

# 12. PRÓXIMOS PASOS

Los siguientes pasos están ordenados por prioridad y dependencia. Los pasos 1-3 son bloqueantes para iniciar el desarrollo.

## Paso 1 — Validación Legal (Semana 1-2)
**Responsable:** Cliente con su abogado  
Determinar el modelo legal definitivo para las empresas proveedoras de crédito. ¿Opera la plataforma como canal exclusivo del operador (Modelo A) o como marketplace de entidades financieras (Modelo B)?  
**Output esperado:** Decisión documentada sobre el modelo de negocio legal.

## Paso 2 — Aprobación del Proyecto (Semana 1-2)
**Responsable:** Cliente + Uplabs AI  
Revisión y ajuste de este documento. Firma del contrato de desarrollo. Selección de la opción de presupuesto (A por fases o B llave en mano).  
**Output esperado:** Contrato firmado, cronograma acordado, canal de comunicación establecido.

## Paso 3 — Definición de Identidad de Marca (Semana 2)
**Responsable:** Cliente  
Nombre final de la plataforma, logotipo, colores corporativos, dominio web (.bo o .com).  
**Output esperado:** Brief de marca completo entregado a Uplabs AI.

## Paso 4 — Kick-off Comercial (Semana 2-3)
**Responsable:** Cliente  
Identificar y comprometer las 2-3 primeras empresas empleadoras piloto (idealmente del portafolio actual del cliente). Identificar la primera empresa proveedora para el MVP.  
**Output esperado:** Lista de empresas piloto confirmadas, contacto de la persona de RRHH.

## Paso 5 — Workshop de UX (Semana 3-4)
**Responsable:** Uplabs AI + Cliente  
Sesión de 2-3 horas para validar los flujos de usuario principales antes de diseñar y codificar. Se revisan: flujo de solicitud de crédito, flujo de descuento de planilla y flujo de aprobación del proveedor.  
**Output esperado:** Flujos validados y aprobados por el cliente.

## Paso 6 — Inicio de Sprint 1 (Semana 4-5)
**Responsable:** Uplabs AI  
Una vez completados los pasos 1-3, inicio formal del desarrollo.

---

---

## APÉNDICE A — GLOSARIO

| Término | Definición |
|---------|-----------|
| **ASFI** | Autoridad de Supervisión del Sistema Financiero — regulador financiero de Bolivia |
| **Capacidad Crediticia** | Monto máximo de crédito que un empleado puede comprometer (% salario neto - cuotas activas) |
| **Descuento de Planilla** | Mecanismo por el cual la empresa retiene la cuota del salario del empleado antes de pagarlo |
| **Empresa Empleadora** | Empresa que afilia su planilla para que empleados accedan a créditos |
| **Empresa Proveedora** | Empresa que ofrece productos o préstamos a través de la plataforma |
| **INFOCRED** | Buró de crédito de Bolivia — registro de historial crediticio |
| **Modelo A** | Plataforma como canal exclusivo del operador para crédito en efectivo |
| **Modelo B** | Plataforma como marketplace de múltiples entidades financieras |
| **Multi-tenant** | Arquitectura donde múltiples empresas comparten el sistema con datos aislados |
| **MVP** | Minimum Viable Product — versión mínima funcional para validar el negocio |
| **OTP** | One-Time Password — código de un solo uso para verificación/firma |
| **RBAC** | Role-Based Access Control — control de acceso basado en roles |
| **SaaS** | Software as a Service — modelo de suscripción mensual al software |
| **SMN** | Salario Mínimo Nacional — mínimo inembargable en Bolivia |
| **TEA** | Tasa Efectiva Anual — costo real del crédito expresado anualmente |

---

## APÉNDICE B — PREGUNTAS FRECUENTES

**¿La plataforma reemplaza el sistema de planilla de la empresa?**  
No. PlanillaCredit se integra *con* el sistema de planilla existente, ya sea leyendo el Excel que la empresa ya genera o conectándose vía API. La empresa sigue usando su sistema actual.

**¿Qué pasa si un empleado es despedido y tiene deuda activa?**  
El contrato tripartito (empresa-empleado-plataforma) define el protocolo: (1) descuento del sueldo final si alcanza para cubrir la cuota, (2) acuerdo de pago directo por el empleado, o (3) derivación al proceso de cobranza del operador.

**¿Pueden las empresas proveedoras ser de cualquier rubro?**  
Sí, con la condición de que los productos/servicios sean legales y que, si ofrecen crédito en efectivo, cuenten con la habilitación legal correspondiente.

**¿El empleado puede tener créditos de múltiples proveedores al mismo tiempo?**  
Sí, siempre que la suma de las cuotas mensuales no supere su capacidad crediticia disponible.

**¿La plataforma cobra al empleado?**  
No directamente. El empleado no paga por usar la plataforma. La comisión de la plataforma está incluida en la tasa del crédito o es cobrada al proveedor.

---

*Documento elaborado por Uplabs AI | Confidencial — Solo para uso interno del cliente*  
*Versión 1.0 — Mayo 2026*
