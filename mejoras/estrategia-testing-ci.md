# Estrategia de Testing y CI

## Piramide de pruebas recomendada
1. Unitarias (rapidas)
- Reglas de auth, validaciones, scoring y logica de grupos.

2. Integracion
- Endpoints con base de datos de prueba.
- Casos de error y autorizacion.

3. E2E (smoke)
- Registro/Login.
- Crear grupo / unirse por codigo.
- Cargar y editar pronostico.
- Cierre de partido y recuento de puntos.

## Pipeline minimo en CI
1. Instalar dependencias
2. Lint frontend + backend
3. Ejecutar unitarias e integracion
4. Ejecutar build frontend
5. Ejecutar auditoria de dependencias
6. Publicar reporte de cobertura

## Criterios de bloqueo para merge
- Sin errores de lint.
- Sin fallos de pruebas.
- Sin vulnerabilidades criticas nuevas.
- Build exitoso.

## Herramientas sugeridas
- Backend: Jest + Supertest
- Frontend: Vitest + React Testing Library
- E2E: Playwright
- CI: GitHub Actions
