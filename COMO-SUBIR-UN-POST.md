# Cómo subir un nuevo post al Blog

## Paso 1 — Agregar la tarjeta al índice

Abrí el archivo `src/pages/blog.astro` y agregá una nueva entrada al array `posts`:

```js
{
  slug: "el-titulo-del-post",       // sin espacios ni mayúsculas, usar guiones
  title: "El título del post",       // título que se muestra en la tarjeta
  excerpt: "Descripción corta...",   // 1-2 oraciones que resumen el post
  date: "2025-06-15",                // formato YYYY-MM-DD
  image: "/imagen-del-post.jpg",     // imagen en /public, o URL externa
  category: "Historia",              // debe coincidir con un filtro existente
  readTime: "4 min",                 // estimación a ojo
},
```

**Categorías disponibles:** Historia · Familia · Eventos · Naturaleza

---

## Paso 2 — Crear la página del post

Copiá cualquiera de los archivos existentes como base:

```
src/pages/blog/un-sueno-una-construccion.astro
```

Guardalo con el mismo nombre que pusiste en `slug`:

```
src/pages/blog/el-titulo-del-post.astro
```

Luego editá dentro del archivo:

- El `<title>` en el frontmatter (`---`)
- La badge de categoría
- El `<h1>` con el título
- La fecha en `datetime` y el texto visible
- El tiempo de lectura
- El `src` de la imagen
- El contenido dentro de `<div class="post-content">`

---

## Ejemplo completo

**En `blog.astro`:**
```js
{
  slug: "la-selva-en-peligro",
  title: "La selva en peligro",
  excerpt: "Cada año se pierden miles de hectáreas de selva misionera. Te contamos qué está pasando y cómo podés ayudar.",
  date: "2025-06-15",
  image: "/selva.jpg",
  category: "Naturaleza",
  readTime: "3 min",
},
```

**Archivo:** `src/pages/blog/la-selva-en-peligro.astro`
```astro
---
import Layout from "../../layouts/Layout.astro";
import Header from "../../components/globals/header.astro";
import Footer from "../../components/globals/footer.astro";
---

<Layout title="La selva en peligro - La Aripuca">
  <Header />
  <section class="post-hero">
    <div class="container">
      <span class="post-category-badge">Naturaleza</span>
      <h1>La selva en peligro</h1>
      <div class="post-meta">
        <time datetime="2025-06-15">15 de junio de 2025</time>
        <span class="separator">•</span>
        <span>3 min de lectura</span>
      </div>
    </div>
  </section>
  <main class="blog-section">
    <div class="container-narrow">
      <img src="/selva.jpg" alt="La selva en peligro" class="post-image" />
      <div class="post-content">
        <p>Tu contenido acá...</p>
      </div>
      <a href="/blog" class="back-link">← Volver al Blog</a>
    </div>
  </main>
  <Footer />
</Layout>

<!-- Copiá el bloque <style> de cualquier post existente -->
```

---

## Reglas importantes

- El `slug` en `blog.astro` **debe ser idéntico** al nombre del archivo `.astro` (sin la extensión).
- Usá solo letras minúsculas, números y guiones en el slug. Sin espacios, acentos ni caracteres especiales.
- Las imágenes locales van en la carpeta `/public` y se referencian como `/nombre.jpg`.
- Siempre copiá el bloque `<style>` de un post existente para mantener el diseño uniforme.
