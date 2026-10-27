# Acta de reunión: despliegue del sitio Librería Independiente Raíz

- **Fecha:** lunes 26 de octubre de 2026
- **Modalidad:** virtual (trabajo remoto: Bello, El Poblado y centro de Medellín)
- **Tipo de reunión:** planeación y decisión técnica de despliegue
- **Elabora el acta:** consultor de despliegue (trabajo individual; los demás roles son los personajes del caso)

## Asistentes (roles)

| Rol | Persona | Responsabilidad en el despliegue |
|---|---|---|
| Líder técnica | Laura Restrepo | Coordina, revisa y aprueba los Pull Requests, activa GitHub Pages |
| Desarrollador | Carlos Méndez | Renombrar el punto de entrada y corregir rutas |
| Diseñadora UX/UI | Sofía Álvarez | Exportar y optimizar las imágenes |
| Cliente | Miguel Ángel Raíz | Recibe la URL y valida el sitio |
| Consultor de despliegue | Autor del informe | Diagnóstico, plan, documentación y comunicación con el cliente |

## Situación

Al activar GitHub Pages desde `main` el sitio responde **404**. Se identificaron: punto de entrada llamado
`inicio.html`, rutas absolutas del equipo de Carlos, imágenes en una carpeta inexistente y archivos `.psd`
renombrados a `.jpg`. El cliente necesita la URL pública a las 3:00 p. m.

## Decisiones

| # | Decisión | Responsable | Fecha límite |
|---|---|---|---|
| 1 | Se elige la **opción 1**: corregir la estructura y desplegar desde `main` (raíz) | Laura | 26/10, 10:15 a. m. |
| 2 | Renombrar `inicio.html` a `index.html` (rama `fix/index-entrypoint`) | Carlos | 26/10, 10:45 a. m. |
| 3 | Mover CSS y JS a `assets/` (rama `refactor/estructura-assets`) | Carlos | 26/10, 11:15 a. m. |
| 4 | Convertir todas las rutas a relativas (rama `fix/rutas-relativas`) | Carlos | 26/10, 11:45 a. m. |
| 5 | Exportar imágenes reales JPG/PNG de máx. 300 KB a `assets/img/` (rama `fix/imagenes-optimizadas`) | Sofía | 26/10, 12:15 p. m. |
| 6 | Todo cambio entra a `main` solo por Pull Request con al menos 1 aprobación | Laura | Permanente |
| 7 | Commits con Conventional Commits (`fix:`, `refactor:`, `docs:`) | Todo el equipo | Permanente |
| 8 | Activar Pages (Settings → Pages → rama `main`, carpeta `/ (root)`) y verificar la URL | Laura | 26/10, 1:00 p. m. |
| 9 | Enviar a Miguel un primer mensaje de estado (11:00 a. m.) y la URL verificada antes de las 2:30 p. m. | Consultor | 26/10, 2:30 p. m. |

## Riesgos y plan B

- Si una imagen no queda lista a tiempo, se publica con una imagen provisional ligera y se actualiza por PR después.
- Si Pages tarda en compilar, se espera hasta 10 minutos y se revisa la pestaña **Actions** del repositorio.

## Próxima revisión

Verificación final del sitio el 26/10 a la 1:30 p. m. (checklist del README).
