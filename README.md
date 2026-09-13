# Portfolio de Carlos Calderón

Portfolio personal construido con Astro y TypeScript. La página presenta el perfil profesional, experiencia, habilidades, certificaciones, proyectos y formas de contacto de Carlos.

## Estructura

- `src/data/portfolio.json`: fuente de toda la información personal que se renderiza en la página.
- `src/pages/index.astro`: plantilla principal y composición de las secciones.
- `src/styles/global.css`: estilos, responsive design y sistema visual.
- `Dockerfile` y `docker-compose.yml`: entorno reproducible para desarrollo y validación.
- `astro.config.mjs` y `tsconfig.json`: configuración de Astro y TypeScript.

## Desarrollo con Docker

Necesitas Docker Engine y Docker Compose.

```bash
docker compose up --build -d
```

Abre [http://localhost:4321](http://localhost:4321). El proyecto se monta dentro del contenedor, por lo que los cambios en `src/` se actualizan automáticamente.

Para detener el entorno:

```bash
docker compose down
```

Para ejecutar las comprobaciones del proyecto dentro del contenedor:

```bash
docker compose run --rm portfolio npm run check
docker compose run --rm portfolio npm run build
```

Para revisar los registros del servidor:

```bash
docker compose logs -f portfolio
```

## Desarrollo local

Necesitas Node.js 18.17 o superior.

```bash
npm install
npm run dev
```

Para verificar el proyecto y generar la versión de producción:

```bash
npm run check
npm run build
```

La página principal está en [`src/pages/index.astro`](src/pages/index.astro) y los estilos globales en [`src/styles/global.css`](src/styles/global.css).

## Flujo Git

El repositorio utiliza una estructura Git Flow sencilla:

- `main`: versiones estables listas para publicar.
- `develop`: integración de cambios antes de publicar.
- `feature/*`: nuevas funcionalidades o mejoras.

Flujo recomendado:

```bash
git switch develop
git switch -c feature/nombre-del-cambio
# realizar cambios y validarlos
git add .
git commit -m "feat: describe el cambio"
git switch develop
git merge --no-ff feature/nombre-del-cambio
```

