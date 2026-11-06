# test-manager-library-3239188-tool

Utilidades de *Manager Library*: sembrador de datos de demostración. Prueba técnica SDD · Ficha ADSO 3239188.

## Papel en el spec

Genera datos reales para la feria de presentación y para la prueba de carga de RNF-1 (búsqueda en menos de 300 ms con 5 000 libros). Tarea T-21.

## Regla de diseño

El sembrador usa **únicamente la API**, nunca SQL directo (`data-model.md` §9). Así respeta todas las reglas de negocio: ejemplares descontados, vencimiento a 14 días, valores congelados y máximo 3 libros por socio.

## Qué debe generar

| Dato | Cantidad mínima |
|---|---|
| Libros | 40, repartidos en las cinco categorías |
| Socios | 10 |
| Préstamos | 15 |
| Préstamos con líneas vencidas | 3 |

El administrador inicial no se siembra aquí: lo crea el arranque de la API desde variables de entorno.

## Evidencia esperada

Tras ejecutarlo, `GET /loans/overdue` devuelve 3 líneas y `GET /reports/most-borrowed` tiene filas.

## Estado

| Elemento | Estado |
|---|---|
| Diseño y alcance | Hecho (este documento) |
| Implementación | Pendiente |

> Este README describe el diseño previsto. No afirma que la implementación exista.