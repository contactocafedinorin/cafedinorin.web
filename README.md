# CAFÉ DINORÍN — Tienda Web PWA
**El sabor que se queda en casa — Altas Montañas de Veracruz**

Tienda 100% funcional, sin dependencias de pago, lista para GitHub Pages e instalable como app Android (PWA).

## 📁 Estructura del proyecto
```
/cafe-dinorin
├── index.html
├── style.css
├── script.js
├── manifest.json
├── service-worker.js
├── /images
│   ├── logo.png            ← REEMPLAZA con tu logo real (400x400px recomendado)
│   ├── cafe-500g.png       ← REEMPLAZA con foto real de bolsa 500g (600x800px)
│   └── cafe-1kg.png        ← REEMPLAZA con foto real de bolsa 1kg / 2x500g
├── /icons
│   ├── icon-192.png
│   ├── icon-192-maskable.png
│   ├── icon-512.png
│   └── icon-512-maskable.png
└── README.md
```

## ✅ Lo que ya hace (checklist)
- [x] Carrito: agregar, subir/bajar cantidad, eliminar
- [x] Cálculo correcto: subtotal + envío = total
- [x] Validación de formulario (nombre, teléfono, dirección)
- [x] Generación de pedido con resumen completo
- [x] Botón "Enviar pedido por WhatsApp" con mensaje preformateado
- [x] Responsive mobile-first, botones grandes
- [x] PWA: manifest.json + service-worker.js + instalable
- [x] Sin enlaces rotos, sin pasarelas de pago
- [x] Inventario localStorage que descuenta al confirmar pedido
- [x] Zonas de envío configurables
- [x] Estructura preparada para email futuro (función buildEmailBody)

## 🚀 Cómo subir a GitHub Pages (paso a paso)

### 1. Crear el repositorio
1. Entra a github.com y crea cuenta si no tienes.
2. Click **New repository** → Nombre: `cafe-dinorin` → Público → **Create repository**
3. No inicialices con README si ya tienes los archivos locales.

### 2. Qué archivos subir
Sube TODO el contenido de la carpeta `/cafe-dinorin` tal cual:
- index.html, style.css, script.js, manifest.json, service-worker.js en la raíz
- Carpeta /images con tus fotos reales
- Carpeta /icons

Puedes subirlos desde la web: en tu repo → **Add file → Upload files** → arrastra todos los archivos y carpetas.

O con git:
```bash
cd cafe-dinorin
git init
git add .
git commit -m "Tienda CAFÉ DINORÍN v1"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/cafe-dinorin.git
git push -u origin main
```

### 3. Dónde colocar imágenes y logo
- Logo: reemplaza `/images/logo.png` con tu logo cuadrado, fondo transparente o crema. Mantén el mismo nombre.
- Producto 500g: reemplaza `/images/cafe-500g.png` (foto vertical de la bolsa)
- Producto 1kg: reemplaza `/images/cafe-1kg.png`

Tip: Usa 600x800px, fondo claro, buena luz. No cambies los nombres, solo el contenido.

### 4. Activar GitHub Pages
1. En tu repositorio → **Settings → Pages**
2. En **Build and deployment** → Source: **Deploy from a branch**
3. Branch: **main** / **(root)** → Save
4. Espera 1-2 minutos.

### 5. Obtener el enlace público
Te aparecerá arriba: `https://TU_USUARIO.github.io/cafe-dinorin/`
Ese es tu dominio gratuito. Abre en incógnito para probar.

### 6. Instalar como app en Android (PWA sin Play Store)
1. Abre tu enlace en Chrome Android
2. Toca los 3 puntos ⋮ → **Instalar aplicación** o **Agregar a pantalla principal**
3. Si configuraste bien el SW, verás también un botón "Instalar app" dorado en el header.
4. La app quedará como icono con tu logo, abre a pantalla completa, funciona offline para navegar.

En iPhone: Compartir → Agregar a inicio (Apple no permite instalación automática PWA completa, pero funciona como app).

### 7. Cómo actualizar productos, precios e inventario

**Opción A - Panel rápido (sin tocar código):**
1. Abre tu tienda con `?admin=1` al final: `.../cafe-dinorin/?admin=1`
2. O toca 5 veces seguidas el logo en el header.
3. Edita: número WhatsApp, datos bancarios, costos de envío, precio, stock, activo/inactivo.
4. Guarda. Se queda en tu navegador. Ideal para cambios rápidos.

**Opción B - Permanente (código):**
Edita `script.js` → `CONFIG_DEFAULT`:
- `whatsapp`: pon `521228XXXXXXX` (sin espacios, con 521)
- `banco`: tus datos de transferencia
- `envios.xalapa.costo`: ej 50, etc.
- `productos[0].precio`, `.stock`, `.activo`

Sube de nuevo a GitHub y Pages se actualiza solo.

**Inventario:** Se descuenta automáticamente cuando se confirma un pedido. Se guarda en localStorage, así que aunque recargues no se pierde hasta que lo restablezcas.

## 📲 WhatsApp - Cómo funciona
Al finalizar pedido, el botón genera un mensaje tipo:
```
Hola CAFÉ DINORÍN! Quiero hacer este pedido:
PEDIDO DIN-123456
Cliente: Ana...
...
TOTAL: $350 MXN
```
Y abre `https://wa.me/TU_NUMERO?text=...` directo a tu WhatsApp. Debes configurar tu número real, si no, te pedirá copiar el resumen.

## ✉️ Email futuro (estructura lista)
En `script.js` existe `buildEmailBody()` y un botón deshabilitado. Para activarlo:
- Opción gratis: usa FormSubmit.co o EmailJS
- Cuando quieras, te ayudo a conectarlo sin costo.

## 🌐 Dominio propio más adelante
Este proyecto ya está preparado. Cuando compres dominio (ej: cafedino rin.com en Namecheap o Hostinger):
1. En GitHub Pages → Settings → Custom domain → pon tu dominio
2. En tu proveedor de dominio crea un CNAME apuntando a `TU_USUARIO.github.io`
3. No necesitas cambiar código, funciona igual.

## 🔧 Datos pendientes [PENDIENTE]
Busca en el proyecto `[PENDIENTE]`:
- Número WhatsApp real
- Datos bancarios CLABE
- Email de contacto
- Altura exacta del café, si quieres detallar origen

Reemplázalos cuando los tengas. La tienda funciona aunque estén pendientes, pero te avisará.

## Soporte
¿Quieres que te genere el ZIP listo para subir? ¿O que conecte el dominio? Dime y lo preparamos.

Hecho con cariño desde Xalapa para las Altas Montañas.
