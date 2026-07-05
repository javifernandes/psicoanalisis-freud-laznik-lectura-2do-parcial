# Handoff del proyecto

## Contexto general

El usuario está cursando Psicoanálisis Freud, cátedra Laznik, UBA. La materia está organizada en módulos, bloques y guías de lectura. La fotocopiadora tiene dos tomos de apuntes:

- Libro 1: rotulado como primer parcial, pero contiene textos adelantados de módulos 3/4.
- Libro 2: rotulado como segundo/tercer parcial, contiene módulos 3, 4, 5 y 6 mezclados.

El objetivo inicial era ordenar qué leer para el segundo parcial. Durante el trabajo se descubrió que no alcanza con listar apuntes porque:
- hay textos repetidos entre libros;
- hay fragmentos parciales;
- algunas lecturas se retoman en distintos módulos/bloques;
- la fotocopia tiene al menos un error grave.

La hipótesis de cortes por parcial quedó:

- 1º parcial: módulos 1 y 2.
- 2º parcial: módulos 3 y 4.
- 3º parcial/integrador: módulos 5 y 6.

La app actual se concentra en módulos 3 y 4.

## Módulos relevantes

### Módulo 3

Título oficial usado en sitio:

**PULSIÓN, FANTASÍA Y NARCISISMO**

Bloques guía:

- Teóricos: Puntos 7 y 8. Irrupción de la sexualidad. Enmienda de la teoría traumática.
- Seminarios: Puntos IV y V. Revisión de la teoría traumática. Constitución del narcisismo.
- Prácticos: Punto IV. Crítica de la etiología: sexualidad y represión.

### Módulo 4

Título oficial usado en sitio:

**REPRESIÓN, INCONSCIENTE, TRANSFERENCIA, GANANCIA DE LA ENFERMEDAD, ANGUSTIA**

Bloques guía:

- Teóricos: represión, inconsciente, transferencia, ganancia de la enfermedad.
- Seminarios: formación de síntoma, ganancia de la enfermedad, angustia.
- Prácticos: inconsciente, represión, tótem/tabú, técnica y transferencia.

## Modelo conceptual acordado

Hay tres niveles distintos.

### 1. Programa / guía

Responde: ¿qué quiere enseñar la cátedra?

Estructura:

```txt
Module
  Block
    Topic
      Ejes / preguntas / puntos de lectura
      readingRefs[]
```

Ejemplo:

```txt
Módulo 3
  Teóricos
    Puntos 7 y 8
      Conferencia 20
        Eje: ¿Qué puede averiguarse de la vida sexual del niño?
        1. Libido
        2. Apuntalamiento
        3. Chupeteo y ganancia de placer
        4. Caracteres decisivos de la sexualidad infantil
```

### 2. Lectura de cátedra / ReadingTask

Responde: ¿qué páginas hay que leer?

Card = obra + páginas Amorrortu + módulo + bloque + unidad.

Ejemplo:

```txt
Módulo 3 · Prácticos · Práctico IV
Tres ensayos de teoría sexual, cap. I puntos 4 y 5, y cap. II
pp. 148–154, 157–188
```

### 3. Fuente física

Responde: ¿dónde lo leo?

Puede ser:

- Libro 1
- Libro 2
- Amorrortu XIII
- PDF externo

Ejemplo:

```txt
Pies (zapatos) abochornados
Fuente recomendada: Amorrortu XIII, pp. 199–200
```

## Decisiones UX importantes

### Cards

Las cards del tablero son ReadingTasks, no tópicos de guía. No deben intentar representar toda la guía oficial.

### Programa / Guías

El tab Programa / Guías debe mostrar la guía como árbol documental, no como tablero.

Propuesta acordada:

```txt
┌───────────────────────┬───────────────────────────┐
│ árbol guía            │ detalle tópico             │
│                       │                           │
│ Módulo 3              │ Conferencia 20             │
│   Teóricos            │ Eje...                     │
│     Conferencia 20    │ puntos...                  │
│     Conferencia 21    │ Lecturas vinculadas...     │
│                       │                           │
└───────────────────────┴───────────────────────────┘
```

La izquierda debe ser más angosta; la derecha panel fijo. Hoy el intento de Programa/Guías está demasiado ancho y muestra demasiada info en línea.

## Progreso

- Debe persistir por `readingId`.
- `readingId` actualmente se basa en título normalizado + páginas canónicas.
- Duplicados exactos comparten progreso.
- Inclusiones totales deben compartir progreso por implicación.
- Superposiciones parciales NO deben compartir progreso.

Ejemplo inclusión:

- Pulsiones 113–122 contiene 121–122.
- Si 113–122 está leído, 121–122 debe mostrarse leído.
- No necesariamente al revés.

## LocalStorage

La versión compartida debe arrancar 0%.

No usar `status: leído` como default.

Regla correcta en `isChecked`:

```js
if (progress[pid] !== undefined) return progress[pid];
if (impliedByLargerReading(progress, pid)) return true;
return false;
```

Reset debe borrar:
- storage actual
- storage legacy
- open cards
- custom order
- hide repeats
- hide read

## Deployment

GitHub Pages sirve bien:

```txt
index.html
data/readings.json
data/guides/module3.json
data/guides/module4.json
```

Para probar local:

```bash
npm install
npm run dev
```

No abrir `index.html` con `file://` si usa `fetch`, porque puede fallar por CORS.

## Problema detectado en último ZIP

Al extraer a JSON se produjo una regresión: el usuario levantó el proyecto local y no vio:

- filtro `ocultar leídos`;
- tab `Programa / Guías`.

Revisar el repo local y restaurar estas features desde la última versión HTML si hiciera falta.
