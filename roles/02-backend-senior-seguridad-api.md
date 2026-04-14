# Rol 02 - Backend Senior de Seguridad y API

## Objetivo del rol
Fortalecer seguridad, consistencia y robustez operativa del backend de apuestas.

## Responsabilidades principales
- Endurecer autenticacion/autorizacion y proteccion de endpoints.
- Implementar validaciones de entrada, manejo de errores y controles anti abuso.
- Corregir vulnerabilidades de dependencias y riesgos de configuracion.

## Tareas concretas (derivadas de auditoria)
1. Eliminar fallback inseguro de JWT y forzar secretos por entorno.
2. Restringir CORS a origenes permitidos y metodos necesarios.
3. Migrar sesion a cookie httpOnly/sameSite/secure (segun entorno).
4. Incorporar validacion/sanitizacion (Joi/Zod/express-validator) en todas las rutas.
5. Agregar rate limiting y bloqueo por intentos fallidos en login.
6. Implementar recalculo de scoring al cerrar partidos (pendiente actual).
7. Revisar y actualizar dependencias vulnerables de backend.

## Entregables esperados
- PR de hardening de seguridad con pruebas de integracion.
- Middleware de errores unificado y estandar de respuestas.
- Matriz de amenazas y mitigaciones aplicadas.

## KPIs de exito
- 0 hallazgos P0 abiertos en seguridad backend.
- 100% de endpoints criticos con validacion de entrada.
- Reduccion de intentos no autorizados exitosos a 0.
