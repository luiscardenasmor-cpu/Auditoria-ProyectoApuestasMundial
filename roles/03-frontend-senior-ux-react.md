# Rol 03 - Frontend Senior UX y Arquitectura React

## Objetivo del rol
Convertir la experiencia actual en una aplicacion confiable, accesible y conectada a datos reales.

## Responsabilidades principales
- Asegurar estabilidad de enrutado y estado de sesion.
- Estandarizar arquitectura de frontend (capa API, estado, componentes).
- Mejorar UX para flujos core de apuestas con criterios de accesibilidad.

## Tareas concretas (derivadas de auditoria)
1. Corregir bug critico de App (referencia a simbolo no definido / hooks).
2. Implementar guardas de rutas para usuario autenticado y rol admin.
3. Crear cliente API centralizado con manejo de tokens, errores y reintentos.
4. Reemplazar vistas mock por consumo real de backend en dashboard y admin.
5. Aplicar code splitting por rutas para reducir chunk inicial.
6. Corregir errores de lint y estandarizar componentes reutilizables.
7. Incluir estados UX de loading/error/empty y mejoras WCAG.

## Entregables esperados
- Frontend sin errores de lint en rama principal.
- Dashboard y admin conectados a API real.
- Guia de patrones UI reutilizables.

## KPIs de exito
- 0 errores de lint bloqueantes.
- Reduccion del chunk principal por debajo de 500 kB.
- Mejora de tasa de finalizacion en flujo pronosticar partido.
