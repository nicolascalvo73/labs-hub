# labs-hub

Proyecto de Vercel que es dueño del dominio `labs.mondistudio.com.ar` y reenvía
cada ruta `/nombre-negocio/*` al sitio de GitHub Pages correspondiente, vía
`rewrites` en `vercel.json` (proxy, no redirect: la URL visible no cambia).

Motivo: un dominio custom de GitHub Pages es 1 a 1 con un repo y sirve en la
raíz. Este hub permite que varias propuestas —cada una su propio repo y
deploy en GitHub Pages, como pide la skill `mondi-proposal`— convivan bajo
`labs.mondistudio.com.ar/nombre-negocio`.

## Agregar una propuesta nueva
1. Agregar dos entradas a `vercel.json`, replicando el patrón existente con
   el nuevo nombre y su URL de `https://<usuario>.github.io/<repo>/`.
2. Agregar el link en `index.html`.
3. Push a `main`: Vercel redeploya solo (proyecto conectado por Git).

## Deploy
Importado en Vercel desde este repo de GitHub (sin build step: sitio
estático). El dominio `labs.mondistudio.com.ar` se asigna desde
Vercel → Project → Settings → Domains (el DNS de `mondistudio.com.ar` ya usa
nameservers de Vercel, así que no hace falta cargar ningún registro aparte).
