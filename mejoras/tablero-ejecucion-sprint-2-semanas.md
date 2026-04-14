# Tablero de Ejecucion - Sprint 2 Semanas

## Sprint
- Duracion: 10 dias habiles
- Objetivo: cerrar P0 de seguridad/sesion y estabilizar base tecnica para P1

## Roles responsables
- Arquitecto/a de Plataforma y Escalabilidad
- Backend Senior de Seguridad y API
- Frontend Senior UX y Arquitectura React
- QA Automation Lead
- DevOps/SRE de Observabilidad y Release
- Product Manager de Flujos de Apuestas

## Backlog del sprint (planificado)
| ID | Item | Responsable principal | Apoyo | Prioridad | Estado |
|---|---|---|---|---|---|
| SP-01 | Endurecer auth backend (JWT obligatorio, cookie httpOnly, CORS restringido) | Backend Senior | Arquitecto, DevOps | P0 | Hecho |
| SP-02 | Corregir bug critico de App (hook/enrutado) | Frontend Senior | QA | P0 | Hecho |
| SP-03 | Migrar cliente a sesion por cookie (sin token en localStorage) | Frontend Senior | Backend Senior | P0 | Hecho |
| SP-04 | Implementar logout backend + auto-logout frontend | Backend Senior | Frontend Senior | P0 | Hecho |
| SP-05 | Actualizar dependencias vulnerables criticas/altas | DevOps/SRE | Backend Senior, Frontend Senior | P0 | Hecho |
| SP-06 | Configurar variables de entorno ejemplo para despliegue seguro | DevOps/SRE | Backend Senior | P0 | Hecho |
| SP-07 | Smoke test de autenticacion (login/logout/me) | QA Automation Lead | Backend Senior | P0 | En progreso |
| SP-08 | Crear quality gate CI (lint/build/audit) | DevOps/SRE | QA | P1 | Pendiente |
| SP-09 | Implementar route guards por rol y sesion | Frontend Senior | QA | P1 | Pendiente |
| SP-10 | Definir reglas de terminado para scoring y cierre de pronosticos | Product Manager | Arquitecto, Backend | P1 | Pendiente |

## Definicion de Terminado (DoD) por item
| Item | Definicion de terminado |
|---|---|
| SP-01 | JWT sin fallback, CORS por whitelist, auth por cookie httpOnly, rate limit activo en auth |
| SP-02 | Sin referencia a simbolos no definidos en App y navegacion estable |
| SP-03 | No se persiste token de acceso en localStorage; login con credentials include |
| SP-04 | Endpoint /api/auth/logout operativo y cierre por inactividad funcional |
| SP-05 | npm audit sin vulnerabilidades abiertas (frontend y backend) |
| SP-06 | Archivos .env.example creados y documentados |
| SP-07 | Casos exitoso/fallido de login y logout verificados en ambiente de prueba |
| SP-08 | Pipeline bloquea merge ante falla de lint/build/audit |
| SP-09 | Acceso a rutas privadas/admin protegido por estado de sesion y rol |
| SP-10 | Reglas de negocio formalizadas y trazables a historias y pruebas |

## Calendario sugerido (2 semanas)
| Dia | Foco | Responsables |
|---|---|---|
| D1-D2 | Seguridad auth y CORS | Backend, Arquitecto |
| D3-D4 | Frontend sesion y fix App | Frontend, QA |
| D5 | Dependencias y hardening final | DevOps, Backend, Frontend |
| D6-D7 | Smoke tests y validacion cruzada | QA, Backend, Frontend |
| D8-D9 | CI quality gate y route guards | DevOps, Frontend, QA |
| D10 | Demo, retro y plan del siguiente sprint | PM, todos |

## Riesgos y mitigaciones
- Riesgo: backend local sin MongoDB disponible para pruebas completas.
- Mitigacion: usar entorno remoto para smoke tests y preparar contenedor Mongo para entorno local.

- Riesgo: deuda de lint en modulos no P0.
- Mitigacion: crear sub-tareas P1 para limpieza y ajuste de reglas por archivo.
