# Prueba técnica — Equipo Canales Digitales (Científico de Datos)

Resolución integral de la prueba técnica para el rol de Científico de Datos, con enfoque en analítica de negocio, experiencia de cliente, recomendación en tiempo real y activación de IA comercial.

## 1) Contexto de la entrega

Este repositorio responde los 7 puntos del enunciado oficial, usando el dataset provisto y una implementación completa en notebook.

- **Enunciados oficiales:** [Prueba Técnica Equipo Canales Digitales - Científico De Datos.pdf](Prueba%20T%C3%A9cnica%20Equipo%20Canales%20Digitales%20-%20Cient%C3%ADfico%20De%20Datos.pdf)
- **Notebook entregable principal:** [prueba_tecnica_canales_digitales.ipynb](prueba_tecnica_canales_digitales.ipynb)

---

## 2) Objetivo

Resolver de forma estructurada los siguientes frentes:

1. productos/categorías líderes por volumen e ingresos,  
2. principal dolor del cliente y categorías asociadas,  
3. segmentación accionable para marketing (RFM),  
4. arquitectura de recomendador híbrido en tiempo real,  
5. ciudad/zona recomendada para tienda insignia,  
6. base de conocimiento JSON para agente de IA,  
7. tres system prompts hiperpersonalizados.

---

## 3) Estructura del proyecto

```text
.
├── README.md
├── prueba_tecnica_canales_digitales.ipynb
├── base_conocimiento.json
└── Dataset_prueba/
    ├── customers_dataset.csv
    ├── geolocation_dataset.csv
    ├── order_items_dataset.csv
    ├── order_payments_dataset.csv
    ├── order_reviews_dataset.csv
    ├── orders_dataset.csv
    ├── product_category_name_translation.csv
    ├── products_dataset.csv
    ├── sellers_dataset.csv
    └── validacion_datasets.ipynb
```

Archivos clave:
- Entregable principal: [prueba_tecnica_canales_digitales.ipynb](prueba_tecnica_canales_digitales.ipynb)
- Base de conocimiento generada: [base_conocimiento.json](base_conocimiento.json)
- Validación de estructura de datos: [Dataset_prueba/validacion_datasets.ipynb](Dataset_prueba/validacion_datasets.ipynb)

---

## 4) Metodología y decisiones analíticas

Supuestos explícitos usados en el análisis:

- **Volumen vendido**: conteo de líneas en [Dataset_prueba/order_items_dataset.csv](Dataset_prueba/order_items_dataset.csv).
- **Ingresos de producto**: suma de `price` (sin `freight_value`).
- **Ventas efectivas**: foco en pedidos `delivered`.
- **Dolor del cliente**: señal compuesta por atraso (`late_delivery`), reseña baja (`low_review`) y estado problemático (`problem_status`).
- **Nivel de análisis comercial**: principalmente categorías, por ausencia de naming comercial legible por SKU.

---

## 5) Cómo ejecutar

1. Abrir [prueba_tecnica_canales_digitales.ipynb](prueba_tecnica_canales_digitales.ipynb).
2. Ejecutar celdas en orden.
3. Verificar disponibilidad de [Dataset_prueba/](Dataset_prueba/) o `Dataset_prueba.zip` en el directorio de trabajo.
4. Revisar salidas tabulares, gráficas y conclusiones por punto.

Dependencias utilizadas en notebook:
- `pandas`
- `numpy`
- `matplotlib`
- `json`, `zipfile`, `pathlib`

---

## 6) Artefactos generados

- Base de conocimiento para IA: [base_conocimiento.json](base_conocimiento.json)
- Función de scoring de recomendación: [`recommendation_score`](prueba_tecnica_canales_digitales.ipynb)
- Resumen de historial para personalización: [`construir_historial_compras`](prueba_tecnica_canales_digitales.ipynb)

---

## 7) Resumen ejecutivo de hallazgos

1. **Negocio actual**  
   El crecimiento se soporta en categorías de alta rotación (`bed_bath_table`) y alto valor (`health_beauty`, `watches_gifts`).

2. **Dolor principal del cliente**  
   La fricción dominante es logística (atrasos), con impacto en reseñas y percepción de servicio.

3. **Oportunidad comercial**  
   Alta concentración de clientes de una sola compra; prioridad: segunda compra y recurrencia por segmentos RFM.

4. **Palanca tecnológica**  
   Recomendador híbrido en tiempo real para combinar personalización, reglas comerciales y contexto de navegación.

5. **Expansión física**  
   **São Paulo (SP)** aparece como ciudad líder; la ubicación óptima debe aproximarse por centro de demanda ponderado por ingresos.

6. **Activación IA**  
   Se deja activo un activo reutilizable: base de conocimiento + prompts segmentados para recomendación consistente y controlada.

---

## 8) Próximos pasos sugeridos

1. MVP de recomendación con pruebas A/B por segmento.  
2. Plan de mejora logística en categorías críticas.  
3. Validación de ubicación física con variables offline (renta, tráfico, competencia).  
4. Gobernanza de prompts/base de conocimiento con métricas como CTR, CVR, AOV y retención.

---

**Autor:** David Santiago Rojo Castrillón  
**Contacto:** dsrojo10@gmail.com