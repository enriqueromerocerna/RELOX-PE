# RELOX PERU — Propuesta de rediseño

Sitio estático (HTML + CSS + JS, sin frameworks ni build step) hecho como propuesta de
nueva imagen para **reloxperu.com**. Usa contenido, precios y fotos de producto reales
tomados del catálogo actual, con una dirección visual completamente nueva: fondo verde
noche, acentos en latón, tipografía Bodoni Moda / Manrope / Space Mono, un dial de reloj
animado como firma visual, y animaciones al hacer scroll.

## Estructura

```
relox-peru/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── main.js
└── README.md
```

## Ver el sitio localmente

Es 100% estático, no necesita instalar nada. Solo abre `index.html` en el navegador,
o si prefieres un servidor local:

```bash
cd relox-peru
python3 -m http.server 8000
# abre http://localhost:8000
```

## Subirlo a GitHub

```bash
cd relox-peru
git init
git add .
git commit -m "Rediseño Relox Peru"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
git push -u origin main
```

Para publicarlo gratis con **GitHub Pages**: en el repositorio, ve a
`Settings → Pages → Source` y selecciona la rama `main` (carpeta `/root`). En un par de
minutos el sitio queda disponible en `https://TU-USUARIO.github.io/TU-REPO/`.

## Notas importantes

- **Imágenes:** se cargan directamente desde el CDN de Shopify de reloxperu.com
  (`cdn/shop/files/...`). Son las fotos reales de los productos, no hay que subir nada
  aparte. Si en algún momento migran de Shopify, esas imágenes habría que descargarlas
  y alojarlas aparte (por ejemplo en una carpeta `/img` del mismo repo).
- **WhatsApp:** todos los botones de compra apuntan a `+51 966 483 150` (el mismo número
  que ya usan en la tienda actual) y arman un mensaje automático con el nombre del
  producto. Para cambiar el número, edítalo en `js/main.js` (constante
  `WHATSAPP_NUMBER`) y en los 3 enlaces `wa.me` que están escritos directo en
  `index.html` (header, hero y CTA final).
- **Productos mostrados:** es una selección de 11 productos reales (6 relojes, 1 lentes
  en formato destacado, 4 perfumes) a modo de muestra — no el catálogo completo de 114
  productos. Cada sección de categoría enlaza a la colección completa en la tienda
  actual (`Ver los 82 modelos`, etc.). Para agregar más productos, se puede copiar el
  bloque `<article class="product-card">` de cualquier producto existente y cambiar
  imagen, nombre, precio y el atributo `data-product`.
- Es una propuesta visual / demo: no tiene carrito ni checkout propio (igual que el
  botón "Comprar ahora" del sitio actual, las compras se coordinan por WhatsApp).
