# Plan Priorizado de Mejoras - 90 Dias

## Objetivo
Reducir riesgo tecnico y operativo del proyecto de apuestas del Mundial, priorizando seguridad, confiabilidad y escalabilidad.

## Fase 1 (Dia 1-15) - Contencion de Riesgo Critico
Prioridad: P0

1. Seguridad de autenticacion y sesion
- Eliminar JWT fallback secret.
- Restringir CORS por entorno.
- Migrar a cookie httpOnly/sameSite/secure.

2. Estabilidad frontend
- Corregir bug de enrutado/hook en App.
- Resolver errores de lint bloqueantes.

3. Dependencias vulnerables
- Actualizar paquetes con advisories criticos/altos.
- Verificar regresiones post-upgrade.

4. Hardening de endpoints
- Introducir validacion de entrada.
- Agregar rate limiting y proteccion de login.

## Fase 2 (Dia 16-45) - Confiabilidad de Producto
Prioridad: P1

1. Testing
- Pruebas unitarias backend para auth/groups/predictions.
- Pruebas de integracion con BD de test.
- Smoke E2E de flujos principales.

2. Reglas de negocio
- Implementar scoring engine auditable.
- Formalizar cierre de pronosticos por tiempo servidor.

3. Performance
- Code splitting por rutas frontend.
- Paginacion y filtros en consultas backend.
- Optimizar recordatorios (batch/cola).

4. Documentacion
- README backend + arquitectura + OpenAPI.
- .env.example para ambos lados.

## Fase 3 (Dia 46-90) - Escalado y Operacion
Prioridad: P1-P2

1. Observabilidad
- Logging estructurado con correlation-id.
- Dashboards de negocio y plataforma.
- Alertas y runbooks.

2. DevOps
- CI/CD con quality gates.
- Flujo por entornos y controles de release.

3. Gobierno tecnico
- ADRs, convenciones de codigo y checklist de PR.
- Auditoria ciclica quincenal.

## Metricas objetivo a 90 dias
- 0 hallazgos P0 abiertos.
- Cobertura backend >= 60% en modulos core.
- Chunk inicial frontend < 500 kB.
- MTTR y tasa de errores en descenso sostenido.
