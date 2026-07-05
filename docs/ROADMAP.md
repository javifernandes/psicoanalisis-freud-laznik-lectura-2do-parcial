# Roadmap

## Prioridad 0: corregir regresión

El usuario levantó el proyecto local y no vio:
- filtro `ocultar leídos`;
- tab `Programa / Guías`.

Revisar `index.html` local.

Comparar con la última versión HTML funcional generada antes de extraer JSON:
- tenía buscador;
- ocultar repetidos;
- ocultar leídos;
- tabs Módulo 3 / Módulo 4 / Programa-Guías;
- GitHub icon;
- warning de Amorrortu en Pies/zapatos;
- progress dots como barra de progreso;
- páginas leídas/total;
- scroll interno preservado.

## Prioridad 1: estabilizar datos

Mantener:
- `data/readings.json`
- `data/guides/module3.json`
- `data/guides/module4.json`

No mover a backend.

## Prioridad 2: vista Programa / Guías

Reemplazar vista ancha por master-detail.

### Layout

```txt
Programa / Guías
┌────────────────────┬─────────────────────────────┐
│ árbol izquierdo    │ panel detalle derecho       │
└────────────────────┴─────────────────────────────┘
```

### Árbol

Debe mostrar:

```txt
Módulo 3 — PULSIÓN, FANTASÍA Y NARCISISMO
  Teóricos — Puntos 7 y 8...
    Conferencia 20
    Conferencia 21
    ...
  Seminarios — Puntos IV y V...
  Prácticos — Punto IV...
```

### Detalle

Al seleccionar tópico:

- título;
- eje;
- puntos;
- lectura(s) vinculadas;
- fuente física;
- progreso;
- warning si existe.

## Prioridad 3: parseo fiel de guías

Los `module3.json` y `module4.json` iniciales son aproximados. Hay que reemplazarlos por transcripción fiel de guías.

Ideal:

- Copiar textos exactos de guía.
- Mantener `rawGuideText`.
- Estructurar `points`.

## Prioridad 4: data audit visible

Agregar en detalle de card o guía:
- Fuente recomendada.
- Notas de auditoría.
- Warning de errores de fotocopiadora.
- Caso de inclusión/superposición si corresponde.

## Prioridad 5: README público

Actualizar README del repo para explicar:

- qué es;
- cómo usar;
- cómo correr local;
- cómo contribuir;
- qué significa Libro 1 / Libro 2 / Amorrortu;
- disclaimer: no oficial.

## Nice to have

- Exportar/importar progreso local.
- Agregar módulos 5 y 6.
- Agregar notas personales por card.
- Deep links por card o tópico.
- Modo sólo pendientes.
