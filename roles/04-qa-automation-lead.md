# Rol 04 - QA Automation Lead

## Objetivo del rol
Construir la capacidad de testing automatizado para prevenir regresiones funcionales y de seguridad.

## Responsabilidades principales
- Definir estrategia de pruebas por capas: unitarias, integracion, contrato y E2E.
- Integrar quality gates en CI/CD.
- Establecer trazabilidad de requisitos de negocio a casos de prueba.

## Tareas concretas (derivadas de auditoria)
1. Crear base de pruebas backend para auth, groups y predictions.
2. Implementar pruebas de integracion con base de datos aislada.
3. Construir smoke E2E de flujos criticos:
   - Registro/Login
   - Crear/unirse a grupo
   - Cargar pronostico
   - Cierre de partido y scoring
4. Agregar pruebas de seguridad basica (auth bypass, input invalido, rate limit).
5. Integrar ejecucion en CI con umbral minimo de cobertura.

## Entregables esperados
- Suite automatizada ejecutable local y en CI.
- Reporte de cobertura y tendencia por sprint.
- Matriz de riesgo de pruebas por modulo.

## KPIs de exito
- Cobertura backend >= 60% en modulos core.
- Tiempo de deteccion de regresion < 1 dia.
- Reduccion de bugs escapados a produccion por sprint.
