# PLANILLACREDIT — ROLES Y PLAN DE TRABAJO
## Distribución de Responsabilidades entre Socios

**Fecha:** Mayo 2026  
**Versión:** 1.0 — Confidencial

---

## ASIGNACIÓN DE ROLES

| Socio | Título | Área de Responsabilidad |
|-------|--------|------------------------|
| **Socio 1** | CEO — Director General y Financiero-Legal | Regulación, contratos, finanzas del proyecto, decisiones estratégicas |
| **Socio 2** | CTO — Director de Tecnología y Producto | Supervisión del desarrollo, arquitectura, producto digital |
| **Socio 3** | CCO — Director Comercial y de Alianzas | Ventas, empresas piloto, proveedores, relaciones con el mercado |

---

---

## SOCIO 1 — CEO / DIRECTOR GENERAL Y FINANCIERO-LEGAL

### Responsabilidades Permanentes
- Toma de decisiones estratégicas del negocio.
- Relación con ASFI y cumplimiento regulatorio.
- Aprobación de contratos y documentos legales.
- Gestión financiera del proyecto (presupuesto, pagos a Uplabs AI, caja).
- Representación legal de la plataforma ante terceros.
- Aprobación final de toda empresa que quiera afiliarse.

---

### TAREAS — MES 1 (ARRANQUE DEL PROYECTO)

#### Semana 1-2
- [ ] **Contratar abogado especialista en ASFI** para definir el modelo legal de las empresas proveedoras de crédito (Modelo A vs Modelo B). Esta es la tarea más urgente de todo el proyecto — bloquea el inicio del desarrollo.
- [ ] **Definir la estructura legal de la plataforma:** ¿opera bajo la empresa existente o se crea una nueva razón social para PlanillaCredit? Consultar con abogado.
- [ ] **Definir el nombre comercial final** de la plataforma y verificar disponibilidad de dominio (.bo y .com).
- [ ] **Abrir cuenta bancaria exclusiva** para la plataforma (separada de la empresa de préstamos actual) donde las empresas empleadoras depositarán los descuentos de planilla.

#### Semana 3-4
- [ ] **Entregar al abogado los 4 contratos a redactar:**
  1. Contrato de afiliación para Empresas Empleadoras.
  2. Contrato para Empresas Proveedoras.
  3. Consentimiento y contrato del Empleado (incluyendo autorización de descuento de planilla).
  4. Contrato de crédito (cumplimiento ASFI — TEA informada, plan de pagos).
- [ ] **Definir los parámetros financieros iniciales** de la plataforma:
  - Porcentaje máximo del salario neto que se puede comprometer (propuesta: 25-30%).
  - Plazos máximos de crédito (propuesta: 6, 12, 18, 24 meses).
  - Tasas de interés para créditos en efectivo del operador.
- [ ] **Aprobar la propuesta económica de Uplabs AI** y firmar contrato de desarrollo.

---

### TAREAS — MES 2-3 (DURANTE DESARROLLO DEL MVP)

- [ ] **Revisar y aprobar los contratos redactados por el abogado** antes de integrarlos en la plataforma.
- [ ] **Definir el mecanismo de firma electrónica:** OTP por SMS/WhatsApp (más simple) o integración con ADSIB (mayor validez). Decidir con el abogado cuál aplica.
- [ ] **Gestionar la integración bancaria:** Coordinar con el banco la API o webhook para conciliación automática de transferencias (para Fase 2). En MVP: proceso manual documentado.
- [ ] **Establecer el proceso de conciliación de pagos:**
  - ¿Quién verifica que la empresa empleadora transfirió?
  - ¿Quién autoriza la distribución a los proveedores?
  - ¿Con qué periodicidad?
- [ ] **Definir la política de mora y cobranza** para casos de empleados que dejan la empresa. Basar en el proceso actual de la empresa de préstamos.
- [ ] **Diseñar la estructura de precios SaaS** (validar los rangos del documento de proyecto o ajustarlos al mercado boliviano).

---

### TAREAS — MES 4 (PRE-LANZAMIENTO)

- [ ] **Revisar y aprobar el MVP** junto con el Socio 2 antes del lanzamiento con empresas piloto.
- [ ] **Registrar la marca "PlanillaCredit"** (o el nombre final) ante SENAPI Bolivia.
- [ ] **Preparar el pitch de presentación** a futuras empresas empleadoras y proveedoras (junto con Socio 3).
- [ ] **Definir el equipo operativo de soporte:** ¿quién atiende consultas de empleados y empresas una vez lanzada la plataforma?

---

### KPIs del Socio 1
- Contratos redactados y aprobados antes del Sprint 6 del desarrollo.
- Cuenta bancaria operativa antes del Sprint 7.
- Modelo legal definido antes del inicio del desarrollo (Sprint 1).
- Marca registrada en SENAPI antes del lanzamiento público.

---
---

## SOCIO 2 — CTO / DIRECTOR DE TECNOLOGÍA Y PRODUCTO

### Responsabilidades Permanentes
- Punto de contacto técnico con Uplabs AI (equipo de desarrollo).
- Validación y aprobación de entregables técnicos de cada sprint.
- Decisiones sobre arquitectura, integraciones y stack tecnológico.
- Gestión del producto digital: priorización de funcionalidades, UX, roadmap.
- Supervisión de la seguridad y cumplimiento técnico de la plataforma.
- Gestión de la infraestructura cloud una vez lanzada.

---

### TAREAS — MES 1 (ARRANQUE DEL PROYECTO)

#### Semana 1-2
- [ ] **Asistir al kick-off técnico con Uplabs AI** y validar la arquitectura propuesta (stack, base de datos, infraestructura).
- [ ] **Registrar y configurar los servicios de infraestructura:**
  - Cuenta AWS o Railway (hosting).
  - Cuenta GitHub (repositorio del código).
  - Cuenta Resend (email transaccional).
  - Cuenta Twilio o Meta Business API (WhatsApp/SMS).
- [ ] **Adquirir el dominio web** (ej: planillacredit.bo y planillacredit.com) y configurar DNS básico.
- [ ] **Definir con Uplabs AI el canal de comunicación del proyecto:** Slack, WhatsApp Business o correo electrónico. Frecuencia de reuniones de avance.

#### Semana 3-4
- [ ] **Asistir al Workshop de UX** con Uplabs AI para validar los flujos de usuario principales antes de que se diseñe la interfaz.
- [ ] **Recopilar y entregar a Uplabs AI:**
  - Logo, colores corporativos, tipografía (si ya están definidos).
  - Ejemplos de sistemas o apps que le gusten al equipo en términos de diseño.
  - Requisitos de accesibilidad o idioma (¿solo español? ¿quechua/aymara en alguna interfaz?).
- [ ] **Coordinar con el Socio 3** para conseguir el archivo Excel de planilla de la empresa piloto (con datos reales o anonimizados) para usarlo en las pruebas de integración del Sprint 3.

---

### TAREAS — MES 2-3 (DURANTE DESARROLLO DEL MVP)

- [ ] **Revisar demo de cada sprint** (cada 2 semanas) y documentar feedback claro para el equipo de Uplabs AI.
- [ ] **Validar el template Excel de planilla** que generará Uplabs AI — verificar que sea compatible con los formatos de Excel que usan las empresas piloto.
- [ ] **Probar la integración de planilla** con datos reales antes del Sprint 7 para confirmar que el motor de capacidad crediticia calcula correctamente.
- [ ] **Definir los textos de contratos digitales** que aparecerán en la plataforma (en coordinación con el Socio 1 y el abogado).
- [ ] **Probar el flujo completo end-to-end** al menos 2 veces antes del lanzamiento: simular ser empleado, empresa y administrador.
- [ ] **Configurar el monitoreo:** Sentry para errores, alertas de caída del servicio.
- [ ] **Documentar el proceso de carga de planilla** para entregarle a las empresas empleadoras piloto.

---

### TAREAS — MES 4 (PRE-LANZAMIENTO)

- [ ] **Coordinar la capacitación** con el equipo de RRHH de las empresas piloto.
- [ ] **Crear cuentas de administrador** para el equipo operativo del Socio 1.
- [ ] **Preparar el plan de soporte técnico:** ¿canal de WhatsApp? ¿correo de soporte? ¿horario de atención?
- [ ] **Verificar copias de seguridad** (backups) y plan de recuperación ante fallos.
- [ ] **Definir el proceso de actualización de la plataforma** — ¿en qué horarios se hacen deployments para no afectar el proceso de planilla?

---

### TAREAS FASE 2 (Meses 5-7)
- [ ] **Liderar el proceso de integración API** con los sistemas de planilla de las nuevas empresas (coordinar entre Uplabs AI y el equipo de TI de cada empresa).
- [ ] **Gestionar la publicación de la app móvil** en App Store (Apple) y Google Play:
  - Crear cuentas de desarrollador (Apple: USD 99/año, Google: USD 25 único).
  - Coordinar el proceso de revisión y aprobación con las tiendas.
- [ ] **Definir el roadmap de Fase 3** junto con Uplabs AI y el equipo.

---

### KPIs del Socio 2
- Infraestructura cloud operativa antes del Sprint 1.
- Dominio y servicios de terceros configurados antes del Sprint 2.
- Feedback de cada sprint entregado en menos de 3 días hábiles.
- Cero bugs críticos sin reportar al equipo de desarrollo.
- App móvil publicada en ambas tiendas en la Fase 2.

---
---

## SOCIO 3 — CCO / DIRECTOR COMERCIAL Y DE ALIANZAS

### Responsabilidades Permanentes
- Adquisición de nuevas empresas empleadoras y proveedoras para la plataforma.
- Gestión de relaciones con socios estratégicos.
- Definición de la estrategia comercial y de precios (con validación del Socio 1).
- Marketing y posicionamiento de PlanillaCredit en el mercado boliviano.
- Atención y fidelización de empresas afiliadas.
- Retroalimentación del mercado al equipo de producto (Socio 2).

---

### TAREAS — MES 1 (ARRANQUE DEL PROYECTO)

#### Semana 1-2
- [ ] **Identificar y comprometer las empresas piloto:**
  - Mínimo 2 empresas empleadoras (del portafolio actual del cliente o contactos directos).
  - Mínimo 1 empresa proveedora de productos físicos a crédito.
  - Estas empresas deben estar dispuestas a participar en las pruebas del MVP y dar feedback real.
- [ ] **Hacer una lista de las primeras 20 empresas objetivo** (empleadoras y proveedoras) con nombre, rubro, número estimado de empleados y contacto.

#### Semana 3-4
- [ ] **Reunirse con el RRHH de las empresas piloto** para:
  - Presentar el proyecto y explicar el proceso de integración de planilla.
  - Solicitar un archivo Excel de planilla de muestra (puede ser con datos ficticios o anonimizados).
  - Levantar las dudas o resistencias del área de RRHH para anticiparlas en el diseño de la plataforma.
- [ ] **Validar el modelo de precios SaaS** con las empresas piloto — ¿los rangos de precios del documento son aceptables para el mercado boliviano?
- [ ] **Definir la propuesta de valor comercial** para cada tipo de empresa (empleadora y proveedora) en lenguaje simple y sin tecnicismos.

---

### TAREAS — MES 2-3 (DURANTE DESARROLLO DEL MVP)

- [ ] **Preparar el material comercial básico:**
  - [ ] Presentación de ventas (PowerPoint/Canva) de 10-15 slides.
  - [ ] Brochure o PDF resumen de la plataforma para enviar por WhatsApp/correo.
  - [ ] Preguntas frecuentes (FAQ) para responder objeciones comunes.
- [ ] **Establecer el proceso de onboarding comercial:**
  - ¿Cómo se presenta la plataforma a una empresa nueva?
  - ¿Quién firma el contrato? (coordinar con Socio 1)
  - ¿Cuánto tiempo demora onboardear una empresa nueva desde el primer contacto hasta que sus empleados pueden solicitar crédito?
- [ ] **Mapear el ecosistema de empresas proveedoras potenciales en Bolivia:**
  - Tiendas de electrodomésticos.
  - Tiendas de tecnología.
  - Proveedores de servicios (seguros, salud, educación).
  - Entidades financieras reguladas (para crédito en efectivo, si aplica el Modelo B).
- [ ] **Definir la estrategia de lanzamiento:** ¿evento presencial? ¿campaña digital? ¿activación en las empresas empleadoras piloto?

---

### TAREAS — MES 4 (PRE-LANZAMIENTO)

- [ ] **Comprometer al menos 3-5 empresas empleadoras** listas para activarse el día del lanzamiento.
- [ ] **Comprometer al menos 2-3 empresas proveedoras** con catálogo cargado y listo.
- [ ] **Organizar el evento o proceso de lanzamiento oficial:**
  - Invitar a las empresas afiliadas y a prospectos.
  - Demo en vivo de la plataforma.
  - Comunicado de prensa (si aplica).
- [ ] **Diseñar el plan de comisiones o incentivos** para los primeros 6 meses (ej: 3 meses de SaaS gratis para las primeras empresas, descuentos en comisión para proveedores fundadores).
- [ ] **Crear las redes sociales de la plataforma** (LinkedIn, Facebook, Instagram según el público objetivo boliviano).

---

### TAREAS FASE 2-3 (Meses 5-12)
- [ ] **Alcanzar 8-12 empresas empleadoras** activas al mes 12.
- [ ] **Expandir el catálogo de proveedores** a mínimo 5-8 empresas con oferta diversa.
- [ ] **Implementar un proceso de referidos** — empresas activas que refieren a otras obtienen beneficios.
- [ ] **Explorar alianzas estratégicas** con cámaras de comercio, asociaciones de empresarios o sindicatos bolivianos para acceder a nuevas empresas en bloque.
- [ ] **Levantar feedback trimestral** de las empresas activas para alimentar el roadmap del producto.
- [ ] **Preparar la estrategia de expansión** a otras ciudades (Cochabamba, Santa Cruz) si La Paz es exitosa.

---

### KPIs del Socio 3
- 2 empresas empleadoras piloto confirmadas antes del Sprint 3.
- 1 empresa proveedora piloto confirmada antes del Sprint 4.
- Material comercial completo antes del mes 3.
- 5+ empresas activas en el día del lanzamiento (mes 4).
- 10+ empresas activas al mes 10.

---
---

## REUNIONES DEL EQUIPO DE SOCIOS

Para que el proyecto avance coordinado, se propone la siguiente cadencia de reuniones internas:

| Reunión | Frecuencia | Duración | Participantes | Objetivo |
|---------|-----------|----------|---------------|----------|
| **Stand-up semanal** | Cada lunes | 30 min | Los 3 socios | Avances de la semana, bloqueos, prioridades |
| **Revisión de sprint** | Cada 2 semanas | 1 hora | Los 3 socios + Uplabs AI | Ver demo del sprint, dar feedback |
| **Revisión comercial** | Mensual | 1 hora | Socio 1 + Socio 3 | Pipeline de empresas, precios, contratos |
| **Revisión financiera** | Mensual | 30 min | Socio 1 + Socio 2 | Gastos del proyecto, proyecciones, pagos |

---

## TABLERO DE TAREAS COMPARTIDO

Se recomienda usar una herramienta de gestión de tareas para que los 3 socios tengan visibilidad de lo que hace cada uno. Opciones:

| Herramienta | Costo | Mejor para |
|-------------|-------|-----------|
| **Notion** | Gratis (plan básico) | Documentación + tareas en un solo lugar |
| **Trello** | Gratis | Tablero visual simple, fácil de aprender |
| **Linear** | USD 8/mes por usuario | Más estructurado, ideal si el Socio 2 ya lo usa con Uplabs AI |
| **WhatsApp + Excel** | Gratis | Si el equipo prefiere herramientas mínimas |

**Recomendación:** Notion — permite tener el documento del proyecto, el tablero de tareas y las notas de reuniones en un solo lugar accesible para los 3 socios.

---

## RESUMEN: PRIMERAS 4 SEMANAS — ¿QUIÉN HACE QUÉ?

| Tarea Crítica | Responsable | Plazo |
|---------------|------------|-------|
| Contratar abogado especialista ASFI | **Socio 1** | Semana 1 |
| Definir modelo legal de proveedores de crédito | **Socio 1 + Abogado** | Semana 2 |
| Aprobar propuesta Uplabs AI y firmar contrato | **Socio 1** | Semana 1-2 |
| Registrar servicios cloud (AWS, GitHub, etc.) | **Socio 2** | Semana 1-2 |
| Comprar dominio web | **Socio 2** | Semana 1 |
| Identificar empresas piloto (empleadoras y proveedoras) | **Socio 3** | Semana 1-2 |
| Reunirse con RRHH de empresa piloto y obtener Excel de planilla | **Socio 3** | Semana 3-4 |
| Definir nombre final de la plataforma | **Los 3 socios** | Semana 1 |
| Workshop de UX con Uplabs AI | **Socio 2 + Los 3 socios** | Semana 3-4 |
| Inicio del desarrollo (Sprint 1) | **Uplabs AI** | Semana 4-5 |

---

*Documento elaborado por Uplabs AI | Confidencial*  
*Versión 1.0 — Mayo 2026*
