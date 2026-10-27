# Librería Independiente Raíz

Actividad No. 3 · Jennifer Espinosa

Sitio web estático de la **Librería Independiente Raíz** (Medellín, Colombia), publicado con **GitHub Pages**.

**Sitio en vivo:** https://jespinosa0118.github.io/libreria-raiz/

## Estructura del proyecto

```
libreria-raiz/
├── index.html              # Punto de entrada (obligatorio para GitHub Pages)
├── paginas/
│   ├── nosotros.html
│   └── contacto.html
├── assets/
│   ├── css/main.css
│   ├── js/app.js
│   └── img/                # Imágenes exportadas (JPG/PNG/WebP), menos de 300 KB
├── documentacion/
│   ├── acta-reunion.md
│   └── kanban.md
├── .gitignore
└── README.md
```

## Reglas del proyecto

1. El archivo principal se llama exactamente `index.html` (en minúsculas) y está en la raíz.
2. Todas las rutas son **relativas** (`assets/css/main.css`, `../index.html`). Nunca `C:/...` ni `/Users/...`.
3. Los nombres de archivo van en minúsculas, sin espacios ni tildes (GitHub Pages distingue mayúsculas).
4. Las imágenes se entregan ya exportadas (JPG, PNG o WebP) y optimizadas. Los `.psd` no se suben (ver `.gitignore`).
5. Nada se sube directo a `main`: todo entra por Pull Request con al menos una aprobación.

## Flujo de trabajo (GitHub Flow)

```bash
git switch main && git pull
git switch -c fix/nombre-del-cambio     # rama corta y descriptiva
# ...cambios...
git add .
git commit -m "fix: describe el cambio en una línea"
git push -u origin fix/nombre-del-cambio
# Abrir Pull Request en GitHub → Code Review → Merge → borrar la rama
```

Prefijos de commit (Conventional Commits): `feat:`, `fix:`, `refactor:`, `docs:`, `chore:`.

## Despliegue en GitHub Pages

1. Verifica que el repositorio es **público** y que `index.html` está en la raíz de `main`.
2. Ve a **Settings → Pages**.
3. En **Build and deployment → Source** elige **Deploy from a branch**.
4. En **Branch** selecciona `main` y la carpeta `/ (root)`. Pulsa **Save**.
5. Espera 1 a 3 minutos (pestaña **Actions**, flujo *pages build and deployment*, en verde).
6. Abre la URL: `https://jespinosa0118.github.io/libreria-raiz/`.

### Lista de verificación previa a enviar la URL

- [ ] La portada carga sin error 404.
- [ ] Los estilos y el script se aplican (F12 → Consola sin errores rojos).
- [ ] Las imágenes se ven en todas las páginas.
- [ ] Los enlaces Inicio, Nosotros y Contacto funcionan en ambos sentidos.
- [ ] Se probó en el celular y en una ventana de incógnito.

## Errores frecuentes

| Síntoma | Causa probable | Solución |
|---|---|---|
| 404 en la URL principal | Falta `index.html` o está mal escrito o en otra carpeta | Renombrar a `index.html` en la raíz |
| Página sin estilos | Ruta absoluta o con mayúsculas incorrectas | Usar rutas relativas con el nombre exacto |
| Imagen rota | Carpeta o extensión incorrecta, o archivo no es una imagen real | Exportar a JPG/PNG y revisar la ruta |

## Dominio propio (opcional)

Settings → Pages → *Custom domain*, y en el DNS: registros `A` hacia `185.199.108.153`, `185.199.109.153`,
`185.199.110.153`, `185.199.111.153` y un `CNAME` de `www` hacia `jespinosa0118.github.io`. Luego activa **Enforce HTTPS**.

## Documentación del equipo

- [Acta de reunión](documentacion/acta-reunion.md)
- [Tablero Kanban](documentacion/kanban.md)
