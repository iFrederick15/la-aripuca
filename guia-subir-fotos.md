# Guía para agregar fotos a la galería de La Aripuca

## Estructura de cada foto

Cada foto es un objeto dentro del array `fotos` en el frontmatter del archivo `galeria.astro`.
Copiá esta plantilla y completá los datos:

```javascript
{
  src: "",           // URL de la imagen
  alt: "",           // Descripción de la imagen (accesibilidad / SEO)
  categoria: "",     // arquitectura | naturaleza | cultura | gastronomia
  titulo: "",        // Nombre que aparece sobre la foto
  descripcion: "",   // Texto corto opcional (dejar "" si no hace falta)
  tamaño: "",        // grande | ancho | alto | normal
},
```

---

## Categorías disponibles

| Valor           | Se muestra como |
|-----------------|-----------------|
| `arquitectura`  | Arquitectura    |
| `naturaleza`    | Naturaleza      |
| `cultura`       | Cultura         |
| `gastronomia`   | Gastronomía     |

---

## Tamaños disponibles

| Valor     | Ocupa en la grilla       | Ideal para                        |
|-----------|--------------------------|-----------------------------------|
| `grande`  | 2 columnas × 2 filas     | Foto destacada, paisajes amplios  |
| `ancho`   | 2 columnas × 1 fila      | Panorámicas, grupos               |
| `alto`    | 1 columna × 2 filas      | Retratos, fotos verticales        |
| `normal`  | 1 columna × 1 fila       | Fotos estándar, detalles          |

### Tip para una grilla equilibrada:
- Por cada 12 fotos usá aprox: 1 grande, 2 anchas, 1 alta, 8 normales
- No pongas dos "grande" seguidas
- Alterná categorías para que quede variado

---

## Ejemplo: agregar 4 fotos nuevas

```javascript
const fotos = [
  // ... fotos existentes ...

  {
    src: "https://ejemplo.com/sendero-selva.jpg",
    alt: "Sendero entre helechos gigantes en la selva misionera",
    categoria: "naturaleza",
    titulo: "Senderos del Monte",
    descripcion: "Caminos que invitan a perderse.",
    tamaño: "ancho",
  },
  {
    src: "https://ejemplo.com/talla-yaguarete.jpg",
    alt: "Talla en madera de un yaguareté",
    categoria: "cultura",
    titulo: "El Yaguareté",
    descripcion: "",
    tamaño: "normal",
  },
  {
    src: "https://ejemplo.com/empanadas.jpg",
    alt: "Empanadas caseras recién hechas",
    categoria: "gastronomia",
    titulo: "Empanadas Misioneras",
    descripcion: "",
    tamaño: "normal",
  },
  {
    src: "https://ejemplo.com/puente-madera.jpg",
    alt: "Puente de madera dentro del predio de La Aripuca",
    categoria: "arquitectura",
    titulo: "Puente Centenario",
    descripcion: "Cruzando sobre el arroyo.",
    tamaño: "alto",
  },
];
```

---

## Recordá también actualizar `fotosData` en el `<script>`

Por cada foto que agregues al array `fotos`, agregá también una entrada en
`fotosData` (dentro del tag `<script>`) en el **mismo orden**:

```javascript
const fotosData = [
  // ... entradas existentes ...

  { categoria: "naturaleza", titulo: "Senderos del Monte", descripcion: "Caminos que invitan a perderse." },
  { categoria: "cultura", titulo: "El Yaguareté", descripcion: "" },
  { categoria: "gastronomia", titulo: "Empanadas Misioneras", descripcion: "" },
  { categoria: "arquitectura", titulo: "Puente Centenario", descripcion: "Cruzando sobre el arroyo." },
];
```

---

## Checklist antes de subir

- [ ] La URL de la imagen funciona (abrirla en el navegador para verificar)
- [ ] La categoría es una de las 4 válidas (todo en minúscula, sin tilde)
- [ ] El `alt` describe lo que se ve en la imagen
- [ ] La foto nueva está en el mismo orden en `fotos` y en `fotosData`
- [ ] Si agregaste más de 12 fotos nuevas, probá el botón "Ver más"