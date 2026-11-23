# Programa de recompensas · Inversiones 101

Sitio estático (un solo `index.html`, sin build). Diseño basado en el sistema de diseño de Inversiones 101.

## Antes de publicar

En `index.html`:

1. Al final del archivo, completa `CONFIG`:
   - `formUrl`: enlace de tu formulario de Tally. Si lo dejas vacío, el botón de cobro se oculta.
   - `contactEmail`: correo de soporte. Si lo dejas vacío, la regla de reclamos solo menciona Skool.
2. Reemplaza el bloque `ganadores-data` con tus ganadores reales y borra la línea `"demo": true` (con eso desaparece el aviso de datos de ejemplo).
   - `estado`: `pagado`, `en proceso`, `acumulado` o `alternativo`.
3. Revisa las reglas con tu CPA o abogado. Los plazos (30 días para cobrar, 15 días hábiles para pagar, 12 meses para acumulados) y quién asume las comisiones son valores propuestos que puedes cambiar.

## Publicar en Vercel con tu dominio

Opción A: desde tu computadora (la más rápida)

```bash
npm i -g vercel
cd programa-recompensas
vercel login
vercel --prod
vercel domains add recompensas.inversiones101.lat
```

Opción B: desde GitHub

1. Sube esta carpeta a un repositorio nuevo.
2. En vercel.com, "Add New → Project", importa el repositorio. Framework: "Other". No necesita comando de build ni carpeta de salida.
3. En el proyecto, "Settings → Domains", agrega `recompensas.inversiones101.lat`.

## DNS del subdominio

Vercel te muestra el registro exacto al agregar el dominio. Normalmente es:

| Tipo  | Nombre        | Valor                  |
|-------|---------------|------------------------|
| CNAME | recompensas   | cname.vercel-dns.com   |

Se crea en el proveedor donde administras el DNS de `inversiones101.lat`. Usa el valor que Vercel te indique si es distinto. Si prefieres otro nombre, por ejemplo `programa-de-recompensas`, solo cambia el nombre del registro y el dominio agregado en Vercel.

## Actualizar cada mes

Edita el bloque `ganadores-data` y vuelve a publicar (`vercel --prod`, o un commit si usas GitHub).
