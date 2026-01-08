# 📊 Análisis de Eficiencia de Ventas e Inventario por Departamento

## 🎯 Objetivo del Proyecto
Este análisis se enfoca en evaluar el comportamiento de ventas en los diferentes departamentos de la organización. El fin principal es identificar las tiendas y departamentos con mayor eficiencia operativa para optimizar la **asignación de presupuesto** y la **planificación estratégica de inventario**.

## 📑 Estructura del Proyecto (Libro de Trabajo)
El archivo está organizado siguiendo un flujo lógico de datos, desde la captura bruta hasta la toma de decisiones:

| Hoja | Tipo | Descripción |
| :--- | :--- | :--- |
| **raw_ventas** | Raw Data | Datos originales por semana, tienda y departamento. |
| **raw_departamento** | Raw Data | Diccionario de IDs y nombres de departamentos. |
| **raw_tiendas** | Raw Data | Dimensiones (m²) y ubicación de las tiendas. |
| **Clean_ventas** | Clean Data | Información centralizada y cruzada mediante procesos de limpieza. |
| **Clean_departamento** | Clean Data | Ajuste de registros sin ID para asegurar integridad. |
| **Pivot** | Reportes | Tablas dinámicas que estructuran los KPIs core. |
| **Dashboard** | Consolidado | Tablero de control visual interactivo para monitoreo de KPIs. |
| **Resumen** | Conclusión | Análisis bajo enfoque C-F-I (Contexto-Factores-Impacto). |

## 📈 KPIs y Fórmulas de Negocio
Se implementaron indicadores clave para medir el rendimiento desde distintas dimensiones:

### 1. Ventas por m² (Eficiencia de Espacio)
* **Fórmula:** `=SUM(ventas_semanales) / AVERAGE(tamaño)`
* **Propósito:** Analizar qué departamentos optimizan mejor el uso del espacio físico y la rotación de productos.

### 2. Participación por Departamento (Share de Mercado)
* **Fórmula:** `% de Ventas Totales`
* **Propósito:** Identificar departamentos representativos para priorizar esfuerzos de marketing y presupuesto.

### 3. Volatilidad (Coeficiente de Variación - CV)
* **Fórmula:** `=STDEV(ventas_semanales) / AVERAGE(ventas_semanales)`
* **Interpretación:** * **CV cercano a 0:** Ventas predecibles y estables.
    * **CV mayor a 1:** Alta incertidumbre y riesgo operativo.

## ✅ Validación y Calidad de Datos (QA)
Para garantizar la veracidad de las conclusiones, se aplicaron los siguientes controles:

* **Tratamiento de Nulos:** Se identificaron 6,435 registros de tiendas sin departamento asignado (ID #16), los cuales fueron reclasificados como **"Otros"** para evitar distorsiones.
* **Integridad Financiera:** Validación de discrepancia cero ($0.00) entre los datos crudos y los reportes dinámicos.
* **Anomalías:** Identificación y manejo de 27 registros con ventas negativas o nulas.
* **Estabilidad:** Confirmación de un CV máximo de 1.16, manteniéndose dentro de los rangos razonables del sector.

## 🎨 Semáforo de Gestión (Dashboard)
El Dashboard utiliza alertas visuales basadas en los siguientes umbrales críticos:

| Indicador | 🟢 Alerta Verde | 🔴 Alerta Roja |
| :--- | :--- | :
