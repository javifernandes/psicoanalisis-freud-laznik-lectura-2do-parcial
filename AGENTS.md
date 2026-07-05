# AGENTS.md

## Proyecto

Aplicación estática para organizar el segundo parcial de Psicoanálisis Freud, cátedra Laznik, UBA.

Repo del usuario:

https://github.com/javifernandes/psicoanalisis-freud-laznik-lectura-2do-parcial/

La app está pensada para GitHub Pages y desarrollo local con `npm run dev`.

## Objetivo

No es sólo un checklist. Es una guía de lectura crítica que cruza:

1. Programa oficial / guías de lectura de la cátedra.
2. Lecturas efectivas por módulo, bloque y unidad.
3. Fuentes físicas disponibles: Libro 1, Libro 2, Amorrortu/PDF.
4. Progreso local de cada estudiante en `localStorage`.

## Reglas importantes

- La fuente de verdad pedagógica son las guías/programa, no la fotocopiadora.
- La fotocopiadora es sólo una fuente física y puede estar:
  - duplicada,
  - incompleta,
  - recortada,
  - mal ordenada,
  - o directamente equivocada.
- Cada card del tablero representa una **lectura de cátedra**: obra + páginas Amorrortu + módulo + bloque/unidad.
- No fusionar en una sola card fragmentos del mismo texto si la cátedra los trabaja en momentos/bloques distintos.
- El progreso debe ser por fragmento bibliográfico, no por aparición visual.
- Si un fragmento mayor contiene completamente a otro menor, marcar el mayor como leído debe implicar el menor.
- Si sólo hay superposición parcial, NO auto-marcar.
- No usar datos personales de progreso embebidos. El sitio compartido debe arrancar limpio.
- El `localStorage` pertenece al usuario; los JSON pertenecen al contenido.
- Mantener compatibilidad hacia atrás del progreso siempre que sea posible.

## Estilo de código

- Mantener app estática, sin backend.
- Preferir datos en `data/readings.json` y `data/guides/moduleX.json`.
- No meter más lógica bibliográfica hardcodeada si se puede modelar en datos.
- Si se cambia el modelo de datos, documentarlo en `docs/`.
- Evitar dependencias pesadas. Vite como server local es suficiente.

## UX actual esperada

- Tabs principales:
  - Módulo 3
  - Módulo 4
  - Programa / Guías
- Tablero por módulo:
  - 3 columnas: Teóricos, Prácticos, Seminarios.
  - Cards compactas expandibles.
  - Checkbox moderno.
  - Progreso por bloque con puntitos como mini progress bar, no mapa de cards.
  - Páginas leídas/total por bloque, tipo `10/89p`.
  - Filtro `ocultar repetidos`.
  - Filtro `ocultar leídos`.
  - Buscador.
  - Drag & drop dentro de cada columna, persistido en localStorage.
  - Scroll interno por columna sin resetearse al marcar leído.
- Programa / Guías:
  - Debe evolucionar a vista tipo master-detail:
    - izquierda: árbol documental de guías.
    - derecha: detalle del tópico seleccionado.
  - Debe mostrar la estructura original de guías, no sólo derivar de las cards.

## Cuidado

Hubo una versión donde al extraer datos a JSON se perdieron cambios recientes de UI:
- `ocultar leídos`
- tercer tab `Programa / Guías`

Revisar que estén presentes en la versión local actual.
