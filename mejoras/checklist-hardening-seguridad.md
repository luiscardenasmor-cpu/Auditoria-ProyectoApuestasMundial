# Checklist de Hardening de Seguridad

## Configuracion y secretos
- [ ] Remover secretos hardcodeados y fallbacks inseguros.
- [ ] Configurar JWT secret por entorno seguro.
- [ ] Crear .env.example sin secretos reales.
- [ ] Rotar claves y credenciales iniciales de seeder.

## API y autenticacion
- [ ] Implementar validacion/sanitizacion en todas las rutas.
- [ ] Configurar rate limiting global y especifico en login.
- [ ] Definir estrategia de sesion con cookie httpOnly.
- [ ] Reforzar control de acceso por rol en endpoints admin.

## Capa web
- [ ] Restringir CORS por dominio permitido.
- [ ] Endurecer cabeceras de seguridad con helmet parametrizado.
- [ ] Revisar politicas CSP para frontend.

## Dependencias
- [ ] Actualizar dependencias con vulnerabilidades altas/criticas.
- [ ] Activar escaneo de dependencias en CI.
- [ ] Definir cadencia mensual de patching.

## Operacion segura
- [ ] Logging de eventos de seguridad (login fail, token fail, rate-limit).
- [ ] Alertas para actividad anomala.
- [ ] Runbook de respuesta a incidente de seguridad.
