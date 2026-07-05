# Modelo para guías

## Objetivo

Representar la guía oficial de lectura como árbol pedagógico, independiente de las cards de lectura.

## Estructura propuesta

```ts
type GuideModule = {
  id: string
  label: string // "Módulo 3"
  title: string // "Pulsión, Fantasía y Narcisismo"
  blocks: GuideBlock[]
}

type GuideBlock = {
  id: "theory" | "seminar" | "practice"
  label: "Teóricos" | "Seminarios" | "Prácticos"
  title: string // texto oficial de la guía: "Puntos 7 y 8..."
  topics: GuideTopic[]
}

type GuideTopic = {
  id: string
  label: string // "Conferencia 20"
  title: string // "La vida sexual de los seres humanos"
  eje?: string
  points?: string[]
  rawGuideText?: string
  readingRefs: ReadingRef[]
}

type ReadingRef = {
  title: string
  pages?: string
}
```

## Importante

`GuideTopic` no es una card.

Un tópico puede apuntar a una lectura física agrupada.

Ejemplo:

```json
{
  "label": "Conferencia 20",
  "title": "La vida sexual de los seres humanos",
  "readingRefs": [
    { "title": "Conferencias 20, 21, 22 y 23" }
  ]
}
```

La guía puede tener cuatro tópicos:
- Conferencia 20
- Conferencia 21
- Conferencia 22
- Conferencia 23

aunque la fotocopia y la ReadingTask agrupen:

```txt
Conferencias 20, 21, 22 y 23
```

## Vista Programa / Guías deseada

No usar tarjetas anchas con todos los ejes visibles.

Usar master-detail:

```txt
┌───────────────────────────┬─────────────────────────────┐
│ Árbol                     │ Detalle                     │
│                           │                             │
│ Módulo 3                  │ Conferencia 20              │
│  Teóricos                 │ Eje...                      │
│   Puntos 7 y 8            │ 1. Libido                   │
│    Conferencia 20         │ 2. Apuntalamiento           │
│    Conferencia 21         │                             │
│                           │ Lecturas vinculadas         │
│                           │ Conferencias 20-23          │
└───────────────────────────┴─────────────────────────────┘
```

## Títulos oficiales ya identificados

### Módulo 3

```txt
PULSIÓN, FANTASÍA Y NARCISISMO
```

Bloques:

```txt
Teóricos: Puntos 7 y 8: Irrupción de la sexualidad. Enmienda de la teoría traumática
Seminarios: Puntos IV y V: Revisión de la teoría traumática. Constitución del narcisismo
Prácticos: Punto IV: Crítica de la etiología: sexualidad y represión
```

### Módulo 4

```txt
REPRESIÓN, INCONCIENTE, TRANSFERENCIA, GANANCIA DE LA ENFERMEDAD, ANGUSTIA
```

Nota: la guía puede escribir "inconciente" sin s; los textos de Freud/Amorrortu a veces aparecen como "inconsciente". Mantener el texto oficial en títulos de módulo, pero normalizar internamente para búsqueda.

## Ejemplo de tópico guía real del Módulo 3

El usuario mencionó que la guía 3 dice:

```txt
Conferencia 20º: La vida sexual de los seres humanos

Eje: ¿Qué puede averiguarse de la vida sexual del niño?

1- Libido
2- Apuntalamiento
3- Chupeteo y ganancia de placer
4- Caracteres decisivos de la sexualidad infantil
```

Esto debe estar en `module3.json`.

## Pendiente

Parsear fielmente guías 3 y 4 desde los PDFs/documentos originales.

Lo que hay en el ZIP generado por ChatGPT es un primer esqueleto, no una transcripción completa garantizada.

Codex debería actualizar `data/guides/module3.json` y `data/guides/module4.json` con el texto exacto de las guías.
