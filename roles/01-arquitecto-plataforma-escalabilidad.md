# Rol 01 - Arquitecto/a de Plataforma y Escalabilidad

## Objetivo del rol
Disenar y gobernar la evolucion arquitectonica para pasar de MVP a plataforma escalable, mantenible y auditable.

## Responsabilidades principales
- Definir arquitectura target frontend/backend con separacion de responsabilidades por dominio.
- Establecer lineamientos de escalabilidad, resiliencia y contratos de integracion.
- Guiar decisiones de versionado de API y modularizacion.

## Tareas concretas (derivadas de auditoria)
1. Disenar capa de servicios de dominio en backend para auth, groups, predictions y scoring.
2. Definir estrategia de versionado de API y contrato OpenAPI.
3. Diseñar esquema de indices y paginacion para endpoints de alto trafico.
4. Crear blueprint para procesamiento asincrono de recordatorios y eventos.
5. Revisar y aprobar decisiones tecnicas de roles Backend/Frontend/DevOps.

## Entregables esperados
- Documento de arquitectura objetivo (C4 nivel contenedor + componentes).
- Mapa de dominios y ownership tecnico.
- ADRs (Architecture Decision Records) para decisiones criticas.

## KPIs de exito
- Reduccion de incidencias por acoplamiento inter-modulo.
- Mejora de latencia p95 en endpoints criticos.
- Cierre de hallazgos de arquitectura P1 dentro de 6 semanas.
