# Robot Legal - Sitio estático

Sitio estático, mobile-first, sin JavaScript, con HTML y CSS puros.

## Estructura
- `index.html` página única con hero, botones y disclaimer.
- `styles.css` estilos globales, cargados con parámetro rompe caché `?v=1`.

## Requisitos previos
- Tener un repositorio en GitHub con estos dos archivos en la raíz.
- Tener una cuenta en Cloudflare y acceso a **Pages**.

## Publicar en Cloudflare Pages
1. Entra a Cloudflare y ve a **Pages**.
2. Clic en **Create a project** y elige **Connect to Git**.
3. Autoriza GitHub y selecciona tu repositorio.
4. **Build settings**:
   - Framework preset: `None`.
   - Build command: _vacío_.
   - Build output directory: `/` (raíz del repo).
5. Clic en **Save and Deploy**.

Cloudflare tomará la rama principal y publicará el sitio de forma automática en cada push.

## Conectar dominio
1. En tu proyecto de Pages ve a **Custom domains** y agrega `www.robotlegal.cl` o el dominio que uses.
2. Sigue las instrucciones para crear el registro CNAME en tu DNS de Cloudflare apuntando a tu proyecto de Pages.
3. Si quieres que `robotlegal.cl` redirija a `www.robotlegal.cl`, crea una **Page Rule** o una **Redirect rule**:
   - Origen: `https://robotlegal.cl/*`
   - Destino: `https://www.robotlegal.cl/$1`
   - Código: 301

## Actualizar estilos
- Modifica `styles.css` y aumenta el número de versión del query string en `index.html`, por ejemplo `styles.css?v=2`.
- Haz commit y push, Cloudflare desplegará automáticamente.

## Accesibilidad y usabilidad
- Header fijo con altura reservada para evitar solapes.
- Botones con altura táctil mínima de 44px y `focus-visible` para navegación con teclado.

## Licencia
Uso libre.
