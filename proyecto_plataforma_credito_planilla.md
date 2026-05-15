# PROYECTO: PLATAFORMA DE CRÉDITO VÍA PLANILLA
## Documento de Factibilidad y Plan de Proyecto

**Cliente:** Empresa de préstamos y cobranza (Bolivia)  
**Elaborado por:** Uplabs AI  
**Fecha:** Mayo 2026  
**Versión:** 1.0

---

## 1. RESUMEN EJECUTIVO

Se propone el desarrollo de una plataforma digital B2B llamada provisionalmente **"PlanillaCredit"** que conecta tres actores: (1) empresas empleadoras que afilian su planilla para que accedan a créditos, (2) empresas proveedoras de productos/servicios a crédito, y (3) empleados como beneficiarios finales. El diferenciador central es el **descuento automático de cuotas vía planilla**, eliminando el riesgo de incobrabilidad y haciendo atractivo el crédito tanto para el proveedor como para el empleado.

**La plataforma es 100% GRATUITA** para empresas empleadoras y proveedoras. El operador genera ingresos únicamente por comisión sobre cada crédito originado.

El operador de la plataforma es la empresa cliente (entidad financiera regulada ante ASFI Bolivia), lo que habilita legalmente la intermediación de créditos en efectivo.

---

## 2. ANÁLISIS DE FACTIBILIDAD

### 2.1 Factibilidad Legal/Regulatoria ✅ VIABLE
- El cliente opera como entidad financiera regulada (ASFI), lo que permite:
  - Intermediación de créditos en efectivo
  - Cobro de intereses y comisiones
  - Gestión de cobranza automatizada
- **Riesgo identificado:** La plataforma actúa como marketplace para que *otras* empresas ofrezcan crédito. Se debe verificar si dichas empresas requieren licencia ASFI propia o si operan bajo el paraguas del cliente. **Acción requerida:** Consulta legal para definir el modelo jurídico de las empresas proveedoras de crédito en la plataforma.
- El descuento de planilla requiere acuerdo firmado entre la empresa empleadora, el empleado y la plataforma (consentimiento expreso).

### 2.2 Factibilidad Técnica ✅ VIABLE
- Integración Excel + API con sistemas de planilla es estándar y ejecutable.
- Los principales sistemas de RRHH en Bolivia (Tanner, SAP, sistemas locales) tienen exportación Excel nativa.
- Arquitectura cloud escalable desde el inicio es costo-efectiva en ese rango de usuarios.

### 2.3 Factibilidad Comercial ✅ VIABLE CON RIESGO MEDIO
- **Mercado objetivo inicial:** 5-10 empresas, ~500 empleados (fase piloto)
- **Propuesta de valor clara:** El empleado accede a crédito sin burocracia bancaria; la empresa proveedora elimina el riesgo de impago; la empresa empleadora ofrece un beneficio laboral sin costo.
- **Riesgo principal:** Adopción inicial — convencer a las primeras empresas empleadoras de integrar su planilla. Se recomienda arrancar con empresas del propio portafolio del cliente.

### 2.4 Factibilidad Financiera ✅ VIABLE
- Modelo de comisiones puras elimina complejidad de facturación recurrente.
- Plataforma gratuita acelera la adopción comercial significativamente.
- El ticket promedio de crédito en Bolivia (electrodomésticos: USD 300-1,500; préstamos: USD 200-2,000) genera comisiones suficientes con volumen moderado.
- Punto de equilibrio: ~120-150 créditos/mes (alcanzable con 6-10 empresas activas).

---

## 3. ACTORES DEL SISTEMA

| Actor | Rol | Acceso |
|-------|-----|--------|
| **Administrador de Plataforma** | Operador (cliente Uplabs) | Panel maestro completo |
| **Empresa Empleadora** | Afilia su planilla para que sus empleados accedan a créditos (GRATIS) | Portal empresa + integración planilla |
| **Empresa Proveedora** | Ofrece productos/préstamos a crédito | Portal proveedor + catálogo + reportes |
| **Empleado** | Solicita créditos/productos | App/portal empleado |
| **RRHH de Empresa** | Gestiona descuentos de planilla | Módulo descuentos + reportes |

---

## 4. MÓDULOS DEL SISTEMA

### MÓDULO 1: ONBOARDING DE EMPRESAS
**Empresas Empleadoras:**
- Registro y verificación de empresa (NIT, datos legales)
- Firma digital de contrato de afiliación
- Configuración de parámetros de crédito (% máximo del salario neto descontable, configurable por empresa)
- Alta de empleados vía Excel o API
- Definición de ciclo de pago (quincenal/mensual)

**Empresas Proveedoras:**
- Registro y verificación
- Configuración de catálogo de productos o tipo de crédito ofrecido
- Definición de tasas de interés y plazos disponibles
- Integración bancaria para recepción de pagos

### MÓDULO 2: INTEGRACIÓN DE PLANILLA
**Vía Excel:**
- Template estándar descargable (nombre, CI, salario bruto, salario neto, cargo)
- Carga mensual o bajo demanda
- Validación automática y detección de altas/bajas/modificaciones
- Historial de versiones de planilla

**Vía API:**
- REST API documentada con Swagger
- Autenticación OAuth2 / API Key
- Webhook para notificación de cambios en planilla
- Sandbox para pruebas de integración

**Motor de Cálculo de Capacidad Crediticia:**
- Fórmula base: `Capacidad = Salario Neto × % configurado por empresa`
- Descuentos ya comprometidos: `Capacidad disponible = Capacidad - cuotas activas`
- Actualización automática al cargar nueva planilla
- Alerta cuando empleado se acerca al límite

### MÓDULO 3: SOLICITUD DE CRÉDITO (Portal del Empleado)
- Login con CI o correo + contraseña
- Vista de capacidad crediticia disponible
- Catálogo de empresas proveedoras y sus productos/préstamos
- Simulador de crédito (monto → cuota mensual → plazo)
- Solicitud en línea con firma digital
- Tracking del estado de la solicitud
- Historial de créditos activos y pagados
- Notificaciones (WhatsApp/SMS/email) en cada etapa

### MÓDULO 4: GESTIÓN DE CRÉDITOS (Portal Proveedor)
- Recepción y revisión de solicitudes
- Aprobación/rechazo con motivo
- Generación automática de contrato de crédito
- Gestión de cartera activa
- Reportes de cobro por empresa empleadora
- Estado de cuenta por empleado

### MÓDULO 5: GESTIÓN DE DESCUENTOS Y PAGOS (RRHH)
- Reporte mensual de descuentos a aplicar por empleado (exportable a Excel/PDF)
- Confirmación de planilla procesada
- Registro de pagos recibidos de la empresa empleadora a la plataforma
- Redistribución automática a empresas proveedoras
- Gestión de casos especiales (baja de empleado, licencia, embargo)

**Flujo de pago:**
```
Empresa empleadora descuenta cuota de planilla del empleado
→ Transfiere monto total a cuenta de la plataforma
→ Plataforma distribuye a cada empresa proveedora
→ Comisión de plataforma retenida en el proceso
```

### MÓDULO 6: REPORTES Y COBRANZA
- Dashboard ejecutivo (plataforma, empresa empleadora, proveedor)
- Reporte de cartera: al día, en mora, castigada
- Alertas automáticas de pagos pendientes
- Gestión de casos de empleados que abandonan la empresa
- Reportes regulatorios (para ASFI si aplica)
- Exportación a Excel/PDF de todos los reportes

### MÓDULO 7: ADMINISTRACIÓN DE PLATAFORMA
- Gestión de empresas afiliadas (activar/suspender/configurar)
- Configuración global de parámetros
- Panel de comisiones y facturación a empresas
- Auditoría de transacciones
- Gestión de usuarios y roles
- Configuración de notificaciones automáticas

---

## 5. ARQUITECTURA TÉCNICA

### Stack Recomendado

| Capa | Tecnología | Justificación |
|------|-----------|---------------|
| **Frontend Web** | Next.js 14 + TypeScript | SSR para SEO, excelente DX, un solo stack para todos los portales |
| **Mobile** | React Native (Expo) | Código compartido iOS/Android, mismo equipo que frontend |
| **Backend** | Node.js + NestJS | TypeScript end-to-end, arquitectura modular escalable |
| **Base de datos** | PostgreSQL | Transacciones financieras requieren ACID completo |
| **Cache** | Redis | Sesiones, rate limiting, cálculos de capacidad |
| **Storage** | AWS S3 / Cloudflare R2 | Documentos, contratos, importaciones Excel |
| **Cola de mensajes** | BullMQ (Redis) | Procesamiento asíncrono de planillas, notificaciones |
| **Auth** | JWT + Refresh Tokens | Multi-tenant seguro |
| **Email** | Resend | Notificaciones transaccionales |
| **SMS/WhatsApp** | Twilio o API oficial Meta | Notificaciones a empleados |
| **Hosting** | AWS o Railway | Escalabilidad, disponibilidad en región Latinoamérica |
| **CI/CD** | GitHub Actions | Automatización de despliegues |

### Arquitectura Multi-Tenant
- Cada empresa opera en su propio espacio de datos con aislamiento lógico
- Un solo deployment, múltiples tenants
- Subdominios por empresa: `empresa.planillacredit.bo`

### Seguridad
- Encriptación en tránsito (TLS 1.3) y en reposo (AES-256)
- 2FA para administradores y RRHH
- Logs de auditoría inmutables para todas las transacciones financieras
- Rate limiting y protección contra brute force
- OWASP Top 10 como checklist de seguridad en cada release

---

## 6. PLAN DE IMPLEMENTACIÓN (FASES)

### FASE 1 — MVP (Meses 1-4)
**Objetivo:** Plataforma funcional con las empresas del portafolio existente del cliente

| Sprint | Duración | Entregables |
|--------|----------|-------------|
| 1-2 | 4 semanas | Arquitectura base, autenticación, onboarding empresas empleadoras |
| 3-4 | 4 semanas | Integración planilla Excel, motor de capacidad crediticia |
| 5-6 | 4 semanas | Portal empleado (solicitud de crédito), panel proveedor básico |
| 7-8 | 4 semanas | Módulo de pagos y descuentos, reportes básicos, testing |

**Criterio de éxito MVP:** 2 empresas empleadoras integradas, 1 empresa proveedora, 50+ empleados con acceso, primera transacción completada end-to-end.

### FASE 2 — CONSOLIDACIÓN (Meses 5-7)
- Integración API con sistemas de planilla externos
- App móvil (empleado)
- Reportes avanzados y dashboard ejecutivo
- Portal de autogestión para RRHH
- Pruebas de carga y optimización
- Gestión de casos especiales (baja de empleados, refinanciación)

**Criterio de éxito:** 5-10 empresas, 500 empleados, proceso de pago de planilla 100% automatizado.

### FASE 3 — ESCALAMIENTO (Meses 8-12)
- Módulo de scoring crediticio propio (basado en historial de la plataforma)
- Integración con Buró de Crédito Bolivia (INFOCRED)
- API pública para que empresas externas integren sus sistemas
- Módulo de marketing (empresas proveedoras hacen ofertas segmentadas)
- Multi-país (preparación de arquitectura)

---

## 7. EQUIPO DE DESARROLLO

| Rol | Dedicación | Fase |
|-----|-----------|------|
| Tech Lead / Arquitecto | 100% | Todo el proyecto |
| Backend Developer Senior | 100% | Fases 1-3 |
| Frontend Developer Senior | 100% | Fases 1-3 |
| Mobile Developer | 50% | Fase 2-3 |
| QA Engineer | 50% | Fases 1-3 |
| DevOps / Infraestructura | 25% | Todo el proyecto |
| UI/UX Designer | 50% | Fases 1-2 |
| Project Manager | 25% | Todo el proyecto |

---

## 8. MODELO COMERCIAL DE LA PLATAFORMA

### Modelo de Ingresos: 100% Gratuito + Comisiones

**La plataforma es completamente GRATUITA para empresas empleadoras y proveedoras.** No hay costos de suscripción, tarifas mensuales ni pagos recurrentes.

### Única Fuente de Ingreso para el Operador

| Fuente | Modelo | Rango | Momento de Cobro |
|--------|--------|-------|------------------|
| **Comisión por transacción** | Porcentaje sobre cada crédito originado | 1.5% – 3.5% | **ANTES del desembolso al proveedor** |
| **Comisión de cobranza (Fase 3)** | % sobre monto recuperado cuando empleado deja la empresa | 8% – 25% | Al recuperar el monto |

**Ventajas del modelo:**
- ✅ Cero barreras de entrada para empresas
- ✅ Adopción acelerada sin fricción comercial
- ✅ Incentivos alineados: solo ganamos cuando generamos valor
- ✅ Cero riesgo de incobrabilidad (comisión se descuenta automáticamente del flujo de pago)

### Proyección Conservadora (Año 1) — Solo Comisiones

| Período | Empresas | Empleados | Créditos/mes | Ticket Prom. | Volumen/mes | Comisión | Ingreso/mes |
|---------|---------|-----------|--------------|--------------|-------------|----------|-------------|
| M1-M4 (MVP) | 2-3 | 100 | 10 | USD 400 | USD 4,000 | 2.5% | ~USD 100 |
| M5-M8 | 5-7 | 300 | 60 | USD 500 | USD 30,000 | 2.5% | ~USD 750 |
| M9-M12 | 8-12 | 600 | 150 | USD 600 | USD 90,000 | 2.5% | ~USD 2,250 |

**Nota:** Los ingresos iniciales son menores que en un modelo SaaS+comisión, pero la velocidad de adopción es significativamente mayor. El punto de equilibrio se alcanza con mayor volumen transaccional pero menor cantidad de empresas.

---

## 9. PROPUESTA ECONÓMICA DE DESARROLLO

### Opción A — Desarrollo por Fases (Recomendada)

| Fase | Alcance | Precio USD | Duración |
|------|---------|-----------|----------|
| **Fase 1 — MVP** | Módulos 1-6 básicos, web, integración Excel | **USD 18,000 - 22,000** | 4 meses |
| **Fase 2 — Consolidación** | App móvil, API planilla, reportes avanzados | **USD 12,000 - 15,000** | 3 meses |
| **Fase 3 — Escalamiento** | Scoring, Buró, API pública | **USD 10,000 - 14,000** | 4 meses |
| **TOTAL PROYECTO** | | **USD 40,000 - 51,000** | ~11 meses |

### Opción B — Proyecto Llave en Mano (Fases 1+2)

| Concepto | Precio USD |
|---------|-----------|
| Desarrollo completo Fases 1 y 2 | **USD 28,000 - 35,000** |
| Infraestructura mensual (cloud) | USD 150-300/mes |
| Mantenimiento post-lanzamiento | USD 800-1,500/mes |

### Estructura de Pago Sugerida
- 30% inicio del proyecto
- 30% al entregar MVP (Fase 1)
- 25% al entregar Fase 2
- 15% al cierre/estabilización

> **Nota:** Los precios incluyen diseño UI/UX, desarrollo, testing, despliegue en producción y capacitación inicial. No incluyen licencias de servicios de terceros (SMS, hosting, dominio).

---

## 10. RIESGOS Y MITIGACIONES

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|---------|-----------|
| Baja adopción inicial de empresas | Media | Alto | Arrancar con el portafolio existente del cliente; ofrecer 3 meses gratis |
| Empleado abandona empresa con deuda | Alta | Alto | Contrato empleado-empresa-plataforma; cláusula de cesión de deuda |
| Empresa no paga planilla a la plataforma | Baja | Alto | Contrato empresa empleadora con garantías; suspensión automática del servicio |
| Cambio regulatorio ASFI | Baja | Muy Alto | Consulta legal previa; arquitectura flexible para adaptar flujos |
| Retrasos en integraciones API externas | Media | Medio | Priorizar Excel en MVP; API como feature de Fase 2 |
| Seguridad / fraude | Baja | Muy Alto | Auditoría de seguridad antes del lanzamiento; 2FA obligatorio |

---

## 11. PRÓXIMOS PASOS

1. **Validación legal** — Consulta con abogado especialista en ASFI sobre el modelo de empresas proveedoras de crédito en la plataforma (¿necesitan licencia propia?).
2. **Kick-off comercial** — Identificar las 2-3 primeras empresas empleadoras del portafolio actual para el piloto.
3. **Aprobación del proyecto** — Revisión y firma de propuesta económica.
4. **Inicio de diseño** — Workshop de UX con el cliente para validar flujos antes de codificar.
5. **Sprint 1** — Arquitectura base y primeras pantallas en 2 semanas.

---

## APÉNDICE: GLOSARIO

- **Empresa Empleadora:** Empresa que afilia su planilla a la plataforma para que sus empleados accedan a créditos.
- **Empresa Proveedora:** Empresa que ofrece productos o préstamos en efectivo a través de la plataforma.
- **Capacidad crediticia:** Monto máximo de crédito que un empleado puede comprometer, calculado como un % de su salario neto menos cuotas activas.
- **Descuento de planilla:** Mecanismo por el cual la empresa empleadora retiene la cuota mensual del salario del empleado antes de pagar y la transfiere a la plataforma.
- **MVP:** Minimum Viable Product — versión mínima funcional para validar el negocio con usuarios reales.

---

*Documento elaborado por Uplabs AI — Confidencial*
