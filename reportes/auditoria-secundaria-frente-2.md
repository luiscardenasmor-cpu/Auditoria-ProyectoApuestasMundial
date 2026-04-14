# Auditoria Secundaria - Frente 2 (Ciclica)

## Metadatos
- Fecha de auditoria secundaria: 2026-04-14
- Tipo: evaluacion de evolucion tras ciclo simulado de mejoras
- Horizonte simulado: 4-6 semanas posteriores a la Auditoria Inicial

## Supuestos de simulacion
Para este frente se simula una implementacion parcial guiada por los roles definidos en /roles:
- Correcciones P0 completadas en autenticacion base, bug de enrutado y primeras actualizaciones de dependencias.
- Inicio de pruebas automatizadas y de una capa de servicios en backend.
- Primeras mejoras de UX y estandarizacion de flujos clave.

> Nota: este reporte describe el estado esperado tras una iteracion de mejora simulada, no necesariamente el estado exacto del branch actual.

## Resumen Ejecutivo
- Evolucion esperada: de MVP funcional parcial a plataforma pre-productiva controlada.
- Riesgo residual principal: mantenibilidad de largo plazo y observabilidad operacional incompleta.

---

## 1) UX/UI
### Hallazgos positivos
- Interfaz visualmente atractiva y consistente en identidad futbolera.
- Buen uso de microinteracciones y componentes ricos para engagement.
- Navegacion de alto nivel clara (usuario/admin).

### Hallazgos negativos
- Exceso de vistas con datos simulados reduce confianza y trazabilidad del estado real.
- Falta de indicadores de carga, errores y estados vacios conectados al backend.
- Accesibilidad no verificada formalmente (contraste, foco teclado, semantica ARIA).
- Riesgo de sobrecarga visual en pantallas densas sin priorizacion progresiva de informacion.

### Riesgo/Prioridad
- Nivel: Medio
- Prioridad: P1

### Recomendaciones concretas
1. Definir Design System minimo (tokens, espaciado, estados, accesibilidad).
2. Incorporar patron UX para estados asincronos: loading, empty, error, retry.
3. Ejecutar auditoria de accesibilidad WCAG 2.2 AA.
4. Instrumentar eventos UX para validar embudos reales.

---

## 2) Procesos de Negocio y Flujos de Apuestas
### Hallazgos positivos
- Flujo conceptual de registro/login esta claro para usuario final.
- Modelo de grupos, invitaciones y predicciones cubre el nucleo del producto.
- Reglas base de scoring y ventanas de cierre estan en narrativa de UI.

### Hallazgos negativos
- Varias reglas de negocio estan en texto de interfaz y no en logica transaccional verificable.
- Recalculo de puntajes tras cierre de partido aparece pendiente en backend.
- Falta trazabilidad de decisiones de negocio (eventos, historico de cambios, auditoria por apuesta).
- Sin mecanismo robusto de idempotencia y cierre temporal exacto para evitar condiciones de carrera.

### Riesgo/Prioridad
- Nivel: Alto
- Prioridad: P0-P1

### Recomendaciones concretas
1. Convertir reglas de negocio a casos de uso backend testeados.
2. Implementar scoring engine versionado y auditable.
3. Agregar control temporal estricto para cierre de pronosticos por timestamp de servidor.
4. Formalizar catalogo de reglas con aprobacion de Product Manager.

---

## 3) Mantenibilidad y Capacidad de Testing
### Hallazgos positivos
- Estructura modular inicial facilita introducir tests por dominio.
- Linting frontend existente sirve como base para quality gates.

### Hallazgos negativos
- Cobertura de tests practicamente nula en backend y no formalizada en frontend.
- Sin estrategia clara de pruebas E2E para flujos criticos (login, crear grupo, pronosticar, cierre).
- Ausencia de contrato API testeado automaticamente (contract testing).
- Deuda tecnica por mezcla de componentes mock y reales.

### Riesgo/Prioridad
- Nivel: Alto
- Prioridad: P1

### Recomendaciones concretas
1. Objetivo inicial: 60% cobertura backend en modulos auth/predictions/groups.
2. Agregar pruebas de integracion contra Mongo de prueba (testcontainers o memoria).
3. Incluir suite E2E ligera (Playwright/Cypress) para flujos de negocio clave.
4. Habilitar quality gate: no merge sin lint + tests + build.

---

## 4) Integracion con Sistemas Externos
### Hallazgos positivos
- Existe base para integracion de correo automatizado (nodemailer + cron).
- Se contempla sincronizacion con API externa en narrativa del panel admin.

### Hallazgos negativos
- Integraciones clave (API de resultados deportivos) aparecen simuladas en UI, no productivas.
- Riesgo de acoplamiento directo sin capas anti-fragilidad (timeouts, retries, circuit breaker).
- Dependencia de proveedores externos sin politicas de fallback y observabilidad.

### Riesgo/Prioridad
- Nivel: Medio-Alto
- Prioridad: P1

### Recomendaciones concretas
1. Implementar adaptadores por proveedor externo con contratos claros.
2. Agregar politicas de resiliencia (retry exponencial, timeout, dead-letter).
3. Definir SLA/SLO por integracion y alarmas por degradacion.
4. Registrar correlacion entre evento externo y actualizacion interna de apuestas.

---

## 5) Monitoreo y Logs
### Hallazgos positivos
- Existen logs basicos de consola en backend y cron.
- El producto tiene eventos naturales para observabilidad (login, prediccion, scoring, recordatorio).

### Hallazgos negativos
- No hay logging estructurado (JSON) ni trazas con correlation-id.
- No hay metricas de negocio y de plataforma (latencia, error rate, throughput).
- No hay dashboards ni alertas de incidentes.
- Sin politicas de retencion y anonimizado de datos sensibles en logs.

### Riesgo/Prioridad
- Nivel: Alto
- Prioridad: P1

### Recomendaciones concretas
1. Introducir logger estructurado (pino/winston) + niveles + contexto.
2. Instrumentar OpenTelemetry (traces + metrics + logs).
3. Construir dashboards operativos y de negocio (auth failures, predicciones/min, jobs).
4. Definir alertas accionables y runbooks de respuesta.

---

## Balance de evolucion (simulada)
- Riesgo general inicial: Alto-Critico
- Riesgo tras ciclo simulado: Medio-Alto
- Cuellos de botella residuales:
  - Falta de madurez de testing integral
  - Reglas de negocio parcialmente codificadas
  - Observabilidad aun incipiente

## Recomendacion de siguiente ciclo (2-4 semanas)
1. Cerrar completamente trazabilidad de reglas y scoring.
2. Consolidar pruebas E2E y de contrato.
3. Completar pipeline de observabilidad con alertas de produccion.
4. Re-auditar seguridad de autenticacion y sesiones con pentest ligero.
