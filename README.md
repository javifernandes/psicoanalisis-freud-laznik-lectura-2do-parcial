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
- `data/sources/index.json`
- `data/sources/apunte2.json`

Las cards incluyen sólo bibliografía obligatoria. La vista `Programa / Guías` conserva los ejes y desarrollos pedagógicos de las guías. Para los módulos 5 y 6, la ubicación física inicial es el tomo Amorrortu indicado por el programa; queda pendiente auditar esos recortes contra Apunte 1 / Apunte 2.

En el tablero se puede alternar entre páginas `Amorrortu` y páginas de `Apuntes`. La pestaña `Apuntes` reúne los índices físicos disponibles: hoy incorpora el índice manual del Apunte 2 y deja visible que el Apunte 1 todavía no fue relevado. Una obra puede tener varias apariciones porque los apuntes contienen duplicados o recortes distintos.

## Nota

Abrir `index.html` directo con `file://` puede fallar porque el navegador bloquea `fetch()` de archivos locales.
Usar `npm run dev` para probar localmente.
