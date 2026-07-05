# Psicoanálisis Freud · Plan de lectura

Aplicación estática para organizar lecturas de Psicoanálisis Freud, cátedra Laznik.

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

## Nota

Abrir `index.html` directo con `file://` puede fallar porque el navegador bloquea `fetch()` de archivos locales.
Usar `npm run dev` para probar localmente.
