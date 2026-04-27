# OpenVector Intelligence – Landing Page

Landing page oficial de OpenVector Intelligence, desarrollada con Astro. Este proyecto está diseñado para ofrecer alto rendimiento, seguridad, escalabilidad y una base sólida para la expansión futura de servicios, contenido técnico y capacidades interactivas.

---

## Descripción General

Este repositorio contiene la implementación de la landing page corporativa de OpenVector Intelligence. Incluye:

- Presentación de servicios de ciberseguridad
- Blog técnico con soporte Markdown/MDX
- Componentes reutilizables orientados a UI/UX y seguridad
- Integración de widgets dinámicos (por ejemplo, chatbot)
- Preparación para SEO, RSS y distribución de contenido

El proyecto sigue principios de desarrollo moderno: desacoplamiento, modularidad, rendimiento optimizado y superficie de ataque reducida.

---

## Stack Tecnológico

- **Framework:** Astro
- **Lenguajes:** TypeScript, HTML, CSS
- **Contenido:** Markdown (MD), MDX
- **Gestión de dependencias:** npm
- **Arquitectura:** Static Site Generation (SSG)

---

## Estructura del Proyecto

```text
├── astro.config.mjs
├── package.json
├── package-lock.json
├── public
│   ├── favicon.ico
│   ├── favicon.svg
│   ├── logo.jpg
│   ├── logo.png
│   ├── openvector-logo.png
│   └── wall.png
├── README.md
├── src
│   ├── assets
│   │   ├── blog-placeholder-1.jpg
│   │   ├── blog-placeholder-2.jpg
│   │   ├── blog-placeholder-3.jpg
│   │   ├── blog-placeholder-4.jpg
│   │   ├── blog-placeholder-5.jpg
│   │   ├── blog-placeholder-about.jpg
│   │   └── fonts
│   │       ├── atkinson-bold.woff
│   │       └── atkinson-regular.woff
│   ├── components
│   │   ├── BaseHead.astro
│   │   ├── ChatbotWidget.astro
│   │   ├── Footer.astro
│   │   ├── FormattedDate.astro
│   │   ├── Header.astro
│   │   ├── HeaderLink.astro
│   │   ├── Reviews.astro
│   │   └── SecurityNews.astro
│   ├── consts.ts
│   ├── content
│   │   └── blog
│   │       ├── first-post.md
│   │       ├── markdown-style-guide.md
│   │       ├── second-post.md
│   │       ├── third-post.md
│   │       └── using-mdx.mdx
│   ├── content.config.ts
│   ├── layouts
│   │   └── BlogPost.astro
│   ├── pages
│   │   ├── about.astro
│   │   ├── blog
│   │   │   ├── index.astro
│   │   │   └── [...slug].astro
│   │   ├── index.astro
│   │   └── rss.xml.js
│   └── styles
│       └── global.css
└── tsconfig.json
```

```markdown
# Arquitectura y Diseño

## 1. Enfoque SSG (Static Site Generation)

El proyecto utiliza generación estática para:

- Reducir la superficie de ataque (sin backend expuesto)
- Mejorar tiempos de carga (TTFB bajo)
- Facilitar despliegue en CDN

## 2. Componentización

Los componentes están diseñados para ser reutilizables y desacoplados:

- **Header.astro** y **Footer.astro**: navegación y estructura global
- **BaseHead.astro**: control de metadatos, SEO y headers
- **ChatbotWidget.astro**: integración de interacción automatizada
- **SecurityNews.astro**: potencial integración con feeds externos

## 3. Gestión de Contenido

Uso de content collections de Astro:

- Validación de esquema mediante `content.config.ts`
- Tipado seguro en TypeScript
- Separación clara entre contenido y lógica

## 4. Blog Técnico

- Soporte para Markdown y MDX
- Layout dedicado (`BlogPost.astro`)
- Generación dinámica de rutas (`[...slug].astro`)
- RSS feed automático (`rss.xml.js`)

---

# Consideraciones de Seguridad

Este proyecto, aunque es frontend estático, sigue buenas prácticas de seguridad:

## 1. Hardening del Frontend

- Evitar inline scripts no controlados
- Sanitización de contenido MDX si se permite entrada externa
- Uso estricto de headers en despliegue:
  - Content Security Policy (CSP)
  - X-Frame-Options
  - X-Content-Type-Options

## 2. Dependencias

Auditoría periódica con:

```bash
npm audit
```

Fijación de versiones mediante `package-lock.json`

## 3. Chatbot / Integraciones

El componente `ChatbotWidget` debe:

- Evitar exposición de tokens en frontend
- Consumir APIs mediante proxy seguro si aplica
- Implementar rate limiting del lado servidor (si se conecta a backend)

---

# Instalación

```bash
git clone <repository-url>
cd openvector-landing
npm install
```

# Ejecución en Desarrollo

```bash
npm run dev
```

Servidor disponible en: `http://localhost:4321`

# Build de Producción

```bash
npm run build
```

Salida generada en: `/dist`

# Previsualización

```bash
npm run preview
```

---

# Buenas Prácticas de Desarrollo

- Mantener separación entre lógica, presentación y contenido
- Evitar lógica compleja en componentes `.astro`
- Centralizar constantes en `consts.ts`
- Documentar cambios estructurales relevantes
- Validar contenido antes de despliegue

---

# Escalabilidad

Este proyecto está preparado para evolucionar hacia:

- Integración con backend (API Gateway / BFF)
- Autenticación de usuarios (para dashboards o clientes)
- Multi-tenant content delivery
- Internacionalización (i18n)
- Integración con plataformas de análisis (SIEM dashboards embebidos)

---

# SEO y Distribución

Incluye:

- Metadatos dinámicos
- Open Graph
- Sitemap
- RSS Feed

**Recomendaciones adicionales:**

- Integrar schema.org (JSON-LD)
- Optimizar imágenes (WebP/AVIF)
- Implementar lazy loading

---

# Despliegue

Compatible con:

- Vercel
- Netlify
- Cloudflare Pages
- CDN estáticos (S3 + CloudFront)

**Recomendación:**

- Configurar headers de seguridad en el edge
- Usar WAF en capa CDN

---

# Licencia

Propiedad de OpenVector Intelligence. Uso interno o bajo autorización.

---

# Mantenimiento

**Responsabilidades:**

- Actualización de dependencias
- Revisión de seguridad
- Publicación de contenido técnico
- Optimización continua de rendimiento
```