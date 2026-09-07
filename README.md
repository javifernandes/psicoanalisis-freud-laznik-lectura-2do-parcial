# Psicoanálisis Freud · Plan de lectura

Aplicación estática para organizar lecturas de Psicoanálisis Freud, cátedra Laznik.

El tablero cubre los módulos 3, 4, 5 y 6. Los módulos 5 y 6 corresponden al tercer parcial/integrador y fueron modelados a partir de las Guías 5 y 6 y del programa oficial 2026.

## Desarrollo local

```bash
npm install
npm run dev
```

Luego abrir la URL que imprime Vite.

## Deploy en GitHub Pages

El sitio es estático. Se puede publicar con GitHub Pages usando la rama `main` y la carpeta `/root`.

Archivos principales:

- `index.html`
- `data/readings.json`
- `data/guides/module3.json`
- `data/guides/module4.json`
- `data/guides/module5.json`
- `data/guides/module6.json`

Las cards incluyen sólo bibliografía obligatoria. La vista `Programa / Guías` conserva los ejes y desarrollos pedagógicos de las guías. Para los módulos 5 y 6, la ubicación física inicial es el tomo Amorrortu indicado por el programa; queda pendiente auditar esos recortes contra Libro 1 / Libro 2.

## Nota

Abrir `index.html` directo con `file://` puede fallar porque el navegador bloquea `fetch()` de archivos locales.
Usar `npm run dev` para probar localmente.
