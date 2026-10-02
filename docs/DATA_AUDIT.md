# Auditoría de datos

## Principio

La fuente de verdad para las lecturas es:

1. Guía/programa de cátedra.
2. Páginas Amorrortu.
3. Relevamiento de Apunte 1 / Apunte 2.
4. Fuente física recomendada.

No asumir que Apunte 2 es mejor sólo porque corresponde al segundo parcial.

## Índices físicos de apuntes

`data/sources/index.json` funciona como catálogo extensible de apuntes y `data/sources/apunte2.json` modela el relevamiento manual de `docs/INDICE_APUNTES.md` como una capa separada de ubicación física:

- cada entrada registra únicamente la página donde comienza una aparición dentro del apunte;
- `amorrortuPages` sólo se carga cuando fue consignado explícitamente en el relevamiento;
- una obra puede tener varias apariciones, ya sea por duplicación o porque se copiaron recortes distintos;
- la asociación con las cards se hace por título de obra y no afirma que la aparición contenga exactamente el recorte pedido;
- estas ubicaciones no comparten progreso ni intervienen en las reglas de inclusión o duplicación de lecturas;
- Apunte 1 queda explícitamente sin índice y puede incorporarse luego agregando su archivo al catálogo.

Por eso la UI permite alternar dos referencias con funciones diferentes: Amorrortu responde qué fragmento leer; los índices de apuntes responden dónde empezar a buscarlo físicamente.

## Módulos 5 y 6

Las nuevas cards se extrajeron de la bibliografía obligatoria del programa oficial 2026 y se contrastaron con las Guías 5 y 6. La bibliografía electiva permanece como contexto de programa y no suma al progreso.

Hasta completar un relevamiento de los apuntes físicos, la fuente recomendada es el tomo Amorrortu consignado en el programa. No se debe afirmar que el recorte está en Apunte 1 o Apunte 2 sin esa auditoría.

Inclusiones totales nuevas:

- `Más allá del principio de placer`, caps. I a VI, contiene los recortes teóricos de caps. II y III y de caps. IV, V y VI, además del recorte de cap. III del módulo 6.
- `Más allá del principio de placer`, caps. II y III, contiene el recorte de cap. III, pp. 18–20.
- `El yo y el ello`, pp. 15–22, 21–29, 33–37, 49–59, contiene el recorte pp. 15–20, 21–29, 33–37, 49–57.
- `Inhibición, síntoma y angustia`, pp. 106–113, 147–150, contiene el recorte pp. 147–150.
- `Inhibición, síntoma y angustia`, pp. 97–105, 118–124, 125–135, 154–157, contiene el recorte pp. 123–124.

Las superposiciones parciales no implican progreso. Por ejemplo, `El problema económico del masoquismo`, pp. 166–171, y pp. 171–172, comparten sólo una página y deben marcarse por separado.

## Casos auditados

### Pulsiones y destinos de pulsión

Este fue el caso más importante.

Misma obra, distintos fragmentos:

| Fragmento | Apunte 1 | Apunte 2 | Fuente recomendada | Relación |
|---|---|---|---|---|
| 113–122 | sí | parcial: 121–122 | Apunte 1 | contiene 121–122 |
| 121–122 | contenido en 113–122 | sí | Apunte 2 / 1 | incluido por 113–122 |
| 128, 132–134 | no relevado | sí | Apunte 2 | independiente |

Regla:

```txt
113–122 implica 121–122
121–122 NO implica 113–122
128,132–134 no se relaciona con los anteriores a nivel de progreso.
```

Tener cuidado con variante de título en apunte:

- "Pulsiones y destinos de pulsión"
- "Pulsiones y destino de pulsión"

Es la misma obra.

### Lo inconsciente

Caso de superposición parcial, NO inclusión limpia.

Apunte 1 relevado:

```txt
168–172
177–186
197–199
```

Apunte 2 relevado:

```txt
168–172
177–182
183–184
187
197–198
```

Decisión:

- `168–172`: duplicado exacto, puede compartir progreso si misma card.
- `177–186, 197–199` vs `177–182,183–184,187,197–198`: superposición parcial.
- NO auto-marcar entre sí porque faltan páginas:
  - Apunte 2 no cubre 185–186 ni 199.
  - Apunte 1 no coincide exactamente con selección teórica del Apunte 2.

Conclusión: varias cards de Lo inconsciente deben marcarse por separado.

### La represión

Recorte:

```txt
141–152
```

Aparece completo en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

No requiere inclusión especial. Duplicado exacto si aparece en más de una vista/card con mismas páginas.

### Tótem y tabú

Recorte:

```txt
IV, puntos 5 y 6
142–152
```

Aparece completo en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### Introducción del narcisismo

Recorte:

```txt
71–98
```

Aparece completo en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### Sobre las teorías sexuales infantiles

Recorte:

```txt
187–201
```

Aparece completo en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### El esclarecimiento sexual del niño

Recorte:

```txt
117–119
```

Aparece completo en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### Mis tesis sobre el papel de la sexualidad en la etiología de las neurosis

Recorte:

```txt
263–271
```

Aparece completo o equivalente en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### Tres ensayos de teoría sexual

No es un caso de duplicación; son fragmentos distintos de la misma obra.

#### Práctico IV

```txt
cap. I puntos 4 y 5 + cap. II
148–154, 157–188
Fuente: Apunte 2 / 1
```

#### Seminario V

```txt
cap. III, punto 5: El hallazgo de objeto
202–210
Fuente: Apunte 1
```

Regla:

- No auto-marcar entre sí.
- Son fragmentos distintos.

### Dora

Recortes:

```txt
21–22, 36–38, 42–43, 46
```

Aparece equivalente en ambos.

Fuente recomendada:

```txt
Apunte 2 / 1
```

### Experiencias y ejemplos extraídos de la práctica analítica: Pies (zapatos) abochornados

Caso especial: error de fotocopiadora.

La guía pide:

```txt
Freud, 1913.
Experiencias y ejemplos extraídos de la práctica analítica:
Pies (zapatos) abochornados.
Amorrortu XIII, pp. 199–200.
```

El usuario verificó online que Amorrortu XIII pp. 199–200 es correcto.

La fotocopia que tenía hablaba de:
- chistoso / cómico;
- comparación;
- abstracto / concreto;
- Heine.

Eso no coincide con el caso de zapatos. Por lo tanto, la card debe advertir:

```txt
⚠️ El apunte de fotocopiadora parece contener un recorte incorrecto o descontextualizado. Para esta lectura conviene consultar Amorrortu XIII, pp. 199–200.
```

Link usado:

https://www.psicopsi.com/wp-content/uploads/2021/05/Freud-Amorrortu-13.pdf

Fuente recomendada:

```txt
Amorrortu XIII
pp. 199–200
```

Resumen del caso correcto:

- paciente se ofende porque un joven mira con desprecio sus pies;
- cree que es hijo del médico;
- transferencia al médico → hermano;
- recuerdo infantil: mira al hermano orinar;
- intenta orinar como él;
- se moja los zapatos;
- hermano se burla;
- Freud lo usa como ejemplo de influencia de lo sexual sobre el carácter.

Frase clave:

```txt
Un buen ejemplo de la influencia que lo sexual, como paradigma, obra sobre el carácter.
```

## Tipos de relación detectados

### Duplicado exacto

Mismo título + mismas páginas.

Ejemplo:

```txt
La represión 141–152
```

Si se marca una aparición, se marcan todas.

### Inclusión total

Un fragmento contiene completamente a otro.

Ejemplo:

```txt
Pulsiones 113–122 contiene 121–122
```

Si se marca el grande, se marca el chico.

### Superposición parcial

Comparten algunas páginas pero no todas.

Ejemplo:

```txt
Lo inconsciente 177–186,197–199
vs
177–182,183–184,187,197–198
```

No auto-marcar.

### Error de fuente física

Ejemplo:

```txt
Pies (zapatos) abochornados
```

Derivar a Amorrortu/PDF.
