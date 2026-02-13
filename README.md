# Monitoreo de Inversión Pública y Calidad de Datos  
### Municipio de Luján de Cuyo · 2025

Proyecto de Business Intelligence enfocado en trazabilidad financiera, modelado confiable y evaluación de calidad de datos aplicado a inversión pública municipal.

---

## Descripción del Proyecto

Este proyecto integra información de:

- Presupuesto
- Licitaciones
- Obras Públicas

Con el objetivo de:

- Centralizar el análisis del flujo de inversión.
- Medir ejecución presupuestaria.
- Detectar concentración de proveedores.
- Evaluar la calidad del dataset mediante reglas de validación.
- Identificar inconsistencias administrativas que impactan la toma de decisiones.

---

##  Problema de Negocio

La información financiera y operativa se encontraba dispersa en distintos módulos, lo que generaba:

- Falta de trazabilidad entre presupuesto asignado y ejecución real.
- Dificultad para monitorear eficiencia financiera.
- Estados administrativos incompletos.
- Riesgo de análisis engañosos por mala calidad de datos.

---

##  Resultados Clave

- **Presupuesto Total:** $111,8 mil M  
- **Presupuesto Obras:** $38,9 mil M  
- **Total Licitado:** $2,72 mil M  
- **Monto Pagado:** $5,3 mil M  

### Hallazgos Relevantes

- 40% de las obras presentan estado “No Especificado”.
- El Top 10 de contratistas concentra la mayor parte del monto adjudicado.
- Se detectaron **100 inconsistencias sobre 838 registros evaluados**.
- Índice Global de Calidad del Dato: **88%**.

---

## Metodología

### 1️⃣ Recolección de Datos

Integración de tres tablas principales:

- `Presupuesto`
- `Licitacion`
- `ObrasPublicas`

---

### 2️⃣ Limpieza y Transformación (Power Query)

- Normalización de proveedores.
- Estandarización de estados de obra.
- Unificación de formatos de fecha.
- Eliminación de duplicados.
- Detección de valores nulos críticos.

---

### 3️⃣ Validaciones de Calidad (DAX)

Se implementaron reglas específicas:

- Licitaciones sin fecha de adjudicación.
- Obras finalizadas sin fecha fin.
- Inconsistencias temporales (fecha inicio > fecha fin).
- Cuentas presupuestarias incompletas.
---

### 4️⃣ Modelado

Se diseñó un modelo dimensional con enfoque analítico y control de calidad.

- Modelo tipo estrella.
- Claves únicas por tabla.
- Separación entre métricas de negocio y métricas de calidad.
- Medidas modulares (una validación = una medida).
- Eliminación de relaciones ambiguas.
- Optimización de medidas para evitar cálculos redundantes.

El objetivo fue garantizar consistencia, escalabilidad y claridad en el análisis.
## Herramientas Utilizadas

- Power BI Desktop  
- DAX  
- Power Query  
- Excel
- Modelado dimensional  

---

## Estructura del Repositorio

obrasLujan
│
├── data/
│ ├── raw/
│ │ ├── presupuesto_2025.xlsx
│ │ ├── licitacion_2025.xlsx
│ │ └── obras_publicas_2025.xlsx
│ │
│ ├── working/
│ │ ├── presupuesto_2025_mod.xlsx
│ │ ├── licitacion_2025_mod.xlsx
│ │ └── obras_publicas_2025_mod.xlsx
│
├── dashboard/
│ └── ObrasLujan.pbix
│
├── docs/
│ ├── Calidad_Datos.pdf
│
├── README.md
---

## Aprendizajes

- La calidad del análisis depende directamente de la calidad del dato.
- Sin validaciones explícitas, un dashboard puede inducir conclusiones incorrectas.
- Separar métricas estratégicas de métricas técnicas mejora la claridad y transparencia.
- La trazabilidad financiera requiere consistencia entre módulos administrativos.

---

## Autor

Proyecto desarrollado end-to-end como caso integral de Business Intelligence, abarcando:

- ETL
- Modelado
- Métricas avanzadas
- Visualización ejecutiva
- Evaluación de calidad de datos

